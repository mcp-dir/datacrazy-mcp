# DataCrazy

### DataCrazy for Claude, ChatGPT and AI agents

DataCrazy omnichannel CRM (WhatsApp, Instagram, Facebook) via the official API: leads, deals, pipelines and stages, activities, tags, products, conversations and service, lists, attachments and notes. Generate your API key in the dashboard under Settings → API Keys.

- 📊 **64 tools**
- ✏️ **Read and write**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `DataCrazy`, URL `https://api.mcp.ai/p_datacrazy`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=datacrazy&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9kYXRhY3JhenkifQ==)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=datacrazy&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_datacrazy%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_datacrazy
```

---

## 64 tools

| Tool | Description |
|---|---|
| `datacrazy_list_accounts` | Lista as conexões (contas) DataCrazy vinculadas a este install — id, label. |
| `datacrazy_activities_create` | Criar atividade (POST /api/v1/activities). |
| `datacrazy_activities_delete` | Excluir atividade (DELETE /api/v1/activities/{id}). |
| `datacrazy_activities_get` | Buscar atividade por ID (GET /api/v1/activities/{id}). |
| `datacrazy_activities_list` | Buscar atividades (GET /api/v1/activities). |
| `datacrazy_activities_patch` | Atualizar atividade (PATCH /api/v1/activities/{id}). |
| `datacrazy_attendants_crm_get` | Buscar atendente por ID (CRM) (GET /api/v1/attendants/crm/{id}). |
| `datacrazy_attendants_crm_list` | Buscar atendentes (CRM) (GET /api/v1/attendants/crm). |
| `datacrazy_attendants_multi_get` | Buscar atendente por ID (multiatendimento) (GET /api/v1/attendants/multi/{id}). |
| `datacrazy_attendants_multi_list` | Buscar atendentes (multiatendimento) (GET /api/v1/attendants/multi). |
| `datacrazy_business_loss_reasons_create` | Criar motivo de perda (POST /api/v1/business-loss-reasons). |
| `datacrazy_business_loss_reasons_delete` | Excluir motivo de perda (DELETE /api/v1/business-loss-reasons/{id}). |
| `datacrazy_business_loss_reasons_get` | Buscar motivos de perda por ID (GET /api/v1/business-loss-reasons/{id}). |
| `datacrazy_business_loss_reasons_list` | Buscar motivos de perda (GET /api/v1/business-loss-reasons). |
| `datacrazy_business_loss_reasons_update` | Atualizar motivo de perda (PUT /api/v1/business-loss-reasons/{id}). |
| `datacrazy_businesses_actions_lose_create` | Perder negócios (POST /api/v1/businesses/actions/lose). |
| `datacrazy_businesses_actions_move_create` | Mover negócios (POST /api/v1/businesses/actions/move). |
| `datacrazy_businesses_actions_restore_create` | Restaurar negócios (POST /api/v1/businesses/actions/restore). |
| `datacrazy_businesses_actions_win_create` | Ganhar negócios (POST /api/v1/businesses/actions/win). |
| `datacrazy_businesses_create` | Criar negócio (POST /api/v1/businesses). |
| `datacrazy_businesses_delete` | Excluir negócio (DELETE /api/v1/businesses/{id}). |
| `datacrazy_businesses_get` | Buscar negócio por ID (GET /api/v1/businesses/{id}). |
| `datacrazy_businesses_list` | Buscar negócios (GET /api/v1/businesses). |
| `datacrazy_businesses_patch` | Atualizar negócio (PATCH /api/v1/businesses/{id}). |
| `datacrazy_conversations_finish_create` | Finalizar atendimento (POST /api/v1/conversations/{id}/finish). |
| `datacrazy_conversations_list` | Buscar conversas (GET /api/v1/conversations). |
| `datacrazy_conversations_messages_create` | Enviar mensagem para uma conversa (POST /api/v1/conversations/{id}/messages). |
| `datacrazy_conversations_messages_list` | Buscar conversa por ID (GET /api/v1/conversations/{id}/messages). |
| `datacrazy_instances_get` | Buscar instancia por ID (GET /api/v1/instances/{id}). |
| `datacrazy_instances_list` | Buscar instancias (GET /api/v1/instances). |
| `datacrazy_leads_activities_list` | Buscar as atividades do lead (GET /api/v1/leads/{id}/activities). |
| `datacrazy_leads_additional_fields_create` | Criar lead com campos adicionais (POST /api/v1/leads/additional-fields). |
| `datacrazy_leads_attachments_create` | Anexar arquivo ao lead (POST /api/v1/leads/{leadId}/attachments). |
| `datacrazy_leads_attachments_delete` | Apagar arquivo anexado ao lead (DELETE /api/v1/leads/{leadId}/attachments/{id}). |
| `datacrazy_leads_attachments_list` | Buscar os arquivos anexados ao lead (GET /api/v1/leads/{leadId}/attachments). |
| `datacrazy_leads_businesses_list` | Buscar os negocios do lead (GET /api/v1/leads/{id}/businesses). |
| `datacrazy_leads_create` | Criar lead (POST /api/v1/leads). |
| `datacrazy_leads_delete` | Excluir lead (DELETE /api/v1/leads/{id}). |
| `datacrazy_leads_get` | Buscar lead por ID (GET /api/v1/leads/{id}). |
| `datacrazy_leads_history_list` | Buscar histórico do lead (GET /api/v1/leads/{id}/history). |
| `datacrazy_leads_list` | Buscar leads (GET /api/v1/leads). |
| `datacrazy_leads_notes_create` | Adicionar comentário (POST /api/v1/leads/{leadId}/notes). |
| `datacrazy_leads_notes_delete` | Excluir comentário do lead (DELETE /api/v1/leads/{leadId}/notes/{id}). |
| `datacrazy_leads_notes_list` | Buscar comentários do lead (GET /api/v1/leads/{leadId}/notes). |
| `datacrazy_leads_notes_update` | Atualizar comentário do lead (PUT /api/v1/leads/{leadId}/notes/{id}). |
| `datacrazy_leads_patch` | Atualizar lead (PATCH /api/v1/leads/{id}). |
| `datacrazy_lists_create` | Criar lista (POST /api/v1/lists). |
| `datacrazy_lists_delete` | Excluir lista (DELETE /api/v1/lists/{id}). |
| `datacrazy_lists_get` | Buscar lista por ID (GET /api/v1/lists/{id}). |
| `datacrazy_lists_list` | Buscar listas (GET /api/v1/lists). |
| `datacrazy_lists_update` | Atualizar lista (PUT /api/v1/lists/{id}). |
| `datacrazy_pipelines_get` | Buscar pipeline por ID (GET /api/v1/pipelines/{id}). |
| `datacrazy_pipelines_list` | Buscar pipelines (GET /api/v1/pipelines). |
| `datacrazy_pipelines_stages_list` | Buscar etapas da pipeline (GET /api/v1/pipelines/{id}/stages). |
| `datacrazy_products_create` | Criar produto (POST /api/v1/products). |
| `datacrazy_products_delete` | Excluir produto (DELETE /api/v1/products/{id}). |
| `datacrazy_products_get` | Buscar produto (GET /api/v1/products/{id}). |
| `datacrazy_products_list` | Buscar produtos (GET /api/v1/products). |
| `datacrazy_products_update` | Atualizar produto (PUT /api/v1/products/{id}). |
| `datacrazy_tags_create` | Criar tag (POST /api/v1/tags). |
| `datacrazy_tags_delete` | Excluir tag (DELETE /api/v1/tags/{id}). |
| `datacrazy_tags_get` | Buscar tag por ID (GET /api/v1/tags/{id}). |
| `datacrazy_tags_list` | Buscar tags (GET /api/v1/tags). |
| `datacrazy_tags_update` | Atualizar tag (PUT /api/v1/tags/{id}). |

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_datacrazy` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
