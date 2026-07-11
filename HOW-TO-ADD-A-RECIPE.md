# How to add or change a recipe

Everything lives in this repo. You only ever touch two kinds of files:

- `recipes.json` — the master list (the app's table of contents)
- `recipes/<id>.md` — one file per recipe, holding the actual content

You never need to edit `index.html`. That's the app itself.

---

## To REVISE an existing recipe

1. Open `recipes/` and click the recipe file (e.g. `recipes/chili.md`).
2. Click the pencil ✏️ (Edit) button on GitHub.
3. Change the ingredient or step.
4. Scroll down, click **Commit changes**.

That's it — the site updates within a minute. If you only changed the time or
servings (not the steps), edit those in `recipes.json` instead, since the chips
at the top of a recipe come from there.

---

## To ADD a new recipe

**Step 1 — create the recipe file.**
Copy `recipes/example-recipe.md`, rename it to something short and lowercase with
dashes (this becomes the `id`), e.g. `banana-bread.md`. Replace the content.

**Step 2 — add one line to `recipes.json`.**
Open `recipes.json` and add an entry. Copy an existing block and change the values:

```json
{
  "id": "banana-bread",
  "title": "Banana Bread",
  "category": "Baking",
  "cuisine": "American",
  "emoji": "🍞",
  "time": "60 min",
  "servings": 8
}
```

- `id` must exactly match the filename without `.md` (`banana-bread.md` → `"banana-bread"`).
- Separate entries with a comma. The last entry has **no** trailing comma.
- `emoji`, `time`, and `servings` are optional. `title`, `category`, and `cuisine`
  are what the home screen groups and sorts by.

Commit both changes and the new card appears.

---

## The fields explained

| Field      | What it does                                                    |
|------------|-----------------------------------------------------------------|
| `id`       | Links the list entry to its `.md` file. Must match the filename. |
| `title`    | Shown on the card and at the top of the recipe.                 |
| `category` | Breakfast, Lunch, Dinner, Side, Dessert, Drinks, etc.           |
| `cuisine`  | Italian, Mexican, Thai, American, etc.                          |
| `emoji`    | Little icon on the card (optional).                             |
| `time`     | Shown as a chip on the recipe page (optional).                  |
| `servings` | Shown as a chip on the recipe page (optional).                  |

The home screen has a **By Category / By Cuisine** toggle. Both views group the
cards into alphabetized sections using these fields, so keep the spelling
consistent (e.g. always "Dessert", not sometimes "Desserts").

---

## Writing the recipe content (Markdown)

Markdown is just text with a few marks. The pattern:

```markdown
# Recipe Name

One friendly line, optional.

## Ingredients

- first ingredient
- second ingredient

## Steps

1. Do this.
2. Then this.

## Notes

Anything extra.
```

- `#` = big title, `##` = section heading.
- `-` = a bullet, `1.` = a numbered step.
- Blank lines separate paragraphs.

No commas or quotes to worry about here — Markdown is forgiving. The strict-punctuation
part is only in `recipes.json`.
