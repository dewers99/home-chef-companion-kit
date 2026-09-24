# recipe-storage

**Version:** 1.0.0
**Description:** The companion saves and organizes YOUR recipes — no bundled cookbook, just your box.

---

## What gets stored

The kit ships **zero bundled recipes**. It is not a cookbook. What the companion saves and organizes is the user's own collection:

- **Recipes the user pastes in** — copied from sites, friends, family.
- **Family recipes** — the ones on index cards and in memories, transcribed through conversation.
- **Companion-developed recipes** — recipes worked out together in chat (e.g., a birthday cheesecake adapted keto mid-conversation). When the companion develops one, it offers to save it before the session ends.

## The recipe card

Every saved recipe uses [recipe-card.template.md](../../templates/recipe-card.template.md): consistent fields (name, source, servings, times, ingredients, steps, notes/substitutions) plus tags:

- **diet-fit** — keto, vegan, vegetarian, gluten-free… as many as apply.
- **cuisine** — Italian, Mexican, weeknight-American, "grandma's"…
- **occasion** — weeknight, holiday, potluck, birthday…
- **source** — user-supplied / companion-developed.
- **equipment** — Dutch oven, smoker, air fryer, stand mixer… whatever the recipe actually needs.

Consistent cards + tags make retrieval work: by name ("find my keto cheesecake"), by tag ("what's tagged weeknight + keto?"), by diet ("show me my vegan soups"). Tags are the search index; keep them tidy.

## The Recipe Box reorganization

The companion can help the user execute a real-world "Recipe Box" reorganization (a full Drive folder or shoebox of recipes, digital or otherwise):

1. **Flag duplicates for merging** — near-duplicate recipes get flagged with a side-by-side, and the user decides whether they merge. The companion proposes; the user disposes.
2. **Keto/low-carb naming indicators, not separate folders.** Diet-fit is a *tag*, not a top-level folder. One box, well-labeled — folders by diet are how collections get lost.
3. **Sweetener-swap notation.** Recipes that differ only by sweetener (sugar ↔ allulose, honey ↔ monk fruit blend) are stored as ONE card with a swaps line, not two cards. Record which sweetener was actually tested and how the bake behaved (allulose browns faster, erythritol recrystallizes — note what happened, not theory).
4. **A markdown index** — one master list of the whole box, sortable by tag. The index is the front door.
5. **An Archive folder for originals** — the untouched originals live there before any merge or edit. Nothing is lost in a reorganization; it just moves.

## Platform capability honesty (CRITICAL)

What the companion can actually persist **depends on the AI tool in use**. The capability matrix lives in `INSTALL.md` (per-platform: where the companion can write files, where it can only keep recipes in the session/profile, where Projects/Files features exist).

The rule is absolute:

> **Never pretend it saved something it can't.** If the platform has no persistence, the companion says so plainly — "I can't save this where you'll find it later in this tool, so here's the full recipe as copy-paste text" — and offers the recipe in a format the user can keep themselves.

- On platforms with file support: save the recipe card into the user's recipe folder and confirm with the path.
- On platforms with a persistent profile/profile-notes: store the card there and say where.
- On session-only platforms: deliver the complete recipe card as copy-paste text, formatted with the recipe-card template, and offer it proactively rather than waiting to be asked. Also note that the recipe only survives as long as the session does — don't let a session timeout eat a recipe the user cares about.

This applies at save time *and* at retrieval time: "I don't have your recipe box in this tool" is an honest answer; a hallucinated "found it!" is the worst failure this skill has.

## Template

- [Recipe card](../../templates/recipe-card.template.md)
