# UnIdle

**Your Mac keeps working while an AI coding agent does — through system sleep, a locked screen, even a shut lid on battery — and tells you the instant it actually needs you.**

[unidle.app](https://unidle.app) · [Download the latest DMG](https://github.com/rpajaziti/unidle/releases/latest)

---

## What it does

UnIdle is a macOS menu bar utility built for people running Claude Code, Codex, Aider, Cursor, Gemini, or opencode. Kick off a long agent run, close the lid, walk away — UnIdle keeps the Mac alive until the agent is actually done, then tells you.

- **Knows, doesn't guess.** Hooks directly into Claude Code's own lifecycle events, so it knows the moment a task finishes or needs your permission — not a CPU-usage guess that's wrong exactly when an agent is quietly waiting on the model.
- **Never reads your screen or your code.** No Accessibility permission, no screen-scraping. It only checks whether the agent's connection to the model is still open — the same thing `lsof` would tell you.
- **Lock and leave.** One hotkey locks your screen and walks away. Locking never pauses a process — only system sleep does, and that's the thing UnIdle is stopping.
- **Crash-safe.** If UnIdle ever quits mid-session, every sleep override it applied reverts automatically on next launch. A "restore all sleep settings" button undoes anything, anytime.

## Install

Download the latest DMG from [Releases](https://github.com/rpajaziti/unidle/releases/latest), open it, drag UnIdle to Applications. macOS 14+, Apple Silicon and Intel. No account required.

Updates ship automatically via [Sparkle](https://sparkle-project.org/) — the appcast in this repo (`appcast.xml`) is what your installed copy checks against.

## Free vs. Pro

| | Free | Pro — $19 one-time |
|---|---|---|
| Agent auto-detect (6 tools out of the box) | ✅ | ✅ |
| Manual keep-awake + lock & leave | ✅ | ✅ |
| Battery floor + launch at login | ✅ | ✅ |
| Local alerts on finish / needs-permission | ✅ | ✅ |
| Lid shut, still running on battery | | ✅ |
| Phone push (via [ntfy](https://ntfy.sh)) | | ✅ |
| Scheduled deactivation | | ✅ |
| Mouse motion mode | | ✅ |

One-time purchase, no subscription. Every Pro purchase includes updates.

## Privacy

Detection and the awake logic run entirely on-device — no server, no account, no telemetry. The only two things that ever leave your Mac: an optional (off by default) phone push through a randomly generated private topic on ntfy.sh, containing just the agent's name and state — never your code or prompts — and a routine update check against GitHub, same as most distributed Mac apps.

## This repo

This repo hosts release artifacts and the Sparkle update feed only — DMGs under [Releases](https://github.com/rpajaziti/unidle/releases) and `appcast.xml`. Source lives elsewhere.

---

UnIdle is not affiliated with Anthropic, OpenAI, or any AI agent vendor.
