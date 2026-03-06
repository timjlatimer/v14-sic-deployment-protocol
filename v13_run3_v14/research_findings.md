# V14 Design — Phase 2 Research Findings

## Source 1: Agent-MCP Framework (GitHub - rinadelph/Agent-MCP)
**Key Pattern**: Persistent Knowledge Graph as shared context between agents
- "Think Obsidian for your AI agents — a living knowledge graph where multiple AI agents collaborate through shared context"
- Agents query shared knowledge to understand requirements, architectural decisions, implementation details
- "Nothing gets lost between sessions"
- Bootstrap protocol: agents start with minimal context, query knowledge graph for relevant info
- Initialization involves deploying specialized agents for different roles, each with clear responsibilities
- MCP tools: create_agent, assign_task, query_project_context, manage_agent_communication
**V14 Relevance**: The constitutional repository IS the persistent knowledge graph. V14 is the bootstrap protocol that initializes agents with the right context.

## Source 2: Praetorian — Deterministic AI Orchestration
**Key Pattern**: Platform architecture for autonomous development
- Treats LLM as a component within a deterministic orchestration system
- Sequential phases with clear dependencies
- Each phase has defined inputs, outputs, and verification gates
**V14 Relevance**: V14 should be deterministic — same inputs produce same outputs. The franchise kit is a deterministic deployment.

## Source 3: Service Orchestration Pattern (CloudNative)
**Key Pattern**: Three composition patterns — Orchestration, Choreography, Saga
- Service Orchestration: Central coordinator manages the sequence
- Service Choreography: Each service knows what to do next
- Saga: Long-running transactions with compensation
**V14 Relevance**: V14 is an ORCHESTRATOR — it manages the sequence of deploying components. Not choreography (agents don't self-organize) and not saga (no compensation needed).

## Source 4: Akka — AI Orchestration Patterns
**Key Pattern**: Sequential orchestration for multi-step processes
- "Ideal for multi-step processes with clear linear dependencies"
- "Workflow progression that doesn't change between runs"
**V14 Relevance**: V14 is sequential orchestration — same steps every time, configured by Local North Star.

## Source 5: Shopify Roast Framework
**Key Pattern**: Convention-oriented workflow orchestration
- "Structured AI workflows that interleave non-deterministic AI"
- Convention over configuration — reduce setup by following patterns
**V14 Relevance**: V14 should be convention-oriented — follow the franchise kit pattern, minimize configuration.

## KEY SYNTHESIS FOR V14 DESIGN

### V14 = Sequential Orchestrator + Persistent Knowledge Graph + Franchise Kit

The pattern that emerges across all sources:

1. **Orchestrator Pattern**: V14 is a central coordinator that manages the deployment sequence
2. **Persistent Knowledge Graph**: The constitutional repository (GitHub) is the shared brain
3. **Bootstrap Protocol**: Each deployment starts by reading the knowledge graph and configuring for the Local North Star
4. **Deterministic Sequence**: Same steps every time — only the Local North Star configuration changes
5. **Convention Over Configuration**: The franchise kit has sensible defaults; only the Local North Star needs to be specified

### V14 EXECUTION SEQUENCE (Draft from Research)

```
PHASE 0: ORIENT
  → Clone constitutional repository (tim-constitution)
  → Read CONSTITUTION.md, DIRECTIVES.md, PREFERENCES.md
  → Ask: "What is the Local North Star for this initiative?"
  → Ask: "Is this a new initiative or existing?"

PHASE 1: ESTABLISH
  → Create initiative section in KNOWLEDGE.md
  → Create initiative entry in DECISIONS.md
  → If new: scaffold Bingo City (web-db-user) with Local North Star config
  → If existing: connect to existing Bingo City scaffold

PHASE 2: EVALUATE
  → Run Learning Loop V13 on the initiative's core deliverable
  → All 9 phases, configured for Local North Star
  → Constitutional memory enforced throughout

PHASE 3: BUILD
  → Generate HB1000 Operating Manual for this initiative
  → Populate source of truth database with real data
  → Configure Bingo Cards based on Local North Star

PHASE 4: DEPLOY
  → Bingo City goes live with real data
  → Constitutional repository updated with initiative decisions
  → Team briefing protocol executed
  → Tim's Trust Test run on the deployment
```

### TWO-DATABASE ARCHITECTURE (from research)

```
┌─────────────────────────────────────────┐
│         CONSTITUTIONAL DATABASE          │
│         (GitHub Repository)              │
│                                          │
│  CONSTITUTION.md  ← Prime North Star     │
│  DIRECTIVES.md    ← Standing orders      │
│  PREFERENCES.md   ← Tim's preferences    │
│  DECISIONS.md     ← Decision history     │
│  KNOWLEDGE.md     ← Index + definitions  │
│  ACTIVE_CONTEXT.md ← Current state       │
│                                          │
│  Shared by ALL agents, ALL initiatives   │
│  Near-immutable. Git-versioned.          │
└────────────────┬────────────────────────┘
                 │ reads from
                 ▼
┌─────────────────────────────────────────┐
│         INITIATIVE DATABASE              │
│         (MySQL/TiDB per Bingo City)      │
│                                          │
│  Local North Star config                 │
│  Bingo Card definitions                  │
│  Financial data / metrics                │
│  Source of truth for THIS initiative     │
│  User progress / gamification state      │
│                                          │
│  Unique per initiative. Dynamic.         │
│  Powered by web-db-user scaffold.        │
└─────────────────────────────────────────┘
```

The constitutional database INFORMS the initiative database. Directives like "cheapest option always" constrain what the initiative database can contain. The initiative database NEVER contradicts the constitutional database.
