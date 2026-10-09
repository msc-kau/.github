# Security Policy

Security is a core requirement for Microsoft KAU Club technical projects.

This document defines the general security expectations for repositories maintained by the Technical Committee.

Project-specific repositories may include additional security requirements when necessary.

---

## Security Principles

Our technical projects should follow these principles:

- Apply least privilege.
- Protect secrets and credentials.
- Keep sensitive data private.
- Validate access on the backend, not only in the UI.
- Separate development and production when appropriate.
- Avoid unnecessary collection of personal data.
- Treat security as part of development, not as a final step.

---

# Reporting a Security Issue

Security vulnerabilities should be reported **privately**.

Do not open a public GitHub Issue when the report contains:

- Exposed credentials
- Authentication vulnerabilities
- Authorization bypasses
- Private user information
- Database access problems
- Production infrastructure details
- Sensitive internal configuration
- Other information that could increase security risk

Instead, contact the Technical Committee leadership through the club's approved internal communication channel.

Include only the information required to understand and reproduce the issue.

---

## What to Include in a Security Report

A useful report should contain:

```text
Affected project:
Affected feature:
Description:
Steps to reproduce:
Expected behavior:
Actual behavior:
Potential impact:
Screenshots / logs if safe:
```

Do not include passwords, access tokens, or unnecessary personal information in the report.

---

# Secrets and Credentials

Never commit or publish secrets.

Examples include:

```text
Passwords
API keys
Access tokens
Refresh tokens
Database credentials
SMTP credentials
Private certificates
Production credentials
Supabase service role keys
Cloud provider secrets
Webhook secrets
Signing secrets
```

Secrets must never be placed directly inside source code.

---

## Environment Files

Files such as:

```text
.env
.env.local
.env.development.local
.env.production
.env.production.local
```

must not be committed when they contain real credentials.

Repositories should normally include these files in `.gitignore`.

---

## `.env.example`

Projects that require environment variables should provide:

```text
.env.example
```

Example:

```text
SUPABASE_URL=
SUPABASE_ANON_KEY=
EMAIL_API_KEY=
```

Only variable names and safe placeholder values belong in this file.

Never place real secrets inside `.env.example`.

---

# Public vs Secret Configuration

Not every configuration value is automatically secret.

Developers should understand the difference between:

```text
Public configuration
```

and:

```text
Privileged credentials
```

If there is uncertainty about whether a value is safe to expose, ask the project lead before committing it.

---

# Service Credentials

Privileged credentials must never be exposed to client-side applications.

For example:

```text
SUPABASE_SERVICE_ROLE_KEY
```

must never be included in frontend code, browser bundles, public repositories, or client-accessible environment variables.

Privileged operations should run only in trusted backend environments.

---

# If a Secret Is Accidentally Exposed

If a credential is accidentally committed, uploaded, shared publicly, or exposed in logs:

1. Inform the project lead immediately.
2. Revoke or rotate the credential.
3. Stop using the exposed credential.
4. Replace it in affected environments.
5. Review where it may have been exposed.
6. Review logs or activity when necessary.
7. Document the incident if it affected an important system.

Deleting the Git commit alone is **not sufficient**.

Once a secret has been exposed, assume that it may have been compromised.

---

# Access Control

Access should follow the principle of **least privilege**.

Members should receive only the permissions required for their responsibilities.

Examples:

```text
Organization Owner
→ Limited to trusted technical / organizational leadership

Repository Admin / Maintain
→ Project maintainers when required

Repository Write
→ Active developers

Repository Read
→ Members who only need repository visibility
```

Administrative access should remain limited.

---

## Access Changes

Permissions should be reviewed when:

- A member joins a project
- A member changes responsibilities
- A project is completed
- A member leaves the committee
- Technical leadership changes
- A handover occurs

Access that is no longer required should be removed.

---

# Authentication

Authentication verifies who a user is.

Authentication systems should follow the security requirements of the specific project.

For privileged administrative systems, stronger authentication such as MFA should be used when available and appropriate.

Authentication should not automatically imply authorization.

---

# Authorization

Authorization determines what an authenticated user is allowed to do.

Applications must enforce authorization in trusted backend or database layers.

Do not rely only on:

```text
Hidden buttons
Disabled UI controls
Frontend route checks
Client-side role checks
```

A user may bypass frontend controls and communicate directly with an API.

Sensitive actions must therefore be protected by backend authorization.

---

# Database Security

Database access should follow project-specific access-control rules.

Developers should consider:

- Row Level Security
- Roles and permissions
- Foreign key constraints
- Unique constraints
- Input validation
- Sensitive column exposure
- Public API access
- Administrative access

Public clients should never receive unrestricted database access.

---

# Row Level Security

When Row Level Security is used, policies should be treated as part of the project's security model.

Developers should test both:

```text
Allowed actions
```

and:

```text
Forbidden actions
```

A feature is not considered secure only because the expected request succeeds.

Tests should also verify that unauthorized requests fail.

---

# Personal and Sensitive Data

Collect only the data required for the feature.

Sensitive information may include:

- Student IDs
- University emails
- Personal email addresses
- Phone numbers
- Authentication information
- Attendance records
- Administrative records
- Internal club information

Do not expose sensitive records through public APIs or pages without a valid reason.

---

## Data Minimization

Before collecting new information, ask:

```text
Do we actually need this data?
```

If the answer is no, do not collect it.

Reducing unnecessary data reduces security and privacy risks.

---

# Logs

Logs must not contain unnecessary sensitive information.

Avoid logging:

```text
Passwords
Access tokens
Authentication secrets
Full credentials
Private keys
Sensitive personal information
```

Use logs for debugging and monitoring without turning them into another source of sensitive data.

---

# File Uploads

Projects that support file uploads should validate:

- File type
- File size
- Access permissions
- Storage location
- Public/private visibility

Do not trust a file only because its filename appears valid.

---

# Public and Private Storage

Not all files should use the same visibility rules.

Examples:

```text
Public:
Event cover images
Public member photos
Published media
```

Possible private content:

```text
Certificates
Internal documents
Private exports
Sensitive attachments
```

Private files should use appropriate access controls or signed access when required.

---

# Production Environment

Production systems require additional care.

Avoid:

- Testing destructive operations directly in production
- Using production credentials during ordinary development
- Manually changing production data without documentation
- Sharing production access unnecessarily

When practical, development and production environments should remain separated.

---

# Database Migrations

Database changes should follow the project's migration workflow.

Before applying a migration, consider:

- Existing production data
- Constraints
- Indexes
- RLS policies
- Backward compatibility
- Deployment order
- Failure scenarios

Avoid undocumented manual production schema changes.

---

# Dependencies

Before adding a dependency, consider:

- Is it actively maintained?
- Do we actually need it?
- Does it introduce security risk?
- Can the existing stack solve the problem?
- Does it significantly increase complexity?

Security-sensitive dependencies should receive additional review.

---

# Input Validation

Never assume user input is trustworthy.

Validate data where appropriate for:

- Type
- Format
- Length
- Allowed values
- Required fields
- Permissions

Frontend validation improves user experience.

Backend validation provides security.

Use both when appropriate.

---

# Error Messages

Errors should provide enough information to help users without exposing sensitive technical details.

Avoid exposing:

```text
Database credentials
Internal stack traces
Private paths
Secret values
Internal infrastructure configuration
```

Detailed diagnostics should remain in appropriate internal logs.

---

# Pull Request Security Review

Changes affecting the following areas deserve additional security attention:

- Authentication
- Authorization
- Permissions
- Database
- RLS
- File uploads
- User data
- Admin dashboards
- Environment variables
- External integrations
- Email delivery
- Production infrastructure

Reviewers should verify both functionality and access restrictions.

---

# Security Testing

Depending on the project, security testing may include:

```text
Authentication tests
Authorization tests
RLS tests
Permission tests
Input validation tests
Public API tests
File access tests
Secret scanning
Dependency checks
```

Always test important forbidden actions, not only successful actions.

---

# Third-Party Services

Before integrating a new external service, consider:

- What data is sent to the service?
- What permissions does it require?
- Where are its credentials stored?
- Does it introduce vendor lock-in?
- What happens if the service becomes unavailable?
- Can access be revoked cleanly during handover?

Only grant the permissions the integration actually requires.

---

# Technical Handover

Security is part of project handover.

During leadership or team transitions, review:

- GitHub access
- Repository permissions
- Hosting access
- Database access
- Domain access
- Email provider access
- Cloud services
- Environment secrets
- Deployment systems
- Analytics access
- Other third-party integrations

Old access should be removed when it is no longer required.

---

# Security Incidents

For important incidents:

```text
Detect
  ↓
Contain
  ↓
Revoke / Rotate
  ↓
Investigate
  ↓
Recover
  ↓
Document
  ↓
Prevent recurrence
```

The response should match the severity of the incident.

Not every small bug requires a formal incident process.

---

# Responsible Security Culture

Security reviews should focus on improving the system, not blaming individuals.

If someone accidentally exposes a secret or introduces a vulnerability, the priority is:

1. Protect the system.
2. Correct the issue.
3. Understand why it happened.
4. Improve the process to reduce recurrence.

---

# Questions

If you are uncertain about:

- A credential
- A permission
- Public/private data
- A database policy
- A production operation
- A new integration

ask the project lead or Technical Committee leadership before proceeding.

It is better to ask before exposing sensitive information.

---

<div align="center">

**Microsoft KAU Club — Technical Committee**

Security is part of every technical decision.

</div>
