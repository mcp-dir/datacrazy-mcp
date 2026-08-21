# Ferramentas

DataCrazy expõe 64 ferramentas.

### 1. `datacrazy_list_accounts`
**Input**: `account` (opcional)

Lista as conexões (contas) DataCrazy vinculadas a este install — id, label.

### 2. `datacrazy_activities_create`
**Input**: `account` (opcional), `body` (opcional)

Criar atividade (POST /api/v1/activities).

### 3. `datacrazy_activities_delete`
**Input**: `account` (opcional), `id`, `body` (opcional), `ids` (opcional)

Excluir atividade (DELETE /api/v1/activities/{id}).

### 4. `datacrazy_activities_get`
**Input**: `account` (opcional), `id`, `query` (opcional), `ids` (opcional)

Buscar atividade por ID (GET /api/v1/activities/{id}).

### 5. `datacrazy_activities_list`
**Input**: `account` (opcional), `query` (opcional)

Buscar atividades (GET /api/v1/activities).

### 6. `datacrazy_activities_patch`
**Input**: `account` (opcional), `id`, `body` (opcional), `ids` (opcional)

Atualizar atividade (PATCH /api/v1/activities/{id}).

### 7. `datacrazy_attendants_crm_get`
**Input**: `account` (opcional), `id`, `query` (opcional), `ids` (opcional)

Buscar atendente por ID (CRM) (GET /api/v1/attendants/crm/{id}).

### 8. `datacrazy_attendants_crm_list`
**Input**: `account` (opcional), `query` (opcional)

Buscar atendentes (CRM) (GET /api/v1/attendants/crm).

### 9. `datacrazy_attendants_multi_get`
**Input**: `account` (opcional), `id`, `query` (opcional), `ids` (opcional)

Buscar atendente por ID (multiatendimento) (GET /api/v1/attendants/multi/{id}).

### 10. `datacrazy_attendants_multi_list`
**Input**: `account` (opcional), `query` (opcional)

Buscar atendentes (multiatendimento) (GET /api/v1/attendants/multi).

### 11. `datacrazy_business_loss_reasons_create`
**Input**: `account` (opcional), `body` (opcional)

Criar motivo de perda (POST /api/v1/business-loss-reasons).

### 12. `datacrazy_business_loss_reasons_delete`
**Input**: `account` (opcional), `id`, `body` (opcional), `ids` (opcional)

Excluir motivo de perda (DELETE /api/v1/business-loss-reasons/{id}).

### 13. `datacrazy_business_loss_reasons_get`
**Input**: `account` (opcional), `id`, `query` (opcional), `ids` (opcional)

Buscar motivos de perda por ID (GET /api/v1/business-loss-reasons/{id}).

### 14. `datacrazy_business_loss_reasons_list`
**Input**: `account` (opcional), `query` (opcional)

Buscar motivos de perda (GET /api/v1/business-loss-reasons).

### 15. `datacrazy_business_loss_reasons_update`
**Input**: `account` (opcional), `id`, `body` (opcional), `ids` (opcional)

Atualizar motivo de perda (PUT /api/v1/business-loss-reasons/{id}).

### 16. `datacrazy_businesses_actions_lose_create`
**Input**: `account` (opcional), `body` (opcional)

Perder negócios (POST /api/v1/businesses/actions/lose).

### 17. `datacrazy_businesses_actions_move_create`
**Input**: `account` (opcional), `body` (opcional)

Mover negócios (POST /api/v1/businesses/actions/move).

### 18. `datacrazy_businesses_actions_restore_create`
**Input**: `account` (opcional), `body` (opcional)

Restaurar negócios (POST /api/v1/businesses/actions/restore).

### 19. `datacrazy_businesses_actions_win_create`
**Input**: `account` (opcional), `body` (opcional)

Ganhar negócios (POST /api/v1/businesses/actions/win).

### 20. `datacrazy_businesses_create`
**Input**: `account` (opcional), `body` (opcional)

Criar negócio (POST /api/v1/businesses).

### 21. `datacrazy_businesses_delete`
**Input**: `account` (opcional), `id`, `body` (opcional), `ids` (opcional)

Excluir negócio (DELETE /api/v1/businesses/{id}).

### 22. `datacrazy_businesses_get`
**Input**: `account` (opcional), `id`, `query` (opcional), `ids` (opcional)

Buscar negócio por ID (GET /api/v1/businesses/{id}).

### 23. `datacrazy_businesses_list`
**Input**: `account` (opcional), `query` (opcional)

Buscar negócios (GET /api/v1/businesses).

### 24. `datacrazy_businesses_patch`
**Input**: `account` (opcional), `id`, `body` (opcional), `ids` (opcional)

Atualizar negócio (PATCH /api/v1/businesses/{id}).

### 25. `datacrazy_conversations_finish_create`
**Input**: `account` (opcional), `id`, `body` (opcional), `ids` (opcional)

Finalizar atendimento (POST /api/v1/conversations/{id}/finish).

### 26. `datacrazy_conversations_list`
**Input**: `account` (opcional), `query` (opcional)

Buscar conversas (GET /api/v1/conversations).

### 27. `datacrazy_conversations_messages_create`
**Input**: `account` (opcional), `id`, `body` (opcional), `ids` (opcional)

Enviar mensagem para uma conversa (POST /api/v1/conversations/{id}/messages).

### 28. `datacrazy_conversations_messages_list`
**Input**: `account` (opcional), `id`, `query` (opcional), `ids` (opcional)

Buscar conversa por ID (GET /api/v1/conversations/{id}/messages).

### 29. `datacrazy_instances_get`
**Input**: `account` (opcional), `id`, `query` (opcional), `ids` (opcional)

Buscar instancia por ID (GET /api/v1/instances/{id}).

### 30. `datacrazy_instances_list`
**Input**: `account` (opcional), `query` (opcional)

Buscar instancias (GET /api/v1/instances).

### 31. `datacrazy_leads_activities_list`
**Input**: `account` (opcional), `id`, `query` (opcional), `ids` (opcional)

Buscar as atividades do lead (GET /api/v1/leads/{id}/activities).

### 32. `datacrazy_leads_additional_fields_create`
**Input**: `account` (opcional), `body` (opcional)

Criar lead com campos adicionais (POST /api/v1/leads/additional-fields).

### 33. `datacrazy_leads_attachments_create`
**Input**: `account` (opcional), `leadId`, `body` (opcional)

Anexar arquivo ao lead (POST /api/v1/leads/{leadId}/attachments).

### 34. `datacrazy_leads_attachments_delete`
**Input**: `account` (opcional), `leadId`, `id`, `body` (opcional), `ids` (opcional)

Apagar arquivo anexado ao lead (DELETE /api/v1/leads/{leadId}/attachments/{id}).

### 35. `datacrazy_leads_attachments_list`
**Input**: `account` (opcional), `leadId`, `query` (opcional)

Buscar os arquivos anexados ao lead (GET /api/v1/leads/{leadId}/attachments).

### 36. `datacrazy_leads_businesses_list`
**Input**: `account` (opcional), `id`, `query` (opcional), `ids` (opcional)

Buscar os negocios do lead (GET /api/v1/leads/{id}/businesses).

### 37. `datacrazy_leads_create`
**Input**: `account` (opcional), `body` (opcional)

Criar lead (POST /api/v1/leads).

### 38. `datacrazy_leads_delete`
**Input**: `account` (opcional), `id`, `body` (opcional), `ids` (opcional)

Excluir lead (DELETE /api/v1/leads/{id}).

### 39. `datacrazy_leads_get`
**Input**: `account` (opcional), `id`, `query` (opcional), `ids` (opcional)

Buscar lead por ID (GET /api/v1/leads/{id}).

### 40. `datacrazy_leads_history_list`
**Input**: `account` (opcional), `id`, `query` (opcional), `ids` (opcional)

Buscar histórico do lead (GET /api/v1/leads/{id}/history).

### 41. `datacrazy_leads_list`
**Input**: `account` (opcional), `query` (opcional)

Buscar leads (GET /api/v1/leads).

### 42. `datacrazy_leads_notes_create`
**Input**: `account` (opcional), `leadId`, `body` (opcional)

Adicionar comentário (POST /api/v1/leads/{leadId}/notes).

### 43. `datacrazy_leads_notes_delete`
**Input**: `account` (opcional), `leadId`, `id`, `body` (opcional), `ids` (opcional)

Excluir comentário do lead (DELETE /api/v1/leads/{leadId}/notes/{id}).

### 44. `datacrazy_leads_notes_list`
**Input**: `account` (opcional), `leadId`, `query` (opcional)

Buscar comentários do lead (GET /api/v1/leads/{leadId}/notes).

### 45. `datacrazy_leads_notes_update`
**Input**: `account` (opcional), `leadId`, `id`, `body` (opcional), `ids` (opcional)

Atualizar comentário do lead (PUT /api/v1/leads/{leadId}/notes/{id}).

### 46. `datacrazy_leads_patch`
**Input**: `account` (opcional), `id`, `body` (opcional), `ids` (opcional)

Atualizar lead (PATCH /api/v1/leads/{id}).

### 47. `datacrazy_lists_create`
**Input**: `account` (opcional), `body` (opcional)

Criar lista (POST /api/v1/lists).

### 48. `datacrazy_lists_delete`
**Input**: `account` (opcional), `id`, `body` (opcional), `ids` (opcional)

Excluir lista (DELETE /api/v1/lists/{id}).

### 49. `datacrazy_lists_get`
**Input**: `account` (opcional), `id`, `query` (opcional), `ids` (opcional)

Buscar lista por ID (GET /api/v1/lists/{id}).

### 50. `datacrazy_lists_list`
**Input**: `account` (opcional), `query` (opcional)

Buscar listas (GET /api/v1/lists).

### 51. `datacrazy_lists_update`
**Input**: `account` (opcional), `id`, `body` (opcional), `ids` (opcional)

Atualizar lista (PUT /api/v1/lists/{id}).

### 52. `datacrazy_pipelines_get`
**Input**: `account` (opcional), `id`, `query` (opcional), `ids` (opcional)

Buscar pipeline por ID (GET /api/v1/pipelines/{id}).

### 53. `datacrazy_pipelines_list`
**Input**: `account` (opcional), `query` (opcional)

Buscar pipelines (GET /api/v1/pipelines).

### 54. `datacrazy_pipelines_stages_list`
**Input**: `account` (opcional), `id`, `query` (opcional), `ids` (opcional)

Buscar etapas da pipeline (GET /api/v1/pipelines/{id}/stages).

### 55. `datacrazy_products_create`
**Input**: `account` (opcional), `body` (opcional)

Criar produto (POST /api/v1/products).

### 56. `datacrazy_products_delete`
**Input**: `account` (opcional), `id`, `body` (opcional), `ids` (opcional)

Excluir produto (DELETE /api/v1/products/{id}).

### 57. `datacrazy_products_get`
**Input**: `account` (opcional), `id`, `query` (opcional), `ids` (opcional)

Buscar produto (GET /api/v1/products/{id}).

### 58. `datacrazy_products_list`
**Input**: `account` (opcional), `query` (opcional)

Buscar produtos (GET /api/v1/products).

### 59. `datacrazy_products_update`
**Input**: `account` (opcional), `id`, `body` (opcional), `ids` (opcional)

Atualizar produto (PUT /api/v1/products/{id}).

### 60. `datacrazy_tags_create`
**Input**: `account` (opcional), `body` (opcional)

Criar tag (POST /api/v1/tags).

### 61. `datacrazy_tags_delete`
**Input**: `account` (opcional), `id`, `body` (opcional), `ids` (opcional)

Excluir tag (DELETE /api/v1/tags/{id}).

### 62. `datacrazy_tags_get`
**Input**: `account` (opcional), `id`, `query` (opcional), `ids` (opcional)

Buscar tag por ID (GET /api/v1/tags/{id}).

### 63. `datacrazy_tags_list`
**Input**: `account` (opcional), `query` (opcional)

Buscar tags (GET /api/v1/tags).

### 64. `datacrazy_tags_update`
**Input**: `account` (opcional), `id`, `body` (opcional), `ids` (opcional)

Atualizar tag (PUT /api/v1/tags/{id}).

## Prompts de exemplo

```
Liste meus leads mais recentes no DataCrazy
Quais negócios estão abertos no pipeline?
Mostre as atividades do lead com email X
```
