# ToF Public UX Language

Shared user-facing language for the four runnable public ToF products.

This is a small consistency contract, not a new design system or framework.

## Core rule

Normal product surfaces explain **what the user can do and what happened**.

Implementation terms stay in technical/details areas unless they are the actual domain data the user needs.

Examples:

- project, workspace, documents, sources, handoff, connection, AI model
- not: repo bridge, runtime, endpoint, sandbox, collector, API as primary UI language

## Shared status vocabulary

Use these ideas consistently where they fit:

- **Ready / Bereit** — the user can continue
- **Check / Prüfen** — worth looking at; not necessarily broken
- **Needs attention / Braucht Aufmerksamkeit** — an important problem or signal
- **Not available / Nicht verfügbar** — information or a local component cannot currently be reached
- **Unknown / Unbekannt** — the state cannot be determined reliably

Do not turn unavailable information into a catastrophic-looking error when the rest of the product can still work.

## Shared guidance vocabulary

Preferred labels:

- **Next step / Nächster Schritt**
- **Find problems / Probleme prüfen**
- **Technical details / Technische Details**
- **Technical log / Technisches Protokoll**
- **Check again / Erneut prüfen**
- **Stop / Stoppen**

A normal error should answer:

1. what did not work?
2. what can the user do next?
3. where are the technical details if they need them?

## Trust language

Keep these boundaries visible in plain language:

- local data stays on the local machine by default
- original/source material is not silently changed where the product promises read-only behavior
- generated/output material is reviewed by the user
- Pulse observes and does not auto-fix
- Knowledge shows sources and keeps no-evidence visible
- Case Organizer is not legal advice and protects handoff integrity

## Accessibility baseline

Public product UIs should provide, where relevant:

- semantic main content
- visible keyboard focus
- a skip-to-content path for substantial pages
- labels for form controls
- live regions for changing user-facing status/results
- responsive layout
- reduced-motion behavior
- language/theme controls with understandable labels

## Product-specific domain terms

Technical-looking terms are allowed when they are the information itself.

Examples:

- container name
- port number
- CPU / memory
- file ID when traceability matters
- document/source name
- operating system
- local path inside an explicitly technical details section

The rule is not to hide useful detail. The rule is to keep implementation language from becoming a prerequisite for ordinary use.
