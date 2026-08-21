# Minimum Action Agent OS Adoption — Civilization X-Ray

Status: **WORKING-METHOD ADDENDUM / NO ARCHITECTURE REOPEN / NO CODE**

Source method: `storm-credit/minimum-action-agent-os` / `AGENT_OS_SPEC.md`

This document adopts the reusable operating rules of Minimum Action Agent OS without changing Civilization X-Ray's closed four-orchestra / seven-artifact architecture.

## 1. Core Interpretation

The project does **not** limit the total number of agents to five.

The bounded quantity is local:

> **At each reasoning node / active agent, expose no more than five meaningful directly selectable actions by default.**

A directly selectable action includes:
- tool;
- subagent;
- MCP action;
- skill invocation;
- other peer callable capability presented as a choice to the model.

The total project may contain more than five agents, specialists, tools, providers, skills, or capabilities. The Capability Registry may also contain more than five entries.

The `<=5` policy applies to the **active local action surface**, not the global inventory.

This is an operating policy, not an Anthropic/OpenAI/API hard technical limit.

## 2. Per-Agent / Per-Node Tool Allocation Rule

Each agent receives only the tools needed for its current responsibility.

Default target:
- active directly selectable actions: `<=5`;
- context: minimum sufficient task packet;
- authority: only what the responsibility contract grants.

If an agent/node would expose more than five meaningful peer actions, perform a decomposition check before proceeding:

1. Are unrelated responsibilities mixed in one agent?
2. Can some capabilities be hidden behind a router/specialist?
3. Can several related calls become one task skill/workflow instead of peer tools?
4. Should read/write/execute permissions be separated?
5. Is every extra action genuinely needed for this task?

If more than five is still safer/simpler, the exception is allowed only when the run/decision record states:
- why the extra action is necessary;
- which task/stage it applies to;
- why further decomposition would increase risk/overhead;
- whether the exception is temporary or persistent.

## 3. Important Non-Rule: No Agent-Count Ceiling

Do not misread the five-action policy as:
- maximum five agents;
- maximum five specialists;
- maximum five tools in the repository;
- maximum five providers;
- maximum five orchestras/capabilities globally.

Agent creation remains evidence-driven.

Create/split an agent only when at least one real boundary exists:
- distinct tool/permission set;
- distinct context requirement;
- independent evaluation/reject authority;
- different source/evidence regime;
- materially different failure mode;
- isolation value justifies delegation overhead.

A persona or perspective that does not need such a boundary should remain a checklist/rule/skill rather than becoming another agent.

## 4. Civilization X-Ray Examples

### Project Orchestrator
Should see a small set of stage-level actions such as:
- Editorial & Research dispatch;
- Visual Production dispatch;
- Audio & Post dispatch;
- Release & Learning dispatch;
- governance/escalation action when needed.

It should not directly expose every research, image, video, Blender, TTS, music, publishing, and QA tool at once.

### Video Director
Default peer choices can remain bounded around:
- Blender Spatial/Camera route;
- Generative Cinematic Video route;
- 2D Motion/Compositing route;
- Visual QA / escalation.

Provider variants belong behind the chosen capability route rather than becoming ten flat peer tools.

### Generative Cinematic Video
If multiple providers/workbenches exist, use a capability/router layer. Do not expose Veo, AniJam, Kling, Runway, Hailuo, Sora, etc. as an ever-growing flat toolbelt to every upstream agent.

### Research
A research worker can have a tightly scoped search/read/citation set while specialized source acquisition or independent verification can be delegated rather than exposing the entire repository/web/tool universe.

## 5. Context Allocation

Adopt the OS principle:

> **Deep Blackboard, small execution context.**

Pass only:
- goal;
- relevant source-of-truth excerpts/IDs;
- constraints;
- acceptance criteria;
- required input/output artifact;
- stop/escalation rules.

Do not pass full conversation history or the whole project by default.

For independent critique, prefer artifact + requirements + acceptance criteria. Do not provide builder rationale unless it is genuinely necessary for the critique.

## 6. Meta-Prompting Alignment

Civilization X-Ray's existing Meta-Prompting Protocol is compatible with Minimum Action Agent OS.

Canonical working cycle:

`Context Dump → Missing Context Check → Prompt Refinement → Execute → Output Review → Learn`

Minimum Action interpretation adds:
1. identify only missing context that materially changes the result;
2. define success and stop conditions;
3. compile for the target environment;
4. remove redundant context/instructions;
5. expose the minimum necessary actions;
6. execute;
7. evaluate independently where risk warrants;
8. revise from observed failure, not speculative complexity.

Meta-prompting is not a ceremony. Skip steps that add no decision value for a trivial task while preserving the underlying checks.

## 7. Agent / Prompt / Tool Anti-Patterns

The following are explicit anti-patterns:

### AP-01 Flat mega-toolbelt
One agent accumulates unrelated peer tools until selection/context noise grows.

Response: `PATCH/ROUTE/SPLIT` before adding another peer tool.

### AP-02 Agent-count fetish
Treating more agents as automatically higher quality.

Response: keep logical roles separate when useful, but physical agent split only for a real boundary.

### AP-03 Fake <=5 compliance
Splitting one responsibility into renamed agents solely to make each displayed count look small while the same node still effectively chooses among many aliases.

Response: reject cosmetic decomposition; bound the real choice surface.

### AP-04 Context soup
Giving every agent all artifacts, full history, all references, and all rules.

Response: compile task-specific context packets.

### AP-05 Shadow authority
A specialist/workbench rewrites Canon, Story, Visual, Spatial, or final Post truth outside its contract.

Response: reject or remap the proposal through the canonical owner.

### AP-06 Fake independent review
Reviewer receives the builder's rationale and identical interpreted evidence and merely agrees.

Response: where material, give reviewer primary evidence/artifact + rubric and preserve independent reject authority.

### AP-07 Blind retry
Retrying the same failed action without changing a causal input.

Response: classify failure and change prompt/spec/reference/model/route or stop.

### AP-08 Vendor-shaped architecture
A provider UI/API determines project responsibilities or source-of-truth structure.

Response: keep capability adapters/workbenches subordinate to project contracts.

### AP-09 Meta-prompt ceremony
Repeating interviews, four alternatives, or missing-context questions when the answer already exists or the choice is inconsequential.

Response: reuse repository truth and run only warranted primitives.

### AP-10 Unbounded router
A nominal router itself exposes a huge list of providers/tools, merely moving the flat-toolbelt problem one level down.

Response: use hierarchical/domain routing with bounded peer choices at each node.

## 8. Dispatch Preflight

Before a serious agent/task dispatch, check:

- responsibility is one sentence and bounded;
- active direct action/tool choices are `<=5` by default;
- if `>5`, exception/decomposition decision is explicit;
- minimum sufficient context is compiled;
- authority boundaries are explicit;
- success/stop conditions exist;
- fallback is not silent;
- retry requires causal change;
- independent evaluation is used only when risk warrants it.

## 9. Relationship to Existing Architecture

This adoption changes **how work is exposed to agents**, not the studio topology.

No change to:
- four responsibility orchestras;
- Stage-Gated Artifact Blackboard + Thin Director;
- seven core physical artifacts;
- Fact/Rights/Quality Governance;
- Blender/2D/generative routing responsibilities;
- code lock.

Verdict:

> **PATCH working method, not NEW DESIGN.**

Implementation remains `NOT STARTED / NOT AUTHORIZED / CODE LOCKED`.
