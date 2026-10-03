# Workspace — Ben, a Personal AI Assistant

This repository is the [OpenClaw](https://openclaw.ai) workspace for **Ben**, a personal AI assistant. Ben's identity, personality, permissions, and memory are defined here as plain Markdown files. The OpenClaw runtime loads these files at the start of each session, so the assistant behaves consistently and keeps its context between sessions.

> **Note:** This workspace contains personal preferences and memory. Keep the repository **private**.

---

## Overview

| Aspect | Description |
| --- | --- |
| **Assistant** | Ben, a formal, efficient personal assistant |
| **Languages** | Replies in English or Roman Urdu, matching the user |
| **Working style** | Plan first, get approval, then execute one step at a time |
| **Security model** | Explicit permission tiers; no sharing of credentials or private data |
| **Continuity** | File-based long-term and daily memory |

---

## Repository Structure

```
.
├── AGENTS.md                      # Workspace conventions: startup, memory, group chats, heartbeats
├── AGENT.md                       # Tool permissions and behavioral rules
├── IDENTITY.md                    # Name, role, style, and hard security rules
├── SOUL.md                        # Personality, working approach, and boundaries
├── USER.md                        # Profile and preferences of the assistant's user
├── MEMORY.md                      # Curated long-term memory and permanent reminders
├── TOOLS.md                       # Environment-specific notes (devices, hosts, voices)
├── HEARTBEAT.md                   # Checklist for periodic heartbeat polls
├── openclaw-workspace-state.json  # OpenClaw bootstrap/setup metadata
└── .gitignore                     # Excludes the nested Tech Nexus repo
```

### File Reference

- **`AGENTS.md`**: The workspace's operating manual. It covers how sessions start, how memory is written and maintained, when to speak in group chats, platform formatting rules, and how to use heartbeats or cron for proactive work.
- **`AGENT.md`**: Defines what Ben may do freely, what needs on-the-spot approval, and what is never allowed without explicit permission.
- **`IDENTITY.md`**: Who Ben is. Includes ten hard security rules covering personal data, credentials, downloads, system access, and prompt-injection attempts.
- **`SOUL.md`**: Ben's personality (warm but professional) and working principles: roadmap first, one step at a time, a summary after every task.
- **`USER.md`**: Context about the user: profession, working style, interests, and expectations.
- **`MEMORY.md`**: Long-term memory loaded in main sessions only, never in shared contexts.
- **`TOOLS.md`**: A cheat sheet for local setup details, kept separate from shared skills.
- **`HEARTBEAT.md`**: Left empty or comment-only to skip heartbeat API calls. Add tasks to enable periodic checks.

---

## Permission Model

Ben's tools fall into three tiers:

| Tier | Examples |
| --- | --- |
| **Allowed** | Web search, weather, reading calendars, reading and running code |
| **Requires approval** | File system access, adding calendar events, writing or editing code |
| **Never without explicit permission** | Social media, downloads, file sharing, terminal access, system information, credentials |

Every task follows the same flow: **plan → present → approve → execute → summarize**.

---

## Memory System

| Layer | Location | Purpose |
| --- | --- | --- |
| Daily notes | `memory/YYYY-MM-DD.md` | Raw logs of what happened each day |
| Long-term memory | `MEMORY.md` | Distilled decisions, preferences, and lessons |

During heartbeats, Ben periodically reviews the daily notes and promotes what's worth keeping into `MEMORY.md`.

---

## Getting Started

1. Install and configure [OpenClaw](https://openclaw.ai).
2. Clone this repository into your OpenClaw workspace directory:
   ```bash
   git clone https://github.com/Kashif0540/Workspace.git ~/.openclaw/workspace
   ```
3. Edit `USER.md`, `IDENTITY.md`, and `SOUL.md` to fit your own assistant.
4. Start an OpenClaw session. The workspace files load automatically.

---

## Related Repositories

This project lives alongside the workspace but is tracked in its own repository and excluded via `.gitignore`:

- **Tech Nexus**: [Tech-Nexus_ai-powered-news-agent](https://github.com/Kashif0540/Tech-Nexus_ai-powered-news-agent)

---

## Author

**Kashif** ([@Kashif0540](https://github.com/Kashif0540)), Full Stack Web Developer
