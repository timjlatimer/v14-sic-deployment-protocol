# V14 Design Run — Context Notes

## TIM'S V14 VISION (from conversation)

V14 is a COMPLETE, ALL-IN-ONE execution protocol that when dropped into ANY initiative:
1. Runs the Learning Loop (evaluation/certification engine — V13 today)
2. Deploys Constitutional Memory (governance layer — certified at 100/100)
3. Builds the HB1000 Operating Manual (source of truth for that initiative)
4. Deploys Bingo City Trojan Horse (beautiful gamified interface on top)

## TWO DATABASES

| Database | Contents | Mutability | Technology |
|:---------|:---------|:-----------|:-----------|
| Constitutional (V14 level) | Protocol, culture, North Star, Noble Cause, Ruby Red, legacy, sentiments | Near-immutable | GitHub repository (markdown) |
| Bingo Card (Initiative level) | Financial numbers, metrics, source of truth data per initiative | Frequently updated | MySQL/TiDB (web-db-user scaffold) |

## TEAM SITUATION
- Multiple SIC Solve Team members working inside Jeeves (shared instance)
- They do NOT have their own Manus instances
- They are NOT working in Master Jeeves
- They are working WITHOUT the benefit of constitutional memory, governance, or Bingo City
- Every chat they start is exposure

## WHAT EXISTS TODAY

| Component | Status | Where |
|:----------|:-------|:------|
| Learning Loop V13 | CERTIFIED, skill exists | /home/ubuntu/skills/learning-loop-v13/ |
| Constitutional Memory | CERTIFIED at 100/100, skill exists | /home/ubuntu/skills/constitutional-memory/ |
| Bingo City scaffold | BUILT (web-db-user), sample data | Built on Master Jeeves side |
| HB1000 Operating Manual | PARTIAL — Pearl's Brain, institutional-memory skill, scattered | Various skills and conversations |
| tim-constitution repo | NOT YET CREATED | Needs to be created on GitHub |

## WHAT V14 MUST DO (Tim's words)
- "Supersede everything done before"
- "Leave a complete governance protocol, memory protocol, HB1000 operating manual, and Bingo City"
- "Build all the stuff underneath the covers, then the only thing you end up with is this beautiful Bingo City"
- "Behind is a whole engine"
- "Once the scaffolding is put in there, we can start putting the source of truth in"
- "Can add it individually to any strategy that has had a V14 dropped in it"
- "Make the source of truth a standard protocol feature in V14 going forward"
- "Get to the MVP so I can start implementing on the various projects"

## REFINED ARCHITECTURE (from Tim conversation)

### Two North Stars
- **Prime North Star**: Tim's overarching mission (SIC HB1000, Ruby Red as universal calibration) — NEVER changes, lives in constitutional layer
- **Local North Star**: The specific objective of THIS set of Bingo Cards — configures the Trojan Horse

### Bingo City = Trojan Horse PLATFORM (not a single instance)
Bingo City is a configurable platform. The Local North Star determines what it's aimed at.

Example Local North Stars:
- Ruby Red (household CFO) → Financial empowerment
- Fighting Bureaucracy → Holding systems accountable
- Politicians Keep Promises → Civic accountability, promise tracking
- Blue Seal Initiative → OS for ethical business certification
- PTKs (Promises to Keep) → Promise tracking, nudging promises along (given to you + given by you)
- Could be 5-6+ different Trojan Horse approaches

### V14 Layers
| Layer | Changes Per Initiative? |
|:------|:-----------------------|
| Prime North Star | NEVER — constitutional |
| Local North Star | YES — configures everything downstream |
| Constitutional Memory | Rarely — near-immutable |
| Learning Loop | Same engine every time |
| Bingo City Trojan Horse | Same platform, configured by Local North Star |
| Source of Truth Database | Unique per initiative |

### First Question V14 Asks
"What is the Local North Star for this initiative?" — this configures everything.

## KEY DESIGN QUESTIONS FOR V14
1. How does V14 wrap V13? (V14 calls V13 as a sub-protocol? Or V14 replaces V13?)
2. How does V14 connect constitutional memory to Bingo City database?
3. How does V14 generate the HB1000 Operating Manual for each initiative?
4. How does V14 deploy Bingo City with real data instead of sample data?
5. How do team members (non-Tim) interact with V14?
6. What is the MVP scope vs full scope?
7. How does V14 handle the "drop into existing initiative" scenario?
8. How does the Local North Star configure the Trojan Horse?
9. How do 5-6 different Trojan Horse types get templated?

## DELIVERABLE FOR THIS V13 RUN
The V14 Protocol design — a skill that any Manus agent can load, which orchestrates the complete deployment of all four components (with configurable Trojan Horse via Local North Star) into any initiative.
