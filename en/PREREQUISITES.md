# Set Sail for the Grand Line — Prerequisites

Arrive with three things working: **Android CLI**, **an AI agent in the terminal** and **an emulator** (or a phone with USB debugging).

- **Time:** about 30–40 minutes, mostly downloads (several GB). Use a good connection.
- **Don't create any project:** we'll do that together in the workshop.
- **Already have something installed?** Skip that step.

> **Windows:** install Android CLI with `winget install --id Google.AndroidCLI` or the installer from the [official page](https://developer.android.com/tools/agents).

## 1. Install Android Studio and Android CLI

1. Install [Android Studio](https://developer.android.com/studio) (stable) and **open it once**: the setup wizard downloads the Android SDK.
2. Install Android CLI from the [official page](https://developer.android.com/tools/agents).
3. In a **new terminal**:

```
android update
android -V && java -version && adb version
```

✅ You should see three versions. If `java` or `adb` fails, see [Common problems](#common-problems).

## 2. Install an AI agent

**Already use a command-line agent (Claude Code, Copilot CLI…)? Skip this step.**

No agent? Install Antigravity CLI, which is free with a Google account:

```
# macOS / Linux
curl -fsSL https://antigravity.google/cli/install.sh | bash

# Windows (PowerShell)
irm https://antigravity.google/cli/install.ps1 | iex
```

Then run `agy` and sign in with your Google account.

✅ The agent starts and you are signed in.

Other options, costs and quota: see the [appendix](#appendix-agents-and-quota).

## 3. Heavy downloads (start them and let them run)

**3.1 · Emulator, from Android Studio.** Open **Device Manager → Create Device**, choose a phone, and pick the **Android 16 (API 36)** image with Google APIs (Studio downloads it for you). Then start it with ▶.

✅ The emulator boots. You can use a phone with USB debugging instead.

**3.2 · Gradle warm-up** (optional, recommended: saves several minutes in Milestone 1). Then delete the `WarmUp` folder:

```
android create --name WarmUp --output WarmUp
cd WarmUp
./gradlew assembleDebug        # Windows: gradlew.bat assembleDebug
```

## 4. Final check

In a new terminal:

```
android info
android emulator list
```

You're ready if:

- [ ] `android info` shows your SDK path.
- [ ] `android emulator list` shows your emulator.

## Common problems

| Symptom | What to try |
| --- | --- |
| `android: command not found` | Close and reopen the terminal. If it still fails, add the Android CLI installation folder to your PATH. |
| `java: command not found` | Install a JDK, or add the one bundled with Android Studio to your PATH and set `JAVA_HOME` to it. Open a new terminal. |
| `adb: command not found` | Add the `platform-tools` folder of your SDK to your PATH (`android info` shows the SDK path). Open a new terminal. |
| The emulator is very slow or "App isn't responding" appears | Not enough memory. Close heavy apps, then `android emulator stop <name>` and `android emulator start <name>`. |
| The agent says you've reached the quota | Wait for it to renew (weekly in Antigravity) or try another agent. |
| Any other error | Copy the full message and send it to the organizers before the workshop, so they can put you in touch with me and we can sort it out calmly. |

## Appendix: agents and quota

Any agent that works from the console is valid. This workshop has only been tested with **Copilot CLI, Claude Code and Antigravity CLI**; others may not behave the same way.

| Agent | Cost | What to keep in mind |
| --- | --- | --- |
| Antigravity CLI (`agy`) | Free with a Google account, with a limited weekly quota | It replaces Gemini CLI. The free quota is tighter than the old one; [Google doesn't publish exact figures](https://www.cloudzero.com/blog/google-antigravity-pricing/). Inside the session, `/usage` shows what's left. |
| OpenCode | Free with the included models (OpenCode Zen); it also accepts your own key | The [free models](https://www.desarrollolibre.net/blog/ia/opencode-complete-guide-to-the-code-agent-with-artificial-intelligence) have limits, rotate and can be slower. Install: `curl -fsSL https://opencode.ai/install \| sh`, then `opencode` and `/models`. On Windows, follow its official documentation. |
| Claude Code | Paid (Claude subscription or API key) | It has no free plan. Follow its official installation guide. |
| GitHub Copilot CLI | Included in Copilot Free, with very limited monthly usage | Since June 2026 it is billed by AI credits; the free limit is low. Follow its official installation guide. |

**With a free plan:** do a single short test and don't spend quota in the days before the workshop.

**If you run out of quota during the workshop:** you don't need to start over. Milestones 3 and 4 start from a checkpoint (a zip you download), so you can jump straight in.
