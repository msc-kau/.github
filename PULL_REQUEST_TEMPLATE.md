# Pull Request

## Summary

Provide a clear and concise summary of this change.

Explain what was added, changed, fixed, or removed.

---

## Why Is This Change Needed?

Explain the problem, requirement, or reason behind this change.

What does this Pull Request solve?

---

## Related Work

### Notion Task

Add the related Notion task if available:

```text
Notion:
```

### GitHub Issue

If this Pull Request is related to a GitHub Issue:

```text
Issue:
```

Use:

```text
Closes #123
```

when the Pull Request should automatically close an Issue after merge.

---

## Type of Change

Select the option(s) that apply:

- [ ] New feature
- [ ] Bug fix
- [ ] UI / UX change
- [ ] Backend change
- [ ] Database change
- [ ] Security change
- [ ] Refactoring
- [ ] Documentation
- [ ] Testing
- [ ] Configuration / maintenance
- [ ] Other

---

## Changes

List the important changes included in this Pull Request.

- 
- 
- 

---

## Implementation Notes

Explain any important technical decisions that reviewers should understand.

Examples:

- Architecture decisions
- Database changes
- API behavior
- New dependencies
- Permission changes
- RLS changes
- Important trade-offs

If there is nothing important to mention, write:

```text
None
```

---

## Screenshots / Recordings

For UI changes, include screenshots or recordings when useful.

### Before

Add before screenshot if relevant.

### After

Add after screenshot if relevant.

Remove this section if it does not apply.

---

# Testing

## How Was This Tested?

Explain how you verified the change.

Examples:

- Tested locally
- Tested on mobile
- Tested on desktop
- Tested authentication flow
- Tested database migration
- Tested permissions / RLS
- Added automated tests

Write the actual testing performed:

- 
- 
- 

---

## Test Checklist

- [ ] The project runs successfully
- [ ] The changed feature works as expected
- [ ] Related existing functionality still works
- [ ] Automated tests pass if available
- [ ] Build passes if configured
- [ ] Lint passes if configured
- [ ] Type checking passes if configured

---

# Security Review

Review this section carefully for backend, authentication, database, or user-data changes.

- [ ] No passwords or credentials were committed
- [ ] No API keys or tokens were committed
- [ ] No `.env` files were committed
- [ ] No sensitive user data is exposed
- [ ] Authentication was considered where required
- [ ] Authorization / permissions were considered where required
- [ ] User input is validated where required
- [ ] Backend security does not rely only on frontend checks
- [ ] Database / RLS policies were reviewed if affected

If this Pull Request has no security impact, state why:

```text
Security impact:
```

---

# Database / Backend

Complete this section if the Pull Request affects the backend or database.

## Database Changes

- [ ] No database changes
- [ ] Database schema changed
- [ ] Migration added
- [ ] Indexes changed
- [ ] Constraints changed
- [ ] RLS policies changed
- [ ] Seed / test data changed

### Migration

If a migration was added:

```text
Migration:
```

### Notes

Explain any important database considerations:

```text
None
```

---

# Environment Variables

Does this Pull Request introduce or change environment variables?

- [ ] No
- [ ] Yes

If yes:

- [ ] `.env.example` was updated
- [ ] No real secret values were committed
- [ ] Required deployment configuration was documented

New or changed variables:

```text
None
```

---

# Dependencies

Does this Pull Request add or remove dependencies?

- [ ] No
- [ ] Yes

If yes, explain why the dependency is required:

```text
None
```

---

# Documentation

Does this change require documentation updates?

- [ ] No documentation changes required
- [ ] README updated
- [ ] Technical documentation updated
- [ ] Architecture documentation updated
- [ ] Setup documentation updated
- [ ] Deployment documentation updated
- [ ] Other documentation updated

---

# Deployment Impact

Does this Pull Request affect deployment or production?

- [ ] No deployment impact
- [ ] Requires environment configuration
- [ ] Requires database migration
- [ ] Requires service configuration
- [ ] Requires manual deployment step
- [ ] Requires post-deployment verification

Notes:

```text
None
```

---

# Risks

Are there any known risks or areas reviewers should pay extra attention to?

Examples:

- Authentication
- Permissions
- Database migration
- Breaking API changes
- Performance
- Existing user data
- Deployment

```text
None
```

---

# Reviewer Notes

Anything specific you want the reviewer to check?

```text
None
```

---

# Final Checklist

Before requesting review:

- [ ] I reviewed my own changes
- [ ] The Pull Request has a clear title
- [ ] The Pull Request focuses on one main change
- [ ] The code works locally
- [ ] I tested the affected functionality
- [ ] I did not commit secrets or credentials
- [ ] I removed unnecessary debug code
- [ ] I removed unnecessary files
- [ ] I updated documentation when necessary
- [ ] I considered security implications
- [ ] I considered existing functionality
- [ ] The change is ready for review

---

## Definition of Ready for Merge

This Pull Request should only be merged when:

- Required review is complete
- Requested changes are resolved
- Required checks pass
- Security concerns are resolved
- Required documentation is updated
- The change is ready for the target environment
