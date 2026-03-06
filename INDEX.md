# V14 SELF-HEALING INDEX

> At the start of every V14 session, verify this index against actual files. Flag any discrepancies.

| File | Purpose | Min Lines | Last Updated |
|:-----|:--------|:----------|:-------------|
| `SKILL.md` | V14 protocol — the single source of truth | 400 | 2026-03-06 |
| `HEARTBEAT.md` | Session audit trail | 5 | 2026-03-06 |
| `INDEX.md` | This file — self-healing index | 20 | 2026-03-06 |
| `HOW_V14_ACTUALLY_WORKS.md` | Plain-English narrative for Tim | 100 | 2026-03-06 |
| `DELIVERY_SUMMARY.md` | Summary of V14 deliverables | 50 | 2026-03-06 |
| `email_to_fidel.md` | Email requesting AI account access | 30 | 2026-03-06 |
| `tim-constitution/CONSTITUTION.md` | Core principles, ethics, mission | 30 | 2026-03-06 |
| `tim-constitution/DIRECTIVES.md` | Standing directives (7 active) | 40 | 2026-03-06 |
| `tim-constitution/PREFERENCES.md` | Tim's preferences | 20 | 2026-03-06 |
| `tim-constitution/DECISIONS.md` | Decision log (9 decisions) | 40 | 2026-03-06 |
| `tim-constitution/KNOWLEDGE.md` | Institutional knowledge (16 sections) | 300 | 2026-03-06 |
| `tim-constitution/ACTIVE_CONTEXT.md` | Current state across initiatives | 20 | 2026-03-06 |
| `tim-constitution/EXHIBITS/exhibit_a_kei_incident.md` | KEI incident founding story | 20 | 2026-03-06 |
| `tim-constitution/feedback/README.md` | Feedback directory structure | 10 | 2026-03-06 |
| `tim-constitution/templates/covering_letters.md` | 7 covering letter templates | 50 | 2026-03-06 |

## Health Check Protocol

At session start, run these checks:

1. **Existence check**: Does every file listed above exist in the repo?
2. **Size check**: Is any file below its minimum line count? (May indicate corruption or accidental overwrite)
3. **Orphan check**: Are there files in the repo NOT listed in this index? (May indicate untracked additions)
4. **Freshness check**: Has any file not been updated in 30+ days? (May indicate knowledge decay)
5. **Heartbeat check**: Is the most recent HEARTBEAT.md entry within 7 days? (Dead Man's Switch)

If ANY check fails, flag it in the ORIENT status dashboard before proceeding.
