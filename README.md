# claude-code-skills

Claude Code plugin marketplace repo for Kyvero Vexus skills.

## Included

- `clim-spec`
  - Build CLIM applications on McCLIM with the CLIM 2 spec as semantic ground truth.
  - Covers the practical app-building workflow **and** the full CLIM 2 feature surface as a minimum.

- `croatoan`
  - Build Common Lisp terminal applications with Croatoan.
  - Covers screens, windows, event loops, forms, menus, dialogs, layouts, styling, mouse/resize, and SLIME-safe terminal workflows.

- `coalton`
  - Build statically typed Common Lisp projects with Coalton.
  - Covers project setup, `.ct` files, typed modules, algebraic data, type classes, Lisp interop, configuration, debugging, testing, and optimization.

## Install in Claude Code

```text
/plugin marketplace add Kyvero-Vexus/claude-code-skills
/plugin install clim-spec
/plugin install croatoan
/plugin install coalton
```

## Local development install

From Claude Code, while your shell is in this repo's parent directory:

```text
/plugin marketplace add ./claude-code-skills
/plugin install clim-spec
```

## Layout

- `.claude-plugin/marketplace.json` — Claude Code marketplace metadata
- `skills/clim-spec/` — full CLIM/McCLIM skill package

## Notes

- This repo follows the lightweight skills-only marketplace pattern.
- The plugin is distributed as a marketplace entry that exposes the bundled skill directory directly.
