## Goal

Check the app with journeys that describe what a user does. In this milestone the agent runs a journey that is already written, and then you can ask it to write its own: pay attention to which Android CLI commands it uses to walk through the app and how it reports the result.

Journeys are saved in the `journeys/` folder at the project root, as `AGENTS.md` indicates.

Steps that start with `Check` or `Verify` are assertions; the rest are interactions.

## Before the prompt

Start from the Milestone 4 checkpoint, which already includes the level 1 journey in `journeys/`:

1. Download [dv-mad-step-4.zip](https://github.com/gemasr/sanjis_galley/archive/refs/tags/dv-mad-step-4.zip) and unzip it into a **new folder**.
2. Open the agent in that folder, in a **new session**.

There is no `android` command that runs a journey by itself: the agent reads the XML and walks through the app with `android input`, `android layout` and `android screen capture`, as the `android-cli` skill explains.

## Level 1: run a journey (required)

Open `journeys/baratie-ramen-shopping.xml` and read it first: it's plain XML.

```
Run the journey in journeys/baratie-ramen-shopping.xml using Android CLI and tell me the result. Show me which Android CLI commands you used for each step.
```

## Level 2 (optional): checking a state change

```
Write a journey that checks the following and run it: when adding 250 ml of cream to the pantry, the recipe "Mellorine for Nami and Robin" goes from "Missing 1 ingredient" to "Available". Use Android CLI to run it.
```

## Level 3 (optional): the hard case

```
Write and run a journey that checks the following: I add to the shopping list the missing ingredients of "Baratie Ramen" and then those of "Thousand Sunny Stew"; in Shopping "Fish stock · 800 ml" must appear on a single line. Use Android CLI to run it.
```

This is the one that most often fails the first time: repeated quantities must be added up on a single line.

## Checks

- [ ]  Level 1 runs and passes
- [ ]  You can say which Android CLI commands the agent used for each step
- [ ]  If you did levels 2 and 3, there is a journey in `journeys/` for each and they pass
- [ ]  If one fails, ask the agent to explain why and fix it

## If you get stuck

```
Show me which step of the journey fails and why.
```

If a step fails because the selector matches several elements (for example, a text that appears in a title and in a button), ask the agent:

```
Use a more specific selector, or check that step with a screenshot.
```
