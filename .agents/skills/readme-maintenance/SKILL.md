---
name: readme-maintenance
description: Create, review and update Linux-builds README files when project functionality, installation, usage, compatibility or repository structure changes.
---

# README Maintenance

Read the repository's AGENTS.md before working.

## Workflow

1. Inspect the relevant implementation and existing documentation.
2. Identify the intended audience and purpose of the README.
3. Follow docs/templates/README.template.md for project READMEs.
4. Preserve useful existing documentation.
5. Use clear Markdown and practical examples.
6. Verify relative links and referenced paths.
7. Report anything that could not be verified.

## Requirements

Every maintained project should document:

- Purpose and current development status.
- Supported or tested environments.
- Dependencies and requirements.
- Installation and configuration.
- Usage examples.
- Verification instructions.
- Known limitations.
- Origin and credits, where applicable.

For the root README, prioritize repository introduction,
architecture, navigation and project links.

## Portability

Explicitly distinguish between intended and tested compatibility.

Do not assume that a configuration works on every distribution,
window manager or display server.

Document environment-specific behaviour where relevant.

## Restrictions

Do not invent features, compatibility or successful tests.

Do not modify unrelated project documentation.

Do not execute destructive installation commands merely to
validate documentation.
