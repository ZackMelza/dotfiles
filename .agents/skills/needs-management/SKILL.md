---
name: needs-management
description: Create and maintain the Linux-builds needs backlog when the owner requests requirements, bug tracking, proposed improvements or future development planning.
---

# Needs Management

Read AGENTS.md before working.

## Purpose

The needs directory records work that is required, requested
or proposed but has not necessarily been implemented.

A documented need is not automatic authorization to implement it.

## Workflow

1. Inspect the existing needs directory.
2. Check for an existing entry before creating a duplicate.
3. Allocate the next unused N-XXX identifier.
4. Use docs/templates/NEED.template.md.
5. Describe the problem before proposing a solution.
6. Define measurable acceptance criteria.
7. Link related needs or implementation reports when relevant.

## Status Values

- Proposed
- Approved
- In Progress
- Blocked
- Completed
- Cancelled

New suggestions default to Proposed.

Only the repository owner can authorize a proposed need or
establish its priority.

## Restrictions

Do not invent requirements.

Do not independently change project priorities.

Do not silently expand the scope of approved work.

When discovering unrelated improvements during development,
mention them to the owner rather than implementing them.

When an approved need is completed, link its implementation
report and update the status as authorized.
