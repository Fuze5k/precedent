# Precedent - privacy policy

Last updated: 22 November 2026.

Precedent is a Forge app for Jira Cloud. It runs entirely on Atlassian's Forge platform ("Runs on Atlassian").

**What the app stores.** The decisions people and agents record: title, statement, rationale, rejected
alternatives, scope (projects, components, labels), links to work items and goals, status, dates, and a short
change history. The only personal data it stores is **Atlassian account IDs**: the author of a decision, the
person who accepted it, the people named as its deciders, and the person behind each history entry. It stores
no names, email addresses or avatars; Jira shows those from the account ID when a page is displayed. It stores
app settings chosen by a site admin (no personal data). It writes a small property on Jira work items (decision
ids and counts, no personal data) and, if the admin allows it, a short comment when a decision is accepted.

**Personal data reporting.** Once a week the app reports the account IDs it stores to Atlassian through the
Forge personal data reporting API, as Atlassian's user privacy guidelines require. When Atlassian answers that an
account has been closed, the app replaces that account ID with the marker `closed-account` in every decision
and history entry; the decision itself stays readable, and the screens show "Closed account" in that place.
The app keeps no other data about a person, so nothing else needs updating when an account changes.

**Where.** In Forge storage and in Jira, on Atlassian's infrastructure, inside the customer's site. The app
sends no data to servers outside Atlassian, uses no third-party services and no external analytics. The
developer does not copy customer data into any other system.

**What it reads.** Jira work items, comments and projects the user is allowed to see, and Teamwork Graph
relationships (goals and pull requests linked to a work item), always within the permissions of the user or,
for MCP clients that cannot act as the user, after an explicit permission check for that user.

**Who sees it.** Users of the same Jira site, limited to decisions in projects they can browse.

**Deletion.** Account IDs of closed Atlassian accounts are erased as described above. Decisions can be removed by
uninstalling the app; Atlassian deletes the app's Forge storage according to its Forge data retention rules. Jira
comments and work item properties stay in Jira like any other Jira data and can be deleted there.

**Contact.** [Open an issue](https://github.com/Fuze5k/precedent/issues) in this repository.
