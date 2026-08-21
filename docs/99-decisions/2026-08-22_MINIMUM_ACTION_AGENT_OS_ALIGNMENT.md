# 2026-08-22 — Minimum Action Agent OS Alignment

- Trigger: user clarified that the `<=5` rule means **tools/actions exposed to one agent/reasoning node**, not a limit on the total number of agents.
- Source method: `storm-credit/minimum-action-agent-os` / `AGENT_OS_SPEC.md`.
- Confirmed source rule: project-wide agent/tool counts may exceed five; the default design target is a bounded local action surface of no more than five meaningful directly selectable actions per reasoning node.
- Direct action includes tool, subagent, MCP action, skill invocation, or peer callable capability.
- The `<=5` value is an operating policy, not an Anthropic/OpenAI/API hard limit.
- New local rule: if active choices exceed five, perform decomposition check before adding more peer actions; document exceptions when `>5` is genuinely safer/simpler.
- Agent-count rule: **no fixed agent ceiling**. Split/create agents only for real permission/context/evaluation/evidence/failure-isolation boundaries.
- Anti-pattern additions/clarifications: flat mega-toolbelt, agent-count fetish, fake `<=5` compliance, context soup, shadow authority, fake independent review, blind retry, vendor-shaped workflow, meta-prompt ceremony, unbounded router.
- Meta-prompting remains the existing project cycle and is aligned with Minimum Action Agent OS by removing redundant context/actions and executing with minimum necessary exposure.
- Architecture impact: none. Four orchestras, Thin Director, seven core artifacts and code lock remain unchanged.
- Implementation impact: none. No runtime/tool code is introduced.
- Operational note: several empty branches were accidentally created while loading connector actions (`method/minimum-action-os-alignment`, `-v2`, `-v3`, `-v4`). They contain no project changes and are not authoritative. Actual work branch: `method/minimum-action-os-alignment-final`.
