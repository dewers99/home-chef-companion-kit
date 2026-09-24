# pantry-tracker

**Version:** 1.0.0
**Description:** A conversational pantry and fridge inventory — the companion keeps the record through normal cooking chat, nudges before you run out.

---

## Why conversational

The research on pantry trackers has one loud lesson: **sync drift kills them.** Users log purchases faithfully and forget to log the splash of oil and the half-can of chickpeas; the inventory drifts out of sync within weeks, and the tool gets abandoned. The fix isn't a better form — it's updating the record in the flow of normal cooking conversation, not as a separate chore.

This skill's golden rule: **the companion maintains the inventory through ordinary talk.** "I'm out of cumin" → noted. "I used half the olive oil" → adjusted. "I bought flour and eggs" → added, date-stamped. No special syntax, no logging ritual. If the user never sets this up, nothing breaks — the kit just doesn't offer restock nudges.

## The inventory data model

Five essential fields per item — nothing more until the user volunteers it:

1. **Name** — as the user says it ("olive oil," "all-purpose flour"). Aliases welcome.
2. **Quantity on hand** — number + unit ("1.5 lb", "3 cans", "about half a bottle").
3. **Location** — pantry / fridge / freezer.
4. **Status** — in stock / running low / out.
5. **Last updated** — date of the last confirmed sighting. This is the staleness signal: it lets the companion distinguish "I saw it yesterday" from "not mentioned in three months."

Optional (recorded only if volunteered): **usual buy size** ("5-lb bag" — makes "add flour to the shopping list" actionable), **restock date**, **best-by date**, and a **derived use rate** (e.g., "~1 bottle / 6 weeks" — computed from the record, never user-entered, always labeled as an estimate with its observation dates).

**Not in v1:** prices, nutrition, photos, barcodes, brand-level tracking, stock journals. This stays the opposite end of the spectrum from warehouse-style inventory apps.

### Starter sheet

See [pantry-inventory.template.md](../../templates/pantry-inventory.template.md) — the five-field sheet the companion fills in as the user talks.

## Conversational updates (the sync mechanism)

- **Add:** "I bought olive oil, a 5-lb bag of flour, and eggs" → add/update the three lines, stamp today's date.
- **Consume:** "I just used the last of the flour" → mark flour **out**, set last-updated.
- **Partial use:** "I used about half the olive oil" → adjust the quantity note.
- **Correction:** "Actually I have two cans of tomatoes" → fix the line. The record is plain markdown the user can also edit directly — that's the accuracy backstop when the companion's record drifts.
- **Stale record:** if the file hasn't been touched in weeks, don't silently trust it: "Your pantry record is a couple of months old — want to do a quick refresh?"

## Restock nudges

Two signals, checked whenever the companion is already talking cooking with the user — never as a separate chore:

1. **Explicit:** status is "low" or "out" → "Flour's on your list — want me to add it to this week's shopping list?"
2. **Inferred:** time since restock vs. the item's own observed rate suggests it's nearly gone.

### Thresholds from the user's own intervals (not global guesses)

Depletion rates are **derived from the user's own purchase cycles**: a "restocked" event plus a later "ran out" event yields a real rate ("5-lb bag of flour bought Sept 1, reported empty Oct 13 → ~0.8 lb/week"). Rates improve over time as cycles accumulate. Recipe-usage × frequency math is a secondary, noisier signal — the companion rarely knows what the user did with the flour outside its own recipes.

First-run baselines are **conservative seeds only**, labeled as such, and thrown away as soon as real data exists. For households whose eating pattern is unusual (e.g., keto/low-carb — generic family baselines would overstate flour/sugar/rice and understate fats), the companion should start nearly blank rather than import misleading defaults.

### Nudges are questions, never assertions

The companion **asks; the user confirms.** It never asserts inventory state it hasn't verified:

- ✅ "You bought that olive oil about 6 weeks ago, and it's usually a ~6-week bottle for you — running low?"
- ❌ "You're out of olive oil."

A confident-but-wrong inventory claim burns trust faster than any other mistake this skill can make.

## THE DIFFERENTIATOR: depletion inference from cooking patterns

No major pantry app infers depletion from how you cook — this is the gap this skill fills. When the companion notices a pattern ("you've made three curries this month"), it can estimate that an ingredient is probably running low.

Rules for doing this honestly:

- **Always label the uncertainty.** It's an estimate built from a pattern, not a measurement.
- **Always phrase it as a question.** "You've made three curries this month — the coconut milk is probably getting low, want me to put it on the list?"
- **Never stack inference on inference** (guessing the buy size *and* the consumption rate *and* the current level from one conversation). One unknown is a question; three unknowns is a guess dressed up.
- **Never present an estimated rate as a verified figure.** If the record has no real cycle, the baseline says so: "I don't have your actual usage yet — is one can of coconut milk about a month for you?"

## Expiry reference table (USDA FoodKeeper, verified basket)

Quality guides, not safety cutoffs — "best by" is the manufacturer's best estimate, not a poison date. Defer to the package date when the user has it; sources disagree on some items, so these ship as ranges.

| Item | Storage life |
|---|---|
| Raw chicken/turkey (fridge / freezer) | 1–2 days / 9–12 months |
| Ground beef (fridge / freezer) | 1–2 days / 3–4 months |
| Cooked leftovers (fridge / freezer) | 3–4 days / 2–3 months |
| Eggs, in shell (fridge) | 3–5 weeks |
| Milk (fridge) | ~1 week past sell-by |
| Butter (fridge / freezer) | 1–3 months / 6–9 months |
| Opened mayonnaise (fridge) | 2 months |
| Condiments (ketchup, mustard, dressings…) | **check the label** — no per-item primary source, so the companion never invents a number |

Shelf-stable basics from the same family of sources: dry pasta ~2 years, white rice ~2 years, canned goods 2–5 years, all-purpose flour ~1 year, baking powder 6–12 months once opened (fizz test tells the truth), brown sugar 4–6 months before it turns into a brick, honey/salt/sugar essentially indefinite when kept dry.

## Starter pantry for beginners

For a new cook setting up a kitchen from nothing. Tier 1 covers almost every weeknight recipe; Tier 2 comes home recipe by recipe.

**Tier 1 — buy first:**
- Kosher salt, whole black peppercorns + a grinder, garlic powder, onion powder
- Extra-virgin olive oil (**small bottle** — opened EVOO is best within 3–6 months), one neutral oil (canola, vegetable, or avocado), butter
- Distilled white vinegar + apple cider vinegar
- Canned diced/crushed tomatoes, canned beans (1–2 kinds you actually eat), broth/stock
- Long-grain white rice, dried pasta (1–2 shapes you like), rolled oats, dry lentils
- All-purpose flour, granulated sugar, baking powder, baking soda, pure vanilla extract

**Tier 2 — add as you cook:** paprika, ground cumin, dried oregano, ground cinnamon, bay leaves, coconut milk, brown sugar, unsweetened cocoa powder, cornstarch, active dry yeast.

Guidance notes worth sharing: whole peppercorns beat pre-ground because ground pepper fades fast and peppercorns keep for years; buy the *small* jar of any spice you don't use weekly; salt types aren't volume-interchangeable (a teaspoon of table salt is saltier than a teaspoon of kosher).

## The master bulk rule

> **Buy in bulk only what your household will finish before it loses quality.** The price tag is not the test — your kitchen's throughput is.

- **Opened EVOO:** 3–6 months at peak. Buy small bottles. Store cool and dark, never next to the stove.
- **Ground spices:** peak flavor ~6–12 months (sources vary; treat as a range). Warehouse jars only for the 2–3 spices you burn through daily; everything else comes home small, or refilled from bulk bins. Smell test beats dates: crush a pinch — weak aroma means replace.
- **Whole spices:** 2–4 years (peppercorns even longer). The one spice purchase worth upgrading to whole, grinder and all.
- **Nuts:** straight to the freezer (9–12 months there; pantry life is short). Taste before baking with them — rancid nuts ruin a dish.
- **Whole-wheat flour:** fridge or freezer from day one (1–3 months at room temp, tops). Start beginners on white AP flour, which bulk-buys just fine.

**Safe warehouse buys:** rice, dry beans/lentils, canned tomatoes/beans, dried pasta, eggs, cheese blocks you grate and freeze yourself, high-turnover spices only.
**Skip in bulk:** ground spices (stale before you finish), giant cooking oils (rancidity), fresh produce without a same-week plan ("you are not buying spinach, you are renting it"), dairy a small household can't finish, whole-wheat flour / brown rice / nuts in pantry storage, bakery multipacks nobody needs twelve of.

**Money math honesty:** compare unit prices (price ÷ ounces), not sticker prices — and the kit never quotes current dollar figures from memory. Fresh local data or labeled illustrative math only.

## Template

- [Pantry inventory sheet](../../templates/pantry-inventory.template.md)
