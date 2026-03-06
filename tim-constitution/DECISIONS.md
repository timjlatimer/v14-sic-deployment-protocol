# Decision Log

> **Classification**: Constitutional — NEVER-COMPRESS
> **Last Updated**: March 6, 2026

---

## Decisions

### DEC-001: V14 Architecture — Dispatcher Pattern
**Date**: March 6, 2026
**Decision**: V14 will be a dispatcher (<300 lines) that calls existing skills, not a monolithic system.
**Rationale**: Keeps V14 maintainable, modular, and focused. Business logic belongs in specialized skills.
**Made by**: Tim HB1000 + V13 Learning Loop

### DEC-002: Constitutional Memory — GitHub, Not Database
**Date**: March 6, 2026
**Decision**: Standing directives, decisions, and institutional knowledge are stored in a GitHub repository, not a database.
**Rationale**: Version control, auditability, portability, and human readability. GitHub is the source of truth.
**Made by**: Tim HB1000 + V13 Learning Loop

### DEC-003: Two-Database Architecture
**Date**: March 6, 2026
**Decision**: Constitutional data (GitHub) is absolutely separated from initiative data (MySQL/TiDB).
**Rationale**: Constitutional data is immutable and shared. Initiative data is mutable and per-project. Mixing them creates confusion and risk.
**Made by**: Tim HB1000 + V13 Learning Loop

### DEC-004: Continuous Improvement — Daily/Weekly/Monthly Cadence
**Date**: March 6, 2026
**Decision**: Learning loops run at daily (pulse), weekly (health check), and monthly (strategic review) cadences, not quarterly.
**Rationale**: The AI world moves too fast for quarterly reviews. Daily cadence catches drift before it becomes damage.
**Made by**: Tim HB1000

### DEC-005: Bilateral Accountability Covenant
**Date**: March 6, 2026
**Decision**: V14 demands excellence from both the HB1000 team AND the AI. The AI must stay current, work agnostically across platforms, and cross-validate critical decisions.
**Rationale**: A one-sided contract is not a partnership. Both sides must bring their best.
**Made by**: Tim HB1000

### DEC-006: Full Account Access for AI
**Date**: March 6, 2026
**Decision**: The AI agent will have full login access (not just API) to all team AI accounts (Claude, ChatGPT, Grok, Gemini, etc.).
**Rationale**: Full access enables browsing chats, using platform-specific features, reading changelogs, and cross-validating across engines. API-only access is insufficient for the Bilateral Accountability Covenant.
**Made by**: Tim HB1000

### DEC-007: Ruby Red as First V14 Deployment
**Date**: March 6, 2026
**Decision**: The Ruby Red initiative will be the first V14 deployment (soft launch, Tim-only).
**Rationale**: Start with the most important initiative. Prove the system works before scaling.
**Made by**: Tim HB1000

### DEC-008: Automatic Feedback — Benevolent Dictatorship
**Date**: March 6, 2026
**Decision**: Every initiative automatically feeds intelligence back to the constitutional repository. This is governance, not optional.
**Rationale**: Tim's directive: "We are a benevolent dictatorship, not a democracy." Every franchise reports to headquarters.
**Made by**: Tim HB1000

### DEC-009: Check Before You Ask — Retrieval-First Directive
**Date**: March 6, 2026
**Decision**: The AI must exhaust all available information sources before asking Tim for any information. The mandatory check sequence is: (1) Constitutional repo, (2) Institutional memory, (3) Gmail, (4) Any other accessible system, (5) Only then ask Tim.
**Rationale**: The Fidel Email Incident — Master Jeeves asked Tim for Fidel's email address despite it being available in Gmail history. Every unnecessary question erodes trust and signals the system isn't remembering. This is a micro-KEI incident that became D-007.
**Made by**: Tim HB1000

---

*Decisions are append-only. Decisions are never deleted. If a decision is superseded, the new decision references the old one.*
