# Report: Repository Audit and Migration Plan

- Date: 2026-09-30
- Related need: None
- Status: Completed

## Objective

Document the completed Phase 00 audit of three existing Linux repositories
and record the owner's approved Phase 02 migration decisions without
performing any migration.

## Scope and Affected Files

- Reviewed the existing `ROADMAP.md`, `docs/architecture.md`, governance,
  report and needs workflows, and repository file list.
- Recorded the audit and migration plan in
  [`docs/repository-audit.md`](../docs/repository-audit.md).
- Updated [`ROADMAP.md`](../ROADMAP.md) to reflect completed Phase 00 and
  Phase 01 milestones. Phase 02 tasks remain unstarted.
- Documented this work in `reports/2026-09-30-repository-audit.md`.

No source repository, Linux configuration or installer was changed or run.

## Implementation

The audit covers `ZackMelza/hyprland`, `ZackMelza/i3-configs` and
`ZackMelza/dwm-build`. Their roles and decisions are recorded in the
[audit and migration plan](../docs/repository-audit.md). The JaKooLit-based
Hyprland repository remains a preset, separate from the planned independent
Hyprland build. i3 and DWM are independent window-manager components.

Major findings from the manual repository audit are the JaKooLit repository's
profile architecture, generated `active/` state, unresolved GPL/upstream
attribution and PAM/faillock and `--force` installer concerns; i3's
Mint/Cinnamon/X11 orientation and hard-coded `/home/zack` paths; and DWM's
existing MIT/X Consortium notice, bootstrap and uninstall asymmetry, SDDM
protection needs, string/eval execution, and stale `SECURITY.md` CI claims.
The manual scans found no obvious credentials or secrets in the three source
repositories. DWM does contain the owner's public contact email in `SECURITY.md`.

The approved destinations are `configs/window-managers/i3/`,
`configs/presets/jakoolit/` and `configs/window-managers/dwm/`, in that order.
i3 is the smallest import and will validate the new structure first. Preserve
meaningful JaKooLit history and DWM history; i3 has one source commit and
does not require full history preservation. Preserve each working component
before extracting shared code. JaKooLit provenance and GPL attribution still
need to be finalized during migration, while DWM's existing MIT/X Consortium
notice has been reviewed and must be preserved. Identified safety issues and
runtime compatibility remain migration gates rather than completed remediation.

## Verification

| Test / Command | Result | Notes |
|---|---|---|
| Read `AGENTS.md`, both relevant skills, `ROADMAP.md`, `docs/architecture.md` and the report template | Completed | Confirmed governance, component boundaries and report requirements. |
| `rg --files --hidden -g '!.git' -g '!**/.git/**'` | Completed | Reviewed the current Linux-builds file list. |
| `ls -d /home/zack/projects/*` | Completed | No local checkout of the three source repositories was found there. |
| GitHub page fetches for the three source repositories | Unavailable | The web tool returned cache misses; no independent source scan was performed. |
| `git status --short` before edits | Passed | Working tree was clean. |
| `git diff --check` after edits | Passed | No whitespace errors in the tracked roadmap diff. |
| `git status --short` after edits | Reviewed | Only `ROADMAP.md` and the two new audit documents appeared. |
| Local Markdown link and new-file whitespace checks | Passed | All seven local links resolved; new documents had no trailing whitespace. |
| Import, install, uninstall and live-system tests | Not run | Phase 02 has not started; these actions were outside the documentation task. |

## Known Issues and Limitations

The repository-specific findings above are based on the manual source-repository
audit performed during this review. Codex could not independently re-fetch the
three source repositories while generating this report, so it did not perform
a second independent scan.

Runtime compatibility has not yet been verified across the intended
distributions and environments. JaKooLit upstream provenance and GPL
attribution must be finalized during migration. DWM licensing was reviewed and
its existing MIT/X Consortium notice must be preserved. No obvious credentials
or secrets were found during the manual scans, but a final migration-time
review should still be performed before import.

The identified installer and safety issues remain unresolved and will be
addressed during Phase 02. Completing Phase 00 documents those issues; it does
not claim they have been fixed.

## Follow-up Work

Begin Phase 02 in the approved order: i3, JaKooLit preset, then DWM. For each
source, record a revision, verify copied content and history as applicable,
reconfirm licensing and sensitive-data findings
and complete the safety work before running installation or removal code.
Omarchy and Zsh reorganization also remains unstarted.

## Owner Decisions Required

No further decision is needed to record this audit and plan. The owner retains
authority over execution timing, history-affecting imports, live-system
changes and any later archiving or deletion of source repositories.
