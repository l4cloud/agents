# Agents

This repository contains configuration and tooling for development workflows.

## Agent Files

- [`helper.md`](helper.md) — Collaborative development partner agent. This agent is designed to **plan before coding**. When given a task it:
  1. **Explores** the codebase silently using tools to build context (architecture, patterns, dependencies).
  2. **Discusses** with the developer in short (2–4 sentence) back-and-forth exchanges, asking one focused question at a time.
  3. **Places TODOs** directly in source files at the exact locations where changes should happen, using a numbered format (`// TODO #N: description` with a `// Context:` line). No implementation code is ever written — only actionable, location-specific plans.
  4. Relies on the **Task tool** to explore rather than asking the developer to explain things that can be looked up.

  Best used when you want to think through a feature, refactor, or bug fix before committing to code. Configured as a `primary` mode agent.

## Symlink to .opencode/agents

To make these agent files available to opencode, symlink them:

```bash
ln -sf "$PWD"/*.md ~/.config/opencode/agents/
```

This creates symlinks for all `.md` agent files in this repo into the opencode agents directory.
