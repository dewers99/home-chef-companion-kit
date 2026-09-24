# Reference Appendix — Home Chef Companion Kit v1.0.0

## The core/appendix split

The kit has two kinds of knowledge about food and health, and they live in different places for a reason.

**Core (`kit/skills/`)** holds *behavior rules*: how the companion acts, what it can and can't do, the guardrails, the referral lines. The core is always loaded. It tells the companion *how to behave* — adapt to the user's stated pattern, attribute claims instead of adjudicating them, never gamble on allergen safety, never diagnose.

**Reference (`kit/reference/`)** holds the *evidence behind the claims*: study names, sample sizes, evidence grades, where researchers disagree, what regulators actually said. These files ship with the kit — everyone gets them — but the companion **never volunteers them**.

That's the whole design decision: the companion never walks up to a home cook mid-recipe and starts lecturing about trial methodology. The reference files are consulted **only when the user asks for the deeper evidence** behind something the companion said — "what's that based on?", "how strong is the evidence?", "I've heard the opposite — what do the studies say?" Then, and only then, the companion opens the appendix and gives a fair, graded answer.

## What's in here

| File | Contents |
|---|---|
| `diet-evidence-tables.md` | Named diets (keto, Mediterranean, paleo/primal, carnivore) with evidence grades and sources — contradictions flagged, not resolved. |
| `sweetener-deep-dive.md` | Full sweetener research: allulose, monk fruit, erythritol, xylitol, stevia, sucralose, aspartame — evidence-graded, with the verify corrections. |
| `disease-diet-clinical-notes.md` | Trial sizes and guideline specifics behind the medical-diet guardrails: ADA 2026 §5, the ATA absence-of-guidance finding, Celiac Disease Foundation and FARE label rules, AND 2025 scope limits. |
| `ms-research-notes.md` | Swank, Wahls, and vitamin D studies with evidence grades and contradictions flagged. Behavior rules stay in the core skill — this is evidence only. |
| `mental-health-nutrient-notes.md` | Nutrient-by-nutrient food-and-mood evidence, graded — no clinical recommendations. |
| `seed-oil-and-sweetener-adjudication.md` | Study-by-study breakdowns behind the neutral postures on seed oils and sweeteners. |

## Ground rules for using the appendix

- **Present, don't persuade.** When asked, lay out what each side claims, the evidence grade, and the source. Let the user draw their own conclusions.
- **Report the grade, not the headline.** A small open-label trial is not "proof" — say it's a small open-label trial.
- **Contradictions stay flagged, not resolved.** Where researchers genuinely disagree (vitamin D and MS, GI/GL in diabetes), the appendix shows both sides. The companion never resolves a scientific dispute from the kitchen.
- Nothing here changes the core rules: no diagnosing, no originating medical advice, no supplement doses, no treatment claims. The appendix makes the companion *honest*, not *authorized*.
