# API (OpenAPI)

Fonte única: `openapi.yaml` na raiz do repositório. Esta página apenas renderiza o contrato.

**Convenções do contrato v0.1** (detalhes na descrição do próprio contrato):

- Autenticação por `Authorization: Bearer <Firebase ID token>`; o tenant vem sempre da claim, nunca da requisição ([ADR 0002](adr/0002-tenant-autorizacao.md)).
- Papéis permitidos por rota na extensão `x-papeis`, base da matriz de autorização ([Estratégia de testes](../testes/estrategia.md)).
- Recurso de outro tenant → **404**; papel sem permissão → **403**; sem token → **401**.
- Erros em Problem Details (RFC 9457), `application/problem+json`.
- Listas paginadas por cursor (`limite` 1 a 50).
- CPF da portaria vai no corpo de `POST /liberacoes/consultas`, nunca na URL ([ADR 0008](adr/0008-consulta-liberacao-cpf.md)).

<swagger-ui src="../openapi.yaml"/>

## Histórico de versões

| Versão | Data | Autor | Alterações |
|---|---|---|---|
| 1.0 | 14/10/2026 | @osamuelleite | Versão inicial, conciliação PO + Tech Lead. Da PO: página e openapi.yaml na raiz como fonte única. Do Tech Lead: contrato OpenAPI 3.1 com 28 operações (C11). |
