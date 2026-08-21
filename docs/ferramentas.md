# Ferramentas

Supabase expõe 29 ferramentas.

### 1. `supabase_search_docs`
**Input**: `graphql_query`

Search the Supabase documentation using GraphQL.

### 2. `supabase_list_organizations`
**Input**: nenhum input

Lists all organizations that the user is a member of.

### 3. `supabase_get_organization`
**Input**: `id`, `ids` (opcional)

Gets details for an organization.

### 4. `supabase_list_projects`
**Input**: nenhum input

Lists all Supabase projects for the user.

### 5. `supabase_get_project`
**Input**: `id`, `ids` (opcional)

Gets details for a Supabase project.

### 6. `supabase_get_cost`
**Input**: `type`, `organization_id`, `organization_ids` (opcional)

Gets the cost of creating a new project or branch.

### 7. `supabase_confirm_cost`
**Input**: `type`, `recurrence`, `amount`

Ask the user to confirm their understanding of the cost of creating a new project or branch.

### 8. `supabase_create_project`
**Input**: `name`, `region`, `organization_id`, `confirm_cost_id`, `organization_ids` (opcional), `confirm_cost_ids` (opcional)

Creates a new Supabase project.

### 9. `supabase_pause_project`
**Input**: `project_id`, `project_ids` (opcional)

Pauses a Supabase project. Bulk support: accepts project_ids for batched execution.

### 10. `supabase_restore_project`
**Input**: `project_id`, `project_ids` (opcional)

Restores a Supabase project. Bulk support: accepts project_ids for batched execution.

### 11. `supabase_list_tables`
**Input**: `project_id`, `schemas`, `verbose`, `project_ids` (opcional)

Lists all tables in one or more schemas.

### 12. `supabase_list_extensions`
**Input**: `project_id`, `project_ids` (opcional)

Lists all extensions in the database.

### 13. `supabase_list_migrations`
**Input**: `project_id`, `project_ids` (opcional)

Lists all migrations in the database.

### 14. `supabase_apply_migration`
**Input**: `project_id`, `name`, `query`, `project_ids` (opcional)

Applies a migration to the database.

### 15. `supabase_execute_sql`
**Input**: `project_id`, `query`, `project_ids` (opcional)

Executes raw SQL in the Postgres database.

### 16. `supabase_get_logs`
**Input**: `project_id`, `service`, `project_ids` (opcional)

Gets logs for a Supabase project by service type.

### 17. `supabase_get_advisors`
**Input**: `project_id`, `type`, `project_ids` (opcional)

Gets a list of advisory notices for the Supabase project.

### 18. `supabase_get_project_url`
**Input**: `project_id`, `project_ids` (opcional)

Gets the API URL for a project.

### 19. `supabase_get_publishable_keys`
**Input**: `project_id`, `project_ids` (opcional)

Gets all publishable API keys for a project, including legacy anon keys (JWT-based) and modern publishable keys (format: sb_publishable_...).

### 20. `supabase_generate_typescript_types`
**Input**: `project_id`, `project_ids` (opcional)

Generates TypeScript types for a project.

### 21. `supabase_list_edge_functions`
**Input**: `project_id`, `project_ids` (opcional)

Lists all Edge Functions in a Supabase project.

### 22. `supabase_get_edge_function`
**Input**: `project_id`, `function_slug`, `project_ids` (opcional)

Retrieves file contents for an Edge Function in a Supabase project.

### 23. `supabase_deploy_edge_function`
**Input**: `project_id`, `name`, `entrypoint_path`, `import_map_path` (opcional), `verify_jwt`, `files`, `project_ids` (opcional)

Deploys an Edge Function to a Supabase project.

### 24. `supabase_create_branch`
**Input**: `project_id`, `name`, `confirm_cost_id`, `project_ids` (opcional), `confirm_cost_ids` (opcional)

Creates a development branch on a Supabase project.

### 25. `supabase_list_branches`
**Input**: `project_id`, `project_ids` (opcional)

Lists all development branches of a Supabase project.

### 26. `supabase_delete_branch`
**Input**: `branch_id`, `branch_ids` (opcional)

Deletes a development branch. Bulk support: accepts branch_ids for batched execution.

### 27. `supabase_merge_branch`
**Input**: `branch_id`, `branch_ids` (opcional)

Merges migrations and edge functions from a development branch to production.

### 28. `supabase_reset_branch`
**Input**: `branch_id`, `migration_version` (opcional), `branch_ids` (opcional)

Resets migrations of a development branch.

### 29. `supabase_rebase_branch`
**Input**: `branch_id`, `branch_ids` (opcional)

Rebases a development branch on production.

## Prompts de exemplo

```
Liste as tabelas do meu projeto Supabase
Rode um SELECT na tabela de usuários e me mostre os 10 últimos
Crie uma migration que adiciona a coluna status na tabela pedidos
```
