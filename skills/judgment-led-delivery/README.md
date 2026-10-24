# Judgment-led delivery

![Judgment-led delivery: Decide, Build, Refine, Verify](cover.svg)

**Build what's worth building. Know when not to.**

Judgment-led delivery guides coding agents from product decisions through implementation, UX refinement, and verification. It examines what already exists, weighs meaningful alternatives, and helps deliver a working experience backed by real evidence. Straightforward fixes stay lightweight; unresolved product decisions get clarified before implementation.

## What it does

| Step | What the agent focuses on |
| --- | --- |
| **1. Decide** | Inspect the existing experience, compare useful alternatives, and clarify consequential decisions. |
| **2. Build** | Deliver a functional slice using existing architecture, components, and data flows. |
| **3. Refine** | Review the actual experience, including interaction states, accessibility, and responsive behavior. |
| **4. Verify** | Run relevant checks and distinguish what passed, failed, or couldn't be tested. |

The steps are **proportional to the work**, not a mandatory ceremony. This skill complements frontend, architecture, and testing skills rather than replacing them.

## What makes it different

- **Questions when they matter:** Investigates first and asks only about consequential missing decisions.
- **Judgment before code:** Considers doing less, preserving distinct user needs, or keeping a working experience unchanged.
- **Respect for existing work:** Follows the project's conventions and scope without disturbing unrelated changes.
- **Evidence over confidence:** Checks relevant UX and implementation behavior, and separates observed results from assumptions and gaps.

## Install this skill

Install **only judgment-led-delivery** globally for Codex and Claude Code:

```bash
npx skills add rafa-ochoa/r8a-skills --skill judgment-led-delivery -g -a codex -a claude-code -y
```

Requires Node.js 22.20 or later. Remove `-g` for a project-only install. To install the entire collection, see the [main README](../../README.md#install-the-collection).

Already installed? Update this skill globally with `npx skills update judgment-led-delivery -g -y`.

## Use it

Open your project in Codex or Claude Code and describe the work. Your agent may select this skill automatically for relevant tasks, but automatic selection is not guaranteed. To explicitly invoke it in **Codex**, start your request with `$judgment-led-delivery` (for example, `$judgment-led-delivery Review this checkout flow without editing files`). Once active, the skill decides how much clarification is needed.

## Examples

### 1. Implement a well-defined feature

> Use judgment-led-delivery to add a “Copy invoice link” action to the invoice detail page. Reuse our button and notification components.

**Expected behavior**

- Inspects the existing page and implements a working copy interaction.
- Handles appropriate success and error feedback, then verifies relevant behavior.
- Doesn't start an unnecessary requirements interview.

### 2. Evaluate a proposed simplification

> Use judgment-led-delivery to evaluate replacing Copy Address and Directions with one Maps button on mobile. Review the existing experience and recommend the best approach. Don't edit files.

**Expected behavior**

- Inspects the actual mobile experience and recognizes that copying an address and opening directions serve different needs.
- Compares keeping, simplifying, or removing the actions without assuming which one most visitors prefer.
- May recommend no change; respects the mobile-only scope and makes no edits.

### 3. Clarify one important decision

> Use judgment-led-delivery to add a public/private profile setting.

**Expected behavior**

- Checks the existing account model and requirements before asking anything.
- If the default visibility for new profiles is unresolved, asks for that decision with a recommendation.
- Implements the chosen behavior without inventing other product requirements.

### 4. Work through complex requirements

> Use judgment-led-delivery to design and build a team invitation flow for our admin dashboard.

**Expected behavior**

- Investigates existing users, permissions, and invitation patterns.
- If material decisions are open, asks foundational questions (such as who can invite) before dependent ones (such as invitation permissions and expiry).
- Proceeds with the agreed scope and checks the end-to-end invitation journey.

### 5. Fix a focused bug

> Use judgment-led-delivery to fix the orders page filters resetting on refresh.

**Expected behavior**

- Finds the cause and makes a targeted change using project conventions.
- Checks refresh and navigation regressions.
- Skips product discovery and unrelated refactors.

### 6. Review without editing code

> Use judgment-led-delivery to review mobile checkout for keyboard accessibility and usability. Don't change files.

**Expected behavior**

- Inspects the available experience and reports prioritized, observable issues.
- Suggests concrete improvements **without modifying the project**.
- Says clearly when a UI or behavior couldn't be inspected.

### 7. Explore an idea before implementing it

> Use judgment-led-delivery to assess whether AI-generated support-ticket summaries would help our team. Don't build anything yet.

**Expected behavior**

- Separates actual product evidence from assumptions.
- Identifies trade-offs and a small way to test the value.
- Returns a recommendation, **not code or fabricated research**.

## What you should get back

Expect the useful conclusion first, with detail scaled to the task rather than a fixed report template:

- **Implementation:** what changed, why it matters, and the relevant checks.
- **Product evaluation or audit:** a recommendation or prioritized findings grounded in the available evidence and trade-offs.
- **Verification review:** one readiness verdict, backed by the checks performed and any material gaps.

The agent should distinguish directly verified behavior from previous reports and code inspection. It should mention a next step or user decision only when one is genuinely needed—not invent risks or fill empty sections. A quality review is not permission to merge or deploy.

## Read more

- [Skill instructions](SKILL.md) — the workflow the agent follows
- [Decision brief](references/decision-brief.md) — extra guidance for ambiguous product decisions
- [Quality reference](references/quality-bar.md) — more detailed checks for substantial or risky changes

## Inspiration

Megan's [*Design Will Never Be The Same*](https://youtu.be/na1OyJ3E7Kc) informed the product-quality workflow. Matt Pocock's [Grilling](https://github.com/mattpocock/skills/blob/main/skills/productivity/grilling/SKILL.md) informed the dependency-aware questioning approach.
