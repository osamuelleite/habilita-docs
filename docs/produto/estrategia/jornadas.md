# Mapeamento de Jornadas

!!! info "Sobre esta página"
    **Para que serve:** Descrever, passo a passo, o caminho de cada usuário no sistema. As jornadas viram os testes da demo.

    **O que escrever:** Detalhar cada jornada (passos, quem faz, resultado esperado).

    **Prazo:** CP1 · 18/10 · detalhar até CP2

## As 5 jornadas do MVP

| # | Jornada | Persona |
|---|---|---|
| J1 | Criar contratos e a matriz de exigências | Gestor(a) SST |
| J2 | Cadastrar trabalhadores e enviar documentos | Terceirizada |
| J3 | Aprovar ou rejeitar documentos, com motivo | Gestor(a) SST |
| J4 | Atualizar vencimentos, status e alertas | Sistema |
| J5 | Consultar a liberação e registrar o acesso | Portaria |

## Fluxo principal

```mermaid
flowchart LR
  J1[J1 · Contrato e exigências] --> J2[J2 · Trabalhador e documentos]
  J2 --> J3[J3 · Aprovar / rejeitar]
  J3 --> J4[J4 · Vencimentos e semáforo]
  J4 --> J5[J5 · Portaria libera ou bloqueia]
```

## Cena da demo

Reutilizar documentos válidos em outro contrato e mostrar o semáforo e a consulta de portaria.

## Detalhamento das jornadas

Passos propostos pelo Tech Lead a partir do backlog; a PO valida até o CP2.

### J1 · Contrato e exigências — Gestor(a) SST

1. Cadastra a empresa terceirizada (H08) e os tipos de documento com prazo padrão (H09).
2. Cria o contrato com vigência e escolhe os documentos exigidos (H01).
3. **Resultado:** contrato vigente com matriz de exigências; trabalhadores alocados têm o semáforo recalculado.

### J2 · Trabalhador e documentos — Terceirizada

1. Cadastra o trabalhador com nome e CPF (H02).
2. Vincula o trabalhador ao contrato (H10); documentos já aprovados e válidos são reaproveitados automaticamente (H11).
3. Envia os documentos que faltam, informando a data de validade (H02, RF03).
4. **Resultado:** documentos `PENDENTE` na fila do gestor; pendências visíveis por contrato.

### J3 · Aprovar ou rejeitar — Gestor(a) SST

1. Abre a fila de pendentes e visualiza o arquivo por link temporário (H12).
2. Aprova conferindo a validade (H13) ou rejeita com motivo obrigatório (H03).
3. A terceirizada vê o motivo e reenvia (H14).
4. **Resultado:** decisão registrada na trilha de auditoria (H20); semáforo recalculado.

### J4 · Vencimentos e semáforo — Sistema

1. Todo dia às 03:00, o recálculo idempotente atualiza a situação de cada documento (H15).
2. Gera alertas de "vence em 30 dias" e "vencido", sem duplicar (H05).
3. Atualiza o semáforo por trabalhador e por contrato (H16).
4. **Resultado:** gestor(a) vê alertas e semáforo atualizados sem nenhuma ação manual.

### J5 · Portaria — Porteiro(a)

1. Digita o CPF do trabalhador (H04).
2. Recebe `LIBERADO`, `BLOQUEADO` (com pendências) ou `NAO_CADASTRADO`.
3. Registra a entrada ou o barramento (H18).
4. **Resultado:** acesso registrado e auditável.
