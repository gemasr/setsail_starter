## Goal

See how the agent finds and installs a skill to get up-to-date knowledge, and how it uses it to set up the navigation skeleton of the app.

## Before the prompt

The agent needs the `navigation-3` skill, which teaches it how to set up Jetpack Navigation 3 correctly. **Don't install it yourself**: the prompt asks the agent to find it and install it with Android CLI.

Open the agent in the project folder, in a **new session**.

## Prompt

```
Use Android CLI to search for a Navigation 3 skill. If you don't have it installed, install it. Read the skill and use it. Look at the project's current code and set up the app skeleton: a bottom navigation bar with three destinations (Pantry, Recipes, Shopping), in that order, each with a placeholder screen that shows only its title. The initial destination is Recipes. Use the exact texts from SPEC.md. Do not implement anything else. When you finish, build it, run it on the emulator and check the screen using Android CLI, and tell me what you verified.
```

## Checks

- [ ]  The agent searched for the skill with `android skills find`
- [ ]  The agent installed `navigation-3` with `android skills add`, or checked that it already had it
- [ ]  The agent read the skill before writing code
- [ ]  The app builds and opens on **Recipes**
- [ ]  You can navigate between **Pantry**, **Recipes** and **Shopping**

## If you get stuck

```
Review your implementation against the milestone prompt and tell me what is missing.
```
