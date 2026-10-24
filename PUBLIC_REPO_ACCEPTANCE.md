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

Overall: **ACCEPTED**

| ID | Status | Evidence / note |
| --- | --- | --- |
| R1 | PASS | README and START_HERE provide direct purpose, audience, requirements and first-run path |
| R2 | PASS | DEV proof: cross-platform smoke executes the real `run.py --once --no-open` generation path on Linux/macOS/Windows; OS start wrappers are thin direct launchers into the same runtime path |
| R3 | PASS | START_HERE describes all six generated HTML pages and the visible success state |
| R4 | PASS | one-shot and watch workflows match `run.py`; stop for watch mode is documented as Ctrl+C |
| R5 | PASS | START_HERE now gives an explicit first-failure path through `scripts/smoke_check.py` and explains the first useful error |
| R6 | PASS | read-only boundary, private infrastructure warning and SECURITY.md are aligned |
| R7 | PASS | existing valid proof reused: unit CI and cross-platform smoke passed before the documentation-only troubleshooting update |
| R8 | PASS | final source/doc check: Python 3.10+ claim matches Ruff target; six-page names, start commands, watch behavior, platform support and generated outputs match implementation |

Open P0/P1: none.

Acceptance note: host-specific deep signal availability is intentionally outside this DEV acceptance. The suite is accepted when unavailable signals degrade to unknown/N/A rather than crashing, as defined by the product contract.

## 2. tof_local_knowledge

Overall: **ACCEPTED**

| ID | Status | Evidence / note |
| --- | --- | --- |
| R1 | PASS | README and START_HERE explain purpose, audience, prerequisites, safe demo-first use and first action in English/German |
| R2 | PASS | Fresh-clone default now uses the bundled synthetic `./demo/source_1`; existing public demo evidence proves the real scan → extract → search → grounded-answer chain; current CI validates `.env.example` + `compose.full.yml` configuration |
| R3 | PASS | START_HERE and demo docs define visible success: healthy services, indexed demo source, search evidence, citations and explicit no-evidence behavior |
| R4 | PASS | setup/up/check/status/ui/down commands and OS wrappers match the Python CLI; Windows wrappers now accept `py` or `python` and stop on the first failed startup step |
| R5 | PASS | beginner guide and START_HERE point to `doctor`; runtime commands report Docker, source-root and port readiness without requiring internal architecture knowledge |
| R6 | PASS | source mount is read-only; private-data/screenshot rules are documented; all Docker-published ports now default to loopback through `BIND_HOST=127.0.0.1`; a test guards the local-bind default |
| R7 | PASS | current main CI run 42 passed: dependency install, compile, Docker Compose config validation and pytest; QA fallback, local bind and fresh-demo defaults are covered |
| R8 | PASS | final source/doc check aligns Python 3.11+, UI port 8785, service ports, Postgres 55432 host default, optional Ollama/Open WebUI profiles, demo source path and runtime commands |

Open P0/P1: none.

Acceptance fixes made during review:
- CI test import/dependency path corrected
- Docker service exposure changed from all host interfaces to loopback by default
- fresh-clone source changed from a host-specific `/srv/...` path to bundled synthetic demo data
- Windows launchers made tolerant of `py`/ `python` and fail-fast
- stale pre-merge branch instruction removed from the demo guide

Acceptance note: deep runtime behavior on every possible user host is outside DEV acceptance. The existing neutral local demo evidence is reused; current configuration/test proof covers the changes made during this acceptance.

## 3. tof_local_builder

Overall: **ACCEPTED**

| ID | Status | Evidence / note |
| --- | --- | --- |
| R1 | PASS | README and START_HERE explain product purpose, audience, requirements, first-run wizard, Open WebUI and source/sandbox model |
| R2 | PASS | placeholder/invalid source paths force the first-run wizard before Docker start; tests cover placeholder rejection and completed setup; CI validates `compose.yml` with a real source path override |
| R3 | PASS | START_HERE defines visible success: services up, WebUI reachable, repo bridge reachable, selected model present and source/sandbox configured |
| R4 | PASS | setup/up/check/status/ui/down paths match the Python CLI; Windows wrappers accept `py` or `python` and fail-fast |
| R5 | PASS | START_HERE points to `doctor`; doctor reports Docker, source, sandbox and port readiness without requiring internal architecture knowledge |
| R6 | PASS | normal source is mounted read-only, writes are sandbox-only, published service ports default to loopback, repo-bridge tests reject parent/symlink escapes and source writes; advanced host-reader mode is separately warned and documented |
| R7 | PASS | current main CI run 6 passed: compile, Compose config validation and pytest including repo-bridge boundary and first-run wizard contract tests |
| R8 | PASS | browser-open preference is now actually executed by `up`; stale command text was corrected; docs, wizard, runtime commands, source/sandbox paths and ports now match implementation |

Open P0/P1: none.

Acceptance fixes made during review:
- clarified containerized read-only bridge as normal/default path and host-reader as advanced mode
- added repo-specific security guidance and path-boundary tests
- corrected CI test loading
- made `BUILDER_OPEN_BROWSER=1` actually open Open WebUI or print the manual URL
- added first-run wizard contract tests and Compose config validation
- made Windows launchers tolerant of `py` / `python` and fail-fast
- corrected stale docs claiming `up.sh` wrapped a different start mechanism

Acceptance note: actual model download time and hardware performance vary by user system and are outside DEV acceptance. The accepted contract is that the guided setup, boundary enforcement and diagnostics behave as documented.

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
