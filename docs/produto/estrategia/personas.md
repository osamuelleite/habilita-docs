# Personas do Usuário

!!! info "Sobre esta página"
    **Para que serve:** Descrever quem usa o sistema, para guiar decisões de tela e prioridade.

    **O que escrever:** Validar as hipóteses abaixo com as entrevistas. Uma seção por persona.

    **Prazo:** Recomendado no CP1

!!! warning "Hipóteses"
    Derivadas das jornadas do Guia de Projetos. Ainda não validadas.

## 1. Gestor(a) de SST / Facilities (contratante)

Define as exigências de cada contrato, aprova ou rejeita documentos e acompanha o semáforo. Provável decisor(a) da compra (hipótese HP5 das entrevistas). Papel no sistema: `gestor`.

## 2. Responsável da empresa terceirizada

Cadastra trabalhadores e envia os documentos exigidos. Papel no sistema: `terceirizada` (vê apenas os próprios trabalhadores).

## 3. Porteiro(a) / controle de acesso

Consulta se o trabalhador está liberado e registra a entrada. Papel no sistema: `porteiro`.

| Persona | Objetivo | Dor principal | Frequência de uso (hipótese) |
|---|---|---|---|
| Gestor(a) SST | Saber quem está apto, por contrato, sem montar planilha | Vencimentos passam despercebidos; aprovar documento por e-mail não deixa histórico | Diária |
| Terceirizada | Enviar os documentos uma vez e saber o que falta | Reenvia o mesmo documento para cada contrato; não sabe por que foi recusado | A cada admissão, vencimento ou rejeição |
| Portaria | Liberar ou barrar com segurança, rápido | Lista impressa desatualizada; responsabilidade sem ferramenta | Várias vezes por dia, a cada entrada |

## Histórico de versões

| Versão | Data | Autor | Alterações |
|---|---|---|---|
| 1.0 | 14/10/2026 | @osamuelleite | Versão inicial, conciliação PO + Tech Lead. Da PO: página e orientações. Conteúdo: três personas (gestor de SST, terceirizada, portaria) como hipóteses derivadas das jornadas. |
