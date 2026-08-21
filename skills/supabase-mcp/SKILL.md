---
name: supabase-mcp
description: Skill da REST API do Supabase na MCP.AI: 29 endpoints em /api/supabase. Sua conta Supabase por linguagem natural: rode SQL, aplique migrations, gerencie tabelas, storage, edge functions e branches, e consulte a documentação. Conecte com sua conta em um clique, sem chave nem token. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Supabase — REST API skill

Você tem acesso à **Supabase** REST API na MCP.AI.

> Sua conta Supabase por linguagem natural: rode SQL, aplique migrations, gerencie tabelas, storage, edge functions e branches, e consulte a documentação. Conecte com sua conta em um clique, sem chave nem token.

## Base URL

```
https://api.mcp.ai/api/supabase
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
curl -X POST https://api.mcp.ai/api/supabase/apply/migration \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"project_id":"...","name":"...","query":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/supabase/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (29)

#### `supabase_apply_migration`

Applies a migration to the database. _(POST /api/supabase/apply/migration)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `project_id` | string | Sim |  |
| `name` | string | Sim | The name of the migration in snake_case |
| `query` | string | Sim | The SQL query to apply |

#### `supabase_confirm_cost`

Ask the user to confirm their understanding of the cost of creating a new project or branch. _(POST /api/supabase/confirm/cost)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `type` | string | Sim |  (project, branch) |
| `recurrence` | string | Sim |  (hourly, monthly) |
| `amount` | number | Sim |  |

#### `supabase_create_branch`

Creates a development branch on a Supabase project. _(POST /api/supabase/create/branch)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `project_id` | string | Sim |  |
| `name` | string | Sim | Name of the branch to create |
| `confirm_cost_id` | string | Sim | The cost confirmation ID. Call `confirm_cost` first. |

#### `supabase_create_project`

Creates a new Supabase project. _(POST /api/supabase/create/project)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `name` | string | Sim | The name of the project |
| `region` | string | Sim | The region to create the project in. (us-west-1, us-east-1, us-east-2, ca-central-1, eu-west-1, eu-west-2, eu-west-3, eu-central-1, eu-central-2, eu-north-1, ap-south-1, ap-southeast-1, ap-northeast-1, ap-northeast-2, ap-southeast-2, sa-east-1) |
| `organization_id` | string | Sim |  |
| `confirm_cost_id` | string | Sim | The cost confirmation ID. Call `confirm_cost` first. |

#### `supabase_delete_branch`

Deletes a development branch. _(POST /api/supabase/delete/branch)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `branch_id` | string | Sim |  |

#### `supabase_deploy_edge_function`

Deploys an Edge Function to a Supabase project. _(POST /api/supabase/deploy/edge/function)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `project_id` | string | Sim |  |
| `name` | string | Sim | The name of the function |
| `entrypoint_path` | string | Sim | The entrypoint of the function |
| `import_map_path` | string | Não | The import map for the function. |
| `verify_jwt` | boolean | Sim | Whether to require a valid JWT in the Authorization header. You SHOULD ALWAYS enable this to ensure authorized access. ONLY disable if the function previously had it disabled OR you've confirmed the function body implements custom authentication (e.g., API keys, webhooks) OR the user explicitly requested it be disabled. |
| `files` | object[] | Sim | The files to upload. This should include the entrypoint, deno.json, and any relative dependencies. Include the deno.json and deno.jsonc files to configure the Deno runtime (e.g., compiler options, imports) if they exist. |

#### `supabase_execute_sql`

Executes raw SQL in the Postgres database. _(POST /api/supabase/execute/sql)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `project_id` | string | Sim |  |
| `query` | string | Sim | The SQL query to execute |

#### `supabase_generate_typescript_types`

Generates TypeScript types for a project. _(POST /api/supabase/generate/typescript/types)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `project_id` | string | Sim |  |

#### `supabase_get_advisors`

Gets a list of advisory notices for the Supabase project. _(POST /api/supabase/get/advisors)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `project_id` | string | Sim |  |
| `type` | string | Sim | The type of advisors to fetch (security, performance) |

#### `supabase_get_cost`

Gets the cost of creating a new project or branch. _(POST /api/supabase/get/cost)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `type` | string | Sim |  (project, branch) |
| `organization_id` | string | Sim | The organization ID. Always ask the user. |

#### `supabase_get_edge_function`

Retrieves file contents for an Edge Function in a Supabase project. _(POST /api/supabase/get/edge/function)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `project_id` | string | Sim |  |
| `function_slug` | string | Sim |  |

#### `supabase_get_logs`

Gets logs for a Supabase project by service type. _(POST /api/supabase/get/logs)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `project_id` | string | Sim |  |
| `service` | string | Sim | The service to fetch logs for (api, branch-action, postgres, edge-function, auth, storage, realtime) |

#### `supabase_get_organization`

Gets details for an organization. _(POST /api/supabase/get/organization)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string | Sim | The organization ID |

#### `supabase_get_project`

Gets details for a Supabase project. _(POST /api/supabase/get/project)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string | Sim | The project ID |

#### `supabase_get_project_url`

Gets the API URL for a project. _(POST /api/supabase/get/project/url)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `project_id` | string | Sim |  |

#### `supabase_get_publishable_keys`

Gets all publishable API keys for a project, including legacy anon keys (JWT-based) and modern publishable keys (format: sb_publishable_...). _(POST /api/supabase/get/publishable/keys)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `project_id` | string | Sim |  |

#### `supabase_list_branches`

Lists all development branches of a Supabase project. _(POST /api/supabase/list/branches)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `project_id` | string | Sim |  |

#### `supabase_list_edge_functions`

Lists all Edge Functions in a Supabase project. _(POST /api/supabase/list/edge/functions)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `project_id` | string | Sim |  |

#### `supabase_list_extensions`

Lists all extensions in the database. _(POST /api/supabase/list/extensions)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `project_id` | string | Sim |  |

#### `supabase_list_migrations`

Lists all migrations in the database. _(POST /api/supabase/list/migrations)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `project_id` | string | Sim |  |

#### `supabase_list_organizations`

Lists all organizations that the user is a member of. _(POST /api/supabase/list/organizations)_

#### `supabase_list_projects`

Lists all Supabase projects for the user. _(POST /api/supabase/list/projects)_

#### `supabase_list_tables`

Lists all tables in one or more schemas. _(POST /api/supabase/list/tables)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `project_id` | string | Sim |  |
| `schemas` | string[] | Sim | List of schemas to include. Defaults to all schemas. |
| `verbose` | boolean | Sim | When true, includes column details, primary keys, and foreign key constraints. Defaults to false for a compact summary. |

#### `supabase_merge_branch`

Merges migrations and edge functions from a development branch to production. _(POST /api/supabase/merge/branch)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `branch_id` | string | Sim |  |

#### `supabase_pause_project`

Pauses a Supabase project. _(POST /api/supabase/pause/project)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `project_id` | string | Sim |  |

#### `supabase_rebase_branch`

Rebases a development branch on production. _(POST /api/supabase/rebase/branch)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `branch_id` | string | Sim |  |

#### `supabase_reset_branch`

Resets migrations of a development branch. _(POST /api/supabase/reset/branch)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `branch_id` | string | Sim |  |
| `migration_version` | string | Não | Reset your development branch to a specific migration version. |

#### `supabase_restore_project`

Restores a Supabase project. _(POST /api/supabase/restore/project)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `project_id` | string | Sim |  |

#### `supabase_search_docs`

Search the Supabase documentation using GraphQL. _(POST /api/supabase/search/docs)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `graphql_query` | string | Sim | GraphQL query string |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_supabase` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
