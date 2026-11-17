# Connect an MCP client to Precedent

1. A site or org admin of the Jira site where Precedent is installed turns on its tools:
   admin.atlassian.com > Apps > Sites > *your site* > Connected apps > Precedent > View app details >
   Tools > **Enable tools**.
2. Add the server to your agent. For Claude Code:

   ```bash
   claude mcp add --transport http precedent https://mcp.atlassian.com/forge/d8345358-6715-4a8d-945d-ae1e7a5ecb15
   ```

   Then run `/mcp` in Claude Code, pick `precedent`, choose Authenticate and sign in to Atlassian with the
   account you use on that site.
3. Copy [`skills/precedent/`](../skills/precedent/) into your agent's skills folder (Claude Code:
   `.claude/skills/precedent/` in your repository, or `~/.claude/skills/precedent/`).

Try it: "Before you change anything, check with precedent whether moving order history to DynamoDB is OK."

The agent can only *propose* decisions; people accept them in Jira.
