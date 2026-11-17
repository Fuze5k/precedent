---
name: precedent
description: Before implementing, refactoring, migrating or choosing a tool in a project tracked in Jira, check the team's recorded decisions through the Precedent MCP server, and propose new lasting decisions instead of silently making them.
license: MIT
compatibility: Needs the Precedent MCP server (https://mcp.atlassian.com/forge/d8345358-6715-4a8d-945d-ae1e7a5ecb15) connected in the agent, and the Precedent app installed on the Jira site.
---
# Precedent: respect what the team already decided

Teams record decisions in Precedent (a Jira app). This skill makes a coding agent check those
decisions before it acts, so it does not reintroduce an option the team rejected, and so lasting
choices it makes become visible to the team.

## When to use

- Before starting work on a Jira work item (a key such as `ENG-42` in the task, branch name or
  commit message).
- Before choosing or replacing a library, database, service, API style, data location, vendor or
  process step.
- Before a migration, a refactor across modules, or a change to a public interface.
- When the user asks "what did we decide about ...".

## Steps

1. If a work item key is known, call `decisions-for-work-item` with it. Treat every decision under
   `inForce` as a hard constraint for the task. Mention them in your plan.
2. Write your plan in one to five sentences and call `check-plan` with it (and the work item key).
   - `likely-conflict`: stop. Tell the user which decision conflicts (id, title, why the option was
     rejected). Ask whether to change the plan or to propose replacing the decision. Do not proceed
     with the conflicting approach on your own.
   - `review-needed`: read each listed decision (`get-decision` if needed) and adjust the plan so it
     fits all of them.
   - `no-precedent-found`: continue.
3. If, while working, you make a choice that will outlive the task (a new dependency, a schema
   convention, an API rule), call `find-decisions` to check it is new, then `propose-decision` with
   a clear title, statement, rationale, rejected alternatives and the work item key. Tell the user it
   is waiting for review in Jira. Never present a proposal as accepted.
4. In the pull request description, list the decision ids you followed (for example
   "Follows DEC-12, DEC-31; proposes DEC-40").

## Tool reference

| Tool | Use |
|---|---|
| `find-decisions(query, project?, includeClosed?)` | Search by topic |
| `get-decision(decisionId)` | Full record of one decision |
| `decisions-for-work-item(issueKey)` | What applies to a work item and why |
| `check-plan(plan, issueKey?)` | Verdict + warnings + decisions to respect |
| `propose-decision(title, statement, rationale?, rejectedAlternatives?, tags?, issueKey?, project?, supersedes?, reviewBy?)` | Record a proposal for people to review |
| `link-decision(decisionId, issueKey)` | Make an existing decision show on another work item |
| `decision-overview(project?)` | What is waiting for review or due for another look |

Statuses: `accepted` binds the team; `proposed` does not bind anyone yet; `superseded`, `reversed`
and `rejected` are history.

Some MCP clients show the tools with an environment suffix, for example `check-plan_development`;
they are the same tools.
