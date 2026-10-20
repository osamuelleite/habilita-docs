# Requisitos Não Funcionais

!!! info "Sobre esta página"
    **Para que serve:** Listar **como** o sistema deve se comportar: segurança, desempenho, qualidade, custo.

    **O que escrever:** As metas abaixo vêm do documento de Checkpoints e são obrigatórias. Acrescentar as específicas do Habilita.

    **Prazo:** CP1 · 18/10

| ID | Categoria | Requisito | Origem |
|---|---|---|---|
| RNF01 | Segurança | Autorização por cliente (tenant) e papel em 100% das rotas | Checkpoints CP4 |
| RNF02 | Segurança | Upload seguro de documentos | Guia · desafio de engenharia |
| RNF03 | Segurança | Zero vulnerabilidade crítica/alta sem exceção registrada | CP4 |
| RNF04 | Desempenho | p95 de leitura ≤ 800 ms e de escrita ≤ 1,5 s | CP4 |
| RNF05 | Qualidade | Cobertura ≥ 80% no domínio e ≥ 60% global | CP4 |
| RNF06 | Usabilidade | Lighthouse ≥ 90 | CP4 |
| RNF07 | Operação | Endpoints /healthz e /readyz; logs JSON com requestId | CP3 |
| RNF08 | Custo | Gasto ≤ US$ 5 até CP2, ≤ US$ 12 até CP3, teto US$ 50 | CP2/CP3 |
| RNF09 | Privacidade | Nenhum dado pessoal real em ambientes de teste e demo | ADR 0004 |
| RNF10 | Disponibilidade | Fluxo principal funcional em produção no Demo Day, com smoke test verde | Checkpoints · Demo Day |
| RNF11 | Privacidade | Nenhum CPF completo, token ou conteúdo de documento em logs | LGPD · ADR 0008 |
| RNF12 | Reprodutibilidade | `docker compose up` sobe todo o sistema numa máquina limpa seguindo só o README | CP1 |
| RNF13 | Usabilidade | Tela de portaria utilizável em celular (360 px de largura), com a cor do semáforo sempre acompanhada de texto | Produto · J5 |

!!! note "RNF10 a RNF13"
    Propostos pelo Tech Lead a partir dos Checkpoints, da LGPD e da jornada da portaria. RNF01 a RNF09 são da PO. Onde e como cada RNF é atendido: [Arquitetura](../../arquitetura/index.md).

## Histórico de versões

| Versão | Data | Autor | Alterações |
|---|---|---|---|
| 1.0 | 14/10/2026 | @osamuelleite | Versão inicial, conciliação PO + Tech Lead. Da PO: RNF01 a RNF09, vindos do documento de Checkpoints. Do Tech Lead: RNF10 a RNF13 propostos (C5). |
