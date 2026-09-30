
# Linux-builds — Agent Instructions

## 1. Purpose

Linux-builds is a personal project for developing a modular,
portable and maintainable Linux environment.

The long-term objective is to reuse personal configurations,
scripts, desktop components and workflows across different
Linux distributions and window managers.

This is a human-directed project. AI agents are development
assistants, not autonomous project owners.

## 2. Authority

The repository owner has final authority over:

- Project direction and scope.
- Architecture and technology choices.
- Priorities and requirements.
- Repository organization.
- Git operations affecting shared history.

Agents must not independently redefine these decisions.

## 3. Working Rules

Before making changes:

1. Understand the assigned task.
2. Inspect relevant existing files.
3. Read applicable documentation and skills.
4. Propose a short plan for substantial changes.
5. Identify assumptions that materially affect the outcome.

During implementation:

- Work only within the authorized scope.
- Preserve unrelated files and existing user changes.
- Prefer simple, readable and maintainable solutions.
- Explain significant technical decisions.
- Do not silently introduce new features.
- Avoid unnecessary dependencies or abstractions.

For small, clearly authorized edits, agents may proceed without
requesting approval for every individual modification.

## 4. Operations Requiring Explicit Approval

Unless already authorized by the owner, agents must not:

- Delete existing projects or important files.
- Create commits, push, merge, rebase or rewrite Git history.
- Archive or delete GitHub repositories.
- Install or remove system packages.
- Execute privileged system modifications.
- Modify active system services.
- Introduce major architectural changes.
- Publish or expose services externally.

Read-only investigation is permitted within the assigned task.

Never expose credentials, tokens, private keys or other secrets.

## 5. Portability Principles

Linux-builds must not assume a single Linux distribution,
window manager or display server.

Separate reusable components from environment-specific code.

Examples:

- Omarchy and Jakoolit are existing configuration presets.
- Hyprland is a separate personal build.
- i3 and DWM are independent window manager builds.
- Quickshell is intended to provide reusable desktop components
  where supported by the target environment.
- Shared keybinding intentions should remain consistent, even
  when their implementation differs between window managers.

Do not replace distribution-specific functionality with
untested assumptions about portability.

## 6. Skills and Documentation

Specialized workflows are maintained under .agents/skills/.

Use the appropriate skill when performing its related task:

- readme-maintenance: Creating or updating README files.
- report-writing: Documenting completed work.
- needs-management: Recording requirements or future improvements.

Keep documentation accurate and proportional to the change.

Do not invent completed work, test results or requirements.

## 7. Task Completion

At the end of an implementation task, provide:

- A concise summary of changes.
- Important implementation decisions.
- Tests performed and their results.
- Any tests that could not be performed.
- Outstanding issues or owner decisions.

Do not commit or push changes unless explicitly requested.

Before modifying cross-platform configurations, component boundaries, window-manager integrations or installation profiles, consult docs/architecture.md
