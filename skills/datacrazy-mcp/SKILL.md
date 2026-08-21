---
name: datacrazy-mcp
description: Skill da REST API do DataCrazy na MCP.AI: 64 endpoints em /api/datacrazy. CRM omnichannel DataCrazy (WhatsApp, Instagram, Facebook) via API oficial: leads, negócios, pipelines e estágios, atividades, tags, produtos, conversas e atendimento, listas, anexos e comentários. Gere sua chave de API no painel em Configurações → Chaves de API. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# DataCrazy — REST API skill

Você tem acesso à **DataCrazy** REST API na MCP.AI.

> CRM omnichannel DataCrazy (WhatsApp, Instagram, Facebook) via API oficial: leads, negócios, pipelines e estágios, atividades, tags, produtos, conversas e atendimento, listas, anexos e comentários. Gere sua chave de API no painel em Configurações → Chaves de API.

## Base URL

```
https://api.mcp.ai/api/datacrazy
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
curl -X POST https://api.mcp.ai/api/datacrazy/activities/create \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/datacrazy/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (64)

#### `datacrazy_activities_create`

Criar atividade (POST /api/v1/activities). _(POST /api/datacrazy/activities/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |

#### `datacrazy_activities_delete`

Excluir atividade (DELETE /api/v1/activities/{id}). _(POST /api/datacrazy/activities/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_activities_get`

Buscar atividade por ID (GET /api/v1/activities/{id}). _(POST /api/datacrazy/activities/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_activities_list`

Buscar atividades (GET /api/v1/activities). _(POST /api/datacrazy/activities/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |

#### `datacrazy_activities_patch`

Atualizar atividade (PATCH /api/v1/activities/{id}). _(POST /api/datacrazy/activities/patch)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_attendants_crm_get`

Buscar atendente por ID (CRM) (GET /api/v1/attendants/crm/{id}). _(POST /api/datacrazy/attendants/crm/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_attendants_crm_list`

Buscar atendentes (CRM) (GET /api/v1/attendants/crm). _(POST /api/datacrazy/attendants/crm/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |

#### `datacrazy_attendants_multi_get`

Buscar atendente por ID (multiatendimento) (GET /api/v1/attendants/multi/{id}). _(POST /api/datacrazy/attendants/multi/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_attendants_multi_list`

Buscar atendentes (multiatendimento) (GET /api/v1/attendants/multi). _(POST /api/datacrazy/attendants/multi/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |

#### `datacrazy_business_loss_reasons_create`

Criar motivo de perda (POST /api/v1/business-loss-reasons). _(POST /api/datacrazy/business/loss/reasons/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |

#### `datacrazy_business_loss_reasons_delete`

Excluir motivo de perda (DELETE /api/v1/business-loss-reasons/{id}). _(POST /api/datacrazy/business/loss/reasons/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_business_loss_reasons_get`

Buscar motivos de perda por ID (GET /api/v1/business-loss-reasons/{id}). _(POST /api/datacrazy/business/loss/reasons/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_business_loss_reasons_list`

Buscar motivos de perda (GET /api/v1/business-loss-reasons). _(POST /api/datacrazy/business/loss/reasons/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |

#### `datacrazy_business_loss_reasons_update`

Atualizar motivo de perda (PUT /api/v1/business-loss-reasons/{id}). _(POST /api/datacrazy/business/loss/reasons/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_businesses_actions_lose_create`

Perder negócios (POST /api/v1/businesses/actions/lose). _(POST /api/datacrazy/businesses/actions/lose/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |

#### `datacrazy_businesses_actions_move_create`

Mover negócios (POST /api/v1/businesses/actions/move). _(POST /api/datacrazy/businesses/actions/move/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |

#### `datacrazy_businesses_actions_restore_create`

Restaurar negócios (POST /api/v1/businesses/actions/restore). _(POST /api/datacrazy/businesses/actions/restore/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |

#### `datacrazy_businesses_actions_win_create`

Ganhar negócios (POST /api/v1/businesses/actions/win). _(POST /api/datacrazy/businesses/actions/win/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |

#### `datacrazy_businesses_create`

Criar negócio (POST /api/v1/businesses). _(POST /api/datacrazy/businesses/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |

#### `datacrazy_businesses_delete`

Excluir negócio (DELETE /api/v1/businesses/{id}). _(POST /api/datacrazy/businesses/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_businesses_get`

Buscar negócio por ID (GET /api/v1/businesses/{id}). _(POST /api/datacrazy/businesses/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_businesses_list`

Buscar negócios (GET /api/v1/businesses). _(POST /api/datacrazy/businesses/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |

#### `datacrazy_businesses_patch`

Atualizar negócio (PATCH /api/v1/businesses/{id}). _(POST /api/datacrazy/businesses/patch)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_conversations_finish_create`

Finalizar atendimento (POST /api/v1/conversations/{id}/finish). _(POST /api/datacrazy/conversations/finish/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_conversations_list`

Buscar conversas (GET /api/v1/conversations). _(POST /api/datacrazy/conversations/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |

#### `datacrazy_conversations_messages_create`

Enviar mensagem para uma conversa (POST /api/v1/conversations/{id}/messages). _(POST /api/datacrazy/conversations/messages/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_conversations_messages_list`

Buscar conversa por ID (GET /api/v1/conversations/{id}/messages). _(POST /api/datacrazy/conversations/messages/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_instances_get`

Buscar instancia por ID (GET /api/v1/instances/{id}). _(POST /api/datacrazy/instances/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_instances_list`

Buscar instancias (GET /api/v1/instances). _(POST /api/datacrazy/instances/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |

#### `datacrazy_leads_activities_list`

Buscar as atividades do lead (GET /api/v1/leads/{id}/activities). _(POST /api/datacrazy/leads/activities/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_leads_additional_fields_create`

Criar lead com campos adicionais (POST /api/v1/leads/additional-fields). _(POST /api/datacrazy/leads/additional/fields/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |

#### `datacrazy_leads_attachments_create`

Anexar arquivo ao lead (POST /api/v1/leads/{leadId}/attachments). _(POST /api/datacrazy/leads/attachments/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `leadId` | string | Sim | Path param "leadId" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |

#### `datacrazy_leads_attachments_delete`

Apagar arquivo anexado ao lead (DELETE /api/v1/leads/{leadId}/attachments/{id}). _(POST /api/datacrazy/leads/attachments/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `leadId` | string | Sim | Path param "leadId" (obrigatório) |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_leads_attachments_list`

Buscar os arquivos anexados ao lead (GET /api/v1/leads/{leadId}/attachments). _(POST /api/datacrazy/leads/attachments/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `leadId` | string | Sim | Path param "leadId" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |

#### `datacrazy_leads_businesses_list`

Buscar os negocios do lead (GET /api/v1/leads/{id}/businesses). _(POST /api/datacrazy/leads/businesses/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_leads_create`

Criar lead (POST /api/v1/leads). _(POST /api/datacrazy/leads/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |

#### `datacrazy_leads_delete`

Excluir lead (DELETE /api/v1/leads/{id}). _(POST /api/datacrazy/leads/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_leads_get`

Buscar lead por ID (GET /api/v1/leads/{id}). _(POST /api/datacrazy/leads/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_leads_history_list`

Buscar histórico do lead (GET /api/v1/leads/{id}/history). _(POST /api/datacrazy/leads/history/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_leads_list`

Buscar leads (GET /api/v1/leads). _(POST /api/datacrazy/leads/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |

#### `datacrazy_leads_notes_create`

Adicionar comentário (POST /api/v1/leads/{leadId}/notes). _(POST /api/datacrazy/leads/notes/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `leadId` | string | Sim | Path param "leadId" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |

#### `datacrazy_leads_notes_delete`

Excluir comentário do lead (DELETE /api/v1/leads/{leadId}/notes/{id}). _(POST /api/datacrazy/leads/notes/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `leadId` | string | Sim | Path param "leadId" (obrigatório) |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_leads_notes_list`

Buscar comentários do lead (GET /api/v1/leads/{leadId}/notes). _(POST /api/datacrazy/leads/notes/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `leadId` | string | Sim | Path param "leadId" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |

#### `datacrazy_leads_notes_update`

Atualizar comentário do lead (PUT /api/v1/leads/{leadId}/notes/{id}). _(POST /api/datacrazy/leads/notes/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `leadId` | string | Sim | Path param "leadId" (obrigatório) |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_leads_patch`

Atualizar lead (PATCH /api/v1/leads/{id}). _(POST /api/datacrazy/leads/patch)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_list_accounts`

Lista as conexões (contas) DataCrazy vinculadas a este install — id, label. _(POST /api/datacrazy/list/accounts)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |

#### `datacrazy_lists_create`

Criar lista (POST /api/v1/lists). _(POST /api/datacrazy/lists/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |

#### `datacrazy_lists_delete`

Excluir lista (DELETE /api/v1/lists/{id}). _(POST /api/datacrazy/lists/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_lists_get`

Buscar lista por ID (GET /api/v1/lists/{id}). _(POST /api/datacrazy/lists/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_lists_list`

Buscar listas (GET /api/v1/lists). _(POST /api/datacrazy/lists/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |

#### `datacrazy_lists_update`

Atualizar lista (PUT /api/v1/lists/{id}). _(POST /api/datacrazy/lists/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_pipelines_get`

Buscar pipeline por ID (GET /api/v1/pipelines/{id}). _(POST /api/datacrazy/pipelines/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_pipelines_list`

Buscar pipelines (GET /api/v1/pipelines). _(POST /api/datacrazy/pipelines/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |

#### `datacrazy_pipelines_stages_list`

Buscar etapas da pipeline (GET /api/v1/pipelines/{id}/stages). _(POST /api/datacrazy/pipelines/stages/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_products_create`

Criar produto (POST /api/v1/products). _(POST /api/datacrazy/products/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |

#### `datacrazy_products_delete`

Excluir produto (DELETE /api/v1/products/{id}). _(POST /api/datacrazy/products/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_products_get`

Buscar produto (GET /api/v1/products/{id}). _(POST /api/datacrazy/products/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_products_list`

Buscar produtos (GET /api/v1/products). _(POST /api/datacrazy/products/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |

#### `datacrazy_products_update`

Atualizar produto (PUT /api/v1/products/{id}). _(POST /api/datacrazy/products/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_tags_create`

Criar tag (POST /api/v1/tags). _(POST /api/datacrazy/tags/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |

#### `datacrazy_tags_delete`

Excluir tag (DELETE /api/v1/tags/{id}). _(POST /api/datacrazy/tags/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_tags_get`

Buscar tag por ID (GET /api/v1/tags/{id}). _(POST /api/datacrazy/tags/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `datacrazy_tags_list`

Buscar tags (GET /api/v1/tags). _(POST /api/datacrazy/tags/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `query` | string | Não | Query params como JSON string (filtros do recurso + paginação skip/take). Ex.: {"search":"acme","take":50}. Campos em docs.datacrazy.io. |

#### `datacrazy_tags_update`

Atualizar tag (PUT /api/v1/tags/{id}). _(POST /api/datacrazy/tags/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas DataCrazy conectadas: id ou label da conexão. Veja datacrazy_list_accounts. |
| `id` | string | Sim | Path param "id" (obrigatório) |
| `body` | string | Não | Corpo da requisição como JSON string (campos do recurso). Ex. criar lead: {"name":"Acme","email":"...","phone":"..."}. Campos em docs.datacrazy.io. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_datacrazy` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
