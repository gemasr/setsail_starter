## Goal

Find a visual bug by letting the agent look at the app with `android layout` and `android screen capture`.

## Before the prompt

From here on, the app is already built: you start from a checkpoint instead of writing the Pantry, Recipes and Shopping screens yourself.

1. Download the Milestone 3 checkpoint: [dv-mad-step-3.zip](https://github.com/gemasr/sanjis_galley/archive/refs/tags/dv-mad-step-3.zip).
2. Unzip it into a **new folder**. Don't reuse the one from the previous milestones.
3. Open the agent in that folder, in a **new session**. The folder already has `AGENTS.md` and `SPEC.md`.
4. Build and run it on the emulator, with the agent or with `android run`.

## The symptom

Open the recipe **Baratie Ramen**. The "Add missing to shopping list" button doesn't work well: it's hard to see or to tap. The app builds and nothing crashes, so there is no error message to read.

You won't be told the cause. The point is to let the agent find it by looking at the screen.

## Prompt

```
In the detail of the recipe "Baratie Ramen", the "Add missing to shopping list" button doesn't look or behave right. Use android layout and android screen capture to see what the screen looks like on the emulator, find out why, fix it, and check the result with the same commands. Tell me what you found and what you changed.
```

## Checks

- [ ]  The agent used `android layout` and `android screen capture` before touching the code
- [ ]  The agent explains the cause in its own words
- [ ]  In "Baratie Ramen", the button is fully visible and you can tap it
- [ ]  The rest of the app still works

## If you get stuck

```
Show me the layout and the screenshot you are looking at, and tell me what you see in them.
```

If you run out of quota, or you want to compare, the solution is in the branch [dv-mad-step-3-solution](https://github.com/gemasr/sanjis_galley/compare/dv-mad-step-3...dv-mad-step-3-solution). Download its zip, or apply the diff, and move on to the next milestone.
