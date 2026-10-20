---
name: feedback_jira_issue_description_english
description: When creating a Jira issue, write the description in English, ready for Claude Code to implement
metadata:
  type: feedback
---

When creating a Jira issue, write the description in English and make it ready for Claude Code to implement.

Include which repo and workspace to edit only if the user told me when asking to create the issue; if not told, leave it out (don't guess or ask).

**Why:** User instruction; the description is the input Claude Code works from.

**How to apply:** Every Jira issue creation — English description written as an implementable spec for Claude Code. Summary stays Thai, see [[feedback_jira_issue_thai]].
