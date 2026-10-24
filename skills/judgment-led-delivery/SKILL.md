---
name: judgment-led-delivery
description: >-
  Use for planning, adding, implementing, fixing, or reviewing user-facing
  app features, from small frontend interactions (copy buttons, forms, feedback,
  navigation) to larger workflows (sharing, invitations, onboarding, permissions).
  Connect product intent, existing design and code patterns, working behavior,
  accessibility, and proportionate verification alongside specialist skills.
  Clarify only consequential missing decisions; keep straightforward fixes
  lightweight. Skip unrelated CI, infrastructure, and formatting-only tasks.
license: MIT
---

# Judgment-led delivery

Apply **Decide → Build → Refine → Verify** at the depth warranted by the task. The user's intent and the existing project take priority over a generic process.

## Operating rules

- Read the request, prior decisions, repository instructions, and relevant code before proposing new scope or architecture. Respect existing design systems and tests.
- Distinguish **evidence**, **user decisions**, and **assumptions**. Do not fabricate research, metrics, test results, screenshots, approval, or working integrations.
- Do the requested kind of work: **review, planning, or skill evaluation only** means no implementation; a **prototype** may use clearly labeled mocks when requested or agreed; an **implementation** must deliver real functionality within the authorized scope. Never silently replace a requested working feature with a simulated demo.
- Keep one responsible agent by default. Do not create agents, tickets, documents, tools, or unrelated refactors just to follow a process.
- Use relevant architecture, frontend, design, and testing guidance alongside this skill. Its job is to connect specialist work to user value, a coherent experience, and justified readiness—not to duplicate their steps or require a separate coordinator.
- A request to **build** authorizes scoped changes to the identified project, not switching projects or substituting a hosted demo. Preserve unrelated files and existing uncommitted work; never discard, reset, clean, stash, or overwrite another person's changes to make the task easier. Get explicit authorization before committing, pushing, opening a PR, merging, deploying (including private previews or ChatGPT Sites), publishing, or changing audience access. A quality verdict is not permission.
- **Stop deliberately.** Finish when the requested acceptance criteria are met with proportionate evidence, or report a blocker, user-owned decision, or essential verification gap that cannot be resolved within the authorized scope. Return to an earlier stage only when new evidence reveals a material issue. Do not reopen settled decisions, endlessly refine cosmetic details, or expand scope to keep the workflow running.

## Choose depth before acting

- **Clear feature:** implement the intended behavior, inspect the real experience, and verify.
- **Ambiguous feature or new idea:** investigate the product first; resolve only material uncertainties before committing to decisions.
- **Small bug or refactor:** diagnose, fix narrowly, and check regressions. Skip product discovery.
- **Audit or planning request:** inspect and report findings or decisions. Do not edit code unless requested.

## Clarify automatically, only when needed

No special phrase, flag, or extra skill is required **once this skill is active**.

1. **Find facts yourself.** Inspect the codebase, prior answers, docs, and accessible evidence. Do not ask the user to repeat known details or answer questions tools can resolve.
2. **Separate decisions from implementation details.** Let the user choose product goals, critical behavior, permissions, data retention, and significant trade-offs. Make conventional, low-risk, reversible implementation choices yourself and disclose consequential assumptions.
3. **Choose the lightest conversation.** If the request is clear, ask nothing. If one material decision blocks progress, ask one focused question with a suggested default and reason. **If the intended app, data model, or backend is absent, and a new app was not requested, ask which project to extend or whether a prototype is wanted; do not choose a substitute deliverable.** If multiple unresolved decisions depend on one another, automatically interview in short rounds: ask independent foundational questions first, wait for answers, then ask only questions those answers unlock. Do not dump a generic questionnaire.
4. **Know when to stop.** Once the scope, main user paths, and relevant acceptance criteria are clear enough, summarize any important decisions and continue the originally requested work. Do not require repeated confirmation, exhaustive discovery, or a formal brief. If the user requests a deeper interview, go deeper; if they say "you decide," choose within their delegated scope.
5. **Respect blockers and boundaries.** If an important choice cannot be inferred safely and the user has not delegated it, don't silently invent it. If implementation is not requested, end with the plan. Never use product critique as an unrequested veto; explain concerns and practical alternatives.


## 1. Decide — target a useful outcome

For meaningful new or unclear features, establish the user, problem, product fit, smallest valuable scope, and observable success. Check whether the existing experience already solves the goal. Evaluate the proposed change against the strongest practical alternative, including keeping or simplifying existing behavior. Name the distinct user need each option serves and any capability it removes; sharing a context or destination does not make two actions redundant. Base the recommendation on observed evidence, not just fewer controls, less code, or an assumed majority preference. If an assumption determines the winner, state the recommendation conditionally and favor a reversible, lower-regret change when practical. Stay within the requested surface (for example, mobile versus all devices); propose broader changes separately with their own justification. Make a clear recommendation without vetoing an authorized choice or turning routine work into a research project.

For expensive or genuinely ambiguous decisions, consult [the optional decision brief](references/decision-brief.md). Do not produce a formal document by default.

## 2. Build — make a working vertical slice

- Inspect existing architecture, UI components, API/data flows, content, and tests.
- Implement the narrowest usable interaction that proves the benefit. Prefer integration in the product to static demos. If a required integration is unavailable, clarify scope before proceeding; a simulated UI may illustrate a design but does not fulfill a request for a working integration.
- Handle meaningful loading, empty, success, error, retry, permission, and recovery states as relevant.
- Keep code maintainable and changes scoped; test risky assumptions early.

## 3. Refine — check the actual experience

Assess the complete user journey, simplicity, copy, visual consistency, responsive behavior, keyboard access, screen reader names/feedback, and meaningful edge cases.

Use a runnable app, browser, or screenshots **when available**. If you cannot inspect the experience, report that limitation; do not claim the UI looks good. Iterate only on findings that matter.

## 4. Verify — state what the evidence supports

- Define proportionate acceptance criteria for the promised behavior and material edge cases.
- Run applicable existing tests, typecheck, lint, build, e2e, and UX/accessibility/security/performance checks according to risk. Distinguish **checked in this run**, **reported from a prior run**, **inferred from inspection**, and **not verified**. Credit relevant earlier evidence without presenting it as a fresh test; note its scope and any missing proof.
- Prioritize findings by evidence and likely user impact. Distinguish observed defects from plausible risks, unverified behavior, and optional coverage improvements. A missing automated test is not automatically a product defect or release blocker.
- Use [the optional quality reference](references/quality-bar.md) for larger or riskier changes, not every small patch.
- Give **one primary verdict**: **ready for review** when evidence sufficiently supports the requested work; **not ready** when a known blocker exists; **verification incomplete** when essential behavior or a material risk cannot be assessed. For significant unverified checks, state briefly why they are essential or nonblocking, based on user impact, risk, and available evidence. List nonblocking gaps separately; do not combine verdicts into “ready for review, with verification incomplete.” Mark demos and mocks clearly: simulated flows do not verify real delivery, authentication, persistence, or authorization. Do not call work ready to ship or claim limitations were accepted without the user's agreement.

Lead with the result relevant to the request: what changed for implementation, a recommendation for a product decision, prioritized findings for an audit, or the **single readiness verdict** for verification. Follow with just enough evidence, meaningful trade-offs, and material limitations to support that result; distinguish direct checks from prior reports and inspection. Include a next action or user decision **only when genuinely needed**. Do not invent risks, follow-ups, or empty sections to fill a template. Match detail and format to task complexity; keep small-task responses short.

## Behavior examples

- **Clear request:** "Add a save/unsave button using our existing favorites API." Implement and test; don't reopen product strategy.
- **Single blocker:** "Add saved stories" when persistence exists but saved-list visibility is a user decision. Ask whether saved stories need a dedicated view, with a recommendation.
- **Interdependent blockers:** "Build a collaborative story editor" when roles, sharing, and access are undefined. Investigate first, then ask product decisions in dependency order **automatically** before implementing those decisions.
- **Product trade-off:** "Simplify mobile location actions by removing Copy Address." Compare navigation and address copying as distinct needs, consider less prominent placement before removal, and do not extend mobile scope to desktop without a reason. If usage evidence is missing, qualify the recommendation instead of claiming most users prefer one action.
- **Bug:** "Fix the Save button staying disabled after an error." Fix and test recovery; no product interview.
- **Missing application:** "Add family sharing to recorded stories" in a workspace with no app, recording model, or backend. Inspect first, then ask which app to extend or whether a prototype is intended. Do not invent a deployable replacement.
- **Review only:** "Audit mobile onboarding; don't edit files." Return evidence-based findings, not code.
- **Can't verify:** If an essential interaction cannot be tested or otherwise established, return **verification incomplete** and explain why it blocks the verdict. Missing optional checks should be disclosed without blocking an otherwise supported **ready for review** verdict.

