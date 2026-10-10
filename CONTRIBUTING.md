# Contributing

Thank you for helping make Trupeo work better from Claude.

## What this repository holds

Only the plugin: nine skills in Markdown under `skills/`, the manifest in `.claude-plugin/plugin.json` and the connector address in `.mcp.json`. The Trupeo connector itself (the MCP server and its tools) is not in this repository, so a change to what a tool does belongs in an issue rather than a pull request.

## Welcome changes

- A skill that gets a real situation wrong: an association, a school office or a small business that works differently from what the skill assumes. Describe the situation in the pull request.
- Clearer or shorter wording, and fixes to tool names or parameters that no longer match the connector.
- A new skill for a situation the existing ones do not cover. Open an issue first, so we can agree on its scope before you write it.

## Rules for skills

- Every tool a skill names must exist in the Trupeo connector, with the parameters it uses.
- A skill never makes Claude send, delete, invite, remove or change access without the person's clear yes.
- No promise Trupeo or the organisation cannot keep (tax receipts, refunds, prices, delays).
- Plain, human wording; no marketing language.
- Repository content is written in English. Skills tell Claude to answer in the user's language.

## Before opening a pull request

```bash
claude plugin validate .
```

It must report `Validation passed`. Keep one topic per pull request.

## Review and release

A maintainer reviews every pull request. Changes reach users only after a maintainer merges them and Anthropic reviews the new version for its plugin directory, so a merged change may take a few days to appear.

By contributing, you agree that your contribution is licensed under the [MIT License](LICENSE).
