# Changelog

## Unreleased

(nothing yet)

## [1.3.0] — 2026-10-04

- **Household recipe sharing.** The companion can now export any recipe as a share file and import share files from household members, with adaptations tailored to the recipient.
- **New template:** `templates/recipe-share.template.md` — the share contract: YAML frontmatter (author, tested date, servings, diet-fit, equipment, license, version) over a clean markdown recipe body. schema.org/Recipe property names where they exist (`recipeYield`, `recipeCuisine`, `suitableForDiet`); kit extensions where they don't (`diet_fit` for keto/low-carb, which the schema.org diet enumeration doesn't cover; `oven_notes`; `rejected`). `license` defaults to `household-only`.
- **Recipe-delivery skill:** new "Sharing recipes (household)" section. Export fills the share template from the recipe card + profile and asks about forwarding (default household-only); oven notes carry raw tested facts, never diagnoses. Import is adaptive: the companion summarizes the incoming recipe, diffs it against the recipient's profile across equipment, servings, diet conflicts, and household preferences ("who you're feeding"), and proposes a "your kitchen's version" — each adaptation individually declinable. The shared original is never rewritten; on full decline the original is filed as-is. Deeper dimensions (pantry gaps, skill calibration, time-budget, seasonal) spec'd as follow-ups.
- **Recipe-storage skill:** template list now points at the share template; imported recipes (original + adapted version) file like any other card.
- **INSTALL.md:** honest-limits note on sharing — the kit generates the file, the user hands it over; no companion-to-companion channel.
- Origin: Daniel's 2026-10-04 decision to define proper sharing after the live-install fathead-pizza share with Trish; share-contract research verified against primary sources (schema.org/Recipe; audit caught and fixed a `suitableForDiet` omission before build).

## [1.2.0] — 2026-10-04

- **Cook-session logging + feedback loop.** The companion now actively maintains a session log during cooks instead of relying on transcript memory.
- **New template:** `templates/cook-session.template.md` — session log with timing agreement, ingredients (with brands), equipment, adjustments, timing notes, outcome observations, unanswered offers, feedback, and annotations for next time.
- **New AGENT.md section "Cook sessions":** at the start of the cook the companion asks when the food will be eaten and permission to follow up; during the cook it logs actively (with proactive consolidated snapshots when the recipe evolves significantly, and record-don't-diagnose timing discipline); at the end it wraps cleanly; at follow-up it asks "How'd it turn out?" and converses over three dimensions (overall result, what worked/didn't, what to change next time), re-raising any unanswered offers.
- **Recipe-delivery skill:** house rules 7 (session logging) and 8 (proactive snapshots) added; rule 6 now sources post-cook notes from the session log.
- **INSTALL.md:** honest limits on follow-up scheduling — platform-dependent, with next-interaction fallback where the platform can't ping proactively.
- Origin: Daniel's 2026-10-04 fathead pizza cook audit (live install recorded nothing; transcript-only state proved fragile).

## [1.1.3] — 2026-10-04

- **Research re-verification pass.** Closed the self-flagged primary-source gaps from the 2026-10-04 truthfulness audit — no fabricated claims were found; this release attaches primary citations and corrects two figures.
- **MS research notes:** Swank 1990 characterization verified against the NLM primary abstract (PMID 1973220; full text paywalled at The Lancet — noted honestly). Both 2026 vitamin-D/MS papers verified from primary PubMed abstracts (network meta-analysis: PMID 42242131, 32 RCTs, n=2,254, RR 0.80 for relapse; *Brain and Behavior* systematic review: DOI 10.1002/brb3.71692, 11 studies, narrative synthesis). The apparent contradiction is resolved in-file: the June paper pools quantitatively and finds a modest long-term signal; the September paper declines to pool and reports inconsistency — both agree the evidence doesn't support disease-modification claims. Grade stays "contested."
- **Food safety:** burn-cooling verified against redcross.org ("immediately run cool (not cold) water over the affected area for 10–20 minutes") — the skill now cites redcross.org. Tomato acidification measures verified against NCHFP's acidification table (lemon juice 1 Tbsp/pint, 2 Tbsp/quart; citric acid ¼ tsp/pint, ½ tsp/quart; 5% vinegar 2 Tbsp/pint, 4 Tbsp/quart).
- **Corrections:** FoodKeeper butter storage corrected **1–3 months → 1–2 months** refrigerated (verified against the FoodKeeper database on foodsafety.gov; 6–9 months frozen and mayo 2 months confirmed). Jerky temperature rule tightened to match the FSIS Meat and Poultry Hotline's current recommendation: heat meat to 160°F / poultry to 165°F **before** dehydrating ("before or after" was looser than the current guidance); the live fsis.usda.gov domain was unreachable ("Access Denied"), so verification used the September 2026 Wayback Machine snapshot — noted in-file.
- **Diet evidence tables:** VA HSR&D eBrief no. 104 and PMIDs 39783962, 41129328, 41599961 independently verified; Sources section now carries full titles, DOIs, and verification notes.
- **New Sources sections** in the cooking-methods, technique, and kitchen-math skills: Maillard ~285°F (McGee *On Food and Cooking*; 140°C/284°F food-science figure), carryover 8–15°F (convention, 5–25°F literature range), yeast temps (Red Star Yeast: ADY 110–115°F, instant ~120°F, dies ~140°F), altitude (NMSU Extension Guide E-215; CSU Extension), Gas Mark conversions.
- Standing cautions preserved untouched: the niacin "spot-check a physical package" caveat, the Petersen-review Soy Nutrition Institute funding disclosure, and the two retracted monk-fruit paper disclosures.

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
