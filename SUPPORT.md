# Support

This document explains where to go when you need help with Microsoft KAU Club technical projects.

GitHub is primarily used for software development, technical collaboration, and repository-related work.

Not every question or request should become a GitHub Issue.

---

## Development Questions

If you are a Technical Committee member and need help with development:

1. Read the repository `README.md`.
2. Check the available documentation.
3. Review relevant Pull Requests and Issues.
4. Check the assigned Notion task.
5. Ask the project lead or the appropriate technical team if you are still blocked.

Examples:

```text
How do I run this project locally?

Which environment variables do I need?

Where is the database migration documentation?

Which branch should I use?

Who should review my Pull Request?
```

These are development questions and should normally be handled through the project documentation or internal technical communication channels.

---

## Bug Reports

Use a GitHub Issue when you have found a reproducible technical problem in a repository.

Examples:

```text
The registration form crashes after submission.

The mobile navigation does not open.

An event page returns an unexpected error.

A backend endpoint returns incorrect data.
```

Before creating a Bug Report:

- Check whether the issue already exists.
- Confirm the problem can be reproduced.
- Provide clear steps.
- Remove any sensitive information.
- Include screenshots or safe logs when useful.

Use the repository's Bug Report template when available.

---

## Feature Requests

GitHub Issues may be used for repository-specific technical feature discussions.

A good feature request explains:

```text
What problem exists?

Who is affected?

What is the proposed solution?

Are there simpler alternatives?
```

Large club initiatives should normally begin through the club's internal planning process before being treated as development work.

Examples:

```text
Good GitHub Feature Request:
Add filtering to the events page.

Internal Planning First:
Build a complete student portal for the club.
```

The second example affects product scope, planning, resources, and multiple systems, so it should first be discussed through the appropriate internal process.

---

## Technical Tasks

Small repository-specific technical tasks may be tracked through GitHub when appropriate.

Examples:

- Refactoring
- Technical debt
- Dependency updates
- Repository configuration
- Test improvements
- Performance improvements
- Documentation fixes

Project-level planning and deadlines should remain in the club's project-management system.

---

## Project Management

GitHub is not the primary project-management platform for the club.

Use the internal project-management system for:

- Project planning
- Task assignment
- Deadlines
- Meetings
- Roadmaps
- Team responsibilities
- Project status
- Decisions and follow-up

GitHub should remain focused on:

- Source code
- Pull Requests
- Code reviews
- Technical Issues
- Repository documentation

---

## Security Issues

Do **not** create a public Issue for sensitive security problems.

Examples:

- Exposed credentials
- Authentication bypass
- Authorization problems
- Private student data exposure
- Database access vulnerabilities
- Production secrets
- Internal infrastructure details

Follow the instructions in:

```text
SECURITY.md
```

Security issues should be reported privately to the Technical Committee leadership through an approved internal communication channel.

---

## Exposed Credentials

If you find:

```text
API key
Password
Access token
Database credential
Private certificate
Service role key
Production secret
```

do not repost the value in a public Issue, Pull Request, comment, screenshot, or chat.

Report it privately and allow the responsible maintainer to revoke or rotate it.

---

## Pull Request Help

If you need help with a Pull Request:

1. Read `CONTRIBUTING.md`.
2. Complete the Pull Request template.
3. Explain what is blocking you.
4. Request review from the appropriate team or maintainer.

Do not open a separate Issue only to ask:

```text
Can someone review my PR?
```

Use the Pull Request itself or the team's internal communication channel.

---

## Repository Access

If you believe you need access to a repository, team, or technical service:

Contact the appropriate project lead or Technical Committee leadership.

Access should only be granted when required for your responsibilities.

Do not request broader permissions than necessary.

---

## Environment and Setup Problems

If a project does not run locally:

Before asking for help, check:

- Repository README
- Setup instructions
- Required runtime versions
- Package installation
- Environment variables
- Database setup
- Migration status
- Existing Issues

When asking for help, include:

```text
Operating system:
Runtime version:
Relevant command:
Error message:
What you already tried:
```

Remove secrets before sharing logs or screenshots.

---

## Production Problems

If a production system is unavailable or behaving incorrectly:

Do not make random production changes before understanding the issue.

Report:

```text
Affected system:
Time discovered:
Observed behavior:
Affected users:
Recent known changes:
```

Escalate important production problems to the responsible project lead or Technical Committee leadership.

Security-related production problems should follow the security reporting process.

---

## General Club Questions

GitHub Issues should not be used for general club questions such as:

- Membership
- Event schedules
- Registration questions
- Attendance questions
- General announcements
- Partnership inquiries
- Social media inquiries

Use the club's official communication channels for these topics.

---

## Suggestions for the Club

Ideas that affect the entire club or require organizational approval should go through the club's normal internal planning or idea-review process.

GitHub is mainly used after an idea has become a technical project or repository-specific feature.

---

## Before Asking for Help

A good support request shows that you have already tried to understand the problem.

Before asking:

1. Read the relevant documentation.
2. Search existing Issues.
3. Check recent Pull Requests.
4. Reproduce the problem when possible.
5. Collect useful non-sensitive information.
6. Ask the correct team or maintainer.

Do not stay blocked silently.

If you have tried reasonable steps and are still stuck, ask for help early.

---

## What Not to Share

Never include these in a support request:

```text
Passwords
API keys
Access tokens
Private certificates
Database passwords
Production secrets
Private student information
Full .env files
Sensitive internal credentials
```

When sharing logs, remove any sensitive values first.

---

## Quick Guide

| Situation | Where to Go |
| --- | --- |
| Bug in a repository | GitHub Issue |
| Small technical improvement | GitHub Issue |
| Code review | Pull Request |
| Development question | Project docs / technical team |
| Task or deadline | Notion |
| Project planning | Notion |
| Security vulnerability | Private security reporting |
| Exposed credential | Private security reporting |
| Repository access | Project lead / Technical Committee |
| General club question | Official club communication channels |

---

## Need Help Deciding?

If you are unsure where a request belongs, ask the project lead or Technical Committee leadership before creating a public Issue.

The goal is to keep GitHub organized while making it easy for contributors to get the support they need.

---

<div align="center">

**Microsoft KAU Club — Technical Committee**

Ask clearly. Share safely. Use the right channel.

</div>
