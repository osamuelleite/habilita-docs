# FinOps

| Campo | Valor |
|---|---|
| Responsável | DevOps (aprovação: Tech Lead) |
| Última atualização | 14/10/2026 |

## Acompanhamento por gate

| Gate | Teto acumulado | Gasto real | Ação |
|---|---|---|---|
| CP2 | US$ 5 | | |
| CP3 | US$ 12 | | |
| CP4 | US$ 40 (gatilho de corte) | | |

Alertas de orçamento: 50% / 80% / 100% de US$ 50. A documentação é publicada no GitHub Pages e não consome orçamento GCP.

Estimativa da ficha do projeto: **US$ 8 a 18** no ciclo inteiro (planejamento, não preço garantido).

**Regra de ouro:** até a Semana 4, tudo roda localmente com Docker Compose e emuladores. Pergunta "precisamos subir para o Firebase já?" → resposta: não.

## Alertas de orçamento (Checkpoint 1)

| Limiar | Valor | Ação |
|---|---|---|
| 50% | US$ 25 | Revisar o relatório de custos na reunião semanal |
| 80% | US$ 40 | **Plano de corte** (abaixo), executado no mesmo dia |
| 100% | US$ 50 | Desligar recursos não essenciais; avisar os tutores |

**Evidência para o gate:** print da tela de orçamentos do projeto GCP mostrando os três limiares, salvo em `docs/finops/evidencias/alertas-orcamento.png`.

> Alertas de orçamento **avisam**, não bloqueiam gastos. O controle real vem dos limites abaixo.

## Controles de custo por serviço

| Serviço | Controle |
|---|---|
| Cloud Run | `min-instances=0`; `max-instances` baixo (proposta: 3); CPU alocada só durante requisições; imagem pequena |
| Firestore | Listas paginadas (máx. 50); sem *listeners* em tempo real sem justificativa; semáforo materializado para evitar leituras repetidas; job lê só documentos aprovados |
| Cloud Storage | Limite de 10 MiB por arquivo; sem duplicar arquivos no reuso (o documento é do trabalhador) |
| Artifact Registry | Retenção das últimas 5 imagens |
| Cloud Scheduler | Um único job diário |
| Logging | Logs estruturados e sem payloads grandes; nível `info` em produção |

**Nenhum recurso novo no GCP sem ADR ou aprovação do Tech Lead** (Definition of Done).

## Plano de corte ao atingir US$ 40

1. Reduzir `max-instances` do Cloud Run para 1.
2. Pausar o Cloud Scheduler (rodar o recálculo manualmente só antes das demonstrações).
3. Apagar revisões e imagens antigas além das 3 últimas.
4. Desligar ambientes de preview de PRs já fechados.
5. Registrar a ação e o motivo no relatório de custos.

## Relatório semanal

Preencher a partir da Semana 3 (e consolidar na tabela por gate acima):

| Semana | Gasto na semana (US$) | Acumulado (US$) | Maior item | Ação |
|---|---|---|---|---|
| S1 | 0,00 | 0,00 | — | Tudo local |
| S2 | | | | |

## Histórico de versões

| Versão | Data | Autor | Alterações |
|---|---|---|---|
| 1.0 | 14/10/2026 | @osamuelleite | Versão inicial, conciliação PO + Tech Lead. Orçamento, limites por gate e alertas de 50/80/100%. |
