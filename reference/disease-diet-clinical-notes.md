# Disease-Diet Clinical Notes — Home Chef Companion Kit v1.0.0

**Reference appendix.** The trial sizes and guideline specifics behind the medical-diet guardrails in the core skill. Consulted only when the user asks for the evidence behind a claim. Behavior rules live in the core skill — this file is evidence only.

---

## 1. Diabetes — ADA Standards of Care, 2026, Section 5

Verified against the ADA's own journal (*Diabetes Care* 2026;49 Suppl. 1, Section 5: "Facilitating Positive Health Behaviors and Well-being to Improve Health Outcomes"):

- **Rec 5.13:** recommend **individualized meal plans** for diabetes prevention and management — nutrient quality, total calories, and metabolic goals kept in mind.
- **Rec 5.14:** eating patterns should emphasize nonstarchy vegetables, whole fruits, legumes, lean proteins, whole grains, nuts and seeds, and low-fat dairy or nondairy alternatives; minimize red meat, sugar-sweetened beverages, sweets, refined grains, and processed/ultraprocessed foods.
- **Rec 5.15:** "Consider reducing carbohydrate intake for **some** adults with diabetes to improve glycemia" — explicitly selective, not blanket.
- **Table 5.2:** "**There is no ideal percentage of calories from carbohydrate, protein, or fat**… macronutrient distribution should be based on an individualized assessment of current eating patterns, preferences, and metabolic goals." **Verify correction applied:** the companion never encodes a macro percentage for diabetes — individualization is the guideline.
- **Rec 5.16–5.17:** supplementation with micronutrients (magnesium, chromium) or herbs/spices (cinnamon, aloe vera) is **not recommended** for glycemic benefits; β-carotene supplementation counseled **against**.
- **Rec 5.10:** provide individualized medical nutrition therapy by referring to a registered dietitian nutritionist (A-level recommendation) — the basis for the companion's RDN referral.

**Glycemic index / glycemic load — contested, not an ADA directive:** the EASD Diabetes and Nutrition Study Group's 2024 evidence review rates the evidence for low-GI/GL diets improving glycemia in type 2 diabetes as "moderate certainty" but notes isolating GI/GL effects "remains challenging." NICE (UK) recommends low-GI carbohydrate sources; Diabetes Canada gives a Grade B for glycemic control. **The current ADA Standards of Care give no specific GI/GL recommendation for medical nutrition therapy.** A 12-month RCT of low-GI education vs. ADA diet education found glycemic differences between arms were small and mostly non-significant by 12 months (PMC2330083). The companion may use GI/GL as a *descriptive recipe cue* ("this lentil soup has a lower glycemic load than white-rice soup because fiber and protein slow glucose rise") — never as a treatment recommendation.

**The companion's lane:** adapt recipes to the user's stated pattern (a carb target range from their RDN, the Diabetes Plate Method — half the plate nonstarchy vegetables, a quarter lean protein, a quarter whole grains or starchy vegetables), show carb estimates per serving, flag high-carb items. It never sets a carb target, predicts blood sugar, adjusts medication, interprets A1C/CGM data, or evaluates whether a meal is "good for diabetes."

---

## 2. Thyroid — the ATA absence-of-guidance finding (verified)

**Verified finding: the American Thyroid Association says almost nothing about diet — and that's the finding.** Primary ATA source checked: the ATA Task Force "Guidelines for the Treatment of Hypothyroidism" (*Thyroid*, 2014; PMC4267409). Its only diet-relevant content is in the dietary-supplement/nutraceutical section:

- "No data support the role of iodine in enhancing thyroid function (patient advised to discontinue use)."
- "No published data… support the claim that ingestion of tyrosine increases the production of thyroid hormone."
- Interaction notes: calcium, iron, and bone meal, bugleweed, red yeast, kelp can affect thyroid-hormone absorption/action; **soy protein "has been studied and may interfere with LT4 absorption."**

**Verify correction applied:** there is no ATA "thyroid diet," no endorsed food list, and no Graves-specific dietary pattern. The companion must not invent thyroid diet guidance — claims about goitrogenic vegetables, selenium dosing, or gluten-free-for-Graves are **not** ATA guidance.

What the companion *can* state (medication facts, not diet advice):

- **Levothyroxine timing — FDA drug labeling (DailyMed):** take on an empty stomach, 30–60 minutes before breakfast; do not take within 4 hours of iron, calcium supplements, or antacids. Coffee/caffeine, soy products, and fiber can impair absorption; take with water only, consistently at the same time daily. Bedtime dosing (≥3 hours after the evening meal) is an ATA-recognized alternative. The companion may surface this *scheduling* information and help plan breakfast around the user's established routine — it never changes dose timing or adjudicates label-vs-habit conflicts.
- **Iodine — the real lever and real harm:** the ATA recommends avoiding supplements containing >500 µg iodine per daily dose. Excess iodine can cause iodine-induced hypo- or hyperthyroidism and induce autoimmune thyroiditis (Medscape, citing ATA). Most of the U.S. is iodine-sufficient; kelp/spirulina products have highly variable iodine content. Never recommend iodine supplementation.
- **Goitrogens and cruciferous vegetables — myth at normal intakes:** glucosinolates in crucifers yield thiocyanate, which can inhibit thyroid hormone synthesis (real mechanism) — but human data at dietary intakes show no thyroid-function effect. The only harm case in the literature is an extreme outlier (an 88-year-old woman eating 1.0–1.5 kg of raw bok choy daily for months). Cooking reduces goitrogenic effects; moderate cooked cruciferous consumption is "generally safe for most people with thyroid issues." The "avoid all cruciferous vegetables" lists contradict the clinical evidence — the companion sides with the evidence.
- **Graves' disease (hyperthyroidism) — honest, limited:** there is no "Graves' diet" in any major guideline. The narrow, evidence-based points: avoid excess iodine (high-dose supplements, kelp — not ordinary eggs/dairy); caffeine doesn't cause hyperthyroidism but can intensify palpitations, tremor, anxiety, and insomnia — reducing it while levels are uncontrolled is symptom management, not disease treatment. A low-iodine diet is a specialized, temporary pre-procedure protocol (mainly before radioactive iodine) prescribed by the medical team, not a lifestyle choice — the companion never starts one. Gluten elimination for Graves' and "anti-inflammatory diet cures Graves'" are speculative/insufficient-evidence claims the companion does not repeat.

---

## 3. Celiac disease and food allergies — CDF/FARE label rules (verified)

### Gluten-free standard

- **FDA final rule (2013, 21 CFR 101.91): <20 ppm gluten.** "Gluten-free" means the food is inherently gluten-free or has no gluten-containing grain ingredient, with any unavoidable gluten below 20 ppm — "the lowest level that scientifically validated analytical methods could reliably detect." The claim is **voluntary**; manufacturers aren't required to test but are legally responsible for meeting the standard. A 2020 companion rule covers fermented/hydrolyzed foods.
- **Regulatory gap:** only wheat is a FALCPA major allergen — barley and rye can hide under "malt extract," "flavorings," or "spices."
- **Celiac Disease Foundation (verified):** it is currently possible for a food to meet the <20 ppm gluten-free standard yet still carry a "may contain wheat or gluten" warning if the manufacturer cannot fully rule out cross-contact. CDF's comment to FDA (May 2026, with its Scientific Advisory Committee, AGA, NASPGHAN, Gluten Intolerance Group, **FARE**, and others): "The **voluntary and unregulated** use of precautionary allergen labeling (PAL) creates serious confusion…" — urging a single standardized evidence-based statement if PAL is adopted.
- **Cross-contact (celiac-center consensus — BIDMC Celiac Center, McMaster Celiac Clinic):** shared fryer/grill and shared pasta water (tested at 33.9–115.7 ppm — **above** the 20 ppm threshold) are real risks; bulk bins are high risk; dedicated GF equipment or toaster bags for toasters, cutting boards, colanders, wooden utensils; no double-dipping shared condiments. One contested nuance: a Boston Children's study found shared-toaster transfer was **<5 ppm** in most samples (below the FDA line) — but the study is contested within the celiac community, and the companion **keeps the dedicated-toaster recommendation** rather than reassuring on one study.
- **Celiac vs. NCGS vs. wheat allergy:** celiac is autoimmune with validated biomarkers and villous atrophy (strong evidence); wheat allergy is IgE-mediated (strong); non-celiac gluten sensitivity has **no validated biomarkers** — diagnosis is by the impractical Salerno criteria (6-week GFD trial then double-blind gluten challenge), many double-blind trials show no gluten-specific response with high nocebo rates, and FODMAPs/amylase-trypsin inhibitors may explain many cases. Grade: contested/preliminary. Never present NCGS as diagnostically equivalent to celiac.

### Food allergies — the Big 9 and precautionary labels

- **The Big 9 (federal law):** FALCPA (2004) established 8; the **FASTER Act (signed April 23, 2021) added sesame as the ninth, effective January 1, 2023**. Current list: milk, eggs, fish, crustacean shellfish, tree nuts, peanuts, wheat, soybeans, sesame.
- **FARE (verified, foodallergy.org):** precautionary labels "are **voluntary and unregulated**" — "If there is no precautionary statement, **don't assume that the food is safe** for you to consume." Advisory/precautionary labeling "is **not regulated in the U.S.** and therefore should not be relied upon to reliably reflect the true allergen content (or lack thereof)."
- **The never-gamble rule's basis:** cross-contact — allergen protein transferred between foods/surfaces — can trigger severe reactions from trace amounts (e.g., a plain burger cross-contacted by a slice of cheese placed on it for less than a second). The companion treats allergen avoidance as safety-critical, never preference-like.

### What the companion can teach

Label literacy: "Certified Gluten-Free" / "gluten-free" on the label (claim-makers are more likely to control cross-contact); avoid vague phrasing like "made with gluten-free ingredients" — a red flag that the manufacturer doesn't test; read labels every time (formulations change); hidden gluten sources (malt/barley, brewer's yeast, "natural flavors" that may hide malt, soy sauce unless tamari/GF). Kitchen cross-contact prevention for both gluten and allergens (separate or thoroughly washed utensils/boards/pans, clean surfaces, sealed dedicated containers, allergen-free foods stored above allergen foods).

---

## 4. AND 2025 — scope limits (verified)

- **Primary text read:** "Vegetarian Dietary Patterns for Adults: A Position Paper of the Academy of Nutrition and Dietetics" (Raj et al., *J Acad Nutr Diet* 2025). Approved January 2025; in effect through **December 31, 2032**.
- **Position (verbatim):** "It is the position of the Academy of Nutrition and Dietetics that, in adults, **appropriately planned** vegetarian and vegan dietary patterns can be nutritionally adequate and can offer long-term health benefits such as improving several health outcomes associated with cardiometabolic diseases."
- **Scope: adults ≥18 who are not pregnant or lactating.** Vegetarian patterns for under-18s, pregnant, or lactating individuals "requires specific guidance… outside the scope of this Position Paper." The companion **refers out** (to a clinician/RDN) for all three groups.
- **Verify correction applied:** the companion's confirmed nutrient list from the 2025 text is **vitamin B12, vitamin D, iron/ferritin, iodine** (vegans may show mild–moderate iodine deficiency; iodized salt helps — seaweed is variable-risk), **choline**, and **calcium/bone health** (lower bone mineral density and increased fracture risk for vegans; reduced ferritin and iodine biomarkers). Several concerns are rated low/very low quality in the paper. The companion does **not** name zinc, omega-3s, or protein as AND-2025-designated concerns (not re-confirmed from the 2025 text).
- **Guardrails:** the companion may state the headline position and flag the confirmed nutrients as needing attention — but never gives supplementation doses or meal plans; "appropriately planned" is the operative word, and the companion is not the planner. Pregnancy, children, athletes, deficiency symptoms, or complex multi-restriction planning all trigger referral.

---

## 5. Psyllium + medication timing — the DailyMed basis

**Verified:** DailyMed (NLM's FDA drug-label database), official Drug Facts label for psyllium-husk fiber laxative (Metamucil): "**Ask a doctor or pharmacist before use if you are taking any other drug. Take this product 2 or more hours before or after other drugs. Laxatives may affect how other drugs work.**" Also on the label: choking warning (take with adequate fluid) and allergy alert for psyllium sensitivity.

This is FDA-mandated OTC label language — the direct, primary basis for the companion's "ask a pharmacist about timing psyllium with medications" referral. Secondary literature describes the gel-matrix mechanism (psyllium can reduce absorption of some oral drugs like lithium, digoxin, carbamazepine; evidence rated weak/minor and drug-specific) — but the label alone is sufficient authority, and the companion's only move is the referral, never a timing rule.

**Kitchen facts:** psyllium is the standard gluten-stand-in in keto/low-carb/GF baking — structure, elasticity, binding, moisture retention; virtually zero net carbs. Culinary consensus: ~1–3 tbsp per recipe; mix into **dry** ingredients before adding liquids; too little water → crumbly, too much → gummy; powdered ≠ whole husk 1:1 (powder ≈ 85% of whole-husk amount). Always take with plenty of water (label warnings: taken dry or with too little water it can swell in the throat and cause choking or blockage).

---

## 6. When the companion must suggest a clinician or RDN

Trigger moments (with the general phrasing the companion uses):

- The user asks what diet they *should* follow for a condition: "That's a medical-nutrition question, and the safest person to answer it is your doctor or a registered dietitian — they know your labs and meds. What I can do is cook inside whatever plan you and they land on."
- Symptom descriptions: "I can't diagnose anything from symptoms — please bring that to your doctor soon. I'm here for the cooking side whenever you have a plan from them."
- Allergen/gluten uncertainty: "I can't confirm this is safe — the label doesn't show a warning, but those warnings are voluntary, so absence of one isn't proof. Here's what to check: the full ingredient list, the manufacturer's allergen statement online or by phone, and whether it's made on shared lines. When in doubt, skip it."
- Medication timing: "The label says [quote it] — that's straight from the FDA labeling. If your routine makes that hard, your pharmacist or doctor can help you adjust; I won't change medication timing myself."
- MS-related: "If you and your neurologist or dietitian settle on a pattern, tell me and I'll adapt anything to fit it."
- Diabetes-specific: diabetes on insulin or sulfonylureas + carb restriction (hypoglycemia risk); kidney disease; pregnancy; eating-disorder history; children; known lipid disorders, gallbladder disease, pancreatitis, gout, liver disease; symptoms on a diet (chest pain, fainting, persistent GI distress); considering restrictive elimination long-term; any medication with food interactions (e.g., warfarin + vitamin K shifts).

## Sources

- ADA Standards of Care in Diabetes—2026, Section 5, *Diabetes Care* 2026;49 Suppl. 1 (Recs 5.10, 5.13–5.17, Table 5.2).
- ATA Task Force, "Guidelines for the Treatment of Hypothyroidism," *Thyroid* 2014 (PMC4267409).
- DailyMed (NIH), levothyroxine sodium tablets FDA labeling; DailyMed, psyllium-husk fiber laxative Drug Facts label (Metamucil).
- FDA gluten-free labeling final rule (78 FR 47154; 21 CFR 101.91); FDA companion rule on fermented/hydrolyzed foods (2020).
- Celiac Disease Foundation: 20-ppm standard explainer (Dec 2025); comment to FDA on PAL reform (May 2026).
- FARE: food-labeling resource; "Food Allergy Facts and Statistics" (July 2024); PAL explainer blog (all foodallergy.org, voluntary-and-unregulated position).
- FASTER Act (sesame, 9th allergen, effective Jan 1, 2023); FALCPA (2004).
- BIDMC Celiac Center, "Avoiding Cross-Contact with Gluten"; McMaster Celiac Clinic cross-contamination checklist; BC Celiac Association newly-diagnosed food safety checklist.
- Weisbrod et al. (Boston Children's) shared-toaster / pasta-water cross-contamination data (via The Celiac Scene).
- Salerno Experts' Criteria (*Nutrients* 2015); Cambridge / Nutrition Research Reviews NCGS overview.
- EASD Diabetes and Nutrition Study Group 2024 evidence review, GI/GL in type 2 diabetes (PMC11519289); low-GI vs ADA diet RCT, 12 months (PMC2330083).
- Johns Hopkins Patient Guide to Diabetes (ADA summary: no single diet; carb counting; Diabetes Plate Method).
- Raj et al., *Vegetarian Dietary Patterns for Adults* (AND position paper), *J Acad Nutr Diet* 2025.
- St. Louis Children's Hospital FAME Toolkit (cross-contact, label reading, epinephrine-then-911).
- Medscape: "Thyroid Diet: What's the Evidence?" (ATA iodine >500 µg/day guidance); "The Thyroid Diet: Is There Such a Thing?" (goitrogens).
- Healthline / Newtrist hyperthyroidism diet explainers (narrow agreed points; gluten-elimination-for-Graves' caveat).
