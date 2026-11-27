# Extra step: move purchased items to the pantry

This step is **optional**, in case you have time left. This time there's no prompt to copy: we tell you what has to happen and you write the prompt.

## Goal

Add a complete feature and check it with a journey: what you mark as purchased in **Shopping** moves to **Pantry**, and the recipes update.

## Before you start

1. Carry on in the Milestone 4 folder. If you didn't do that milestone, download [dv-mad-step-4.zip](https://github.com/gemasr/sanjis_galley/archive/refs/tags/dv-mad-step-4.zip) and unzip it into a **new folder**.
2. Open the agent in that folder, in a **new session**.

## What you have to achieve

- **Shopping** has a `Move purchased to pantry` button (the text is in `SPEC.md`).
- When pressed, the quantities of the purchased ingredients are added to the pantry.
- The pantry still never has two lines for the same ingredient.
- Purchased ingredients disappear from the shopping list; the ones not purchased stay.
- There is a journey in `journeys/` that checks the whole flow, from a recipe with missing ingredients until it shows as `Available`.

## Before writing your prompt

Think about what the agent needs to know and what it already knows from `AGENTS.md` and `SPEC.md`:

- When is the button visible? `SPEC.md` doesn't say: you decide.
- How will you know it finished correctly?
- What don't you want it to do?

## Checks

Close and reopen the app before starting, so you begin from the sample data.

- [ ]  Add the missing ingredients of "Baratie Ramen", mark only "Wheat noodles" as purchased and move it: "Fish stock" stays in **Shopping** and the recipe is missing 1 ingredient
- [ ]  In **Pantry**, add 100 ml of "Fish stock". Then mark "Fish stock" as purchased and move it: "Fish stock · 600 ml" appears on **a single line**
- [ ]  **Shopping** shows "Nothing to buy" and "Baratie Ramen" shows as "Available"
- [ ]  Your journey is in `journeys/` and it passes

## If you get stuck

- Compare your prompt with the ones in the previous milestones: do you say what to do, with which rules and how to check it?
- Ask the agent to review its implementation against the specific check that fails, telling it what you expected and what you saw.
- If it's the journey that fails, ask it to show you which step fails and why.
