# Microsoft KAU GitHub Configuration

This repository contains the organization-wide GitHub configuration, standards, templates, and technical guidelines for **Microsoft KAU Club**.

It is maintained by the Technical Committee and provides shared defaults and documentation for repositories across the organization.

---

## Purpose

The `.github` repository acts as the central configuration repository for the Microsoft KAU GitHub organization.

Instead of repeating the same contribution rules, security policies, and templates inside every repository, shared defaults are maintained here.

This helps keep our repositories:

- Consistent
- Secure
- Easier to maintain
- Easier for new members to understand
- Ready for future technical handover

---

## Repository Structure

```text
.github/
│
├── profile/
│   └── README.md
│
├── .github/
│   └── ISSUE_TEMPLATE/
│
├── CONTRIBUTING.md
├── PULL_REQUEST_TEMPLATE.md
├── SECURITY.md
├── SUPPORT.md
└── README.md
```

---

## What Each File Does

### `profile/README.md`

Controls the public profile displayed on the main Microsoft KAU GitHub organization page.

It provides an overview of:

- Microsoft KAU Club
- The Technical Committee
- Our development workflow
- Development principles
- Security expectations
- Technical continuity and handover

---

### `CONTRIBUTING.md`

Defines the general contribution workflow for Technical Committee members.

It includes guidelines for:

- Starting work
- Branch naming
- Commit messages
- Pull Requests
- Code review
- Testing
- Documentation

---

### `PULL_REQUEST_TEMPLATE.md`

Provides a standard template whenever a contributor opens a Pull Request.

The template helps reviewers quickly understand:

- What changed
- Why it changed
- How it was tested
- Whether security was considered
- Whether documentation needs updating

---

### `SECURITY.md`

Defines the organization's general security expectations.

It covers topics such as:

- Secrets
- API keys
- Environment variables
- Credentials
- Production access
- Sensitive data
- Reporting security issues

---

### `SUPPORT.md`

Explains where contributors and users should go when they need help.

It helps separate:

- Development questions
- Bug reports
- Feature requests
- Security issues
- General club inquiries

---

### `.github/ISSUE_TEMPLATE/`

Contains templates for creating structured GitHub Issues.

Examples may include:

```text
Bug Report
Feature Request
Technical Task
```

These templates help ensure that technical issues contain enough information before the team begins investigating them.

---

## Organization-Wide Defaults

Files stored in this repository may be used as shared defaults by other repositories in the Microsoft KAU organization.

Project repositories may define their own versions when they require project-specific rules.

For example:

```text
Organization default
CONTRIBUTING.md

        ↓

microsoft-kau-website

        ↓

Uses the organization default
unless the repository provides its own CONTRIBUTING.md
```

This allows us to maintain common standards without copying the same files into every project.

---

## Project Management vs GitHub

We intentionally separate project management from software development.

| Platform | Responsibility |
| --- | --- |
| **Notion** | Projects, tasks, planning, meetings, deadlines, roadmaps |
| **GitHub** | Code, repositories, branches, Pull Requests, reviews, technical issues |

GitHub should not become a duplicate of our project-management system.

---

## Repository-Specific Documentation

Individual projects should still maintain their own documentation.

For example:

```text
microsoft-kau-website/
├── README.md
├── .env.example
├── docs/
│   ├── architecture.md
│   ├── development.md
│   └── deployment.md
└── ...
```

Organization-wide standards belong here.

Project-specific technical information belongs in the project's repository.

---

## Security

This repository must never contain real:

```text
Passwords
API Keys
Access Tokens
Database Credentials
Production Secrets
Service Role Keys
Private Certificates
.env Files
```

Documentation should explain **where and how credentials are managed**, but must never include the credentials themselves.

---

## Maintenance

The Technical Committee should review this repository when:

- Development workflows change
- Security requirements change
- New organization-wide standards are introduced
- GitHub teams or responsibilities change
- A technical handover takes place

Outdated documentation should be updated or removed.

---

## Continuity

This repository is part of the club's technical handover system.

Future Technical Committee teams should be able to understand:

- How development is organized
- How contributors work
- What security rules apply
- How repositories should be maintained
- Where technical documentation belongs

The goal is to ensure that the club's technical systems continue beyond any individual member or leadership term.

---

<div align="center">

**Microsoft KAU Club — Technical Committee**

Organization configuration and development standards.

</div>
