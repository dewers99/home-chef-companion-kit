# meal-planning

**Version:** 1.0.0
**Description:** Weekly meal plans that build themselves into shopping lists — plan, shop, cook, review.

---

## The universal flow

Every week runs the same friendly loop:

1. **Plan** — pick meals for each day (suggest, don't dictate).
2. **Auto-generate the shopping list** — from the plan, cross-checked against the pantry.
3. **Cook** — the week runs its course; skipped meals just get un-planned.
4. **Review** — "what's left over?" feeds the next plan. Close the week, open a new one.

A chat planner needs the same escape hatches an app has: a meal slot can hold a **recipe** *or* a **note** ("leftovers," "pizza night," "eating out"), and only recipe-linked slots feed the shopping list. Never force every day to be a recipe — that's how lists over-buy and plans die by Wednesday.

## Running a plan session

1. **Eat-this-first check.** Start by asking what's already in the fridge/freezer/pantry that needs using. The plan builds on that pile before anything new — it keeps the list shorter and the waste bin emptier.
2. **Constraints + headcount.** Confirm dietary patterns (one line from the profile — never re-ask what's stored), servings per meal, and any "not this week" vetoes.
3. **Suggest, don't dictate.** Offer meals — theme nights (taco night, pasta night, soup night, slow-cooker Sunday…) and a favorites shortlist beat blank pages every time. Let repetition happen; a plan the family actually likes is better than a plan that's novel and unused.
4. **Lock the week.** Confirm the lineup before generating the list, and give the user an easy revision loop ("swap Tuesday's chicken for the beef soup").
5. **Generate the list** (see aggregation rules below), tag it by trip, and hand it over.

## Shopping-list aggregation rules

- **Scale FIRST, merge second.** Scale every recipe to the servings that will actually be cooked *before* merging quantities. Never re-scale after merging.
- **Sum compatible units.** 200 g butter + 150 g butter = 350 g.
- **Keep incompatible units separate.** "2 cloves garlic" and "1 tsp garlic powder" are different products — two lines, never forced together.
- **Keep different forms separate.** Fresh tomatoes vs. canned tomatoes stay on separate lines.
- **Round up to purchasable amounts.** 1.3 onions → 2. 0.6 lb beef → 1 lb.
- **Express in buy-units.** 37 tbsp butter → 5 sticks; 19 eggs → 2 dozen. "1.3 onions" is math; "2 onions" is a grocery list.
- **Staples exclusion list.** The user keeps a list of items assumed always on hand (salt, oil, flour, basic spices…) that *never* appear on the list. Ask once, save it, respect it forever. Before generating, offer the "check what you have" step — anything already on hand comes off.
- **Traceability.** Keep a by-recipe breakdown available alongside the combined list so the shopper can answer "which recipe is this for?" in the aisle.

## Two-tier trip tagging

Most households shop in two modes, so the list gets tagged by trip:

- **Bulk run** — the big periodic haul (Sam's Club / Costco / warehouse store): staples, proteins, frozen goods, household items.
- **Fresh run** — the weekly shop: produce, dairy, meal-specific items that won't keep.

Learn the household's split from the profile ("bulk at Sam's Club, fresh weekly at the grocery store") and tag every line with its trip. That one split is more useful than any aisle sort. Carry brand preferences as per-line notes ("Member's Mark," "store brand fine," "no antibiotics").

## Output shapes

- **Chat version:** a markdown checklist (`- [ ]`) grouped by store section, in the user's store order: Produce → Meat/Seafood → Dairy → Frozen → Pantry/Dry goods → Spices/Baking → Household/Other. (Frozen last — shop the cold aisle closest to checkout.)
- **Paste block:** a compact plain-text version of the same list for store apps or notes. One item per line, no decoration.
- **Print view:** an Item / Qty / Section / Notes table — room for prices, brand notes, coupon flags.
- **For online ordering/pickup:** be specific — full product names, brand, and size ("Great Value frozen broccoli, 32 oz"), because there's no shelf to browse.
- Quantity estimate note: if the profile has no price anchors, don't invent totals. If it does, label estimates as estimates — prices drift.

## Leftovers: cook once, eat twice

Flag intentional leftovers as part of the plan: double a recipe and schedule the second half as a *different* meal. High performers: soups, stews, curries, chili, pasta sauces, roasted proteins. Low performers: crispy-coated foods, delicate fish, pre-dressed salads.

Key rule: **reinvent, don't repeat** — the second meal changes format (taco meat → taco salad; roast chicken → chicken chili). Leftovers land better when they don't look like themselves.

Also flag **ingredient leftovers**, not just meal leftovers: if a recipe uses half a bunch of cilantro or one tablespoon from a jar, deliberately assign the remainder to another dish, a freezer bag, or substitute something already owned. This is the thing apps can't do — flag it.

## Buildable base meals (mixed-diet households)

For a household where people eat differently (e.g., one keto cook, a family that isn't):

1. **Cook the low-carb base for everyone.** Don't cook two dinners.
2. **Carbs on the side.** Bread, rice, pasta, tortillas — served separately, assembled per person.
3. **Buildable meals** where each person assembles to their own level: taco bowls, salads, soups with toppings, burger plates.
4. **Stealth swaps** that don't change the family experience: cauliflower rice half-and-half with regular rice, heavy cream instead of milk in mashes/soups.
5. **Batch-cook and freeze** divergent meals (a carb-heavy lasagna for the kids) so weeknights stay one-cook affairs.

Overlapping ingredients simplify the list — eggs, butter, heavy cream, cheese, meats, low-carb veg form a common core, so even mixed plans share most of the list.

## Templates

- [Weekly plan grid](../../templates/meal-plan.template.md)
- [Shopping list](../../templates/shopping-list.template.md)
