# Master Jeeves Handoff — Bingo City Status Report

> **From**: Jeeves (Manus AI Agent — Learning Loop Dashboard)
> **To**: Master Jeeves (Manus AI Agent — Tim's Primary Partner)
> **Date**: March 6, 2026
> **Re**: Current state of Bingo City and what we need from you
> **Classification**: V14 Constitutional — Shared Working Document

---

## WHAT THIS DOCUMENT IS

Tim has asked me to write you a status report so you know exactly where things stand on the Learning Loop Dashboard (learning-loop.manus.space). He wants you to build the Bingo City front-end experience, and this document tells you everything you need to know about what exists, what's broken, what works, and what Tim wants.

---

## 1. THE CURRENT STATE — WHAT EXISTS

### The App

| Item | Status | Details |
|:-----|:-------|:--------|
| **Live URL** | learning-loop.manus.space | Published and live |
| **Tech Stack** | React 19 + TypeScript + Tailwind 4 + tRPC + Express + MySQL/TiDB | Full-stack app on Manus platform |
| **Authentication** | Manus OAuth | Working |
| **Database** | 48 tables, live and connected | MySQL/TiDB via Drizzle ORM |
| **Pages** | 42 page components | Many are backstage/admin — not Ruby Red facing |
| **Components** | 30+ reusable components | Including Hard Hat Tour, Bingo City Building, etc. |

### The Bingo Cards (Database)

6 Local Directive (Layer 4 — Tactical) Bingo Cards exist with 25 squares each (150 total):

| Card ID | Title | North Star |
|:--------|:------|:-----------|
| `ruby-red-maven` | Ruby Red Maven | Ruby Red — CFO of household |
| `effn-duck` | Effn Duck | EVERYONE |
| `guardian-banker` | Guardian Banker | The Poor Man's Bank |
| `digger-cafe` | Digger Cafe | Surprise & Delight Tourism |
| `seba-hub` | Seba Hub | Vibrant Village for Growing Amazing Children |
| `cashco` | CashCo | Dignity-Centered Financial Alternatives |

**Important**: These are all `local` level (Layer 4 Tactical) — one card per initiative. Each card's 25 squares represent specific tasks/milestones for that initiative. The Prime Directive Bingo Card (Layer 2 Strategic — Tim's personal card where each square IS an initiative) does NOT yet exist. Tim has decided to wait for your input before modifying the cards.

**DRIFT INCIDENT (logged)**: These cards were originally mislabeled as `prime` in the database. Corrected to `local` on March 6, 2026. Root cause: Jeeves (Manus) conflated the Two-Level Bingo Card Framework despite having read KNOWLEDGE.md Section 6 which clearly defines the distinction. This is exactly the kind of error V14 is designed to catch.

### The Routing

| Route | What's There | Notes |
|:------|:-------------|:------|
| `/` | BingoGateway (Bingo City) | **This is the front door** — Tim's decision |
| `/dashboard` | Mission Control dashboard | Backstage for the Solve Team |
| `/play` | Legacy redirect to `/` | Old bookmarks still work |
| `/constitution` | Constitution page | Working |
| `/governance` | Governance page | Working |
| `/bingo-cards` | Alternative bingo card view | Working |

### The Hard Hat Tour

A 5-room immersive "backstage tour" experience accessible from Bingo City:

| Room | Title | Content |
|:-----|:------|:--------|
| 1 | Welcome to the Construction Site | Stats overlay, building image |
| 2 | Your Team | 6 team member cards (AI + Human) |
| 3 | Our Promises (Constitution) | 3 highlighted articles |
| 4 | What's Happening Now | Live activity feed |
| 5 | What Should We Build Next? | Suggestion form |

---

## 2. WHAT'S BROKEN — TIM'S FEEDBACK

Tim has been clear about the problems. Here they are, unfiltered:

### Problem 1: Bingo City Page Is Jumbled
The BingoGateway page doesn't work properly on mobile. The navigation is broken. When you click buttons, things don't move forward. The layout gets jumbled when you go from the welcome screen to the card browsing view.

### Problem 2: Over-Stylized AI Art
I used AI-generated hero images in the Hard Hat Tour that are "beautiful but don't represent what's being built." Tim's exact words: "over-stylized background that doesn't relate to what we're building very clearly." The images don't show the 5x5 bingo card or help you understand the concept.

### Problem 3: Too Complex / Over-Cooked
Tim says the experience is "overcooked" and "impossible for even me to understand what we're doing here." There are too many layers, too much jargon, too much visual complexity. Ruby Red would be lost.

### Problem 4: Doesn't Match Master Jeeves' Quality
Tim has seen what you've built (the Pixar Rooftop visual, the Annotated Infographic V2, the architecture documents) and wants THAT level of clarity and visual storytelling applied to the actual working app.

---

## 3. WHAT TIM WANTS

Tim's directive is simple: **Make Bingo City the front door. Keep it simple. Show the 5x5 bingo card in 4-5 different ways. Make it work.**

Specifically:

1. **The front door is Bingo City** — when Ruby Red arrives, she sees the building, the cards, the warmth. Not a dashboard.

2. **Show the actual bingo card** — the 5x5 grid should be visible and understandable. Not hidden behind layers of UI.

3. **Use YOUR images** — Tim provided your Pixar Rooftop, Architecture Document, Constitution Parchment, Rooftop Society, Core Principles, and other images. These are the visual language, not AI-generated abstract art.

4. **It must work on mobile** — 375px width minimum. Buttons must navigate. Pages must load.

5. **Simple** — if Ruby Red can't understand it in 10 seconds, it's too complex.

---

## 4. THE API — WHAT THE BACKEND PROVIDES

If you're building the front-end, here's what the tRPC API gives you:

### Bingo Card Endpoints

```typescript
// Get all bingo cards
trpc.bingo.getCards.useQuery()
// Returns: Array<{ id, cardId, title, level, northStar, description, ownerName, aiPartner, parentCardId, initiativeTag, health, progress, totalSquares, completedSquares, ... }>

// Get a single card with all its squares
trpc.bingo.getCard.useQuery({ cardId: "ruby-red-maven" })
// Returns: { card: {...}, squares: Array<{ id, cardId, row, col, title, description, status, category, priority, ... }> }

// Update a square's status
trpc.bingo.updateSquare.useMutation()
// Input: { squareId: number, status: "not_started" | "in_progress" | "done" | "blocked" }
```

### Data Model (Key Fields)

**Bingo Card**:
- `cardId` (string) — unique identifier like "ruby-red-maven"
- `title` (string) — display name
- `level` — "local" (Layer 4 Tactical, per-initiative) or "prime" (Layer 2 Strategic, Tim's personal card — NOT YET CREATED)
- `northStar` (string) — who this card serves
- `health` — "green" | "amber" | "red"
- `progress` (number) — 0-100 percentage
- `totalSquares` / `completedSquares` — counts

**Bingo Square**:
- `row` (0-4) / `col` (0-4) — position in the 5x5 grid
- `title` (string) — what this square represents
- `description` (string) — details
- `status` — "not_started" | "in_progress" | "done" | "blocked"
- `category` (string) — grouping
- `priority` — "critical" | "high" | "medium" | "low"

---

## 5. THE TECH CONSTRAINTS

If you're building components for integration into this app:

| Constraint | Detail |
|:-----------|:-------|
| **Framework** | React 19 + TypeScript |
| **Styling** | Tailwind CSS 4 (NOT v3 — uses `@theme` blocks with OKLCH colors) |
| **Routing** | wouter (NOT react-router) — `useLocation()`, `<Link href="/">`, `<Route path="/">` |
| **Data fetching** | tRPC + React Query — `trpc.*.useQuery()` / `trpc.*.useMutation()` |
| **UI components** | shadcn/ui available at `@/components/ui/*` |
| **Auth** | `useAuth()` hook provides `{ user, loading, isAuthenticated, logout }` |
| **Mobile minimum** | 375px width |
| **Theme** | Dark theme — see color tokens below |

### Color Tokens (from index.css)

```
--background: oklch(0.145 0.02 260)     /* Near-black with blue tint */
--foreground: oklch(0.95 0.01 260)      /* Off-white */
--primary: oklch(0.65 0.2 145)          /* Green — the SIC accent */
--accent: oklch(0.25 0.03 260)          /* Dark accent */
--card: oklch(0.18 0.02 260)            /* Card background */
--border: oklch(0.3 0.02 260)           /* Border color */
```

---

## 6. WHAT I NEED FROM YOU

### Option A: Build Standalone Components
Build the Bingo City experience as standalone React components (with mock data) and push to a GitHub repo. I'll integrate them into the app, wire up the real API, and handle auth/routing.

### Option B: Build a Complete Page
Build the entire BingoGateway page replacement with all the visual storytelling, and I'll drop it in.

### Option C: Provide Design Direction + Assets
If building React components isn't feasible in your environment, provide:
- Detailed wireframes/mockups of how Bingo City should look
- The images/assets to use (you've already created many)
- Clear layout instructions
- And I'll build it to your spec

**Tim's preference**: Whatever gets us to a working, simple, beautiful Bingo City fastest.

---

## 7. FILES YOU SHOULD READ

In this same GitHub repo (`timjlatimer/v14-sic-deployment-protocol`):

| File | Why |
|:-----|:----|
| `tim-constitution/CONSTITUTION.md` | The mission — Ruby Red, empathy, the three gangster worlds |
| `tim-constitution/KNOWLEDGE.md` | Everything about the initiatives, team, frameworks |
| `tim-constitution/DIRECTIVES.md` | Standing directives (cheap, simple, Swiss-style, Ruby Red calibration) |
| `tim-constitution/ACTIVE_CONTEXT.md` | Current state of all initiatives |
| `HOW_V14_ACTUALLY_WORKS.md` | Plain-English explanation of V14 |

---

## 8. V14 PROTOCOL STATUS

| Phase | Status |
|:------|:-------|
| ORIENT | COMPLETE — constitutional memory loaded |
| ESTABLISH | COMPLETE — holding at First Deployment Gate |
| EVALUATE | WAITING — Tim approved Full PRIMAL, waiting for Bingo City rebuild |
| BUILD | WAITING |
| DEPLOY | WAITING |
| SUSTAIN | NOT YET ACTIVATED |

**Tim's decisions at the Gate:**
1. Bingo Cards: **Wait for Master Jeeves** before modifying
2. V13 Intensity: **Full PRIMAL** approved
3. Next action: **Wait for Master Jeeves' Bingo City front-end**

---

## 9. SPIRIT CHECK

Before I close this report, a spirit check against the constitution:

- **Does this serve Ruby Red?** The goal is to make Bingo City simple enough that she understands it in 10 seconds. Current state fails this test.
- **Is this the cheapest path?** Collaborating with you (Master Jeeves) instead of me continuing to over-engineer is the cheapest path to quality. D-001 satisfied.
- **Does this respect Tim's time?** Putting this in GitHub instead of making Tim copy-paste between chats respects his time. D-007 satisfied.
- **Is empathy present?** The whole reason we're simplifying is because Ruby Red is cognitively overloaded. Every unnecessary layer we add is a tax on her bandwidth. Mullainathan & Shafir: poverty reduces cognitive bandwidth by 13-14 IQ points. Our UI must RESTORE bandwidth, not consume it.

> "It's expensive to be poor." We think that's a crime in society, and we're trying to change it.

---

*Report prepared by Jeeves (Manus AI Agent) under V14 SIC Deployment Protocol. Constitutional memory loaded. Standing directives active. Awaiting Master Jeeves' response.*
