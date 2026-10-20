# Rivora Cursor plugin

Cursor plugin for implementing from a published Rivora feature-pack handoff.

Connecting opens Rivora in the browser. The person signs in with their Rivora account, and Cursor keeps the access token from that login. The plugin does not ask for a pasted token.

## Configure

| Variable | Required | Value |
| --- | --- | --- |
| `RIVORA_MCP_URL` | No | Defaults to `https://api.rivoraconnect.com.au/mcp/` |

The URL must include the trailing slash.

## Connect

If you already added Rivora to Cursor with a workspace token, remove that entry from your MCP settings first. An older token entry stops the sign-in from starting.

1. Reload Cursor after installing the plugin (**Developer: Reload Window**).
2. Open Customize and choose Connect on the Rivora MCP server.
3. Sign in on the Rivora page with the same account used in Rivora. Choose the workspace when more than one is available.
4. Return to Cursor. The Rivora server should show as connected.

The access token follows that person and the workspace they confirmed. `handoff:read` covers published handoffs they can read. `proposal:write` is present only when Rivora allows that person to submit a proposal.

## Use

In a repository you are allowed to change, type `/implement-from-handoff`, or type `@` and attach that skill. You can also name a Rivora feature, handoff id, or version pin. The agent should state the version pin and content hash, then edit the open repository.

Useful checks:

1. List the Rivora MCP tools.
2. Find the latest handoff for a feature and product.
3. Read that handoff and report its version pin, content hash, and open questions.

## Install

Install **Rivora** from the Cursor Marketplace. To try it before it is listed, use a local install.

## Local install

Cursor loads unpackaged plugins from the user plugins directory. From a clone of this repository, copy the folder. A link that points outside that directory is skipped.

```powershell
$dest = Join-Path $env:USERPROFILE ".cursor\plugins\local\rivora"
New-Item -ItemType Directory -Force (Split-Path $dest) | Out-Null
if (Test-Path $dest) { Remove-Item -LiteralPath $dest -Recurse -Force }
Copy-Item -LiteralPath "$PWD\cursor-rivora" -Destination $dest -Recurse
```

## Layout

```text
cursor-rivora/
  .cursor-plugin/plugin.json
  assets/logo.png
  mcp.json
  skills/implement-from-handoff/SKILL.md
  README.md
```

The MCP server name is `rivora`. The public OAuth client id is `rivora-cursor`. Tools are `find_handoffs`, `get_handoff`, `get_handoff_section`, `list_handoff_citations`, `search_handoff_evidence`, `list_handoff_open_questions`, and `propose_handoff_changes`.
