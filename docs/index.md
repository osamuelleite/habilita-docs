# Habilita

**Documentação em dia. Acesso sob controle.**

Semáforo de conformidade por trabalhador e contrato, alertas de vencimento e consulta de liberação na portaria.

## Onde encontrar cada evidência

| Gate | Data | Páginas |
|---|---|---|
| CP1 · Fundação | 18/10 | [Checklist do CP1](engenharia/checkpoint-1.md), [Produto e Negócio](produto/index.md), [ADRs](arquitetura/adr/index.md), [API](arquitetura/api.md), [DoD](engenharia/definition-of-done.md), [Estratégia de testes](testes/estrategia.md) |
| CP2 · Núcleo funcional | 01/11 | [Matriz](testes/matriz.md), [Relatórios](testes/relatorios/index.md), [Segurança](seguranca/index.md) |
| CP3 · Nuvem | 15/11 | [Operação](operacao/index.md), [FinOps](finops/index.md) |
| CP4 · Estabilização | 29/11 | [Relatórios](testes/relatorios/index.md), [Operação](operacao/index.md) (rollback) |
| Demo Day | 05/12 | [Demo Day](demo/index.md) |

## Convenções de identificação

Cada artefato tem um ID estável, base da rastreabilidade **requisito → critério de aceite → teste → resultado** ([Matriz](testes/matriz.md)).

| Prefixo | Significado | Onde |
|---|---|---|
| `J1`…`J5` | Jornada do MVP | [Jornadas](produto/estrategia/jornadas.md) |
| `RF01`… | Requisito funcional | [Requisitos Funcionais](produto/requisitos/funcionais.md) |
| `RNF01`… | Requisito não funcional | [Requisitos Não Funcionais](produto/requisitos/nao-funcionais.md) |
| `H01`… / `H01.CA1` | História de usuário / critério de aceite | [Backlog](produto/requisitos/historias-backlog.md) |
| `RN-01`… | Regra de negócio | [Modelo de dados](arquitetura/dados.md) |
| `ADR NNNN` | Decisão de arquitetura | [ADRs](arquitetura/adr/index.md) |
| `T-XXX-NN` | Caso de teste | [Estratégia de testes](testes/estrategia.md) |
| `AM-01`… | Ameaça do modelo de ameaças | [Segurança](seguranca/index.md) |
| `E1`, `ES1` | Entrevista / evidência secundária | [Entrevistas](produto/estrategia/entrevistas.md) |

## Glossário

| Termo | Significado no Habilita |
|---|---|
| **Tenant** | Empresa **contratante** (cliente do Habilita). Os dados de um tenant nunca aparecem para outro. |
| **Terceirizada** | Empresa prestadora contratada pelo tenant. Envia os documentos dos seus trabalhadores. |
| **Trabalhador** | Pessoa da terceirizada que precisa estar apta para trabalhar nas dependências do tenant. |
| **Contrato** | Vínculo entre o tenant e uma terceirizada, com uma matriz de exigências. |
| **Matriz de exigências** | Lista de tipos de documento exigidos em um contrato. |
| **Semáforo** | Verde (apto), amarelo (apto, com vencimento em até 30 dias), vermelho (não apto). |
| **Liberação** | Resposta da portaria: o trabalhador pode ou não entrar. |
| **SST** | Segurança e Saúde no Trabalho. |
| **ASO** | Atestado de Saúde Ocupacional. |

## Histórico de versões

| Versão | Data | Autor | Alterações |
|---|---|---|---|
| 1.0 | 14/10/2026 | @osamuelleite | Versão inicial, conciliação PO + Tech Lead. Página inicial do site: proposta do Habilita, glossário e navegação. |
