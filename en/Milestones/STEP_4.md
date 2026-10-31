## Goal

See which recipes can be made and which ingredients are missing.

## Prompt

```
Read SPEC.md and look at the current code. Implement the Recipes screen and the recipe detail screen. In Recipes, a list of cards with the name, the short description and a label: "Available" if all the ingredients are in the pantry in sufficient quantity, or "Missing N ingredients" ("Missing 1 ingredient" in the singular) if not. The label updates when the pantry changes. Tapping a recipe opens its detail, with a back arrow: name, description, the same label, the "Ingredients" section (each line with quantity and unit; the missing ones highlighted with color and with text, indicating the shortfall, for example "Chicken · 500 g (missing 500 g)") and the "Steps" section as a numbered list. Do not add the add-to-shopping button yet. Use the exact texts from SPEC.md. When you finish, build it, run it on the emulator and check the screen using Android CLI, and tell me what you verified.
```

## Checks

- [ ]  There are 6 recipes; "Sanji's Salmon Onigiri" and "Going Merry Potato Omelette" show **Available**
- [ ]  "Thousand Sunny Stew" shows **Missing 3 ingredients**
- [ ]  In "Luffy's Giant Meat" the chicken is highlighted with "missing 500 g"
- [ ]  If you add "Cream" 250 to the pantry, "Mellorine for Nami and Robin" becomes **Available**

## Expected result with the initial data

| Recipe | Status | Missing |
| --- | --- | --- |
| Sanji's Salmon Onigiri | Available | n/a |
| Going Merry Potato Omelette | Available | n/a |
| Luffy's Giant Meat | Missing 1 ingredient | Chicken 500 g |
| Mellorine for Nami and Robin | Missing 1 ingredient | Cream 250 ml |
| Baratie Ramen | Missing 2 ingredients | Wheat noodles 200 g, Fish stock 500 ml |
| Thousand Sunny Stew | Missing 3 ingredients | Pork 400 g, Carrot 3 pcs, Fish stock 300 ml |

## If you get stuck

```
Review your implementation against the expected result table and fix the differences.
```
