# Contributing

Have a reusable skill that helps an AI agent perform real work more effectively? Contributions are welcome across any discipline.

1. Add `skills/<skill-name>/SKILL.md` following the [Agent Skills specification](https://agentskills.io/specification). Include a clear `name`, `description`, when to use it, instructions, and how to verify the result.
2. Keep it self-contained and agent-agnostic. Use `references/` only for detail the agent needs occasionally. Avoid unnecessary scripts, frameworks, and overlapping skills.
3. Add a brief `README.md` with a real example. A visual cover (`cover.svg` or `cover.png`) is encouraged for sharing, **not required** for community contributions.
4. Open a pull request describing the problem the skill solves, a sample invocation, and any tools, risks, or permissions involved.

Keep private information, secrets, and proprietary prompts out of the repository. Attribute source material and follow the [MIT license](LICENSE).

You can optionally validate an individual skill with `skills-ref validate skills/<skill-name>` if you have the [reference validator](https://github.com/agentskills/agentskills) installed. No custom repository tooling is required.
