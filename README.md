# Supabase

### Supabase para Claude, ChatGPT e agentes de IA

Sua conta Supabase por linguagem natural: rode SQL, aplique migrations, gerencie tabelas, storage, edge functions e branches, e consulte a documentação. Conecte com sua conta em um clique, sem chave nem token.

- 📊 **29 ferramentas**
- ✏️ **Leitura e escrita**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `Supabase` e **URL** `https://api.mcp.ai/p_supabase`.

### Cursor

[➕ Instalar Supabase no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=supabase&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9zdXBhYmFzZSJ9)

### VS Code (Copilot Chat)

[➕ Instalar Supabase no VS Code](vscode:mcp/install?name=supabase&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_supabase%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_supabase
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Liste as tabelas do meu projeto Supabase
Rode um SELECT na tabela de usuários e me mostre os 10 últimos
Crie uma migration que adiciona a coluna status na tabela pedidos
```

---

## 29 ferramentas disponíveis

| Tool | Descrição |
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

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Grátis.

---

## Privacidade & LGPD

- **Sub-processadores**: Supabase, o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_supabase`.


---

## Suporte

- 📧 [supabase@mcp.ai](mailto:supabase@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/supabase-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_supabase` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
