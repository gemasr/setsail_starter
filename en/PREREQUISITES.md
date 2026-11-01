# Set Sail to the Grand Line — Prerequisites

## What we're going to do

To make the most of the workshop, arrive with three things working: **Android CLI**, **an AI agent in the terminal** and **an emulator** (or a phone with USB debugging). Set aside some quiet time: most of it is downloads.

You don't need to create any project. We'll build it together from scratch during the workshop, and the instructions work whichever agent you choose.

> **Note:** if you already have something installed that is asked for here, skip that step. For example, if you already have Android Studio you don't need to install it again, although it's a good idea to keep it up to date.

## What you need

- A laptop with macOS, Linux or Windows and a good connection: several GB are downloaded.
- [Android Studio](https://developer.android.com/studio) in its stable version, opened at least once so it finishes downloading the Android SDK. We'll use it for the emulator and to open the project at the end.
- An account for the agent you choose (for example, a Google account for Antigravity CLI). The options are listed below.
- If you use **Windows**, read the warnings in Step 1: there are two known limitations at the moment.

## Step 1 · Install Android CLI

1. Download Android CLI from the [official page](https://developer.android.com/tools/agents) and follow the instructions for your system.
2. Open a new terminal and update to the latest version:

```
android update
```

3. Check that it works:

```
android -V
android info
```

`android info` tells you which Android SDK it is using.

**Also check that Java is on your PATH.** Some Android CLI features and the `gradlew` script of the projects need it. Run in a new terminal:

```
java -version
```

If it isn't recognized, install a JDK or add to the PATH the one bundled with Android Studio, and set the `JAVA_HOME` variable pointing to it. Then open another terminal and repeat the check.

**Also check `adb`.** The agent uses it to drive the app on the emulator during journeys. Run:

```
adb version
```

If it isn't recognized, it's in the `platform-tools` folder of your SDK (`android info` gives you the SDK path). Add it to the PATH, open another terminal and repeat the check.

**Windows warnings** (according to the [official documentation](https://developer.android.com/tools/agents/android-cli)): for now, downloading Android CLI from PowerShell is not supported, and the `android emulator` command is disabled. In that case, create the emulator from Android Studio (Device Manager) or use a phone with USB debugging.

## Step 2 · Choose and install an agent

**If you already have a command-line agent installed with a subscription, skip this step.** It's only for people who have no subscription and don't currently use any agent.

Choose **only one**. Any of these works for the workshop; if you don't want to pay, the free options are Antigravity CLI and OpenCode.

> **Note:** this workshop has only been tested with Copilot CLI, Claude Code and Antigravity CLI. Other agents may not behave the same way. You can also use any other agent that isn't in the table, as long as it can be used from the console.

| Agent | Cost | What to keep in mind |
| --- | --- | --- |
| Antigravity CLI (`agy`) | Free with a Google account, with a limited weekly quota | It replaces Gemini CLI. The free quota is tighter than the old one; [Google doesn't publish exact figures](https://www.cloudzero.com/blog/google-antigravity-pricing/). |
| OpenCode | Free with the included models (OpenCode Zen); it also accepts your own key | The [free models](https://www.desarrollolibre.net/blog/ia/opencode-complete-guide-to-the-code-agent-with-artificial-intelligence) have limits, rotate and can be slower. |
| Claude Code | Paid (Claude subscription or API key) | It has no free plan. |
| GitHub Copilot CLI | Included in Copilot Free, with very limited monthly usage | Since June 2026 it is billed by AI credits; with the free plan the limit is low. |
| Gemini CLI | No longer free with a personal Google account since June 18, 2026 | [Google has replaced it](https://github.com/google-gemini/gemini-cli/discussions/28017) with Antigravity CLI. |

### Install Antigravity CLI

```
# macOS / Linux
curl -fsSL https://antigravity.google/cli/install.sh | bash

# Windows (PowerShell)
irm https://antigravity.google/cli/install.ps1 | iex
```

Run `agy` and sign in with your Google account. Inside the session, `/usage` shows how much quota you have left.

### Install OpenCode

```
curl -fsSL https://opencode.ai/install | sh
```

Run `opencode` and type `/models` to see the available free models. On Windows, follow the official OpenCode documentation.

### Claude Code or Copilot CLI

Follow each tool's official installation guide and sign in with your account.

**Tip:** with a free plan, do a single short test and don't spend quota in the days before the workshop.

## Step 3 · Set up an emulator

First download the Android 16 (API 36) platform and the system image for the emulator. They are several GB, so this is what takes longest: do it with time and a good connection.

```
android sdk install platforms/android-36
android sdk install system-images/android-36/google_apis/<architecture>
```

Replace `<architecture>` according to your computer:

- `arm64-v8a`: Macs with Apple silicon (M1 or later) and laptops with an ARM processor.
- `x86_64`: Macs with an Intel processor and most Windows and Linux computers.

Then, for the emulator, on macOS and Linux:

```
android emulator create
android emulator list
```

Start the device once with `android emulator start <name>` to check that it works. On Windows, create it from Android Studio (Device Manager).

## Step 4 · Download the documentation and the skills

The first time they are used, `android docs` and `android skills` download their index and can take a couple of minutes. Do it now so you don't wait during the workshop:

```
android docs search "navigation 3"
android skills list
```

If the first search hangs or fails with an index error, wait for it to finish, close it and run it again.

## Final check

If you can tick all of these, you're ready:

- [ ] `android -V` shows a version.
- [ ] `android info` shows the path of your Android SDK.
- [ ] `java -version` and `adb version` work in a new terminal.
- [ ] `android docs search "navigation 3"` and `android skills list` return results.
- [ ] Your agent starts and you have signed in.
- [ ] The Android 16 platform is installed: `android sdk list` shows `platforms/android-36`.
- [ ] An emulator starts, or you have a phone with USB debugging.
- [ ] Test with the agent: in an empty folder, ask it "Run `android --help` and tell me in one sentence what it can do". If it runs it and answers you, everything is connected correctly.

## Common problems

| Symptom | What to try |
| --- | --- |
| `android: command not found` | Close and reopen the terminal. If it still happens, check that the installation folder is on your PATH. |
| Windows: the download from PowerShell fails or `android emulator` doesn't work | These are known limitations. Download from the official page and create the emulator from Android Studio. |
| The emulator is very slow, the app freezes or "App isn't responding" appears | It's usually a lack of memory: new emulators come with only 2 GB of RAM. Close heavy applications, restart the emulator (`android emulator stop <name>` and then `android emulator start <name>`) and try again. |
| The agent says you've reached the quota | Wait for it to renew (in Antigravity it is weekly) or try another agent. |
| Any other error | Copy the full message and send it to me before the workshop, so we can sort it out calmly. |
