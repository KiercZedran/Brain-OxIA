# brain-OxIA 🧠
### Obsidian × AI — Knowledge Brain Skill for Claude

A Claude skill that guides you step by step through building persistent AI knowledge brains in Obsidian — from scratch or from an existing project. Based on Karpathy's LLM Wiki pattern and the complete architecture documented in the included research (v2, May 2026).

---

## What it does

brain-OxIA gives Claude everything it needs to act as a Knowledge Systems Architect. It comes with seven commands:

| Command | What it does |
|---|---|
| `/brain-new` | Builds a full Obsidian brain system from scratch — main orchestrator brain + test brain |
| `/brain-project` | Turns an existing system, project, or documentation into a structured Obsidian brain |
| `/brain-update` | Adds new material to an existing brain without rebuilding it |
| `/brain-migrate` | Moves disorganized notes or an unstructured vault into the brain-OxIA architecture |
| `/brain-connect` | Guides you through connecting an existing vault to Claude (evaluates all routes) |
| `/brain-status` | Quick health check — hot cache, structural issues, recommended next actions |
| `/brain-audit` | Deep audit — full diagnostic report with severity tags, gap analysis, and remediation roadmap |
| `/brain` | Auto-detects what you need, or asks if unclear |

---

## Installation

### Option 1 — Claude Cowork (recommended, no terminal needed)

Claude Cowork is the desktop AI agent built into the Claude Desktop app. It reads and writes files directly in your vault folder — no terminal, no code, no manual copy-paste.

1. Download and install **Claude Desktop**: [claude.ai/download](https://claude.ai/download)
2. Open Claude Desktop and switch to the **Cowork** tab
3. Create a **New Project** → choose **"Use an existing folder"** → select your Obsidian vault folder (or an empty folder if starting from scratch)
4. Inside the project **Instructions**, paste the contents of `brain-OxIA.md`
5. Start a task with any command: `/brain-new`, `/brain-project`, `/brain-update`, `/brain-migrate`, `/brain-connect`, `/brain-status`, `/brain-audit`, or `/brain`

> Cowork reads the `CLAUDE.md` file in your vault folder automatically at the start of every task — no need to re-explain context each time.

**Requirements:** Claude Desktop app + Pro, Max, Team, or Enterprise plan.

---

### Option 2 — Claude Code (for developers, full terminal control)

```bash
# Install Node.js first if you don't have it: https://nodejs.org
# Install the skill:
npx skills add https://raw.githubusercontent.com/KiercZedran/brain-OxIA/main/brain-OxIA.md

# Start a session from your vault folder:
cd ~/path/to/your/vault
claude

# Use any command:
/brain-new
/brain-project
/brain-update
/brain-migrate
/brain-connect
/brain-status
/brain-audit
/brain
```

**Requirements:** Node.js v18+, Claude Code CLI, Pro or Max plan.

---

## Requirements

### Claude
| Option | Plan needed | Notes |
|---|---|---|
| Claude Cowork | Any paid plan (Free not supported) | Recommended — no terminal needed, reads vault files directly |
| Claude Code | Any paid plan (Free not supported) | For developers — full terminal control, skill installation via `npx` |

→ Download Claude Desktop: [claude.ai/download](https://claude.ai/download)

> **⚠️ Token usage warning:** Cowork tasks consume significantly more usage than regular chat — a single complex task can use as much as an entire normal conversation session. Commands like `/brain-new` and `/brain-project` involve many sequential steps and file operations. If you hit your plan's usage limits mid-task, you'll need to wait for the next reset period before continuing. To manage this, brain-OxIA delivers work one step at a time with your approval — so you never lose progress if a session is interrupted.

### Obsidian
- **Version:** v1.8.0 or higher (v1.12.4+ recommended — required for the free built-in CLI)
- **License:** Free personal license is enough — no Sync license needed
- **Plugins needed:** none by default. Only required if using Route B (MCP): install [Local REST API](https://github.com/coddingtonbear/obsidian-local-rest-api) from Community Plugins
- **Operating system:** macOS, Windows, Linux, iOS, or Android

→ Download Obsidian: [obsidian.md](https://obsidian.md)

### Sync (optional but recommended)
brain-OxIA works fully offline — no sync service is required to build or use your vault. Sync is only needed if you want to access your vault from multiple devices.

**Supported options (any of these works):**
- **Google Drive** — free with a Google account. Install [Google Drive for Desktop](https://www.google.com/drive/download) and place your vault inside the local Drive folder.
- **iCloud Drive** — built into macOS and iOS. Place your vault in the iCloud Drive folder.
- **Dropbox / OneDrive / Syncthing** — any service that syncs a local folder works the same way.
- **Obsidian Sync** — Obsidian's official paid sync service (~$10/month). Not required; the free alternatives above work just as well.
- **No sync** — if you only use one device, you don't need any of the above.

> brain-OxIA will ask about your sync setup during onboarding and adapt the vault structure and CLAUDE.md instructions accordingly.

### Node.js (only for Claude Code — Option 1)
- **Version:** v18 or higher
- Used to run `npx skills add` and the Claude Code CLI
- Check if you have it: `node --version`

→ Download Node.js: [nodejs.org](https://nodejs.org)

### Optional tools (brain-OxIA will recommend these only if your project needs them)
- **Graphify** — multimodal preprocessor for ingesting code, PDFs, images, and recordings into Obsidian. Only needed for Mode B with mixed file types. [github.com/graphify-ai/graphify](https://github.com/graphify-ai/graphify)
- **InfraNodus** — knowledge gap analyzer for dense vaults. Only suggested after vault creation if relationship density is high. [infranodus.com](https://infranodus.com)

---

## How it works

> In Claude Cowork, brain-OxIA reads and writes files **directly in your vault folder**. Every command produces real `.md` files in your Obsidian vault — no copy-paste needed. In Claude Code, same behavior via terminal.

### `/brain-new`
Builds your Obsidian brain system from zero:
- Main orchestrator brain (index only, no domain content)
- Second-level brain on a topic of your choice
- CLAUDE.md for each brain (token-optimized, max 400 lines)
- Hot cache structure
- Sync setup instructions (adapts to whichever service you use, or skipped if single device)
- Recommended connection route (Claude Code / MCP / Chat / CLI)

### `/brain-project`
Turns existing material into a structured brain:
- Inventory of your material before any proposal
- Graphify evaluation if you have code, PDFs, or recordings
- Provenance tracking on every note (extracted / inferred / missing)
- Mermaid diagrams for interconnected systems
- `_gaps/knowledge-gaps.md` for everything that couldn't be documented
- Closing report with gap impact assessment

### `/brain-update`
Adds new material to an existing brain without rebuilding:
- Detects what's new vs. what already exists
- Integrates new notes, decisions, and entities into the current structure
- Updates hot cache and gap file after each addition
- Flags conflicts or duplicates for human review

### `/brain-migrate`
Restructures an existing Obsidian vault with no brain-OxIA architecture:
- Full inventory of existing notes before any movement
- Zone mapping proposal — where each note will go
- Migration one zone at a time with approval at each step
- Unclassified notes go to `_inbox/unsorted/` — nothing gets deleted
- CLAUDE.md generated after migration is complete, reflecting final structure

### `/brain-connect`
Focuses exclusively on connecting your vault to Claude:
- Evaluates all connection options against your setup
- Delivers step-by-step configuration for the recommended route
- Includes CLAUDE.md updates if needed for the chosen route
- Works on any existing vault, with or without brain-OxIA structure

### `/brain-status`
Quick health check — results in one structured response:
- Hot cache freshness
- Structural issues (missing index.md, broken links, empty zones)
- Orphan notes and unvalidated inferred items
- Prioritized next actions with command reference per item

### `/brain-audit`
Full diagnostic — use this when you want the complete picture:
- Everything `/brain-status` covers, plus:
- Knowledge quality (provenance coverage, conflicts, missing topics)
- Link density analysis (most-linked notes, isolated notes)
- CLAUDE.md effectiveness review
- Gap analysis with open items and obvious missing knowledge
- Full remediation roadmap with severity tags (🔴/🟡/🟢) and command references

---

## The 4 connection routes

brain-OxIA evaluates and recommends the best connection route for your setup:

| Route | Best for | Requires |
|---|---|---|
| A — Claude Code | Maximum power, full automation | Node.js, terminal |
| B — Claude Desktop + MCP | GUI users, no terminal | Pro/Max plan, Local REST API plugin |
| C — Manual chat | Any AI, zero setup | Nothing extra |
| D — Obsidian official CLI | Agent access without MCP | Obsidian v1.12.4+ running |

---

## Research basis

This skill is grounded in the research document included in `brain-OxIA.md` (v2, May 2026), which covers:

- Karpathy's LLM Wiki pattern and community extensions
- Obsidian vault architecture (single vault MECE zones vs. multi-vault)
- CLAUDE.md design and official Obsidian Skills (kepano/obsidian-skills)
- Plugin stack for AI brains
- MCP server ecosystem
- Layered memory architecture (working / episodic / semantic)
- Hot cache and HOT/WARM/COLD tiering
- Multi-agent patterns
- Contamination prevention (provenance tracking)
- Heartbeat cycles and autonomous maintenance
- Anthropic native memory (April 2026 state)
- Graphify as multimodal preprocessor (May 2026)

---

## License

MIT — free to use, modify, and distribute. Credit appreciated but not required.

---

## Author

**KiercZedran** · [GitHub](https://github.com/KiercZedran/brain-OxIA) · [brain-OxIA repo](https://github.com/KiercZedran/brain-OxIA)

Built on research by the Obsidian + AI community · Inspired by Andrej Karpathy's LLM Wiki · Skills pattern by kepano (Steph Ango, Obsidian CEO)
