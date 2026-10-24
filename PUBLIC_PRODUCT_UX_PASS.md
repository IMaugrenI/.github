# Public Product UX Pass

Finite UX pass for the four runnable public ToF product repositories.

## Rules

This pass is intentionally limited to five checks per product.

- U1 — ToF visual language: calm dark/obsidian base, warm gold accents, restrained surfaces, clear hierarchy
- U2 — Human language: normal user-facing copy avoids developer/runtime/API vocabulary where plain language works
- U3 — Clear next action: a first-time user can see what to do next without understanding the internal architecture
- U4 — Technical depth is secondary: diagnostics, paths, endpoints, logs and implementation terms stay behind an advanced/details layer where possible
- U5 — Existing behavior remains intact: no product-contract expansion; current CI/smoke proof remains green after the UX changes

Exit rule:

- U1–U5 = PASS
- no UX-blocking P0/P1
- product UX status = UX PASS V1 COMPLETE

No additional UX requirements are added to this pass unless a real P0/P1 usability or safety defect is found.

---

## tof_local_builder

Overall: **UX PASS V1 COMPLETE**

| ID | Status | Evidence |
| --- | --- | --- |
| U1 | PASS | Control UI now follows the ToF Systems obsidian/gold visual language |
| U2 | PASS | Primary copy now speaks about project, workspace, AI model, readiness and problems rather than repo bridge/runtime/endpoint/sandbox terminology |
| U3 | PASS | One recommended next action plus a three-step choose → start → check flow |
| U4 | PASS | project-connection/model details and technical activity are collapsed into secondary sections |
| U5 | PASS | current main CI run 8 passed after the human-language UX pass |

## tof_local_knowledge

Overall: **UX PASS IN FINAL CHECK**

| ID | Status | Evidence |
| --- | --- | --- |
| U1 | PASS | Main UI now uses ToF dark/gold styling with a warm optional light mode |
| U2 | PASS | Main experience is framed as asking/searching your documents; API/runtime/grounded-answer terminology is removed from normal copy |
| U3 | PASS | The primary action is asking a question; direct document search is the secondary task |
| U4 | PASS | setup, system controls, technical docs and log are grouped under “Setup & technical details” |
| U5 | PENDING | visual redesign passed in run 43; a final metadata-only human-language cleanup triggered CI run 44, currently running |

## local_case_organizer

Overall: **UX PASS V1 COMPLETE**

| ID | Status | Evidence |
| --- | --- | --- |
| U1 | PASS | Organizer now uses the ToF Systems dark/gold visual language and dark-first presentation |
| U2 | PASS | visible workflow/table language translates internal field/process names into user-facing document/case language |
| U3 | PASS | six-step flow: add documents → bring files in → review → timeline → people/organizations → handoff |
| U4 | PASS | paths, logs and folder/diagnostic actions are moved into “More options & technical details” |
| U5 | PASS | current main CI run 9 passed after the UX changes |

## tof_container_pulse

Overall: **UX PASS V1 COMPLETE**

| ID | Status | Evidence |
| --- | --- | --- |
| U1 | PASS | all six templates moved from neon/cyber styling to ToF obsidian/gold and warm light mode |
| U2 | PASS | primary copy now describes what is running, what needs attention and what the user can look at; collector/CLI/auto-fix language was removed from the normal surface |
| U3 | PASS | page headings and status wording prioritize attention/recommendation rather than implementation detail |
| U4 | PASS | remaining technical values are domain data (container names, ports, measurements); platform badges are humanized |
| U5 | PASS | current main CI run 80 and cross-platform Pulse Suite smoke run 18 both passed after the UX changes |

Open UX-blocking P0/P1: none.
