---
name: cssk
description: Claude Suite Shared Knowledge — Use this skill when the user references their product, prior session work, key decisions, knowledge domains, or asks "what do we know about", "what did we decide", "remind me", "from our previous sessions", "update the CSSK", or "add this to the knowledge base". This skill provides cross-session continuity by loading the right domain files and maintaining a persistent knowledge base that survives across all Claude Code sessions on the same machine.
version: 0.1.0
---

# CSSK — Claude Suite Shared Knowledge

The CSSK is a **persistent, file-based knowledge system** that makes every Claude Code session aware of everything you have ever built, decided, or discovered — across all conversations on this machine.

## The Problem It Solves

Every Claude Code session starts from zero. Without the CSSK, you repeat context every session. With the CSSK, the INDEX.md loads automatically via CLAUDE.md and gives Claude full project awareness from message one.

## Architecture

```
~/.claude/cssk/
├── INDEX.md              ← Master index (always-on, loaded in every session)
└── domains/
    ├── <topic-1>.md      ← Deep knowledge, read on demand
    ├── <topic-2>.md
    └── session-log.md    ← Append-only log of all session outputs
```

## Setup Instructions

### 1. Create the CSSK directory

```bash
mkdir -p ~/.claude/cssk/domains
```

### 2. Create your INDEX.md

Copy the template from `references/index-template.md` and fill in your context:

```bash
cp references/index-template.md ~/.claude/cssk/INDEX.md
```

### 3. Add the SKILL.md to your global skills

```bash
mkdir -p ~/.claude/skills/cssk
cp skills/cssk/SKILL.md ~/.claude/skills/cssk/SKILL.md
```

### 4. Update your global CLAUDE.md

Add this block to `~/.claude/CLAUDE.md`:

```markdown
## Claude Suite Shared Knowledge (CSSK)

At the start of every session, read `~/.claude/cssk/INDEX.md` to load the always-on knowledge index.

Use the `cssk` skill to search, add, or update knowledge mid-session.

Domain files live at `~/.claude/cssk/domains/` — read on demand when a topic is relevant.
```

### 5. Create your first domain files

Copy and adapt the templates from `references/domain-template.md`:

```bash
cp references/domain-template.md ~/.claude/cssk/domains/my-product.md
```

## How to Use Mid-Session

### Load context
Claude reads `INDEX.md` automatically. For deeper context, say: **"Read the CSSK customer-flows domain"**

### Add new knowledge
Say: **"Add this to the CSSK"** or **"Update the CSSK with what we just decided"**

Claude will:
1. Read the relevant domain file
2. Append the new knowledge
3. Update the session log in `INDEX.md`

### Search prior sessions
Say: **"What did we decide about X in a previous session?"**

Claude reads `session-log.md` and the relevant domain file.

## CSSK Maintenance Rules

1. **Read before writing** — always read the domain file before updating
2. **Latest date wins** — newer entries override older ones on conflicts
3. **No duplicates** — update existing entries, don't add parallel ones
4. **Keep INDEX.md under 200 lines** — it loads in every session
5. **Domain files can be long** — they are only read on demand
6. **session-log.md is append-only** — never delete past entries

## Domain File Structure

Each domain file follows this pattern:

```markdown
# CSSK Domain: <Topic Name>
**Last updated:** YYYY-MM-DD

---

## <Section 1>
[Content]

## <Section 2>
[Content]
```

## Index File Structure

```markdown
# CSSK — Claude Suite Shared Knowledge
**Owner:** <name> | **Updated:** YYYY-MM-DD | **Sessions logged:** N

## Who This User Is
[Brief identity and role context]

## <Product / Project Name>
[Key facts always useful to have in context]

## Session Log
| Date | Session | Key Output |
|---|---|---|
| YYYY-MM-DD | Session 1 | [What was built/decided] |

## CSSK Domain Files
| File | Topic | Last Updated |
|---|---|---|
| `domains/<file>.md` | [Topic] | YYYY-MM-DD |
```

## Reference Files

| File | Purpose |
|---|---|
| `references/index-template.md` | Starter INDEX.md you can copy and adapt |
| `references/domain-template.md` | Starter domain file template |
| `references/session-log-template.md` | Session log entry template |
| `references/worked-example.md` | Complete worked example with real CSSK structure |
