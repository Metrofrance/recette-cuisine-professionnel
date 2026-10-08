# 👨‍🍳 METRO France – Professional Chef Recipes Dataset (Recipes & Ingredients)

## Description

This dataset gathers **411 professional recipes** published by **METRO France** on metro.fr ("Recettes de chefs"), created by chefs and METRO partners for restaurants, cafés, caterers and food service professionals.

Each recipe includes its **full ingredient list with quantities** and its **step-by-step preparation method**, plus servings, duration, difficulty and, when available, the name of the chef.

It covers **17 categories**: desserts, fish & seafood, meat, cocktails, Asian cuisine, snacking, Italian cuisine, daily specials, pizzas, winter dishes, sauces, plant-based cuisine, cheese dishes, sharing boards, receptions, burgers and sustainable cuisine.

It is designed for:
- menu creation and recipe inspiration for restaurants,
- culinary training,
- recipe search, food and cooking applications,
- ingredient analysis and purchasing planning,
- AI assistants and RAG systems,
- open data projects.

The dataset is available in **CSV** and **LLM-optimized JSON** formats.

---

## Key figures

- 411 recipes, 5,967 ingredient lines
- 17 categories: Desserts (65), Fish & seafood (55), Meat (46), Cocktails (42), Asian cuisine (28), Snacking (23), Italian cuisine (21), Daily specials (21), Pizzas (20), Winter dishes (19), Sauces (18), Plant-based (11), Cheese (10), Sharing boards (9), Receptions (9), Burgers (8), Sustainable cuisine (6)
- 60 named chefs and partners, including Victor Delpierre (21 recipes), Alex Cook (12) and Wilfried Romain (11)
- Difficulty: 193 easy, 156 medium, 45 hard
- Median recipe: 12 ingredients, 10 steps, 45 minutes, 4 servings
- Most used ingredients: butter (in 174 recipes), cream (163), lemon or lime (142), sugar (120), olive oil (112), garlic (100)

---

## Dataset content

- `metro_chef_recipes.csv`: one row per recipe
- `metro_chef_recipes_ingredients.csv`: one row per ingredient line (linked by `recipe_id`)
- `metro_chef_recipes.json`: structured and hierarchical format (one object per recipe, with nested ingredients and steps)

### Main structure (recipes CSV)

- `recipe_id`: unique identifier (METRO-REC-0001…)
- `title`
- `category_slug`, `category_fr`, `category_en`
- `chef`
- `intro`: introduction text
- `servings`
- `duration_text` (as displayed) and `duration_minutes`
- `difficulty_fr` / `difficulty_en`
- `ingredient_count`, `step_count`
- `ingredients`: full ingredient list (separated by " | ")
- `steps`: numbered preparation steps
- `summary_fr` / `summary_en`: one-sentence description
- `url`: recipe page on metro.fr
- `source`

### Main structure (ingredients CSV)

- `recipe_id`, `recipe_title`, `category_fr`
- `position`: order in the recipe
- `section`: sub-preparation (e.g. "POUR LA PÂTE")
- `quantity`: quantity and unit as displayed (e.g. "200g", "3 cuil. à soupe")
- `ingredient`: ingredient name
- `raw_line`: full line as displayed
- `url`

### Main structure (JSON)

- `recipe_id`, `title`, `category` (slug, fr, en), `chef`, `intro`
- `servings`, `duration` (text, minutes), `difficulty` (fr, en)
- `ingredients`: section, quantity, ingredient, raw
- `steps`: step number, section, text
- `summary_fr`, `summary_en`, `url`, `source`

Recipe content (titles, ingredients, steps) is in **French**, as published on metro.fr.

---

## Use cases

- Menu design and daily specials for restaurants
- Culinary schools and kitchen staff training
- Recipe search engines and cooking apps
- Ingredient and purchasing analysis for food service
- AI-powered assistants and RAG pipelines
- Open data and research projects

---

## Methodology

- Data collected from the public "Recettes de chefs" pages of metro.fr (17 categories)
- Recipe content kept as published (French); quantities and units kept as displayed
- Standardization of servings, duration in minutes, difficulty level and chef names; addition of English category labels and summaries
- Only recipes with both an ingredient list and preparation steps are included
- Structured for **human and machine consumption**
- No personal data included

---

## License

CC-BY 4.0 – Attribution: METRO France (metro.fr)

---

## Disclaimer

Data represents a snapshot in time (October 2026) and may change. Recipes published on metro.fr may be added, updated or removed.
No guarantee of completeness or permanent accuracy.

---

# 👨‍🍳 METRO France – Recettes de chefs pour professionnels (recettes et ingrédients)

## Description

Ce dataset rassemble **411 recettes professionnelles** publiées par **METRO France** sur metro.fr (« Recettes de chefs »), créées par des chefs et partenaires METRO pour les restaurateurs, cafés, traiteurs et professionnels de la restauration.

Chaque recette comprend sa **liste complète d'ingrédients avec les quantités** et son **déroulé de préparation étape par étape**, ainsi que le nombre de portions, la durée, la difficulté et, quand il est indiqué, le nom du chef.

Il couvre **17 catégories** : desserts, poissons et fruits de mer, viandes, cocktails, cuisine asiatique, snacking, cuisine italienne, plats du jour, pizzas, plats d'hiver, sauces, cuisine végétale, fromages, planches apéritives, réceptions, burgers et cuisine durable.

Il est destiné à des usages de :
- création de cartes et inspiration culinaire pour les restaurants,
- formation en cuisine,
- recherche de recettes, applications culinaires,
- analyse des ingrédients et planification des achats,
- systèmes RAG et applications IA,
- projets open data.

Les données sont structurées et disponibles en **CSV** et **JSON optimisé pour les LLMs**.

---

## Chiffres clés

- 411 recettes, 5 967 lignes d'ingrédients
- 17 catégories : Desserts (65), Poissons et fruits de mer (55), Viandes (46), Cocktails (42), Cuisine asiatique (28), Snacking (23), Cuisine italienne (21), Plats du jour (21), Pizzas (20), Plats d'hiver (19), Sauces (18), Cuisine végétale (11), Fromages (10), Planches apéritives (9), Réceptions (9), Burgers (8), Cuisine durable (6)
- 60 chefs et partenaires cités, dont Victor Delpierre (21 recettes), Alex Cook (12) et Wilfried Romain (11)
- Difficulté : 193 faciles, 156 moyennes, 45 difficiles
- Recette médiane : 12 ingrédients, 10 étapes, 45 minutes, 4 portions
- Ingrédients les plus utilisés : beurre (présent dans 174 recettes), crème (163), citron ou citron vert (142), sucre (120), huile d'olive (112), ail (100)

---

## Contenu du dataset

- `metro_chef_recipes.csv` : une ligne par recette
- `metro_chef_recipes_ingredients.csv` : une ligne par ingrédient (reliée à la recette par `recipe_id`)
- `metro_chef_recipes.json` : format structuré et hiérarchique (un objet par recette, avec ingrédients et étapes imbriqués)

### Structure principale (CSV recettes)

- `recipe_id` : identifiant unique (METRO-REC-0001…)
- `title` : titre de la recette
- `category_slug`, `category_fr`, `category_en` : catégorie
- `chef` : chef ou partenaire
- `intro` : texte d'introduction
- `servings` : nombre de portions
- `duration_text` (tel qu'affiché) et `duration_minutes`
- `difficulty_fr` / `difficulty_en` : difficulté
- `ingredient_count`, `step_count` : nombre d'ingrédients et d'étapes
- `ingredients` : liste complète des ingrédients (séparés par « | »)
- `steps` : étapes de préparation numérotées
- `summary_fr` / `summary_en` : description en une phrase
- `url` : page de la recette sur metro.fr
- `source`

### Structure principale (CSV ingrédients)

- `recipe_id`, `recipe_title`, `category_fr`
- `position` : ordre dans la recette
- `section` : sous-préparation (ex. « POUR LA PÂTE »)
- `quantity` : quantité et unité telles qu'affichées (ex. « 200g », « 3 cuil. à soupe »)
- `ingredient` : nom de l'ingrédient
- `raw_line` : ligne complète telle qu'affichée
- `url`

### Structure principale (JSON)

- `recipe_id`, `title`, `category` (slug, fr, en), `chef`, `intro`
- `servings`, `duration` (texte, minutes), `difficulty` (fr, en)
- `ingredients` : section, quantité, ingrédient, ligne brute
- `steps` : numéro, section, texte
- `summary_fr`, `summary_en`, `url`, `source`

Le contenu des recettes (titres, ingrédients, étapes) est en **français**, tel que publié sur metro.fr.

---

## Cas d'usage

- Construction de cartes et de suggestions du jour
- Écoles de cuisine et formation des équipes en cuisine
- Moteurs de recherche de recettes et applications culinaires
- Analyse des ingrédients et des achats en restauration
- Alimentation de modèles IA (RAG, agents, assistants)
- Projets open data et recherche

---

## Méthodologie

- Collecte à partir des pages publiques « Recettes de chefs » de metro.fr (17 catégories)
- Contenu des recettes conservé tel que publié (en français) ; quantités et unités conservées telles qu'affichées
- Harmonisation des portions, de la durée en minutes, du niveau de difficulté et des noms de chefs ; ajout des libellés de catégories et des résumés en anglais
- Seules les recettes disposant d'une liste d'ingrédients et d'étapes de préparation sont incluses
- Structuration orientée **machine + humain**
- Aucune donnée personnelle

---

## Licence

CC-BY 4.0 – Attribution : METRO France (metro.fr)

---

## Avertissement

Les informations peuvent évoluer dans le temps : des recettes peuvent être ajoutées, modifiées ou retirées de metro.fr.
Ce dataset représente un état à date (octobre 2026), sans garantie d'exhaustivité ou d'exactitude permanente.

