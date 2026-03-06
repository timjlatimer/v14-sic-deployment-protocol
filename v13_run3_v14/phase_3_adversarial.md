# V13 Run 3 — Phase 3: System of Adversarial Integrity (Society of Guardians)

## Session ID: LL-V13-V14DESIGN-20260306

---

## GUARDIAN 1: DEVIL'S ADVOCATE (5 Conditions)

### DA-1: THE SCOPE MONSTER — V14 is trying to do too much in one skill

**Attack**: V14 wraps four major components (Constitutional Memory, V13, HB1000 Manual, Bingo City). Each is complex on its own. Putting them in one skill creates a 500+ line SKILL.md that no agent can reliably follow. The V13 skill alone is 400+ lines. V14 would need to be 1000+ lines — far beyond what any AI agent can hold in working memory.

**Severity**: HIGH — this could make V14 undeployable.

**Integration**: V14 SKILL.md must be a DISPATCHER, not a monolith. It orchestrates by calling existing skills:
- Phase 0 (Orient): Calls `constitutional-memory` skill
- Phase 2 (Evaluate): Calls `learning-loop-v13` skill
- Phase 3 (Build): Calls Bingo City scaffold tools
- The V14 skill itself stays under 300 lines — it's the franchise manager, not the franchise manual

**Condition**: V14 SKILL.md must be a dispatcher under 300 lines that calls existing skills. NOT a monolith.

### DA-2: THE CHICKEN-AND-EGG — Can't run V14 without the constitutional repo, can't populate the repo without running V14

**Attack**: V14 Phase 0 says "clone constitutional repository." But the repo doesn't exist yet. The first V14 deployment has a bootstrap problem. And who populates the repo? V14 assumes it's already populated. But Tim hasn't done that yet.

**Severity**: HIGH — blocks first deployment.

**Integration**: Add Phase -1: BOOTSTRAP. This is a one-time-only phase that:
1. Creates the `tim-constitution` GitHub repo
2. Populates the 6 constitutional files from known directives (we have them from 3 V13 runs)
3. Commits and pushes
4. Only runs ONCE — all subsequent V14 deployments skip to Phase 0

**Condition**: V14 must include a Bootstrap phase that creates and populates the repo on first run.

### DA-3: THE BINGO CITY ASSUMPTION — The scaffold may not be compatible with V14's requirements

**Attack**: V14 assumes Bingo City can be "configured by Local North Star." But the existing Bingo City was built for Ruby Red specifically. Its database schema, its card definitions, its gamification — all hardcoded for one use case. V14 assumes configurability that may not exist.

**Severity**: MODERATE — affects post-MVP, not MVP.

**Integration**: MVP explicitly uses the EXISTING Ruby Red Bingo City as-is. V14 Phase 1 includes a "scaffold compatibility check." Post-MVP adds a Bingo City abstraction layer that makes the scaffold configurable. Don't pretend the scaffold is already configurable — be honest about what MVP can do.

**Condition**: MVP must use existing Ruby Red scaffold as-is. Post-MVP must include abstraction layer. V14 must be honest about what's configurable NOW vs LATER.

### DA-4: THE TEAM PROBLEM — Team members on Jeeves can't load skills

**Attack**: V14 assumes agents load the skill. But team members working in Jeeves may not know about V14, may not load it, or may not have it available. The skill-not-loaded scenario from the Constitutional Memory run applies here too — and it's WORSE because there are multiple team members, not just Tim.

**Severity**: HIGH — the team is the primary exposure.

**Integration**: Two mitigations:
1. Tim loads V14 at the START of any initiative chat that team members will use. V14 becomes the initialization step, not an afterthought.
2. The constitutional repo's README.md includes a "TEAM MEMBER QUICK START" — a simplified set of instructions any team member can follow even without the full V14 skill.
3. Post-MVP: Team onboarding protocol that walks each member through loading the skill.

**Condition**: V14 must include team member access path. README.md must have quick-start for non-skill users.

### DA-5: THE V13 NESTING PROBLEM — Running a full V13 inside V14 takes hours

**Attack**: V14 Phase 2 says "Run Learning Loop V13." A full V13 at PRIMAL is 9 phases, each requiring approval. That's hours of work INSIDE a V14 deployment. This makes "drop a V14" a multi-day affair, not the quick deployment Tim envisions.

**Severity**: MODERATE — affects perception and usability.

**Integration**: V14 offers THREE V13 intensity options:
- **FULL V13**: All 9 phases at chosen intensity. For major initiatives. Takes hours.
- **EXPRESS V13**: Phases 0, 2, 3, 6 only (Intake, Innovation, Adversarial, Certification). For established initiatives. Takes 1-2 hours.
- **SKIP V13**: For initiatives that have already been V13-certified. V14 just deploys the stack. Takes 30-60 minutes.

Tim chooses at Phase 2 entry. Default for new initiatives = EXPRESS. Default for certified = SKIP.

**Condition**: V14 must offer V13 intensity options. Not every deployment needs full 9-phase V13.

---

## GUARDIAN 2: NORTH STAR'S VOICE (4 Conditions)

### NS-1: THE HUMAN-AI INTERFACE — V14's handoff between Tim and the agent must be extraordinary

**Attack**: V14 is the most complex protocol Tim will use. If the interface between Tim and the agent during V14 execution is clunky, confusing, or requires Tim to remember what phase he's in, it fails. Tim said the handoff must be "extraordinary." The current design has 5 phases with multiple steps each — that's a lot of cognitive load on Tim.

**Severity**: HIGH — directly impacts Tim's trust and willingness to use V14.

**Integration**: V14 must include a STATUS DASHBOARD at every phase transition:
```
╔═══════════════════════════════════════════╗
║  SIC DEPLOYMENT PROTOCOL (V14)            ║
║  Initiative: [name]                       ║
║  Local North Star: [description]          ║
║  ✅ Orient    ✅ Establish    □ Evaluate   ║
║  □ Build     □ Deploy                     ║
║  Current: Phase 2 — Evaluating deliverable║
║  Next action needed from Tim: [specific]  ║
╚═══════════════════════════════════════════╝
```

Tim sees ONE line telling him what's needed. The agent handles everything else.

**Condition**: V14 must display a status dashboard at every phase transition showing exactly what Tim needs to do next.

### NS-2: THE RUBY RED THREAD — Every V14 deployment must trace back to Ruby Red

**Attack**: As V14 gets deployed across multiple initiatives (PTK, Blue Seal, Fighting Bureaucracy), there's a risk that some initiatives drift from the Ruby Red calibration. The Local North Star might override the Prime North Star in practice. "Fighting Bureaucracy" might optimize for political impact and forget about the 35-45 year old mom.

**Severity**: HIGH — this is the soul of the mission.

**Integration**: V14 Phase 0 must include a RUBY RED CHECK:
- "How does this initiative serve Ruby Red?"
- If the answer is indirect (e.g., "Fighting Bureaucracy helps Ruby Red by holding systems accountable"), document the connection explicitly.
- If the answer is "it doesn't directly serve Ruby Red," flag for Tim's review — it may still be valid, but Tim must consciously approve the exception.
- Write the Ruby Red connection to initiatives/[name]/ruby-red-connection.md

**Condition**: Every V14 deployment must document its Ruby Red connection. No exception without Tim's explicit approval.

### NS-3: THE CHEAPEST OPTION — V14 deployment must cost $0 or near-$0

**Attack**: V14 deploys a web-db-user scaffold (which has infrastructure costs), populates databases, and builds interfaces. If each V14 deployment costs money, Tim can't deploy it across 5-6 initiatives without significant expense. This contradicts the "cheapest option" directive.

**Severity**: MODERATE — the Manus platform covers most costs, but database hosting may not be free.

**Integration**: V14 must include a COST CHECK at Phase 1:
- What are the infrastructure costs for this deployment?
- Are there free-tier options?
- Does this comply with DIRECTIVES.md "cheapest option" rule?
- If costs exceed $0/month, present alternatives to Tim before proceeding.

**Condition**: V14 must include cost check. No deployment proceeds without Tim knowing the cost.

### NS-4: THE LEGACY QUESTION — V14 outputs must be Tim's intellectual property, not locked in a platform

**Attack**: If V14 deploys everything inside Manus sandboxes and Manus-hosted databases, Tim's entire Alexandria Library is platform-dependent. If Manus changes pricing, features, or shuts down, Tim loses everything. This is the "Alexandria burning" scenario at the platform level.

**Severity**: HIGH — existential risk to the mission.

**Integration**: V14 must include an EXPORT PROTOCOL:
- Constitutional repo is already on GitHub (platform-independent) ✓
- Initiative databases must have scheduled exports to GitHub or local backup
- Bingo City source code must be exportable (not just hosted)
- V14 Phase 4 (Deploy) includes: "Verify all outputs are exportable and backed up"

**Condition**: Every V14 deployment must be exportable. No platform lock-in.

---

## GUARDIAN 3: THE PRAGMATIST (5 Conditions)

### PR-1: THE MVP MUST BE DEPLOYABLE IN ONE SESSION — Not "this week," but "today"

**Attack**: Tim said "get to the MVP." The MVP scope says "deploy this week." But Tim's urgency is higher than that. He has team members working WITHOUT governance RIGHT NOW. The MVP should be deployable in a single Manus session — 2-4 hours — not spread across a week.

**Severity**: HIGH — urgency is real.

**Integration**: Redefine MVP as "Single Session Deployable":
- Session 1 (2-4 hours): Bootstrap repo + populate constitutional files + create V14 skill + connect to existing Ruby Red Bingo City
- That's it. One session. Everything else is Post-MVP.

**Condition**: MVP must be deployable in a single 2-4 hour session.

### PR-2: THE SKILL SIZE CONSTRAINT — Manus skills have practical limits

**Attack**: The skill-creator documentation suggests SKILL.md should be under 500 lines. V14 is the most complex skill in the ecosystem. If it exceeds 500 lines, it won't be reliably loaded or followed.

**Severity**: HIGH — structural constraint.

**Integration**: Already addressed by DA-1 (dispatcher pattern). V14 SKILL.md stays under 300 lines by calling other skills. The complexity lives in the sub-skills, not the dispatcher.

**Condition**: V14 SKILL.md must be under 300 lines. Dispatcher pattern mandatory.

### PR-3: THE NAMING CLARITY — "V14" implies it replaces V13

**Attack**: Tim confirmed the name "SIC Deployment Protocol (V14)." But calling it "V14" will confuse team members and future agents into thinking it's "Learning Loop Version 14" — a replacement for V13. This naming collision will cause drift.

**Severity**: MODERATE — affects communication clarity.

**Integration**: The skill must explicitly state in its first lines:
- "V14 is the SIC Deployment Protocol. It is NOT Learning Loop Version 14."
- "V14 CALLS V13. V13 remains the evaluation engine. V14 is the deployment orchestrator."
- Consider alternative shorthand: "SDP" or "Deploy-14" to reduce confusion.

**Condition**: V14 skill must include disambiguation in first 5 lines. Consider alternative shorthand.

### PR-4: THE TESTING PROBLEM — How do you test V14 without deploying a real initiative?

**Attack**: V14 is a deployment protocol. You can't really test it without deploying something. But deploying something with an untested protocol is risky. The first deployment IS the test — and if it fails, Tim's trust drops again.

**Severity**: MODERATE — first deployment is high-stakes.

**Integration**: The Ruby Red initiative IS the test case — and it's the safest one because:
1. Bingo City scaffold already exists (reduces build risk)
2. Tim is deeply familiar with it (can spot errors immediately)
3. It's the most documented initiative (most constitutional data available)
4. If something goes wrong, Tim catches it before team members see it

V14 Phase 4 (Deploy) includes a "soft launch" option: deploy to Tim only, verify, THEN open to team.

**Condition**: First V14 deployment must be Ruby Red with soft launch (Tim-only first).

### PR-5: THE MAINTENANCE REALITY — Who maintains 5-6 deployed V14 initiatives?

**Attack**: Each V14 deployment creates a Bingo City instance with a database, an operating manual, and initiative-specific files. Multiply by 5-6 initiatives. That's 5-6 databases, 5-6 sets of Bingo Cards, 5-6 operating manuals. Who keeps them updated? Tim can't maintain all of them manually.

**Severity**: MODERATE — affects scaling, not MVP.

**Integration**: Post-MVP includes:
1. Automated weekly health check across all deployed initiatives
2. Constitutional repo update automatically propagates to all initiatives (because they all read from the same repo)
3. Initiative-specific maintenance is the responsibility of whoever owns that initiative's Bingo City
4. V14 Phase 4 includes assigning a maintenance owner

**Condition**: Post-MVP must include maintenance assignment and automated health checks.

---

## ACCESSIBILITY AUDIT

| Dimension | Score | Assessment |
|:----------|:------|:-----------|
| Tim can understand it | 5/5 | Franchise Kit metaphor, stack diagram, before/after example |
| Tim can explain it to team | 4/5 | Dashboard helps. But team-facing docs are Post-MVP. |
| Tim can deploy it | 4/5 | MVP is single-session. But first deployment is also the test. |
| Tim can verify it works | 5/5 | Tim's Trust Test + status dashboard + Ruby Red check |
| Tim can maintain it | 4/5 | Constitutional repo is low-maintenance. Multiple Bingo Cities need Post-MVP automation. |
| **Total** | **22/25** | |

---

## ALL 14 CONDITIONS SUMMARY

| ID | Condition | Priority | Integration |
|:---|:----------|:---------|:------------|
| DA-1 | V14 SKILL.md must be dispatcher under 300 lines | P1 | Calls existing skills, not monolith |
| DA-2 | Bootstrap phase for first-run repo creation | P1 | Phase -1: one-time setup |
| DA-3 | MVP uses existing Ruby Red scaffold as-is | P1 | Honest about configurability timeline |
| DA-4 | Team member access path in README.md | P1 | Quick-start for non-skill users |
| DA-5 | V13 intensity options (Full/Express/Skip) | P1 | Not every deployment needs 9-phase V13 |
| NS-1 | Status dashboard at every phase transition | P1 | Shows Tim exactly what's needed next |
| NS-2 | Ruby Red check on every deployment | P1 | Document connection, flag exceptions |
| NS-3 | Cost check at Phase 1 | P2 | No deployment without Tim knowing cost |
| NS-4 | Export protocol — no platform lock-in | P1 | All outputs must be exportable |
| PR-1 | MVP deployable in single 2-4 hour session | P1 | Redefine MVP scope |
| PR-2 | SKILL.md under 300 lines (dispatcher) | P1 | Already addressed by DA-1 |
| PR-3 | Naming disambiguation in first 5 lines | P2 | "V14 is NOT Learning Loop V14" |
| PR-4 | First deployment = Ruby Red with soft launch | P1 | Tim-only first, then team |
| PR-5 | Post-MVP maintenance assignment + health checks | P3 | Scaling concern, not MVP |

**P1 (Must integrate now)**: 10
**P2 (Should integrate)**: 2
**P3 (Post-MVP)**: 2

---

## KPI SCORING

| Dimension | Phase 2 | Phase 3 | Delta | Justification |
|:----------|:--------|:--------|:------|:-------------|
| Completeness | 17 | 19 | +2 | Bootstrap phase, V13 intensity options, export protocol close remaining gaps |
| Clarity | 17 | 19 | +2 | Status dashboard, naming disambiguation, dispatcher pattern make it tangible |
| Accuracy | 16 | 19 | +3 | Honest about scaffold configurability, cost reality, maintenance scaling |
| Depth | 17 | 18 | +1 | Ruby Red check, team access path, soft launch add operational depth |
| Actionability | 16 | 18 | +2 | Single-session MVP, Ruby Red first, soft launch make it immediately deployable |
| **TOTAL** | **83** | **93** | **+10** | |

---

## PHASE COMPLETION PROOF

**Score**: 93/100
**Guardians**: DA (5), NS (4), PR (5) = 14 conditions
**All 14 integrated**: 10 P1, 2 P2, 2 P3
**Accessibility**: 22/25
**Key finding**: DA-1 (dispatcher pattern) is the most important — it makes V14 buildable. NS-1 (status dashboard) is the most important for Tim's trust. PR-1 (single-session MVP) is the most important for urgency.
**Move 37 Alpha**: Franchise Kit validated — the Bootstrap phase IS "opening the franchise headquarters." The first deployment IS "opening the first franchise location."
