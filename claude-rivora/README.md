# Rivora for Claude Code

Build a feature from its approved Rivora handoff without leaving Claude Code.

Rivora Product OS turns a feature request into a reviewed feature pack. When the pack is
approved, Rivora freezes it into a version-pinned handoff. This plugin connects Claude Code to
that handoff and adds a skill that implements from it.

## Install

```bash
claude plugin marketplace add anurag-rivora/rivora-plugins
claude plugin install rivora@rivora
```

Then start Claude Code, run `/mcp`, choose **rivora** and sign in with your Rivora account.
Pick the workspace when you have more than one. No token is copied.

## Use

- `/rivora:implement-from-handoff invoice reminders` builds the named feature from its latest
  approved handoff.
- Or ask in plain words: "Find the Rivora handoff for invoice reminders and read it."
- Rivora's own prompts, "Implement a feature from Rivora" and "Review open questions for a
  feature", also appear in the `/` menu.

## What it can do

- Reads approved handoffs in the workspace you chose. Drafts never leave Rivora.
- Sends suggestions back only if you allowed it when you signed in. A person reviews each one
  on the feature pack. Nothing here changes an approved output.

## Disconnect

In Rivora, open Settings → Integrations → Agent access → Connected agents and press Revoke.
Remove the plugin with `claude plugin uninstall rivora@rivora`.

Help: https://rivoraconnect.com.au/contact · Privacy: https://rivoraconnect.com.au/privacy
