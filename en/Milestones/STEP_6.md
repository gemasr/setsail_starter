## Goal

Check the app with journeys that describe what a user does. In this milestone the agent writes the journeys and runs them: pay attention to how it writes them, which Android CLI commands it uses to walk through the app and how it reports the result.

Journeys are saved in the `journeys/` folder at the project root, as `AGENTS.md` indicates.

You'll see that the XML steps start with English verbs (`Tap`, `Verify`...). That's the format Android CLI uses: actions that start with `Check` or `Verify` are treated as checks, and the rest as interactions.

## Level 1: a simple journey

```
Write a journey that checks the following and run it: in the recipe "Baratie Ramen", when pressing "Add missing to shopping list", the notice "Added to the shopping list" appears and in Shopping "Wheat noodles · 200 g" and "Fish stock · 500 ml" appear. Save it in journeys/, use Android CLI to run it and tell me the result.
```

## Level 2: checking a state change

```
Write a journey that checks the following and run it: when adding 250 ml of cream to the pantry, the recipe "Mellorine for Nami and Robin" goes from "Missing 1 ingredient" to "Available". Use Android CLI to run it.
```

## Level 3: the hard case

```
Write and run a journey that checks the following: I add to the shopping list the missing ingredients of "Baratie Ramen" and then those of "Thousand Sunny Stew"; in Shopping "Fish stock · 800 ml" must appear on a single line. Use Android CLI to run it.
```

This is the one that most often fails the first time: repeated quantities must be added up on a single line.

## Checks

- [ ]  There is a journey in `journeys/` for each level
- [ ]  The journeys run and pass
- [ ]  If one fails, ask the agent to explain why and fix it

## If you get stuck

```
Show me which step of the journey fails and why.
```

If a step fails because the selector matches several elements (for example, a text that appears in a title and in a button), ask the agent:

```
Use a more specific selector, or check that step with a screenshot.
```
