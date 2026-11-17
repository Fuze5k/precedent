# Precedent

**The decision register your team and its AI agents check before they act.**

Precedent is a Forge app for Jira (Codegeist 2026 entry). Teams record decisions - what was decided, why,
which alternatives were rejected, what it replaced - right on the Jira work item. People see the decisions
that apply to their work, with the reason each one applies. AI agents get the same memory: a Rovo agent
inside Atlassian, and MCP tools for Claude Code, Cursor and other MCP clients. Agents can only propose
decisions; people accept them.

This repository holds the open-source parts:

- [`skills/precedent/SKILL.md`](skills/precedent/SKILL.md) - an agent skill (MIT) that teaches coding agents
  to check decisions before they implement and to propose new ones instead of silently making them.
- [`docs/mcp-setup.md`](docs/mcp-setup.md) - how to connect an MCP client to Precedent.
- [`PRIVACY.md`](PRIVACY.md) - privacy policy of the Precedent app.

Questions or problems: [open an issue](https://github.com/Fuze5k/precedent/issues).
