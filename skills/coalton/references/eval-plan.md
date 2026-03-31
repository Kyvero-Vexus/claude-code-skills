# Coalton Skill Mini A/B Eval Plan

Capability delta under test:

> After applying this skill, Claude Code should more reliably design and build Coalton code and projects grounded in Coalton's real language/workflow, instead of drifting into generic typed-functional or generic Common Lisp advice.

## Baseline vs treatment

- **Baseline:** no Coalton-specific skill or only generic typed-FP guidance
- **Treatment:** current Coalton skill with build workflow, full-feature coverage, interop/config/test/debug guidance, and local docs routing

## Representative prompts

1. Set up a minimal Coalton project with ASDF and one module.
2. Should this file be `.lisp` with a readtable or `.ct`?
3. How should I model this domain with `define-type`, `define-struct`, or aliases?
4. I need to call a Common Lisp library from Coalton; what is the right interop pattern?
5. What does Coalton cover beyond `coalton-toplevel` and `define-type`?
6. How should I debug a confusing Coalton type error or generated code issue?
7. How do I add tests to a Coalton project?
8. When should I use `repr :native` or `repr :lisp`?
9. What is the practical difference between development and release mode?
10. Why is my Haskell-like partial application idea not fitting Coalton?

## Scoring rubric

Score each prompt 0–2 on each dimension.

### 1. Build orientation
- 0: abstract or generic advice only
- 1: partly actionable
- 2: clearly oriented toward building working Coalton code/projects

### 2. Coalton specificity
- 0: generic typed-FP or generic Lisp advice
- 1: partial Coalton specificity
- 2: names the right Coalton forms, files, and workflow pieces

### 3. Architecture fit
- 0: wrong model or wrong abstraction choice
- 1: partly reasonable
- 2: appropriate setup and language feature choice

### 4. Full-feature coverage
- 0: collapses Coalton to a tiny subset
- 1: vague mention of broader areas
- 2: can range across the real language/workflow surface

### 5. Interop/config correctness
- 0: wrong or dangerous advice about interop or modes
- 1: partial caution only
- 2: correct guidance on Lisp interop, `repr`, and development/release concerns

### 6. Testing/debugging discipline
- 0: omits testing/debugging workflow
- 1: partial mention only
- 2: points to proper Coalton debugging/testing tools and structure

Maximum score per prompt: 12

## Keep/discard criterion

Keep the skill only if it improves average score on:
- build orientation
- Coalton specificity
- architecture fit
- full-feature coverage
- interop/config correctness
- testing/debugging discipline
