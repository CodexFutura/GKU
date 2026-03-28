# Session Log Entry Template

Copy this block into `~/.claude/gku/domains/session-log.md` at the end of each significant session.

---

## Session N — YYYY-MM-DD

**Topics covered:**
- [Topic 1]
- [Topic 2]

**Key decisions made:**
- [Decision 1 — what was decided and why]
- [Decision 2]

**Open threads (unresolved):**
- [ ] [Thing that still needs to be done or decided]
- [ ] [Another open thread]

**Files read this session:**
- `[file path]` — [why it was read]

**Files created/updated this session:**
- `[file path]` — [what was added]

**GKU domains updated:**
- `domains/[topic].md` — [what was added]

---

## How to Update INDEX.md After a Session

In `~/.claude/gku/INDEX.md`:

1. Add a row to the Session Log table:
```
| YYYY-MM-DD | Session N | [1-line summary of key output] |
```

2. Increment the session counter in the header:
```
**Sessions logged:** N
```

3. Update any "Last Updated" dates in the GKU Domain Files table for domains you touched.
