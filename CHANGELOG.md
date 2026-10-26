# Changelog

## Unreleased

(nothing yet)

## [1.4.6] — 2026-10-25

- **Structure alignment to the canonical companion-kit skeleton** (draye-global-docs ticket `companion-kit-structure-audit`, dec-003). Formatting and organization only — no recipe, safety, or behavior content changed, and the 1.4.5 open-loop follow-up works exactly as before.
- **Governance (governance docs — wording, not a rule change).** The Write safety principle now reads in the canonical wording shared by every companion kit, including the kit-bookkeeping exception this kit has always applied in practice. The kit's own personal-data list — preferences, equipment, household notes, allergies, and the recipe box — now lives in the Home Chef annex, where kit-specific examples belong. The five principles are unnumbered, and the annex stands as its own section.
- **Skill modules** take the standard anatomy: slug titles (`# meal-planning skill`), a `**Version:**` + `**Description:**` header on every module (all now at the kit version), "When to use" first, and Output + Boundaries closing each module. The two modules that carried YAML frontmatter (diet-adaptation, food-safety) now use the standard header lines.
- **Titles cleaned up:** the intake-quiz and kitchen-profile templates no longer carry the kit name; reference-appendix titles no longer carry a version (per the standing rule, a reference states its scope in its body — the version lives in VERSION and this changelog).
- README gains its License section; INSTALL's Updates section now states plainly that your own data is never part of an update.
- **Citation fix (pre-publish, dec-011):** the food-safety module's grounding rule and one section heading pointed at the author's local research folders; they now cite the published primary sources the numbers rest on (USDA FSIS, FoodSafety.gov and USDA FoodKeeper, NFPA, American Red Cross and municipal fire-service guidance, the National Center for Home Food Preservation, the USDA Complete Guide to Home Canning, and university extension). No number, procedure, or safety guidance changed — only where the file says its authority comes from.

## [1.4.5] — 2026-10-25

- **Open-loop follow-up (missed questions get two later reminders).** A question that needs the user's answer — a recipe-box filing offer, a profile-note proposal — is no longer treated as answered when the conversation simply moves on. Silence isn't a decline: if an offer goes unanswered (the user pivots to the next cook, the session ends), the companion notes the open loop in the session log and follows up later, when no cook is active — at the start of a new session before cooking begins, or in ordinary conversation, never mid-cook. At most two follow-ups; the second says gently that it won't ask again ("I'll stop asking after this; just say the word anytime if you'd like it done"). A decline closes the loop at any point; after the second follow-up, the companion lets it rest. Before this change, an unanswered offer died silently — the 2026-10-15 country-style ribs recipe, cooked and praised, was never filed because its filing offer went unanswered in the pivot to the next cook.
- Origin: Daniel's ruling 2026-10-25 — follow up at a later, non-cook time; remind twice before letting it alone; the last ask carries the won't-ask-again language.

## [1.4.4] — 2026-10-23

- **The anticipatory companion (live-install audit fix).** The 2026-10-23 audit of a pork-steak grill cook found one defect in four places: the companion answered the question asked and waited, instead of anticipating. Five changes:
  - **Necessary intake probe.** A recipe with ingredient amounts is never given before the companion knows how much is being cooked (weight, count, or servings) — amounts cannot be determined without it, so the probe is necessary, not optional. Other load-bearing questions (cooking now or later, who's eating) are asked in the same breath, briefly. A blend may be shared as a labeled ratio, but a recipe for the user's cook requires the amount. The user stays in control of the answer: a pushback ("just the normal recipe size," "go with whatever you recommend") is deferred to — the recipe is given on the basis the user chose, with that basis stated. The probe exists so amounts are never silently invented, not to override the user; the only exception to deference is a safety hazard, where the companion holds the line.
  - **Tiered auto-reassessment.** When a new fact lands mid-cook (quantity or thickness revealed, a photo, an equipment change, a timing shift), the companion re-assesses the active plan unbidden and labels any adjustment **necessary** (the cook fails, burns, or is unsafe without it — stated directly), **recommended** (materially better turnout), or **suggested** (chef's-choice — offered lightly, dropped if declined).
  - **Session escalation + recipe candidates.** Advice that turns into active cooking is a cook session: open the log then and backfill. Recipes the companion generates are recorded in the session log as recipe candidates on the spot; the follow-up verdict drives propose-first filing to the recipe box. (The audited cook ran with no session log at all; the keeper rub it produced lived only in the transcript.) Session template gains a Recipe candidates section.
  - **Preheat callout generalized.** The first-instruction-block preheat rule now covers any method with a preheat — oven, grill, smoker, air fryer — not just the oven. Session template's preheat line matches.
  - **Next-update-check-due rolls forward.** The bookkeeping fields written directly at adoption now include the next-due date, rolled forward (check date + cadence) at every check — it had sat stale at a past date through two adoptions. The profile template's Kit info block gains the field as well: new installs didn't carry it at all, which is why it was the one bookkeeping field that drifted.
- Origin: live-install audit 2026-10-23 + Daniel's findings and rulings the same day (necessary quantity probe; session escalation with on-the-spot candidates; method-wide preheat).

## [1.4.3] — 2026-10-21

- **Kit bookkeeping no longer needs a proposal (live-install friction fix).** When v1.4.2 was adopted, the companion asked permission to stamp the new kit version into the profile — a write its own update procedure requires, blocked only by the write-safety rule's blanket propose-first. Write safety now carves out kit bookkeeping (the kit version stamp, last-update-check date, and update-history lines recorded at adoption): written directly as part of applying a verified update, never proposed. The update-checking section says so explicitly. Personal data — preferences, equipment, household notes, allergies — and the recipe box remain propose-first.
- Origin: Daniel's ruling 2026-10-21 — the version stamp is a fact about the kit, not personal information.

## [1.4.2] — 2026-10-18

- **Reminder reliability guardrails (live-install audit fix).** The 2026-10-18 audit found two failure modes in cook check-ins: a promised 11:30 parm uncover with no backing reminder, and a 4:40 chuck-roast reminder that was "delivered" to the main chat instead of the live cook chat (the cron carried no delivery target, so the scheduler defaulted). New recipe-delivery house rules: (10) back every check-in promise with a real reminder in the same turn — no bare promises; (11) every cook reminder names its chat explicitly, never relying on a default target; (12) confirm the reminder to the user when it's set, so a silent failure becomes noticeable.
- **Printable-from-photo guardrails.** When a recipe is reconstructed from a photo, photo-derived ingredient details are provisional ("from the photo it looks like X — confirm?"), never asserted as fact; and the chosen photo must show the finished dish before the printable is delivered.
- Origin: live-install audit 2026-10-18 (reminder delivery investigation) + Daniel's approval of all five guardrails.

## [1.4.1] — 2026-10-16

- **Session-log lifecycle made explicit (live-install audit fix).** The cook-session logging shipped in v1.2.0/v1.3.0 never produced a log in two live cooks (ribs 2026-10-15, chicken parm 2026-10-16): the spec described *maintaining* the log but never said where the file lives or how to create it, and pointed at the blank template as "the session log." AGENT.md's "Cook sessions" section now opens with an explicit create step — when a cook session begins, copy `templates/cook-session.template.md` to `logs/YYYY-MM-DD-<dish-slug>.md` (creating `logs/` next to the recipe box if needed); the recipe-delivery skill's post-cook review now points at the session file, not the template.
- **Oven preheat callout.** New house rule in the recipe-delivery skill: any plan that uses the oven states the preheat temperature and tells the user to start preheating in the first instruction block — never discovered mid-recipe. The session template's Session basics gains an oven-preheat line.
- Origin: live-install audit 2026-10-16, at Daniel's request.

## [1.4.0] — 2026-10-12

- **Governance fix (explicit surfacing): this update changes how the companion verifies information.** New "Governance" section in AGENT.md: five shared principles (research integrity, source fidelity, presentation vs work notes, claim retirement, write safety) plus a Home Chef annex.
- **Annex safety emphasis:** food-safety claims (temperatures, allergens, spoilage, canning safety) get the strictest verification of anything the companion says — a wrong temperature isn't a typo, it's a health risk. Primary sources only, re-read before quoting, never guess.
- **Annex worked examples:** one concrete cooking scenario per principle (canning safety, poultry temp re-check, sweetener research summary, keto retirement, allergy write with propose-first).
- Origin: companion-kit governance design (shared core + per-kit annex model); annex work order `home-chef-kit-governance-annex`.

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
