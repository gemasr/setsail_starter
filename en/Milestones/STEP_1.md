## Goal

Create the Android project with Android CLI and get it building.

## Before the prompt

The agent needs to read `AGENTS.md` to know how to work, so it has to exist before you run the prompt.

1. Create an empty folder called `SanjisGalley`.
2. Copy `AGENTS.md` (from the starter's `util` folder) and `SPEC.md` (from the `en` folder) into it.
3. Open the agent in that folder.

## Prompt

```
Create a new Android project with Android CLI following the conventions in AGENTS.md. Name it SanjisGalley and create it in this same folder, keeping AGENTS.md and SPEC.md. Use Android 16 (API 36) as compileSdk and targetSdk. When you finish, build it, run it on the emulator using Android CLI and tell me what you verified.
```

## Checks

- [ ]  `AGENTS.md` and `SPEC.md` are still in the project root
- [ ]  The project builds
- [ ]  It runs on the emulator and shows the initial screen

## If you get stuck

Ask the agent:

```
Build it and tell me what fails.
```
