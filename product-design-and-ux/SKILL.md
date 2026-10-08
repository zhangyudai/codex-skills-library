---
name: product-design-and-ux
description: >-
  Reusable frontend product-design and UX planning. Use when organizing frontend
  requirements, information architecture, page and task flows, state and recovery models,
  interface contracts, interaction tradeoffs, acceptance criteria, or engineering UX
  handoffs. Use before visual styling when behavior is not yet confirmed. Do not use for
  color, typography, visual polish, frontend implementation, tests, builds, deployment,
  Git, backend work, or unrelated requests.
license: MIT
---

# Product Design and UX

Turn validated evidence and chosen scope into observable behavior people can complete and recover from. Design the interaction, not the brand, pixels, CSS, component implementation, or a particular tool.

## Local Reusable Frontend Policy

This installation is shared across projects and uses the following user-approved routing:

- Trigger when the user asks to organize frontend requirements, decide which pages are needed, map how users complete a task, enumerate UI states, define interaction behavior, or write frontend acceptance criteria.
- For a broad "design or redesign the frontend" request, use this Skill first and hand confirmed behavior to `ui-ux-pro-max` for visual direction.
- Do not trigger for a purely visual request with already-confirmed behavior; route that work to `ui-ux-pro-max`.
- Do not trigger for routine frontend coding, API wiring, state management, tests, builds, deployment, Git operations, copy-only edits, or non-visual bug fixes.
- Produce reviewable requirements and behavior artifacts before production UI changes. Do not implement frontend code unless the user explicitly asks to proceed after reviewing the result.
- Preserve approved scope and repository constraints; missing product decisions must be recorded instead of silently invented.

## Entry Check

Confirm the approved scope, outcome, users or roles, evidence links, constraints, measurable experience goals, and open product decisions. Record missing inputs rather than inventing them.

- Need stakeholder evidence, validation, or raw research? Use [product-discovery](../product-discovery/SKILL.md).
- Need prioritization, scope, or why a feature is being built? Use [product-methodology](../product-methodology/SKILL.md).
- Need WCAG, ARIA, native semantics, or accessibility testing depth? Use [web-accessibility](../web-accessibility/SKILL.md).
- Need an approved interaction contract translated into a software specification and delivery gates? Use [spec-driven-development](../spec-driven-development/SKILL.md).
- Need to design an AI-assisted, generated, predictive, recommendatory, or tool-using interaction? Read [AI interaction and uncertainty](references/ai-interaction-and-uncertainty.md) and use [the AI interaction contract](templates/ai-interaction-contract.md) alongside the general contract. Route model evaluation and observability design to [agent-evals-and-observability](../agent-evals-and-observability/SKILL.md), governance to [ai-governance](../ai-governance/SKILL.md), runtime authority to [agent-production-operations](../agent-production-operations/SKILL.md), product measurement to [product-analytics-and-measurement](../product-analytics-and-measurement/SKILL.md), accessibility to [web-accessibility](../web-accessibility/SKILL.md), and cost/value decisions to [ai-operating-economics](../ai-operating-economics/SKILL.md).
- Need a person to delegate to an agent they use outside the product, then inspect or resume the work across apps? Read [external agent interactions](references/external-agent-interactions.md) and fill [the external agent handoff](templates/external-agent-handoff.md) alongside the AI interaction and task-flow contracts. Do not assume the product hosts that agent or can see its private conversation.

## Workflow

1. Trace each outcome and design decision to evidence with `templates/outcomes-to-design.md`. Optional personas or jobs must change a decision and cite evidence; do not create decorative demographics.
2. Establish information architecture from goals, content objects, terminology, permissions, findability, and service context. Read `references/information-architecture.md`.
3. Define consequential labels, instructions, status, errors, and completion content; review the task's memory, choice, switching, interruption, and recovery demands. Use heuristics to generate testable questions, not verdicts. Read `references/content-and-cognitive-demand.md`.
4. Model important tasks across every participating role, including recipient-side work after a handoff. Stop at the intended user outcome, not merely submission, delivery, or an intermediate status. Include decisions, alternatives, interruption, re-entry, cancellation, recovery, irreversible actions, side effects, permission changes, and completion evidence. Read `references/task-flows-and-state-models.md` and use `templates/task-flow-state-model.md`.
5. Inventory only states forced by the flow, data, permissions, connectivity, and risk. Record risky omissions. Use `templates/screen-state-inventory.md`.
6. Write framework-neutral contracts for content, controls, accessible interaction requirements, actions, transitions, persistence, permissions, responsive/reflow behavior, telemetry, and open decisions. Read `references/interface-contracts-and-responsive-behavior.md` and use `templates/interface-contract.md`.
7. Treat patterns as hypotheses. Compare alternatives, tradeoffs, evidence, and disconfirming conditions with `references/interaction-pattern-selection.md`.
8. Plan or synthesize only authorized usability work. Read `references/usability-testing-and-privacy.md`; use `templates/usability-study.md`. Never invent participants, consent, observations, quotes, or results.
9. Produce an engineering handoff with observable acceptance evidence, dependencies, owners, gates, and deployed-boundary verification. Read `references/engineering-handoff.md`; use `templates/engineering-handoff.md`. Hand approved behavior to [spec-driven-development](../spec-driven-development/SKILL.md).

## Load On Demand

| Need | Load |
|---|---|
| Scope boundary, traceability, or adjacent-skill routing | `references/boundaries-and-traceability.md` |
| Goals, labels, navigation, findability, permissions | `references/information-architecture.md` |
| Plain-language content, heuristic review, cognitive demand | `references/content-and-cognitive-demand.md` |
| Task paths, state applicability, recovery, side effects | `references/task-flows-and-state-models.md` |
| Interaction contract or inclusive responsive behavior | `references/interface-contracts-and-responsive-behavior.md` |
| Pattern alternatives and decision evidence | `references/interaction-pattern-selection.md` |
| Usability protocol, synthesis, consent, or privacy | `references/usability-testing-and-privacy.md` |
| Handoff, acceptance criteria, or deployed verification | `references/engineering-handoff.md` |
| AI uncertainty, grounding, human control, feedback, or model-change acceptance | `references/ai-interaction-and-uncertainty.md` |
| A person delegates work to their own agent outside the product and returns across app boundaries | `references/external-agent-interactions.md`; `templates/external-agent-handoff.md` |
| Methodology self-check with synthetic fixtures | `references/scenario-probes.md` |
| Source authority, status, and examples | `references/source-index.md` |

## Guardrails

- Accessibility is designed throughout, but WCAG/ARIA/native-semantics and testing depth remain with `web-accessibility`.
- Specify behavior under relevant width, zoom/reflow, text expansion/localization, orientation, input modes, reduced motion, degraded connectivity, interruption, and re-entry. Do not use device breakpoints as the model.
- Use synthetic fixtures such as `sample-user@example.test` and `INV-DEMO-042`; never request real credentials, payments, financial access, or secrets for an unsafe prototype.
- A finding from usability work is bounded evidence, not accessibility conformance, population prevalence, analytics, or outcome proof.
- AI output, confidence, explanation, citation, or user feedback is not proof of correctness by itself. Record the evidence boundary and route model-quality and statistical questions to the owning specialist.

## Completion

Stop when every in-scope behavior has traceable evidence, an applicable state/recovery model, observable acceptance criteria, and either a resolved decision or an owner and resolution gate. Report limitations and untested risks rather than filling gaps with assumptions.
