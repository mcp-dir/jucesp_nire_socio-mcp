---
name: jucesp_nire_socio-mcp
description: Skill da REST API do JUCESP: NIRE a partir de Sócio na MCP.AI: 1 endpoint em /api/jucesp_nire_socio. Encontra empresas na JUCESP a partir de um sócio (nome, CPF ou CNPJ), retornando o NIRE de cada participação. Hospedado pela plataforma, sem credenciais, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# JUCESP: NIRE a partir de Sócio — REST API skill

Você tem acesso à **JUCESP: NIRE a partir de Sócio** REST API na MCP.AI.

> Encontra empresas na JUCESP a partir de um sócio (nome, CPF ou CNPJ), retornando o NIRE de cada participação. Hospedado pela plataforma, sem credenciais, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/jucesp_nire_socio
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/jucesp_nire_socio/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/jucesp_nire_socio/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `jucesp_nire_socio_consultar`

Encontra empresas na JUCESP a partir de um sócio (nome, CPF ou CNPJ), retornando o NIRE de cada participação. _(POST /api/jucesp_nire_socio/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `login_cpf` | string | Não | Parâmetro de consulta "login_cpf". |
| `login_senha` | string | Não | Parâmetro de consulta "login_senha". |
| `pkcs12_cert` | string | Não | Parâmetro de consulta "pkcs12_cert". |
| `pkcs12_pass` | string | Não | Parâmetro de consulta "pkcs12_pass". |
| `socio_nome` | string | Não | Parâmetro de consulta "socio_nome". |
| `socio_cpf` | string | Não | Parâmetro de consulta "socio_cpf". |
| `socio_cnpj` | string | Não | Parâmetro de consulta "socio_cnpj". |
| `inclui_inativas` | string | Não | Parâmetro de consulta "inclui_inativas". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_jucesp_nire_socio` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
