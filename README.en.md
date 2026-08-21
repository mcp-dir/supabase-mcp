# Supabase

### Supabase for Claude, ChatGPT and AI agents

Your Supabase account in natural language: run SQL, apply migrations, manage tables, storage, edge functions and branches, and search the docs. Connect your account in one click, no key or token.

- 📊 **29 tools**
- ✏️ **Read and write**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `Supabase`, URL `https://api.mcp.ai/p_supabase`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=supabase&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9zdXBhYmFzZSJ9)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=supabase&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_supabase%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_supabase
```

---

## 29 tools

| Tool | Description |
|---|---|
| `supabase_search_docs` | Search the Supabase documentation using GraphQL. |
| `supabase_list_organizations` | Lists all organizations that the user is a member of. |
| `supabase_get_organization` | Gets details for an organization. |
| `supabase_list_projects` | Lists all Supabase projects for the user. |
| `supabase_get_project` | Gets details for a Supabase project. |
| `supabase_get_cost` | Gets the cost of creating a new project or branch. |
| `supabase_confirm_cost` | Ask the user to confirm their understanding of the cost of creating a new project or branch. |
| `supabase_create_project` | Creates a new Supabase project. |
| `supabase_pause_project` | Pauses a Supabase project. Bulk support: accepts project_ids for batched execution. |
| `supabase_restore_project` | Restores a Supabase project. Bulk support: accepts project_ids for batched execution. |
| `supabase_list_tables` | Lists all tables in one or more schemas. |
| `supabase_list_extensions` | Lists all extensions in the database. |
| `supabase_list_migrations` | Lists all migrations in the database. |
| `supabase_apply_migration` | Applies a migration to the database. |
| `supabase_execute_sql` | Executes raw SQL in the Postgres database. |
| `supabase_get_logs` | Gets logs for a Supabase project by service type. |
| `supabase_get_advisors` | Gets a list of advisory notices for the Supabase project. |
| `supabase_get_project_url` | Gets the API URL for a project. |
| `supabase_get_publishable_keys` | Gets all publishable API keys for a project, including legacy anon keys (JWT-based) and modern publishable keys (format: sb_publishable_...). |
| `supabase_generate_typescript_types` | Generates TypeScript types for a project. |
| `supabase_list_edge_functions` | Lists all Edge Functions in a Supabase project. |
| `supabase_get_edge_function` | Retrieves file contents for an Edge Function in a Supabase project. |
| `supabase_deploy_edge_function` | Deploys an Edge Function to a Supabase project. |
| `supabase_create_branch` | Creates a development branch on a Supabase project. |
| `supabase_list_branches` | Lists all development branches of a Supabase project. |
| `supabase_delete_branch` | Deletes a development branch. Bulk support: accepts branch_ids for batched execution. |
| `supabase_merge_branch` | Merges migrations and edge functions from a development branch to production. |
| `supabase_reset_branch` | Resets migrations of a development branch. |
| `supabase_rebase_branch` | Rebases a development branch on production. |

---

## Pricing

Free.

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_supabase` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
