---
name: report-writing
description: Document substantial completed or partially completed development work in Linux-builds, including changes, technical decisions, tests and outstanding issues.
---

# Report Writing

Read AGENTS.md before working.

## When to use

Use for substantial implementation tasks or when the owner
explicitly requests a development report.

Minor documentation corrections do not automatically require
a separate report.

## Workflow

1. Inspect the actual changes and relevant task requirements.
2. Use docs/templates/REPORT.template.md.
3. Create the report under reports/.
4. Name it YYYY-MM-DD-short-description.md.
5. Reference related needs when applicable.
6. Record verification results accurately.

## Required Information

- Objective and approved scope.
- Summary of modifications.
- Relevant files and directories.
- Important implementation decisions.
- Tests performed and their actual results.
- Tests not performed and why.
- Remaining limitations or problems.
- Decisions requiring owner approval.

## Restrictions

Never fabricate test results or claim unverified success.

Clearly distinguish completed, partial and blocked work.

Do not rewrite historical reports to conceal failures.

Creating a report does not authorize commits or pushes.
