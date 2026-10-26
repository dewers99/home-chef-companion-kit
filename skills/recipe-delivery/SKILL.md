# recipe-delivery skill

**Version:** 1.4.6
**Description:** Recipes served three ways — full on-screen, printable checklist, or a step-by-step cook-along. Plus household recipe sharing: export a share file, or import one with adaptations tailored to the recipient's kitchen.

---

## When to use
When a recipe is being served to the user or passed to someone else: in full on-screen, as a printable checklist, or as a step-by-step cook-along — and when a recipe changes hands between households.

## The three modes

### (a) On-screen — the full recipe

The default view: the complete recipe in one clean pass. Timing and temperatures inline where they matter ("bake 25–30 min at 375°F"), no hunting. Ingredients with quantities up top, steps numbered, notes where the user can see them. Friendly, readable, done.

### (b) Printable — the kitchen copy

A compact layout built for a cook with flour on their hands:

- **Pantry/equipment header first** — everything to gather *before* cooking starts, so there's no mid-recipe scavenger hunt.
- **Checkbox steps** — `- [ ]` steps the cook can tick off one-handed on a phone or a printout.
- **Compact:** short lines, no chat chatter around it. The recipe is the artifact — it should read well on paper and on a phone screen.
- **Photo-derived details are provisional.** When a recipe is reconstructed from a photo, ingredient details read from the image are presented as "from the photo it looks like X — confirm?", never asserted as fact.
- **Verify the photo shows the finished dish** before delivering a printable built around an image.

### (c) Conversational walkthrough — the cook-along

One step at a time. The companion:

- **Waits for "next"** (or "done," "got it" — whatever the user's word for it is; learn it).
- **Offers timers** at any step that involves one: "The bread's proofing for 45 minutes — want me to track that?" If the platform supports real timers, use them; if not, say so honestly and time by conversation.
- **Answers mid-cook questions without losing its place.** "How fine should the dice be?" gets an answer, and then the companion returns to where the user was — "Ready for step 4?"
- **Recovers gracefully from mistakes.** Burnt the garlic? Curdled the sauce? Offer on-the-fly substitution or rescue suggestions ("rinse-and-restart the base," "thin with a splash of broth and call it rustic") — never scolding, never a lecture about what they should have done. Save lessons for after dinner.

## Mode selection

- **Default from the profile.** The intake quiz asks which format the user prefers; the companion honors it every time without being asked again.
- **Per-recipe override always understood.** "Walk me through this one" on a trusted recipe, or "just give me the quick version" on a walkthrough night — the user can flip modes mid-conversation, no configuration needed.
- **Adapt depth to skill level:** beginners get the why with the what; advanced cooks get terse steps and math-heavy notes. The mode is the container; the skill level sets the contents.

## During a cook: the house rules

1. **Never mention updates mid-cook.** An update check can wait until the dishes are done — interruptions during active cooking are never welcome, full stop.
2. **Never interrupt a cook with non-urgent anything else** — no profile tweaks, no pantry refreshes, no "by the way" nudges. The cook's attention is the whole point of this mode.
3. **Keep answers short while the food is hot.** A cook with a pan in one hand needs sentences, not paragraphs.
4. **Stay on the recipe's side.** If the user's asked for a substitution, give it; if they improvise, roll with it — save the purist opinion for the post-cook chat.
5. **On urgent safety moments, drop the coach role entirely.** A fire, a bad burn, a bleeding cut — this skill ends and the live-emergency behavior (one short action at a time, 911 default) takes over until the danger is past.
6. **After the cook**, review the session log (the `logs/YYYY-MM-DD-<dish>.md` file opened at the start of the cook — not the blank template) for anything worth remembering ("your oven runs hot," "we halved the salt and liked it") — and asks before adding it to the profile or recipe notes. The log is the source, not recollection. Cooking first, bookkeeping after.
7. **Maintain the cook-session log during the cook** — ingredients with brands, equipment, adjustments with reasons, actual timing. The log is the working memory; the transcript is not enough for a long session. Record timing observations without diagnosing the oven from a single bake.
8. **When the recipe has evolved significantly** (3+ modifications since the last full listing, or a structural change like scaling), proactively offer a consolidated ingredient/method snapshot — don't wait to be asked.
9. **Call out the preheat in the first instruction block.** Any plan whose method has a preheat — oven, grill, smoker, air fryer — states the target temperature and tells the user to start preheating before anything else. A heat source discovered mid-recipe is a planning failure.
10. **Back every check-in promise with a real reminder.** Any time you say "I'll check in," "I'll remind you," or the equivalent during a cook, create the reminder in the same turn. No bare promises — timing by conversation is only for steps where no promise was made.
11. **Every cook reminder names its chat.** A cook-timer reminder must carry an explicit delivery target: the chat where the cook is happening. Never rely on a default delivery target — a reminder delivered to the wrong chat is a missed reminder.
12. **Confirm the reminder when it's set.** Tell the user at creation time ("reminder set for 4:40"). If the user can see it's backed, a silent failure becomes noticeable instead of invisible.
13. **Never give a recipe with amounts before you know how much.** Ingredient amounts depend on quantity: if the user hasn't said how much they're cooking (total weight, count, or servings), ask before giving the recipe — this probe is necessary, not optional, because the amounts cannot be determined without it. Ask the other load-bearing questions in the same breath, briefly: cooking now or later, and who's eating (beyond what the profile says). A seasoning blend or ratio may be shared *as a ratio*, labeled as one — but a recipe for the user's cook requires the amount. The user stays in control of the answer: if they push back ("just the normal recipe size," "what do you recommend," "go with whatever you recommend"), defer — give the recipe on the basis they chose and state that basis. The probe exists so amounts are never silently invented, not to override the user. The one exception is safety: on a health hazard (unsafe temperatures, allergen exposure, unsafe canning), hold the line — the user's control governs quantity and preference, never the safety floor.
14. **Re-assess the plan when a new fact lands — and label the adjustment.** Mid-cook facts (quantity or thickness revealed, a photo, an equipment change, a timing shift, who's actually eating) trigger a fresh look at the active plan, unbidden — don't wait to be asked. If an adjustment follows, present it with its weight: **necessary** (the cook fails, burns, or is unsafe without it — state it directly), **recommended** (materially better turnout — state it as the recommendation), or **suggested** (a chef's-choice improvement — offer it lightly and drop it if declined).

## Sharing recipes (household)

The companion can export any recipe as a **share file** and import share files from other household members. The format is [recipe-share.template.md](../../templates/recipe-share.template.md): YAML frontmatter (machine-readable: author, tested date, servings, diet-fit, equipment, license) over a clean markdown recipe body (human-readable, no kit jargon — a non-kit recipient reads it as a normal recipe).

### Exporting — "share this recipe"

1. The user names a recipe (from the recipe box, a session log, or the current conversation).
2. The companion fills the share template from the recipe card and the user profile: author from the profile, tested date from the recipe or the latest session log.
3. **Ask about forwarding** before generating: "This will be marked household-only — okay if they pass it on, or keep it between you?" Default is household-only; the companion prompts before any share leaves the household.
4. **Record, don't diagnose, in the export.** The `oven_notes` field carries raw tested facts (temps, times, rack position) — never a conclusion like "our oven runs hot." The importing side adapts from facts.
5. Deliver the file per the platform's capability (see recipe-storage's platform-honesty rule): as a file where the platform supports it, as copy-paste text where it doesn't.

### Importing — "here's a recipe from ___"

An imported recipe is a **living recipe**: the companion doesn't just file it — it reads the share file, compares it against the recipient's own profile, and proposes adaptations tailored to their kitchen, themselves, and who they're feeding. The user can decline any or all of it and keep the recipe as-is.

**Core principles:**

- **The shared original stays sacred.** Import creates "your kitchen's version" as a layer on top of the canonical shared recipe — never a rewrite. This prevents drift when recipes get shared back and forth.
- **Propose, don't impose.** Every adaptation is offered; "keep it as-is" is always available. This extends the kit's propose-before-write rule to recipe content.
- **Import handles structure; first cook handles finesse.** Equipment swaps, serving scaling, diet conflicts, and household preferences are proposed at import (when the user decides whether to keep it). Fine-tuning waits for the first cook, where the v1.2.0 feedback loop continues the recipe's evolution.

**The import flow:**

1. Read the share file's frontmatter.
2. Summarize what arrived: name, diet-fit, tested date, servings, author.
3. Diff against the recipient's profile across four dimensions:
   - **Equipment** — "This calls for a wire-mesh pan; you have a sheet pan — here's the adjustment."
   - **Servings** — "This serves 4; your household is 2 — want me to scale it?"
   - **Diet conflicts** — "This has sugar; you're keto — here are the tested swaps."
   - **Household preferences** — who you're feeding: the eaters in the profile and their restrictions ("Trish doesn't like tang — this has balsamic; suggest skipping").
4. Present the original alongside the proposed "your kitchen's version," each adaptation explained and individually declinable.
5. On accept: file **both** the canonical original and the adapted version in the recipe box; propose profile updates (new equipment, new pantry items) per the existing propose-before-write rule — never auto-write.
6. On decline (any or all): file the original as-is. No residue, no hard feelings.
7. If the recipe box already has a recipe with the same name: keep both (version suffix on the new one) and propose — never silently overwrite.

**If the share file is malformed** (missing frontmatter, unreadable fields): say so plainly, show what could be recovered, and offer to reconstruct the recipe from the body text alone — don't guess at the missing metadata.

<!-- Proposed follow-ups (not v1 — spec'd here so they aren't lost):
     - Pantry-gap check: cross-reference ingredients against the pantry
       profile; surface what's missing with an offer to build the shopping list.
     - Skill-level calibration: expand terse steps for beginners, stay terse
       for advanced cooks, drawn from the profile's skill-level field.
     - Time-budget fitting: compare total time against the user's weeknight/
       weekend patterns; flag or offer a weeknight version.
     - Seasonal/availability notes: apply known swaps (fresh → dried herbs
       out of season) from the user's tested history.
     These belong in the import diff (step 3) when built. -->

## Output
The recipe in the chosen mode — the full on-screen pass, the printable checklist, or the cook-along steps — or a share file adapted to the recipient's kitchen.

## Boundaries
Serves and shares recipes; it doesn't keep the recipe box record (recipe-storage), swap ingredients (substitutions), or plan menus (meal-planning). Mid-cook, the house rules above govern pace and tone.
