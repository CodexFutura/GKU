# Codex Futura

**Claude Suite Shared Knowledge (CSSK)** — persistent cross-session knowledge that gives every Claude Code conversation full context about your product, decisions, and work history.

---

## The Problem

Every Claude Code session starts from zero. You repeat context. You re-explain your product. You rebuild decisions that were made three sessions ago. The model has no memory of what you built last week.

## The Solution

The CSSK is a **persistent, file-based knowledge system** that lives in `~/.claude/cssk/`. It loads automatically at the start of every session via your global `CLAUDE.md`, giving Claude instant full context — your product, your ICP, your decisions, your open threads — without you saying a word.

---

## How It Works

```
~/.claude/
├── CLAUDE.md          ← Instructs Claude to read INDEX.md every session
├── skills/cssk/
│   └── SKILL.md       ← CSSK skill (auto-triggers on relevant queries)
└── cssk/
    ├── INDEX.md        ← Master index (always-on, < 200 lines)
    └── domains/
        ├── product.md          ← Your product context
        ├── customer-flows.md   ← User journeys and ICP flows
        ├── content-strategy.md ← Marketing and content plans
        └── session-log.md      ← Append-only session history
```

**Session 1:** You build a vertical champion flow for HR Tech.
**Session 2:** Claude already knows the HR Tech flow without you re-explaining it.
**Session 10:** Every decision, every flow, every piece of research — instantly available.

---

## Installation

### 1. Clone this repo

```bash
git clone https://github.com/CodexFutura/CSSK.git
cd CSSK
```

### 2. Install the CSSK skill

```bash
mkdir -p ~/.claude/skills/cssk
cp skills/cssk/SKILL.md ~/.claude/skills/cssk/SKILL.md
```

### 3. Create your CSSK directory

```bash
mkdir -p ~/.claude/cssk/domains
cp skills/cssk/references/index-template.md ~/.claude/cssk/INDEX.md
```

### 4. Add the CSSK reference to your global CLAUDE.md

Add this block to `~/.claude/CLAUDE.md`:

```markdown
## Claude Suite Shared Knowledge (CSSK)

At the start of every session, read `~/.claude/cssk/INDEX.md` to load the always-on knowledge index.

Use the `cssk` skill to search, add, or update knowledge mid-session.

Domain files live at `~/.claude/cssk/domains/` — read on demand when a topic is relevant.
```

### 5. Fill in your INDEX.md

Edit `~/.claude/cssk/INDEX.md` with your product context, key facts, and initial domain file table.

### 6. Create your first domain file

```bash
cp skills/cssk/references/domain-template.md ~/.claude/cssk/domains/my-product.md
# Edit it with your product facts
```

**Done.** Every future Claude Code session on this machine will have full context from the first message.

---

## Usage

### Automatic context loading
Claude reads INDEX.md every session — no commands needed.

### Load a specific domain
> "Read the CSSK customer-flows domain"

### Add new knowledge
> "Add this decision to the CSSK"
> "Update the CSSK with what we just built"

### Search session history
> "What did we decide about X in a previous session?"

### Update after a session
> "Update the CSSK session log with today's decisions"

---

## File Reference

| File | Purpose |
|---|---|
| `skills/cssk/SKILL.md` | The Claude Code skill definition — install to `~/.claude/skills/cssk/` |
| `skills/cssk/references/index-template.md` | Starter INDEX.md to copy and adapt |
| `skills/cssk/references/domain-template.md` | Starter domain file template |
| `skills/cssk/references/session-log-template.md` | Session log entry template |
| `skills/cssk/references/worked-example.md` | Complete worked example with real CSSK structure |

---

## Design Principles

**INDEX.md stays under 200 lines.** It loads in every session. If it grows too large, it wastes context on irrelevant knowledge.

**Domain files can be long.** They are only read on demand. A 500-line domain file costs nothing if it's not triggered.

**Session log is append-only.** The history of what was built is as important as the current state.

**Latest date wins on conflicts.** When the same fact appears in multiple entries, the newest one is authoritative.

**No duplicates.** Update existing entries rather than adding parallel ones.

---

## Theoretical Foundation

The CSSK is grounded in **systemic good practices** — specifically the principle that organizational intelligence should be embedded in structure, not in individual memory. When knowledge lives only in people's heads (or in a single conversation), it is lost when that person (or session) ends.

The CSSK creates a **reinforcing feedback loop**: more sessions → more knowledge captured → more context in future sessions → better work → more sessions worth capturing.

The opposing **balancing loop** is maintenance friction. The design keeps updates minimal: one session log entry, one domain file update, never a full rewrite.

---

## Worked Example

See `skills/cssk/references/worked-example.md` for a complete real-world CSSK implementation built for a B2B SaaS product, including:
- A full INDEX.md with product context, proprietary assessment framework, and session log
- Example domain file structure for capability dimensions, customer flows, and content strategy
- Lessons learned about what makes a CSSK effective

---

## What Codex Futura Is

**Codex** — a structured, indexed book of knowledge
**Futura** — built for the future; portable, growing, persistent

This is a portfolio project demonstrating applied AI tooling: using Claude Code's plugin and skill system to build persistent organizational intelligence that compounds over time.

---

## License

MIT — use freely, adapt to your context, contribute back.

---

## Author

Built by [CodexFutura](https://github.com/CodexFutura) using Claude Code and systemic good practices.
