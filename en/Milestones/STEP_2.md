## Goal

Give the agent up-to-date knowledge with a skill, and use it to set up the navigation skeleton of the app.

## Before the prompt

The agent will use the `navigation-3` skill, which teaches it how to set up Jetpack Navigation 3 correctly.

1. Check that the skill is installed:

   ```
   android skills list
   ```

2. If `navigation-3` is not in the list, install it:

   ```
   android skills add navigation-3
   ```

3. Open the agent in the project folder, in a **new session**.

## Prompt

```
Use the navigation-3 skill. Look at the project's current code and set up the app skeleton: a bottom navigation bar with three destinations (Pantry, Recipes, Shopping), in that order, each with a placeholder screen that shows only its title. The initial destination is Recipes. Use the exact texts from SPEC.md. Do not implement anything else. When you finish, build it, run it on the emulator and check the screen using Android CLI, and tell me what you verified.
```

## Checks

- [ ]  The agent says it used the `navigation-3` skill
- [ ]  The app builds and opens on **Recipes**
- [ ]  You can navigate between **Pantry**, **Recipes** and **Shopping**

## If you get stuck

```
Review your implementation against the milestone prompt and tell me what is missing.
```
