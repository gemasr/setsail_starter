## Goal

The Pantry screen working, with real data.

## Prompt

```
Read SPEC.md and look at the current code. Implement the Pantry screen: a list of the pantry's ingredients with their quantity and unit (for example "Egg · 6 pcs"), loaded with the sample data. Add the "Add ingredient" button, which opens a form with the name (chosen from the known ingredients) and the quantity, and a "Save" button. Tapping an item lets you edit its quantity. An empty quantity or 0 cannot be saved. If you add an ingredient that already exists, the quantity is added to the same line. If the pantry is empty, show "The pantry is empty". Use the exact texts from SPEC.md. When you finish, build it, run it on the emulator and check the screen using Android CLI, and tell me what you verified.
```

## Checks

- [ ]  You see "Egg · 6 pcs" and "Rice · 1000 g"
- [ ]  You add "Cream" with 250 and "Cream · 250 ml" appears
- [ ]  You add "Egg" with 2 and the line becomes "Egg · 8 pcs" (no duplicate)

If you close and reopen the app, the data goes back to the sample data: that's expected, because it lives in memory.

## If you get stuck

```
Review your implementation against this milestone's checks and fix whatever fails.
```
