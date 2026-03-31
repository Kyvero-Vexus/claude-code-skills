# Croatoan Skill Mini A/B Eval Plan

Capability delta under test:

> After applying this skill, Claude Code should more reliably design and build Common Lisp terminal applications with Croatoan, grounded in the real Croatoan API and docs, instead of drifting into generic ncurses/TUI advice.

## Baseline vs treatment

- **Baseline:** no Croatoan-specific skill (or generic terminal advice only)
- **Treatment:** current Croatoan skill with build workflow, full-feature coverage, docs/source routing, and thread-safety guidance

## Representative prompts

1. Build a minimal Croatoan app that exits on `q`.
2. Should this TUI use forms or just keybindings and manual cursor movement?
3. How do I structure a Croatoan app with multiple windows or overlays?
4. Does Croatoan support menus, checklists, dropdowns, and dialogs?
5. How should I handle terminal resize and redraw in Croatoan?
6. I want to use Croatoan from SLIME; what is the safe architecture?
7. Does Croatoan support mouse events and styled terminal drawing?
8. When would I use pads versus windows?
9. What is the difference between `croatoan`, `ncurses`, and `ansi-escape` here?
10. What all does Croatoan cover beyond `with-screen` and `add-string`?

## Scoring rubric

Score each prompt 0–2 on each dimension.

### 1. Build orientation
- 0: answer stays abstract or generic
- 1: partly actionable
- 2: clearly oriented toward building a working Croatoan app

### 2. API specificity
- 0: vague/generic terminal advice
- 1: partial Croatoan specificity
- 2: names the right Croatoan forms/objects/functions

### 3. Architecture fit
- 0: wrong model chosen
- 1: partly reasonable
- 2: appropriate choice among screen/windows/forms/menus/layouts/etc.

### 4. Full-feature coverage
- 0: collapses Croatoan to a tiny subset
- 1: mentions broader areas vaguely
- 2: can range across the real library surface

### 5. Thread-safety correctness
- 0: unsafe or wrong advice for SLIME/threaded use
- 1: partial caution only
- 2: correct terminal-thread/`submit` guidance

### 6. Layer discipline
- 0: confuses Croatoan high-level API with low-level ncurses/ANSI layers
- 1: partial distinction
- 2: clear distinction

Maximum score per prompt: 12

## Keep/discard criterion

Keep the skill only if it improves average score on:
- build orientation
- API specificity
- architecture fit
- full-feature coverage
- thread-safety correctness
