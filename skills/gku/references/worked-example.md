# GKU Worked Example — Systems Thinking OS

This file shows a complete, real-world GKU implementation for a B2B SaaS product.
Use it as a reference for structuring your own INDEX.md and domain files.

---

## Example INDEX.md

```markdown
# GKU — Global Knowledge Universe
**Owner:** horatonsan | **Updated:** 2026-03-28 | **Sessions logged:** 1

## Who This User Is
- **Role:** Founder building Systems Thinking OS — a SaaS platform delivering Systems Thinking
  courses + the SII (Structural Intelligence Index) proprietary assessment
- **Acquisition:** Organic / SEO | **Stage:** Pre-launch / first 100 customers

## Product Summary
5 tiers: Individual $89/mo | Individual Plus $159/mo | Team Core $599/mo |
Team Assessment $1,499/mo | Enterprise $25,000/yr (all billed annually)

Primary ICP: Team lead / manager | Year 1 ARR target: ~$631k from 100 customers

## SII Quick Reference
7-dimension structural reasoning assessment
Formula: SII = (0.20×SD) + (0.20×FLI) + (0.15×CMP) + (0.15×DTA) + (0.15×LE) + (0.10×DT) + (0.05×SC)
Risk flag: any dimension < 40. Certification: composite ≥ 75 + no flags + 6 months sustained.

## Session Log
| Date | Session | Key Output |
|---|---|---|
| 2026-03-28 | Session 1 | Champion flows (4 verticals), onboarding (4 ICPs), 52-week SEO roadmap, GKU |

## GKU Domain Files
| File | Topic | Last Updated |
|---|---|---|
| `domains/sii-framework.md` | SII 7 dimensions, rubrics, scoring, calibration | 2026-03-28 |
| `domains/systems-thinking-os.md` | Product context, tech stack, course content | 2026-03-28 |
| `domains/customer-flows.md` | Vertical champion flows, onboarding sequences | 2026-03-28 |
| `domains/content-strategy.md` | 52-week SEO/content roadmap | 2026-03-28 |
| `domains/mirofish-simulation.md` | Simulation setup + Year 1 projections | 2026-03-28 |
| `domains/session-log.md` | Full log of all session outputs | 2026-03-28 |
```

---

## Example Domain: sii-framework.md (excerpt)

```markdown
# GKU Domain: SII Framework
**Last updated:** 2026-03-28

## The 7 Dimensions

| Dim | Name | Weight | Measures |
|---|---|---|---|
| SD | Structural Depth | 20% | Causal chain thinking vs. reactive |
| FLI | Feedback Loop Integrity | 20% | R/B loop recognition and modeling |
| CMP | Constraint Mapping Precision | 15% | Bottleneck ID + archetype recognition |
| DTA | Delay & Time Awareness | 15% | Temporal reasoning + leading/lagging indicators |
| LE | Leverage Efficiency | 15% | High-leverage intervention design |
| DT | Decision Traceability | 10% | Documentation + learning loops |
| SC | Structural Coherence | 5% | Cross-functional alignment |

## Formula
SII = (0.20×SD) + (0.20×FLI) + (0.15×CMP) + (0.15×DTA) + (0.15×LE) + (0.10×DT) + (0.05×SC)

## Maturity Scale
- 0–20: Event-Level — firefighting, purely reactive
- 21–40: Pattern Recognition — sees problems but blames departments not structure
- 41–60: Partial Mapping — basic loops understood; experiments abandoned too early
- 61–80: Managed SI — decisions based on causal chains; indicators calibrated
- 81–100: Optimized Architecture — interventions target rules/goals/paradigms
```

---

## What Made This GKU Effective

1. **INDEX.md is concise** — fits in context without overwhelming; just enough to orient
2. **Domain files are deep** — full rubrics, scoring rules, all flows — read only when needed
3. **Session log is append-only** — never lose what was built or decided
4. **SII quick reference in INDEX.md** — the most-referenced facts are always in context
5. **Vertical separation** — each ICP/vertical has its own section in customer-flows.md

## Key Lessons

- Keep INDEX.md under 200 lines — it loads every session
- Don't put everything in INDEX.md — that defeats the purpose
- Domain files can be 300–500 lines — they're read selectively
- The session log is your memory — update it every session without exception
- Name domain files by topic, not by date
