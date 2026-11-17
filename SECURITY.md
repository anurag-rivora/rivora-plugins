# Security policy

This policy covers the Rivora plugins in this repository (Claude Code, Cursor, and the
ChatGPT and Codex package), the `implement-from-handoff` skill, the MCP settings and the links.
It also covers the Rivora MCP server and its sign-in at `https://api.rivoraconnect.com.au`.

## Report a problem privately

Please report security problems privately, and keep them out of public issues.

1. Open the **Security** tab of this repository and choose **Report a vulnerability**. Only the
   maintainers can see the report.
2. If that does not work for you, email anurag@rivoraconnect.com.au with
   "Security: rivora-plugins" in the subject.

Tell us what you found, how to reproduce it, and what someone could do with it. We aim to reply
within five working days and to tell you what we will do and when.

## What to report

- A plugin file that points an AI tool anywhere other than `https://api.rivoraconnect.com.au/mcp/`,
  or that runs commands, installs hooks or grants tool permissions.
- Text in the skill, or content served by Rivora, that could lead an AI tool to run commands,
  change files outside the open repository, reach other hosts, or send code, secrets or
  personal data anywhere without the person asking for it.
- A way to read a handoff, a draft or a workspace that your Rivora sign-in should not reach, or
  to change an approved output through the MCP tools.
- A link that points somewhere unsafe or has been taken over.
- Anything in this repository or its history that should not be public.

## What the plugins install

- One MCP server entry, `rivora`, at `https://api.rivoraconnect.com.au/mcp/`. You sign in on the
  Rivora page in your browser, and your AI tool keeps the access token. No token or secret is
  stored in these files.
- One skill, `implement-from-handoff`. It gives your AI tool no extra permissions: your tool's
  own permission settings still apply.
- No hooks, commands, scripts, dependencies or settings files.

To end a connection, open Rivora, go to Settings → Integrations → Agent access → Connected
agents and press Revoke.

## Supported versions

Only the latest version on the `main` branch is supported, and fixes land there.
