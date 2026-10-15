# Design System

!!! info "Sobre esta página"
    **Para que serve:** Documentar os componentes de tela reutilizáveis (botões, semáforo, formulários).

    **O que escrever:** Componente, quando usar, estados (carregando, vazio, erro, sucesso — exigidos no CP2).

    **Prazo:** CP2 · 01/11

## Semáforo de conformidade

| Cor | Significado |
|---|---|
| Verde | Apto: todas as exigências do contrato atendidas por documentos válidos por mais de 30 dias |
| Amarelo | Apto, com atenção: todas atendidas, mas ao menos um documento vence em até 30 dias |
| Vermelho | Não apto: falta documento aprovado ou algum está vencido |

Regra completa: RN-06 no [Modelo de dados](../../arquitetura/dados.md). A cor sempre aparece com o texto ("Apto", "Vence em N dias", "Não apto") para quem não distingue cores (RNF13).
