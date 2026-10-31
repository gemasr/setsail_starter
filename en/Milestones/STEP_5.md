## Goal

Turn what's missing into a shopping list.

## Prompt

```
Read SPEC.md and look at the current code. Implement the Shopping screen and the button in the recipe detail. In the detail, add the "Add missing to shopping list" button, visible only if ingredients are missing: when pressed, the missing ingredients are added to the shopping list with their shortfall as the quantity, and the notice "Added to the shopping list" is shown. If an ingredient is already in the list and not purchased, the quantity is added to the same line (it is not duplicated). In Shopping, a list with quantity and unit and a checkbox to mark as purchased; purchased items are shown crossed out and at the end. If there is nothing, show "Nothing to buy". Use the exact texts from SPEC.md. When you finish, build it, run it on the emulator and check the screen using Android CLI, and tell me what you verified.
```

## Checks

Close and reopen the app before starting, so the shopping list is empty. If you press the button more than once on the same recipe, the quantities keep adding up: that's expected.

- [ ]  In "Baratie Ramen", pressing the button shows the notice and in **Shopping** "Wheat noodles · 200 g" and "Fish stock · 500 ml" appear
- [ ]  Also adding the missing ingredients of "Thousand Sunny Stew" leaves "Fish stock · 800 ml" on **a single line**
- [ ]  Marking "Wheat noodles" as purchased shows it crossed out and at the end
- [ ]  In "Sanji's Salmon Onigiri" (available) the button does not appear

## Optional extra

```
Add a "Move purchased to pantry" button in Shopping: it adds those quantities to the pantry and removes them from the list.
```

## If you get stuck

```
Review your implementation against this milestone's checks, especially that repeated quantities are added up on a single line.
```
