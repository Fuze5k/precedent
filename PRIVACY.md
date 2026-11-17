# Precedent - privacy policy

Last updated: 17 November 2026.

Precedent is a Forge app for Jira Cloud. It runs entirely on Atlassian's Forge platform ("Runs on Atlassian").

**What the app stores.** The decisions people and agents record: title, statement, rationale, rejected
alternatives, scope (projects, components, labels), links to work items and goals, status, dates, and a short
change history. With each decision and history entry it stores the Atlassian account ID of the person who
made the change. It stores app settings chosen by a site admin. It writes a small property on Jira work items
(decision ids and counts) and, if the admin allows it, a short comment when a decision is accepted.

**Where.** In Forge storage and in Jira, on Atlassian's infrastructure, inside the customer's site. The app
sends no data to servers outside Atlassian, uses no third-party services and no external analytics. The
developer does not copy customer data into any other system.

**What it reads.** Jira work items, comments and projects the user is allowed to see, and Teamwork Graph
relationships (goals and pull requests linked to a work item), always within the permissions of the user or,
for MCP clients that cannot act as the user, after an explicit permission check for that user.

**Who sees it.** Users of the same Jira site, limited to decisions in projects they can browse.

**Deletion.** Decisions can be removed by uninstalling the app; Atlassian deletes the app's Forge storage
according to its Forge data retention rules. Jira comments and work item properties stay in Jira like any
other Jira data and can be deleted there.

**Contact.** [Open an issue](https://github.com/Fuze5k/precedent/issues) in this repository.
