# Changelog

## Unreleased

(nothing yet)

## [1.1.2] — 2026-09-27

- **Feedback form standardization.** The Tally feedback form moves to the cross-kit standard: tenure-neutral summary, 7 questions in the standard order, hints on every open-text question, standardized thank-you. Companion behavior updated (AGENT.md): the form is offered once two weeks after install and any time the user mentions feedback. INSTALL.md/README.md now note the form can be opened any time.

## [1.1.1] — 2026-09-27

- Fixed 8 stale 1.0.0 version strings left over from the v1.1.0 bump
  (README footer, skill version headers, template and reference titles).
- Unified skill version-header format: all skills now use `**Version:**`.
- The food-safety skill now points at the kitchen-safety-checklist and
  preservation-session templates.

## [1.1.0] — 2026-09-27

- New "Running a survey" section in AGENT.md: a pure-markdown conversational
  survey pattern for gathering several answers before proceeding (intake,
  meal-plan preferences, pantry setup, recipe feedback). One question at a
  time; each question states its type (choose one / choose up to N / choose
  all that apply / type your answer); lettered options with an explicit Other;
  skip / don't-understand / discuss escape hatches honored immediately;
  recap-and-confirm at the end; cancel keeps what's answered. Works on every
  platform from instructions alone — no platform-specific code.

## [1.0.0] — 2026-09-24

First release of the Home Chef Companion Kit: a portable text-file kit that
turns the AI tool of your choice into a personal sous-chef.

**Included:**

- The Sous Chef agent (`AGENT.md`) — persona, tone, boundaries, how it adapts
  to the user's skill level, tastes, dietary pattern, equipment, and pantry
- 11 skill modules:
  - intake-and-adaptation (guided intake quiz, conversational alternative)
  - kitchen-math (conversions, scaling, pan sizes, temperatures)
  - substitutions (ingredient swaps)
  - food-safety (safe temps, storage, kitchen safety, home preservation)
  - technique (knife skills, searing, fundamentals)
  - cooking-methods (grilling, smoking, roasting, baking, and more)
  - diet-adaptation (adapting recipes to dietary patterns)
  - meal-planning (weekly plans + shopping lists)
  - pantry-tracker (inventory, restock reminders, starter-pantry list)
  - recipe-delivery (on-screen, printable, conversational walkthrough)
  - recipe-storage (personal Recipe Box, matched to platform capabilities)
- 8 blank templates (user profile, pantry inventory, meal plan, shopping list,
  recipe records, and more)
- Reference appendix — consulted when asked, never volunteered unprompted
- Per-AI install guides with honest platform limits (Muse AI, ChatGPT, Claude,
  Gemini, Copilot, Cursor/coding agents, any other tool), including a
  recipe-storage capability matrix
- Check-don't-apply update flow: version checked, never silently applied,
  changes always shown before applying
- Anonymous two-week feedback note — always skippable, never nagging

**Not this kit:** not a diet advisor, not a clinician, not a cookbook (no
bundled recipes), not a calorie tracker.
