# Contributing to Microsoft KAU Technical Projects

Thank you for contributing to Microsoft KAU Club technical projects.

This guide defines the general development workflow followed by the Technical Committee.

Individual repositories may include additional project-specific instructions, but these guidelines represent the default way we work across the organization.

---

## Before You Start

Before writing code, make sure you understand the task you are working on.

You should:

1. Check that the task is assigned to you.
2. Read the repository `README.md`.
3. Review any relevant documentation.
4. Understand the expected result.
5. Check whether another member is already working on the same area.
6. Make sure you have the required repository access.

If the task is unclear, ask the project lead before making a large change.

---

## Our Workflow

Our general development workflow is:

```text
Notion Task
    ↓
Create Branch
    ↓
Development
    ↓
Local Testing
    ↓
Push Changes
    ↓
Pull Request
    ↓
Code Review
    ↓
Requested Changes if needed
    ↓
Approval
    ↓
Merge
    ↓
Task Completed
```

---

## Notion vs GitHub

We intentionally separate project management from software development.

### Notion is used for

- Projects
- Tasks
- Deadlines
- Planning
- Meetings
- Roadmaps
- Team responsibilities
- Progress tracking

### GitHub is used for

- Source code
- Branches
- Commits
- Pull Requests
- Code reviews
- Technical Issues
- Repository documentation

Do not duplicate the entire project-management workflow inside GitHub.

A Notion task may contain a link to the related Pull Request or GitHub Issue when useful.

---

# Starting a Task

Before starting development:

1. Open the assigned task in Notion.
2. Read the requirements carefully.
3. Confirm the expected output.
4. Check the relevant repository.
5. Pull the latest changes.
6. Create a dedicated branch.

Do not start large unplanned changes without discussing them first.

---

## Update Your Local Repository

Before creating a branch, make sure your local repository is up to date.

Example:

```bash
git checkout main
git pull
```

Then create your branch.

---

# Branch Naming

Use short, descriptive branch names.

The general format is:

```text
type/short-description
```

---

## Features

Use:

```text
feat/
```

Example:

```text
feat/event-registration
feat/members-page
feat/news-dashboard
```

---

## Bug Fixes

Use:

```text
fix/
```

Example:

```text
fix/mobile-navbar
fix/login-redirect
fix/event-date-validation
```

---

## Documentation

Use:

```text
docs/
```

Example:

```text
docs/backend-setup
docs/deployment-guide
```

---

## Refactoring

Use:

```text
refactor/
```

Example:

```text
refactor/auth-service
refactor/event-query
```

---

## Testing

Use:

```text
test/
```

Example:

```text
test/registration-validation
```

---

## Other Maintenance Work

Use:

```text
chore/
```

Example:

```text
chore/update-dependencies
chore/configure-eslint
```

---

# Creating a Branch

Example:

```bash
git checkout -b feat/event-registration
```

Or using modern Git:

```bash
git switch -c feat/event-registration
```

Work only on your assigned branch unless instructed otherwise.

---

# Commit Messages

Commit messages should clearly explain what changed.

Use the general format:

```text
type: short description
```

Examples:

```text
feat: add event registration form
fix: prevent duplicate event registration
docs: update local development setup
refactor: simplify authentication middleware
test: add registration validation tests
chore: update project dependencies
```

---

## Recommended Commit Types

| Type | Used For |
| --- | --- |
| `feat` | New functionality |
| `fix` | Bug fixes |
| `docs` | Documentation |
| `refactor` | Internal code restructuring |
| `test` | Tests |
| `chore` | Maintenance and configuration |

---

## Avoid Unclear Commits

Do not use messages such as:

```text
update
changes
fix
done
final
final2
working
test
new
```

A developer reading the Git history should understand what happened without opening every commit.

---

# Keep Commits Focused

Whenever possible, keep commits focused on one logical change.

Good:

```text
feat: add event registration validation
```

Then:

```text
test: add registration validation tests
```

Less useful:

```text
update everything
```

---

# Push Your Branch

When your work is ready to share:

```bash
git push -u origin feat/event-registration
```

After the first push, future updates usually only require:

```bash
git push
```

---

# Pull Requests

When your implementation is ready for review, open a Pull Request.

The Pull Request should explain:

- What changed
- Why the change was needed
- How it was tested
- Any important technical decisions
- Any security considerations
- Screenshots for UI changes when relevant

---

## Pull Request Title

Use a clear title.

Good examples:

```text
Add event registration flow
Fix duplicate attendance check-in
Update backend setup documentation
```

Avoid:

```text
Update
Changes
New PR
Fix stuff
```

---

# Keep Pull Requests Focused

A Pull Request should preferably solve one main problem.

Avoid combining:

```text
New event system
+
Navbar redesign
+
Database refactor
+
Documentation rewrite
```

inside one PR unless they are directly related.

Smaller Pull Requests are easier to:

- Review
- Test
- Understand
- Revert if necessary

---

# Before Opening a Pull Request

Check the following:

- The project runs locally.
- Your feature works as expected.
- Related functionality still works.
- Tests pass if the repository has tests.
- Build and lint checks pass if configured.
- No credentials were added.
- No unnecessary files were committed.
- Documentation was updated if required.

---

# Code Review

Code review is a normal part of development.

It is not a personal criticism of the developer.

The goal is to improve:

- Correctness
- Security
- Maintainability
- Readability
- Consistency
- Testing
- Documentation

---

## Reviewers Should Check

### Correctness

Does the implementation solve the requested problem?

### Security

Does the change introduce unnecessary access or expose sensitive data?

### Maintainability

Can another developer understand and maintain the code later?

### Simplicity

Is the solution more complicated than necessary?

### Testing

Has the change been properly tested?

### Impact

Could the change break another part of the project?

### Documentation

Does this change require documentation updates?

---

# Review Feedback

Feedback should remain:

- Technical
- Clear
- Respectful
- Constructive

Examples:

Good:

```text
Could we validate this input on the backend as well?
Frontend validation can be bypassed.
```

Good:

```text
This query is used in multiple places.
Would it be better to move it into the existing service?
```

Avoid:

```text
This is bad.
```

or:

```text
Why did you do this?
```

Explain the technical reason behind feedback.

---

# Requested Changes

If the reviewer requests changes:

1. Update the same branch.
2. Commit the changes.
3. Push again.

The Pull Request updates automatically.

Example:

```bash
git add .
git commit -m "fix: address registration review feedback"
git push
```

You do not need to create a new Pull Request.

---

# Approval and Merge

A Pull Request should be merged only when:

- Required reviews are complete.
- Requested changes have been addressed.
- Tests pass.
- The change is ready for the target branch.

Do not merge your own Pull Request when a review is required unless explicitly authorized.

---

# Main Branch

The `main` branch represents the stable project state unless the repository defines another workflow.

Avoid working directly on:

```text
main
```

for normal development.

Instead:

```text
main
  ↑
Pull Request
  ↑
feature branch
```

---

# Security Rules

Never commit:

```text
.env
.env.local
.env.production
Passwords
API keys
Access tokens
Database credentials
Supabase service role keys
SMTP credentials
Private certificates
Production secrets
```

---

## Environment Variables

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

Only placeholders belong in `.env.example`.

Never place real secrets inside it.

---

# If You Accidentally Commit a Secret

Immediately:

1. Inform the project lead.
2. Revoke or rotate the credential.
3. Stop using the exposed credential.
4. Review where it may have been exposed.
5. Replace the credential in affected environments.

Deleting the commit is not enough.

Once a secret has been published, treat it as compromised.

---

# Sensitive Data

Do not expose private information such as:

- Student IDs
- Personal phone numbers
- Private email addresses
- Authentication information
- Internal administrative data
- Private club records

Public APIs should return only the data required by the public feature.

---

# Dependencies

Before adding a new dependency, consider:

- Do we actually need it?
- Can the existing stack solve the problem?
- Is the library maintained?
- Does it introduce unnecessary complexity?
- Does it affect security?
- Does it significantly increase bundle or application size?

Avoid adding libraries only to solve very small problems.

---

# Testing

Testing requirements depend on the project.

At minimum, developers should manually test the feature they changed.

When automated tests exist, run them before opening a Pull Request.

Possible checks include:

```text
Unit Tests
Integration Tests
Database Tests
RLS / Permission Tests
Build
Lint
Type Checking
Manual QA
```

Follow the repository-specific instructions.

---

# UI Changes

For user-interface changes, test:

- Desktop
- Mobile
- Responsive behavior
- Loading states
- Empty states
- Error states

Add screenshots or recordings to the Pull Request when useful.

---

# Backend Changes

For backend work, consider:

- Authentication
- Authorization
- Validation
- Database constraints
- RLS policies
- Error handling
- Logging
- Rate limiting when necessary
- Sensitive data exposure
- Migration compatibility

Do not rely only on frontend checks for backend security.

---

# Database Changes

Database changes should normally be made using the migration workflow defined by the project.

Avoid making undocumented production database changes manually.

Before applying a migration, consider:

- Existing data
- Foreign keys
- Unique constraints
- Indexes
- RLS
- Rollback / correction strategy
- Production compatibility

---

# Documentation

Update documentation when your change affects:

- Setup instructions
- Environment variables
- Database schema
- Architecture
- APIs
- Permissions
- Deployment
- Operational procedures

Small internal changes usually do not require additional documentation.

---

# GitHub Issues

GitHub Issues are primarily used for technical matters such as:

- Bugs
- Technical debt
- Refactoring
- Repository-specific improvements
- Technical investigations

General team tasks and planning belong in Notion unless the project defines otherwise.

---

# Large Technical Decisions

Do not make major architectural changes without discussing them first.

Examples:

- Changing the database platform
- Replacing the authentication system
- Introducing a new framework
- Changing deployment providers
- Major database redesign
- Changing the permission model
- Adding a major third-party service

Discuss these changes with the project lead before implementation.

---

# Definition of Done

A task is not considered complete only because the code was written.

Depending on the task, completion may require:

```text
Implementation complete
Testing complete
Pull Request reviewed
Changes merged
Documentation updated
Notion task updated
No known critical issue remaining
```

---

# After Merge

After your Pull Request is merged:

1. Confirm the change works in the intended environment.
2. Update the related Notion task.
3. Document important decisions if required.
4. Remove the old local branch when appropriate.

Example:

```bash
git checkout main
git pull
git branch -d feat/event-registration
```

---

# Getting Help

If you are blocked:

1. Read the task again.
2. Check the repository README.
3. Review relevant documentation.
4. Search existing Issues and Pull Requests.
5. Ask the appropriate project lead or team member.

Do not stay blocked for several days without communicating.

---

# Final Principle

The goal is not only to make code work.

We want technical projects that are:

- Secure
- Understandable
- Maintainable
- Reviewable
- Documented
- Transferable to future teams

Technical work should remain usable after the original developer leaves the project.

---

<div align="center">

**Microsoft KAU Club — Technical Committee**

Build carefully. Review thoughtfully. Document what matters.

</div>
