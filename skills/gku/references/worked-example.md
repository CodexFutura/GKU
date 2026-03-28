# GKU Worked Example — B2B SaaS Product

This file shows a complete, real-world GKU implementation for a B2B SaaS product.
Use it as a reference for structuring your own INDEX.md and domain files.

---

## Example INDEX.md

```markdown
# GKU — Global Knowledge Universe
**Owner:** founder | **Updated:** 2026-03-28 | **Sessions logged:** 1

## Who This User Is
- **Role:** Founder building a B2B SaaS platform — professional assessment and
  structured practice suite for team leads and managers
- **Acquisition:** Organic / SEO | **Stage:** Pre-launch / first 100 customers

## Product Summary
5 tiers: Individual $89/mo | Individual Plus $159/mo | Team Core $599/mo |
Team Assessment $1,499/mo | Enterprise $25,000/yr (all billed annually)

Primary ICP: Team lead / manager | Year 1 ARR target: ~$631k from 100 customers

## Assessment Framework Quick Reference
7-dimension proprietary capability assessment
Each dimension scored 0–100; composite weighted score
Risk flag: any dimension < 40. Certification: composite ≥ 75, no flags, 6 months sustained.

## Session Log
| Date | Session | Key Output |
|---|---|---|
| 2026-03-28 | Session 1 | Champion flows (4 verticals), onboarding (4 ICPs), 52-week SEO roadmap, GKU |

## GKU Domain Files
| File | Topic | Last Updated |
|---|---|---|
| `domains/assessment-framework.md` | 7-dimension framework, rubrics, scoring, calibration | 2026-03-28 |
| `domains/product.md` | Product context, tech stack, course content | 2026-03-28 |
| `domains/customer-flows.md` | Vertical champion flows, onboarding sequences | 2026-03-28 |
| `domains/content-strategy.md` | 52-week SEO/content roadmap | 2026-03-28 |
| `domains/simulation.md` | Simulation setup + Year 1 projections | 2026-03-28 |
| `domains/session-log.md` | Full log of all session outputs | 2026-03-28 |
```

---

## Example Domain: assessment-framework.md (excerpt)

```markdown
# GKU Domain: Assessment Framework
**Last updated:** 2026-03-28

## The 7 Dimensions

| Dim | Name | Weight | Measures |
|---|---|---|---|
| D1 | Structural Depth | 20% | Causal chain thinking vs. reactive |
| D2 | Feedback Loop Integrity | 20% | Loop recognition and modeling |
| D3 | Constraint Mapping Precision | 15% | Bottleneck ID + archetype recognition |
| D4 | Delay & Time Awareness | 15% | Temporal reasoning + leading/lagging indicators |
| D5 | Leverage Efficiency | 15% | High-leverage intervention design |
| D6 | Decision Traceability | 10% | Documentation + learning loops |
| D7 | Structural Coherence | 5% | Cross-functional alignment |

## Formula
Score = (0.20×D1) + (0.20×D2) + (0.15×D3) + (0.15×D4) + (0.15×D5) + (0.10×D6) + (0.05×D7)

## Maturity Scale
- 0–20: Event-Level — firefighting, purely reactive
- 21–40: Pattern Recognition — sees problems but blames departments not structure
- 41–60: Partial Mapping — basic loops understood; experiments abandoned too early
- 61–80: Managed — decisions based on causal chains; indicators calibrated
- 81–100: Optimized Architecture — interventions target rules/goals/paradigms
```

---

## What Made This GKU Effective

1. **INDEX.md is concise** — fits in context without overwhelming; just enough to orient
2. **Domain files are deep** — full rubrics, scoring rules, all flows — read only when needed
3. **Session log is append-only** — never lose what was built or decided
4. **Framework quick reference in INDEX.md** — the most-referenced facts are always in context
5. **Vertical separation** — each ICP/vertical has its own section in customer-flows.md

## Key Lessons

- Keep INDEX.md under 200 lines — it loads every session
- Don't put everything in INDEX.md — that defeats the purpose
- Domain files can be 300–500 lines — they're read selectively
- The session log is your memory — update it every session without exception
- Name domain files by topic, not by date
