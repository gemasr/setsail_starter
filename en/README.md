# Set Sail to the Grand Line

A workshop to learn how to work with **Android CLI** and **coding agents** by building an Android app from start to finish.

You won't write the code by hand. You'll learn to give the agent the right context (what to build, with which conventions) and to use Android CLI's tools so the agent can create, run, look at and check the app by itself.

## What we're going to build

**Sanji's Galley**, a cooking app for the Thousand Sunny's cook. It answers one question: *what can I cook today?*

- **Pantry:** the ingredients you have, with their quantity.
- **Recipes:** which recipes you can make with what's there and which you can't, and which ingredients you're missing.
- **Shopping:** a list with what's missing so you can cook.

It's a small app on purpose. Data lives in memory and is loaded from sample data when the app starts, with no database: if you close the app, the data goes back to the sample data, and that's expected. What matters in the workshop is not the app, but how you work with the agent.

## What you'll learn

| Topic | Where you'll see it |
|---|---|
| Giving the agent stable context with `AGENTS.md` (conventions) and `SPEC.md` (what to build) | All milestones |
| Creating a project with `android create` | Milestone 1 |
| Building, installing and launching the app with `android run`, on an emulator managed with `android emulator` | Milestone 1 onwards |
| Giving the agent up-to-date knowledge with skills (`android skills`) and the official documentation (`android docs`) | Milestone 2 |
| Letting the agent see the app with `android layout` and `android screen capture` | Milestones 3 to 5 |
| Letting the agent test the app with `android input` and journeys | Milestone 6 |

## Before you start

To make the most of the workshop, arrive with three things working: **Android CLI**, **an AI agent in the terminal** and **an emulator** (or a phone with USB debugging). Follow the [prerequisites guide](PREREQUISITES.md): most of the time is spent downloading, so take it easy and do it well in advance. You don't need to create any project in advance.

## During the workshop

During the workshop we'll follow these instructions **together**, so please wait for us before starting. You can skim them beforehand, but don't work ahead.

### How we work

1. Each milestone has a **goal**, a **prompt** that you copy to the agent, a list of **checks** to verify the result and some help **if you get stuck**.
2. The agent reads `AGENTS.md` and `SPEC.md` in the project root. That's where the rules of the game are; the prompt only says what to do at each step.
3. The agent implements **only what the milestone asks for** and, when it finishes, builds the app and tells you what it verified.
4. You check the result with the milestone's checkboxes, just as a user would.

Tip: start a **new agent session for each milestone**. Each milestone comes with its complete prompt, and long conversations use more tokens.

### Milestones

| Milestone | What you get |
|---|---|
| [Milestone 1](Milestones/STEP_1.md) | The Android project created with Android CLI, building and running on the emulator |
| [Milestone 2](Milestones/STEP_2.md) | The data model, the sample data and the navigation skeleton with three destinations |
| [Milestone 3](Milestones/STEP_3.md) | The Pantry screen working: view, add and edit ingredients |
| [Milestone 4](Milestones/STEP_4.md) | The recipes and their detail, with what you can cook and what's missing |
| [Milestone 5](Milestones/STEP_5.md) | The shopping list, built from the missing ingredients |
| [Milestone 6](Milestones/STEP_6.md) | Journeys: the agent writes and runs tests that walk through the app like a user |

## What's in this folder

| File | What it's for |
|---|---|
| `PREREQUISITES.md` | What to install and check before the workshop |
| `Milestones/` | The workshop steps, one per file |
| `SPEC.md` | The app specification: data, business rules and exact texts |
| `../util/AGENTS.md` | The project conventions for the agent (architecture, libraries, how to work) |

Copy `SPEC.md` and `AGENTS.md` to the root of your project before running the Milestone 1 prompt. The exact steps are in [Milestone 1](Milestones/STEP_1.md).
