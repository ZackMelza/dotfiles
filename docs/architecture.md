
# Linux-builds — Architecture

**Status:** Proposed
**Version:** 0.1

## 1. Vision

Linux-builds aims to provide a modular and portable personal
Linux environment.

The objective is to preserve a consistent user experience
across multiple Linux distributions, window managers and
hardware configurations.

The distribution provides the operating system.
The window manager handles window management.
Shared components provide the personal environment.

## 2. Design Principles

1. Portability over distribution-specific assumptions.
2. Modularity over duplicated configurations.
3. Shared behaviour with environment-specific implementations.
4. Reproducible installation and restoration.
5. Human-directed development.
6. Clear documentation for every maintained component.

Portability is a design objective, not a guarantee that every
component works identically on every platform.

## 3. Component Architecture

### Shared Components

Common configurations and utilities intended for reuse
across different environments.

Examples:
- Shared shell configuration (a future goal for Zsh).
- Shared scripts and utilities.
- Keybinding conventions.
- Common application preferences.

The existing `zsh/` files are personal configurations. `.zshrc`
contains Omarchy-specific setup and distribution-specific paths;
`starship.toml` includes a machine-specific home path. Their portability
has not been verified. Extracting a reusable Zsh component is future work.

### Window Managers

Each window manager maintains an independent implementation.

Planned components:
- Hyprland (personal build, Wayland).
- i3 (X11).
- DWM (X11).

Additional window managers may be introduced later.

These components should follow common workspace and
keybinding conventions wherever technically possible.

### Desktop Shell

Quickshell is the intended foundation for a reusable
personal desktop interface.

Potential responsibilities:
- Workspace indicators.
- System information.
- Status bar and widgets.
- Notifications and other desktop elements.

Window-manager-specific integrations must be isolated where
possible.

Quickshell functionality and compatibility must be tested
separately for each target environment.

### Existing Configuration Presets

Existing configurations are maintained separately from
independent personal builds.

- Omarchy: existing Omarchy customizations.
- Jakoolit: customizations based on Jakoolit's configuration.

Presets must not be treated as the source of truth for
independent window-manager configurations.

### Distribution Support

Distribution-specific modules will eventually manage
differences such as:

- Package names and package managers.
- Required dependencies.
- System paths and services.
- Installation requirements.

Initial intended distributions:
- Arch Linux.
- Debian.
- Fedora.

Support must be documented according to actual testing.

## 4. Profiles

Profiles define combinations of reusable components.

Examples:

Arch + Hyprland + Quickshell
Debian + i3 + Quickshell
Fedora + Hyprland + Quickshell

Profiles should reference reusable components instead of
maintaining unnecessary duplicate configurations.

These examples represent architectural targets, not
currently verified working installations.

## 5. Consistent User Experience

Linux-builds should aim to preserve:

- Familiar workspace behaviour.
- Common keybinding intentions.
- Consistent visual identity.
- Shared scripts and utilities.
- Predictable configuration management.

For example, switching to workspace 1 should follow the
same user-facing keybinding convention.

The actual command may differ between Hyprland, i3 and DWM.

Functionality that depends on compositor-specific features,
animations or display-server capabilities may not be portable.

## 6. Proposed Repository Organization

configs/
    shared/
    window-managers/
        hyprland/
        i3/
        dwm/
    desktop-shells/
        quickshell/
    presets/
        omarchy/
        jakoolit/
    distributions/
        arch/
        debian/
        fedora/

profiles/
projects/
labs/
docs/
reports/
needs/

This is the target structure.

Existing files must not be moved simply to match this
proposal without an approved migration plan.

## 7. Development Approach

1. Establish governance and documentation.
2. Audit existing repositories and configurations.
3. Migrate existing projects without unnecessary rewrites.
4. Identify reusable components.
5. Establish common conventions.
6. Build independent window-manager configurations.
7. Develop and integrate Quickshell.
8. Introduce profiles and distribution-specific installation.
9. Test supported combinations individually.

## 8. Architectural Changes

Significant changes to this architecture require approval
from the repository owner.

Agents may propose improvements but must not independently
redefine the project's direction.
