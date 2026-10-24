# Public Repository Acceptance Tracker

Central acceptance list for the public IMaugrenI repository family.

## Acceptance rules

This list is intentionally finite.

For each repository:

- only the checks defined here are mandatory
- already proven checks are reused
- no new requirements are added during acceptance unless a real P0/P1 finding makes them necessary
- P0/P1 findings are fixed before dependent acceptance continues
- P2 findings are documented and do not block acceptance unless explicitly promoted
- once all mandatory checks are PASS or justified N/A, the repository is ACCEPTED and should be frozen until a real product change requires reopening it

Status values:

- TODO — not checked yet
- PASS — proven
- FAIL — product defect
- BLOCKED — missing environment/runtime proof
- N/A — not applicable
- FIXED — defect corrected; final proof still required

## Acceptance order

1. tof_container_pulse
2. tof_local_knowledge
3. tof_local_builder
4. local_case_organizer
5. tof-showcase
6. tof-v7-public-frame
7. tof-module-ideas
8. tof-legacy-recovery-workbench
9. tof-bridge-planning-method
10. tof-systems-website

The first four are runnable product repositories.
The remaining repositories are documentation/method or website surfaces and use a smaller acceptance scope.

---

# A. Runnable product repository checklist

Use for:

- tof_container_pulse
- tof_local_knowledge
- tof_local_builder
- local_case_organizer

Mandatory checks:

| ID | Check | Required proof |
| --- | --- | --- |
| R1 | First-visit clarity | README + START_HERE make purpose, audience, prerequisites, and first action obvious |
| R2 | Fresh start path | documented clone/install/start path works from a fresh checkout or existing CI/runtime proof demonstrates the same path |
| R3 | First success state | user can tell what successful startup/output looks like |
| R4 | Everyday operation | normal start/status/check/stop or equivalent workflow is documented and matches implementation |
| R5 | Failure/diagnostic path | obvious doctor/check/error guidance exists and does not require internal architecture knowledge |
| R6 | Safety/privacy boundary | secrets/private data/path/runtime boundaries are documented and technically enforced where applicable |
| R7 | Automated proof | relevant CI/tests/smoke checks are green; existing valid proof is reused |
| R8 | Documentation/runtime consistency | README, START_HERE, commands, supported platforms, ports and behavior do not contradict current code |

Exit rule:

- R1–R8 = PASS or justified N/A
- no open P0/P1
- then repository status = ACCEPTED

---

# B. Documentation / method repository checklist

Use for:

- tof-showcase
- tof-v7-public-frame
- tof-module-ideas
- tof-legacy-recovery-workbench when reviewed as method surface
- tof-bridge-planning-method when reviewed as method surface

Mandatory checks:

| ID | Check | Required proof |
| --- | --- | --- |
| D1 | Entry clarity | first-time reader knows whether this is runnable or documentation/method only |
| D2 | Reading/usage path | START_HERE gives a short ordered path |
| D3 | Boundary truth | planning, architecture, examples and runtime truth are clearly separated |
| D4 | Public safety | no secrets/private runtime details/private data are required or encouraged |
| D5 | Cross-repo navigation | related repos and next step are understandable and not circular/confusing |

Exit rule:

- D1–D5 = PASS or justified N/A
- no open P0/P1
- then repository status = ACCEPTED

---

# C. Website acceptance checklist

Use for tof-systems-website.

| ID | Check | Required proof |
| --- | --- | --- |
| W1 | Local start | documented local start/status/stop works |
| W2 | Navigation/content | main pages and product links are coherent |
| W3 | Responsive/basic accessibility | desktop/mobile structure and core keyboard/navigation basics are acceptable |
| W4 | Product truth | DFA/DLA copy matches current approved product state |
| W5 | Legal placeholders | missing operator/privacy/contact data remain visibly incomplete before launch |
| W6 | Staging safety | noindex remains active until explicit launch approval |
| W7 | Hosting truth | docs do not claim an undecided provider/deployment |
| W8 | Launch gate | public launch remains blocked until legal/operator/hosting items are complete |

Exit rule:

- W1–W8 = PASS or justified N/A for staging acceptance
- public launch is a separate later acceptance

---

# Current status

## 1. tof_container_pulse

Overall: IN ACCEPTANCE

| ID | Status | Evidence / note |
| --- | --- | --- |
| R1 | PASS | README and START_HERE now provide direct purpose and first-run path |
| R2 | TODO | Fresh-user path still to be accepted explicitly |
| R3 | PASS | START_HERE describes six generated HTML pages and success state |
| R4 | PASS | one-shot and watch workflows documented |
| R5 | TODO | verify failure guidance from a fresh-user perspective |
| R6 | PASS | read-only boundary and screenshot/privacy warning documented |
| R7 | PASS | CI and cross-platform smoke green on current main |
| R8 | TODO | final command/platform/doc consistency check |

Open P0/P1: none known.

## 2. tof_local_knowledge

Overall: QUEUED

R1–R8: TODO, except existing evidence may be reused during acceptance.

## 3. tof_local_builder

Overall: QUEUED

R1–R8: TODO, except existing green CI and repo-bridge boundary tests may be reused.

## 4. local_case_organizer

Overall: QUEUED

R1–R8: TODO, except existing green CI and integrity/export tests may be reused.

## 5. tof-showcase

Overall: QUEUED

D1–D5: TODO.

## 6. tof-v7-public-frame

Overall: QUEUED

D1–D5: TODO.

## 7. tof-module-ideas

Overall: QUEUED

D1–D5: TODO.

## 8. tof-legacy-recovery-workbench

Overall: QUEUED

D1–D5: TODO. Runnable-path checks are only added if we explicitly choose to accept it as a runnable tool rather than only as a method surface.

## 9. tof-bridge-planning-method

Overall: QUEUED

D1–D5: TODO. Runnable-path checks are only added if we explicitly choose to accept it as a runnable tool rather than only as a method surface.

## 10. tof-systems-website

Overall: QUEUED

W1–W8: TODO. Public launch acceptance remains separate.
