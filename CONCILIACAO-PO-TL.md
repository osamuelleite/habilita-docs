# Conciliação PO × Tech Lead — Documentação do Checkpoint 1

| Campo | Valor |
|---|---|
| Data | 14/10/2026 |
| Base | Pasta `habilita-docs` da PO (estrutura MkDocs) + documentação do Tech Lead (`habilita-docs-cp1.zip`) |
| Uso | Documento de trabalho para a reunião PO + Tech Lead. Não faz parte do site; pode ser apagado depois do gate. |

## 1. Regra aplicada

- **Produto e tudo o que é do papel da PO** (visão, personas, jornadas, Ishikawa, entrevistas, defensibilidade, requisitos, backlog, prioridades): **a versão da PO prevalece**. O conteúdo do Tech Lead entrou só para **preencher lacunas** que ela deixou em aberto, sem contradizer o texto dela.
- **Campo do Tech Lead** (arquitetura, ADRs, API, dados, segurança, testes, DoD, fluxo Git, CI/CD, FinOps técnico): adaptado para ser **coerente com a estrutura e as decisões da PO**; onde havia **erro ou omissão**, prevaleceu a decisão do Tech Lead, registrada abaixo.

## 2. O que foi feito

1. **Adotada a estrutura da PO por inteiro:** MkDocs + Material, pastas, nomes de arquivo, menu (`mkdocs.yml`), formato de ADR, `openapi.yaml` na raiz, workflow de docs.
2. **Conteúdo do Tech Lead encaixado nas páginas dela.** Nenhuma página da PO foi apagada; as caixas "Sobre esta página" foram mantidas nas páginas de produto (a PO decide quando estão prontas).
3. **IDs renumerados para o padrão dela:** histórias `H01…`, requisitos `RF01…`/`RNF01…`, ADRs `0001…`.
4. **9 páginas novas** adicionadas ao menu: Roteiro de Entrevista, Modelo de Registro, Evidências Secundárias, Checklist do Checkpoint 1 e ADRs 0005 a 0009.

## 3. Conflitos e divergências

### 3.1 Precisam de decisão da PO antes do gate

| # | Tema | Versão da PO | Versão do Tech Lead | Como ficou | Decisão pendente |
|---|---|---|---|---|---|
| **C1** | Categorias do Ishikawa | 5 categorias de exemplo: Pessoas, Processo, Ferramentas, Dados, Comunicação | 6M | **6M**, porque o Guia do Checkpoint 1 exige Método, Máquina, Mão de obra, Material, Medida e Meio ambiente. Os 5 exemplos dela foram mantidos como causas, marcados com ★. O efeito é o dela | PO confirma |
| **C2** | Prioridade dos alertas | H05 = **Should** | Alertas = Must | **Should** (prioridade é da PO) | Q5: a jornada J4 da ficha ("vencimentos, status e **alertas**") é do MVP; o Tech Lead sugere Must |
| **C3** | Métrica da demo | Exemplo: tempo para liberar um trabalhador na portaria | Taxa de reuso na habilitação | **As duas documentadas** em Defensibilidade, com a justificativa do Tech Lead | Q6: qual é a principal. O argumento: a métrica deve provar a hipótese, que é de reuso |
| **C4** | Histórias H07 a H23 | Backlog com H01 a H05 + Won't | 24 histórias | H01 a H06 dela **intactas** (texto e prioridade); as do Tech Lead viraram **H07 a H23**, marcadas como propostas | PO valida a prioridade de cada uma |
| **C5** | RF10 e RNF10 a RNF13 | RF01 a RF09, RNF01 a RNF09 | Trilha de auditoria e outros RNFs | Adicionados **RF10** (auditoria — está no "É" dela, mas sem RF) e **RNF10 a RNF13**, marcados como propostos | PO valida |
| **C6** | Questões de regra de negócio | — | Q1 (rejeição anula documento válido?) e Q2 (portaria: basta um contrato vigente?) | Registradas em Visão e Escopo | PO decide até 18/10 |

### 3.2 Adaptações do Tech Lead para ficar coerente com a PO

| # | Tema | O que mudou do nosso lado |
|---|---|---|
| **C7** | **Validade do documento (RF03)** | A PO definiu "enviar documento **com data de validade**". Antes, nós calculávamos a validade pelo prazo do tipo de documento. Agora a terceirizada **informa `validoAte` no envio** e o gestor confere ou corrige na aprovação; o prazo do tipo só sugere a data e gera aviso. Ajustados: RN-09, OpenAPI (upload e aprovação), H02.CA10, H09.CA3, H13.CA1 e testes T-UPL-08 a T-UPL-10 |
| **C8** | ADRs | Os 4 temas dela foram mantidos (0001 Stack, 0002 Tenant e autorização, 0003 CI/CD, 0004 MkDocs). Nossos ADRs de multi-tenancy e RBAC foram **fundidos na 0002**; a decisão de linguagem entrou **na 0001**; hospedagem e entrega foram para a **0003**. Os demais viraram **0005 a 0009**, para aprovação até o CP2. Todos no formato dela (6 seções) |
| **C9** | Granularidade das histórias | H01 (dela) absorveu "criar contrato" + "definir matriz"; H02 absorveu "cadastrar trabalhador" + "enviar documento", porque ela liga H02 a RF02 e RF03. Os critérios foram renumerados |
| **C10** | Hipóteses de pesquisa | Renomeadas de H1–H5 para **HP1–HP5**, para não confundir com as histórias H01–H05 dela |
| **C11** | OpenAPI | O dela era um esqueleto 3.0.3 com só `/healthz`. O nosso (3.1, 28 operações) foi para a **raiz**, onde ela definiu a fonte única. A cópia `docs/openapi.yaml` foi removida, porque o CI dela a gera e o `.gitignore` a ignora |

### 3.3 Erros ou omissões em que a decisão do Tech Lead prevaleceu

| # | Tema | Problema | Correção |
|---|---|---|---|
| **C12** | Definition of Done | Faltavam itens obrigatórios do Caderno (seção 1.6): revisor diferente do autor, teste ligado a critério, nenhum segredo, telas com estados, logs sem dados pessoais, nenhum recurso GCP sem ADR | Itens dela mantidos; obrigatórios acrescentados; incluída a Definition of Ready |
| **C13** | Ambiente local | Emuladores listados: só Auth e Firestore | Acrescentado o **Storage**: o Guia do PO exige o emulador de Storage para o Habilita |
| **C14** | Frase de LGPD na Visão | Não havia | Acrescentada, com a tabela de decisões de privacidade (exigida pelo Guia do PO na Visão do Produto) |
| **C15** | Consulta da portaria (Escopo HTML) | O rascunho de escopo citava `GET /api/liberacao?cpf=...` | **POST com CPF no corpo** (ADR 0008): CPF em URL vaza para logs e histórico. Não havia conflito com as páginas da PO |
| **C16** | Acesso entre clientes (Escopo HTML) | O rascunho citava 403 | **404**, para não revelar que o recurso existe (ADR 0002). O Guia do PO aceita 403 ou 404 |

## 4. Mapa de IDs (antigo → novo)

| Antigo (Tech Lead) | Novo |
|---|---|
| HAB-04 + HAB-05 | H01 (CA1–3 contrato, CA4–6 matriz) |
| HAB-06 + HAB-08 | H02 (CA1–4 trabalhador, CA5–9 upload, CA10 validade) |
| HAB-12 · HAB-18 · HAB-16 | H03 · H04 · H05 |
| HAB-01, 02, 03, 07, 09, 10, 11, 13, 14, 15, 17, 19, 20, 21, 22, 23, 24 | H07 a H23, na mesma ordem |
| RNF-01 a RNF-12 | RNF01, RNF10, RNF04, RNF04, RNF06, RNF05, RNF03, RNF08, RNF07, RNF11, RNF12, RNF13 |
| ADR-001 · 002+003 · 004 · 005 · 006 · 007 · 008 · 009 | 0005 · 0002 · 0001 · 0006 · 0007 · 0008 · 0009 · 0003 |

## 5. Verificação da ADR 0004 (da PO)

- **Confirmado:** a nota da versão 9.7.7 do Material for MkDocs informa fim de vida previsto para **05/11/2026**, com apenas correções críticas e de segurança até lá, e indica o Zensical como sucessor. A mesma versão corrigiu uma falha de XSS na busca; o `9.7.*` fixado pela PO já pega essa correção.
- **Não verificado por mim:** a afirmação de que o MkDocs 2.0 não constrói projetos 1.x. Não muda a decisão, pois a versão está fixada em 1.6.1.

## 6. O que foi validado e o que não foi

| Verificação | Resultado |
|---|---|
| Toda página em `docs/` está no `nav:` e todo item do `nav:` existe | ✅ 48/48 |
| Todos os links internos e âncoras resolvem dentro de `docs/` (regra do `--strict`) | ✅ |
| IDs cruzados (H, CA, RF, RNF, RN, ADR, T-, AM-) existem | ✅ |
| `openapi.yaml`: referências, parâmetros de caminho e esquemas | ✅ (validador próprio) |
| `mkdocs.yml` é YAML válido | ✅ |
| **`mkdocs build --strict` real** | ✅ Executado em 14/10 antes do primeiro push (MkDocs 1.6.1 + Material 9.7, `requirements-docs.txt`): build sem erros nem avisos. O CI repete a verificação em todo PR |
| **Swagger UI renderiza OpenAPI 3.1** | ⚠️ A confirmar no `mkdocs serve`. Se não renderizar, converter o contrato para 3.0.3 (trocar `type: [x, 'null']` por `nullable: true` e remover `const`/`examples`/`contentMediaType`) |
| Diagramas Mermaid renderizam no tema | ⚠️ A confirmar no `mkdocs serve` |

## 7. Pendências para 18/10

1. ~~Decidir a linguagem da API~~ — **decidido em 14/10: Python + FastAPI** (ADR 0001 atualizada; nova página [Qualidade](docs/engenharia/qualidade.md); controles de segurança por camada na página de Segurança).
2. **PO:** responder Q1, Q2, Q5 e Q6; validar H07 a H23, RF10 e RNF10 a RNF13; confirmar C1.
3. **PO:** realizar as 2 entrevistas (ou manter "hipótese não validada").
4. **Equipe:** `mkdocs build --strict` verde, GitHub Pages ativo, esqueleto no Compose, CI de lint e build, alertas de orçamento.
5. **Ishikawa** redesenhado em espinha de peixe e salvo como imagem.
