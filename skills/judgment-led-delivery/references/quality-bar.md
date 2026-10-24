# Quality review — on-demand reference

Use for significant, complex, or risky changes. **Select applicable dimensions**; do not run every check for every task. Respect the project's established standards and tools.

| Dimension | Evidence to look for |
| --- | --- |
| User outcome | The **requested** journey works end to end, not just in a mockup; simulated invites do not prove sending, access control, or persistence |
| Product cohesion | Fits existing navigation, terminology, workflows, and design patterns |
| Interaction states | Relevant loading, empty, errors, retry, permissions, and recovery are usable |
| Accessibility | Semantic controls, names, keyboard/focus, errors, readable hierarchy, reduced motion where relevant |
| Responsive/visual | Real target viewports, spacing, typography, overflow, tap targets, and consistent components |
| Data/privacy/security | Correct authorization, safe handling of personal data, secrets, data integrity, abuse and recovery risks |
| Engineering | Scoped changes, appropriate regression tests, maintainability, observability, and failure behavior |
| Performance | Relevant baseline/measurements where available; no invented performance claims |
| Content | Clear text, supported locales, edge-case lengths, useful feedback |
| Finish | The complete flow and details feel intentional, not merely code-complete |

## Triage findings

- **Observed defect:** Describe what fails, the supporting evidence, and its effect on users.
- **Credible risk:** Explain the failure mode, likely impact, and what remains unproven. Do not describe a possibility as a reproduced bug.
- **Verification gap:** Identify untested behavior and why it matters. Account for other evidence, including manual browser checks; lack of a particular test harness alone does not establish a defect.
- **Optional improvement:** Keep lower-impact polish or extra coverage separate from blockers.

Prioritize by user impact, likelihood, scope, and recoverability—not by checklist omissions. Raise the urgency of missing evidence when the affected behavior is security-sensitive, high-risk, or central to the promised feature.

## Verification process

1. Select the relevant criteria and risks before calling work done.
2. Inspect or run the product if the environment allows it; use tests to support behavioral claims. A screenshot alone does not prove functionality. Distinguish current-run checks from earlier reported results, code-inspection inferences, and unavailable evidence; don't imply a previous test ran again.
3. Mark observations as **verified**, **failed**, **unverified**, or **not applicable**. Never say a check ran when it did not.
4. Select **one primary verdict**: **ready for review** when evidence supports the requested work and outstanding checks are nonblocking; **not ready** for a confirmed blocker; or **verification incomplete** when essential behavior or a material risk still lacks evidence. State why each significant gap does or does not prevent a confident review. Do not combine verdicts. Limitations are "accepted" only when the user has actually accepted them.
5. Separate blockers from optional fast follows. A broken core path cannot be deferred as polish.

These conclusions assess quality, not authorization to merge, release, publish, or deploy—even to a private preview.
