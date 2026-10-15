# Defensibilidade e Métrica da Demo

!!! info "Sobre esta página"
    **Para que serve:** Responder: por que alguém usaria o Habilita e não uma planilha? E como vamos provar isso no Demo Day?

    **O que escrever:** Uma hipótese de defensibilidade e **uma métrica mensurável** para a demo. Ambas obrigatórias no CP1.

    **Prazo:** CP1 · 18/10

| Item | Conteúdo |
|---|---|
| Hipótese de defensibilidade | Reaproveitar documentos válidos entre contratos reduz retrabalho. Cada documento aprovado passa a valer para todos os contratos do cliente que o exigem; quanto mais contratos, menos trabalho a cada novo contrato, e trocar de ferramenta significa recomeçar do zero |
| Métrica da demo | **A decidir pela PO (Q6).** Opção A (exemplo da PO): tempo para liberar um trabalhador na portaria. Opção B (proposta do Tech Lead): taxa de reuso na habilitação — ver abaixo |
| Valor atual (sem o Habilita) | A medir nas entrevistas (pergunta P5 e P7 do roteiro) |
| Meta com o Habilita | Opção A: p95 ≤ 800 ms na consulta. Opção B: ≥ 70% das exigências atendidas por reuso e semáforo verde em até 2 minutos |

## Opção B detalhada — taxa de reuso na habilitação

> Dado um trabalhador já habilitado no Contrato A, ao vinculá-lo ao Contrato B, medir (1) a porcentagem das exigências de B atendidas sem novo upload e (2) o tempo até o semáforo ficar verde.

**Por que o Tech Lead sugere a Opção B como principal:** a métrica da demo deve provar a **hipótese de defensibilidade**. A Opção A mede velocidade da portaria, que uma planilha compartilhada bem organizada também poderia oferecer; a Opção B mede exatamente o reaproveitamento entre contratos, que é a hipótese desta página e a cena da demo da ficha do projeto. As duas podem ser mostradas; a decisão de qual é a principal é da PO.

## Outras fontes de defensibilidade

- **Matrizes de exigência configuradas por contrato**, que codificam o conhecimento de SST do cliente.
- **Trilha de auditoria contínua** (quem aprovou, quem entrou), que tem valor justamente por ser ininterrupta.

As funcionalidades isoladas (upload, semáforo, alerta) são copiáveis; a defesa está no que se acumula com o uso.
