# Recipe share file

<!-- Companion guidance: this is the share contract (home-chef-recipe/v1).
     Generate this file when the user asks to share a recipe with someone in
     their household. Fill the frontmatter from the recipe card and the user
     profile (author, tested date). The body is the recipe itself — it must
     read as a clean, complete recipe to a human who has never seen the kit.
     See skills/recipe-delivery/SKILL.md "Sharing recipes" for the export and
     import flows. -->

---
share_format: home-chef-recipe/v1
name: <Recipe name>
# Who created/shared this. A real name — it travels with the recipe.
author: <Your name>
# user-supplied | companion-developed | originally from: ____
source: <source>
# Last date this recipe was tested in a real kitchen, YYYY-MM-DD.
tested: <YYYY-MM-DD>
# Increment when the recipe itself changes (not when it's re-shared unchanged).
version: 1
# v1 default: household-only. The companion asks before forwarding outside
# the household. (Future scopes may use open licenses like CC-BY-NC.)
license: household-only
# How much this makes, as tested ("4 servings", "one 14-inch crust").
recipeYield: <yield>
# ISO 8601 durations (PT20M = 20 minutes, PT1H30M = 1 hour 30 minutes).
prepTime: <PT20M>
cookTime: <PT25M>
# Cuisine and category use schema.org names (recipeCuisine, recipeCategory).
recipeCuisine: <cuisine>
recipeCategory: <appetizer | main | side | dessert | ...>
# Free-text tags for search.
keywords: [<tag>, <tag>]
# schema.org enumerated diets where they apply — full URIs, e.g.
# https://schema.org/VegetarianDiet — from the RestrictedDiet enumeration
# (Diabetic, GlutenFree, Halal, Hindu, Kosher, LowCalorie, LowFat,
# LowLactose, LowSalt, Vegan, Vegetarian). Leave empty if none apply.
suitableForDiet: []
# Kit extension: diets the schema.org enumeration doesn't cover
# (keto, low-carb, ...). Tags, not folders.
diet_fit: [<tag>, <tag>]
# Equipment the recipe actually needs.
equipment: [<item>, <item>]
# Kit extension: oven behavior observed while testing. Record the raw facts
# (temps, times, rack position) — never a diagnosis ("our oven runs hot").
# The import flow adapts from facts, not from conclusions.
oven_notes: "<facts>"
# Kit extension: things tried and rejected, with reasons in the body notes.
rejected: []
---

# <Recipe name>

## Ingredients

- qty — item, with prep notes ("1 onion, diced")

## Steps

1. Step text with timings and temps inline ("bake 25–30 min at 375°F").

## Notes / Substitutions

- Notes, rescue notes, what was changed and liked.
- Sweetener behavior observed: ____ (only if tested)
