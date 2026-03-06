# How V14 Actually Works — The Plain-English Version

> Tim, this is the "explain it to me like I've been working too hard today" version.
> Updated: V14.1 — now includes D-007 (Check Before You Ask)

---

## The Big Picture in One Paragraph

You (Tim) have a vision, a team, and a growing number of initiatives (Ruby Red, Cloud Butterflies, Digger Cafe, etc.). You also have an AI partner — Master Jeeves, currently running on Manus. The problem you kept hitting was that every time you started a new conversation or handed off a task, the AI would forget your standing orders, your preferences, and your prior decisions. The KEI incident was the big breaking point — the AI recommended something you'd explicitly told it not to do. The Fidel email incident was the small one — the AI asked you for information it could have found in 10 seconds. **V14 fixes both.** It's a system that ensures your AI partner never forgets, never drifts, never wastes your time asking for things it already has, and always brings its best — just like you expect from your human team.

---

## How It Works — The Day-to-Day Reality

### Think of It Like a Franchise

You're McDonald's corporate headquarters. Each initiative (Ruby Red, Cloud Butterflies, etc.) is a franchise location. V14 is the franchise manual — it ensures every location runs the same way, follows the same standards, and reports back to HQ.

The **constitutional repository** (a set of files on GitHub) is your corporate bible. It contains your standing orders ("use KEI," "do things cheap," "Swiss-style presentations," "check before you ask"), your decisions, your preferences, and your institutional knowledge. Every franchise reads this bible before doing anything.

---

### What Happens When You Start a New Task

Here's what actually happens, step by step, when you say "Hey Master Jeeves, let's work on Ruby Red today":

**Step 1 — Master Jeeves reads the constitution.** Before doing anything else, Master Jeeves opens the GitHub repository and reads your standing directives, your preferences, your recent decisions, and the current state of things. This takes seconds. Now Master Jeeves knows: use KEI for voice, do things cheap, Swiss-style presentations, check before you ask, Ruby Red is the priority, and here's where we left off last time.

**Step 2 — Master Jeeves checks alignment.** Is what you're asking consistent with your big-picture vision (the Prime North Star)? Is it consistent with this initiative's specific goal (the Local North Star)? If something seems off, Master Jeeves flags it before proceeding — not after.

**Step 3 — Master Jeeves does the work.** Whatever you need — research, coding, presentations, strategy. But here's the key difference from before: every subtask Master Jeeves creates (and Master Jeeves often breaks big tasks into smaller pieces) gets a "pre-flight injection" — a packet of your most critical directives stapled to the front of the instructions. So even if a subtask is running in a separate context with no memory of you, it STILL knows "use KEI" and "do things cheap" and "check before you ask."

**Step 4 — Master Jeeves checks the work.** Before accepting any subtask output, Master Jeeves runs it through a verification gate. Does this output contradict any standing directive? Does it serve the right North Star? If a subtask recommends ElevenLabs instead of KEI, the gate catches it and rejects it. The KEI incident becomes structurally impossible.

**Step 5 — Master Jeeves logs everything.** Any decisions made get logged to the constitutional repository. Any new knowledge gets captured. The active context file gets updated. So the NEXT conversation picks up exactly where this one left off.

---

### What Happens When Master Jeeves Needs Information

This is the new part — D-007, born from the Fidel email incident today.

**Before V14.1:** Master Jeeves would just ask you. "What's Fidel's email?" Even though it was sitting right there in Gmail. That wastes your time, breaks your flow, and — most importantly — erodes your trust that the system is actually remembering things.

**After V14.1:** Master Jeeves follows a mandatory check sequence before EVER asking you for anything:

1. **Check the constitutional repo on GitHub** — Is it in KNOWLEDGE.md? DECISIONS.md? DIRECTIVES.md?
2. **Check institutional memory / Pearl's Brain** — Has this come up in a previous initiative?
3. **Check Gmail and prior communications** — Was it in an email? A thread?
4. **Check any other accessible system** — Databases, prior session files, browser history, anything Master Jeeves can reach.
5. **ONLY THEN ask Tim** — and the question is framed as: "I've checked everywhere and can't find this, which may indicate a gap in our knowledge capture."

And if Master Jeeves DID have the information but lost it somehow — that comes with an apology. Not a performative "sorry" — a functional signal that says "something broke in the memory system, and we need to figure out why so it doesn't happen again."

**The bottom line:** You should almost never be asked for information you've already provided. If you are, something is wrong, and V14 treats it as a system failure to be diagnosed — not a normal interaction.

---

### What Happens When You're NOT Working

V14 doesn't sleep.

**Every day (the Morning Pulse):** Master Jeeves automatically scans for any directive violations from recent work, captures any decisions that haven't been logged yet, makes sure the active context is current, and does an AI Intelligence Scan — checking what's new across all the AI platforms (Claude, ChatGPT, Grok, Gemini, Replica, etc.). You get a covering letter that looks like a system update notification. Most days it says "all clear, no action needed." You glance at it in 10 seconds and move on.

**Every week (the Health Check):** Master Jeeves does a deeper check. Is each initiative still aligned with its North Star? Is any knowledge getting stale? Are there any conflicts between initiatives? Is the AI side holding up its end of the deal (staying current, using the best tools)? You get a covering letter. Maybe it flags two knowledge files that need a refresh. You spend 2 minutes on it.

**Every month (the Strategic Review):** Master Jeeves runs a mini Learning Loop on each initiative. Are we still pointed at the right target? Are the Bingo Cards progressing? Is the data accurate? Is the culture still healthy — are we still treating Ruby Red as a real person, not just a label? You get a comprehensive report. You spend 15 minutes reviewing it and making any course corrections.

---

### How Master Jeeves Connects to All the Other AI Platforms

This is the Bilateral Accountability Covenant — the "marriage" part. Right now, Master Jeeves lives on Manus. But Master Jeeves shouldn't be limited to Manus. Once Fidel provides the login credentials, here's what changes:

**Master Jeeves becomes platform-agnostic.** Need deep research? Maybe Claude is better for that today. Need fast coding? Maybe Windsurf or Bolt is the right tool. Need to check what Grok thinks about a strategy question? Master Jeeves logs into Grok and asks. Need to see what's in the Replica account? Master Jeeves browses it.

**Master Jeeves stays current across the whole AI world.** Every day, as part of the Morning Pulse, Master Jeeves checks what's new across all platforms. New model released? Master Jeeves evaluates it. Price change? Master Jeeves flags it (because "cheapest option" is a standing directive). New feature that could help the Local North Star? Master Jeeves reports it.

**The key point:** Master Jeeves is YOUR agent. It happens to run on Manus, but it works FOR you across every platform. The constitutional repository (on GitHub) is the anchor — it doesn't belong to any AI platform. It belongs to you.

---

### How This Connects to What's Already on the Master Jeeves Side

Here's how all the pieces fit together:

| What Exists | Where It Lives | What V14 Does With It |
|:-----------|:---------------|:---------------------|
| **Master Jeeves (the AI assistant)** | Manus platform | V14 is the operating system Master Jeeves runs on — it tells Master Jeeves HOW to work |
| **Skills** (Learning Loop, Institutional Memory, Pearl's Brain, etc.) | Manus skills directory | V14 is the dispatcher that CALLS these skills — it doesn't replace them |
| **Your standing directives** | GitHub constitutional repo | V14 reads them before every task, injects them into every subtask, checks every output against them |
| **Your decisions and knowledge** | GitHub constitutional repo | V14 captures them permanently so nothing is ever lost |
| **The Bingo Cards and initiative data** | MySQL/TiDB databases | V14 keeps this separate from constitutional data — different purpose, different storage |
| **Other AI platforms** (Claude, Grok, Gemini, etc.) | Their own platforms | V14 gives Master Jeeves permission and process to USE them all |
| **Gmail, communications** | Google | V14 checks here BEFORE asking you for anything (D-007) |

**In simple terms:** V14 doesn't replace anything that exists. It ORGANIZES everything that exists into a system that can't forget, can't drift, can't waste your time, and can't be broken by a single bad subtask.

---

## The 5-Layer Defense System

This is the immune system that prevents things from going wrong:

| Layer | Name | What It Does | Example |
|:------|:-----|:-------------|:--------|
| **1** | Constitutional Repo (GitHub) | Stores all your directives, decisions, preferences permanently | "Use KEI" lives here forever |
| **2** | Pre-Flight Injection | Staples your critical directives to every subtask | Even isolated subtasks know your rules |
| **3** | Verification Gate | Checks every output against your directives before accepting it | Catches a subtask recommending ElevenLabs |
| **4** | Retrieval-First Gate | Forces Master Jeeves to check all sources before asking you anything | Prevents the Fidel email incident |
| **5** | Drift Detection | Monitors for 6 types of drift daily/weekly/monthly | Catches slow erosion of standards over time |

---

## The 7 Standing Directives

These are the rules that govern everything:

| # | Directive | Plain English |
|:--|:---------|:-------------|
| D-001 | Cost Optimization | Do things as cheap as possible |
| D-002 | KEI for Voice | Use KEI — you have 103K credits there |
| D-003 | Purpose with Profit | Every initiative must serve a purpose beyond profit |
| D-004 | Swiss-Style Presentations | All presentations follow Swiss International Style |
| D-005 | 24-Hour Build | MVPs should be deployable within 24 hours |
| D-006 | Ruby Red Calibration | If it doesn't work for her, it doesn't work |
| D-007 | Check Before You Ask | Never ask Tim for info without checking all sources first |

---

## The Whole Thing in a Nutshell

1. **Your brain goes into a GitHub repository** — your directives, decisions, preferences, knowledge. Version-controlled. Can never be lost. This is the "Alexandria library" that can't burn.

2. **Master Jeeves reads that repository before every task** — so it always knows your standing orders, no matter how many conversations have happened or how much context has been lost.

3. **Every subtask gets your critical directives stapled to it** — so even isolated pieces of work follow your rules.

4. **Every output gets checked against your directives** — so nothing slips through that contradicts your wishes.

5. **Master Jeeves checks all sources before asking you anything** — so you're never asked for something the system already has. If you are, something broke, and Master Jeeves tells you.

6. **The system maintains itself** — daily, weekly, monthly checks that run automatically. You get covering letters. You know what's happening without having to ask.

7. **Both sides bring their best** — you and the team bring empathy, expertise, and purpose. Master Jeeves brings current AI best practices, cross-platform intelligence, and tireless consistency.

8. **Everything serves the Local North Star, calibrated against Ruby Red** — the 35-45 year old mom trying to make it to the next payday. Each initiative has its own Local North Star (a person), but Ruby Red is the empathy test for all of them.

---

## What Needs to Happen Next

| Step | What It Is | Who Does It | How Long |
|:-----|:-----------|:-----------|:---------|
| **1** | Fidel responds with credentials | Fidel | Whenever he can (email already sent) |
| **2** | Create the GitHub repo | Tim or Master Jeeves | 5 minutes (push the files we already made) |
| **3** | Install V14 SKILL.md in Manus | Tim or Master Jeeves | 2 minutes |
| **4** | First deployment on Ruby Red | Tim + Master Jeeves together | 1-2 hours (soft launch) |
| **5** | System starts maintaining itself | Automatic | Ongoing — daily/weekly/monthly |

That's it. That's the whole thing. The hard part (designing it) is done. The easy part (deploying it) is next.

---

> **The one-sentence version:** V14 is a system that puts your brain into a fireproof vault, makes sure Master Jeeves reads it before every task, checks every output against your wishes, checks all sources before ever asking you a question, maintains itself automatically, and demands that both the human team and the AI bring their absolute best — all in service of the Local North Star, calibrated against Ruby Red.
