# Editorial & Research Orchestra

Status: **Role architecture — no implementation code**

## Mission

> 어떤 질문을 다루고, 어떤 근거를 믿고, 어떤 순서로 시청자에게 이해시킬지를 책임진다.

Director: **Editorial Director**

---

# 1. Hierarchy

```text
Editorial Director
│
├─ Topic Strategist
├─ Research Specialist
├─ Claim Verifier  ← independent reject authority
├─ Narrative Architect / Script Writer
├─ Script Editor / Retention Reviewer
└─ Script ↔ Visual Architect
```

Logical roles are independent contracts; physical agents may be combined except where reviewer independence matters.

---

# 2. Editorial Director

Owns:
- central question
- episode scope
- evidence sufficiency escalation
- story architecture approval
- final script lock recommendation
- handoff readiness to Video Director

Does not:
- silently override Claim Verifier
- invent sources
- choose visual production tool
- optimize clickbait packaging

---

# 3. Topic Strategist

Input:
- channel scope
- topic history
- candidate ideas
- audience assumptions

Output fields:
- candidate title/question
- X-Ray value
- familiarity
- surprise/contradiction
- visual explainability
- evidence availability risk
- overlap/cannibalization risk
- potential episode grammar

Reject if:
- only trivia/tourism value
- no hidden mechanism/system
- explanation cannot be evidenced sufficiently
- visual decomposition adds little

---

# 4. Research Specialist

Produces Evidence Pack draft.

Responsibilities:
- source collection
- terminology
- historical/technical context
- competing explanations
- uncertainty
- reconstruction boundaries
- source-to-claim links

Source discipline:
- prefer primary/official/academic/authoritative technical sources where material
- do not flatten genuine disagreement into one definitive answer
- distinguish direct evidence from secondary interpretation

---

# 5. Claim Verifier

Must be able to read original sources independently of Research summary.

Verdicts:
- VERIFIED
- VERIFIED_WITH_QUALIFIER
- DISPUTED
- UNSUPPORTED
- OUT_OF_SCOPE

Reject authority for:
- key hook claim unsupported
- number/scale claims weakly sourced
- causal statements stronger than evidence
- historical reconstruction presented as documented truth

A great story cannot override a failed critical claim.

---

# 6. Narrative Architect / Script Writer

Input:
- locked/qualified claims
- Episode Brief
- episode grammar
- audience level

Output Story Pack:
- central question
- hook
- information gap
- beat map
- reveal/payoff sequence
- narration units
- claim links
- qualifier placement
- callback/ending
- Audio Beat Map draft

Script principle:
> facts are not arranged in research order; they are arranged in comprehension order without breaking truth.

---

# 7. Script Editor / Retention Reviewer

Independent review of script.

Checks:
- first 30s promise clarity
- unanswered question strength
- repetition
- dead sections
- overlong setup
- fake suspense
- premature answer
- cognitive overload
- terminology burden
- transitions between scale/era/system
- ending payoff

Reject examples:
- every paragraph uses a fake “but actually” twist
- important qualifier buried after a dramatic false claim
- script length exists only to reach a target duration

---

# 8. Script ↔ Visual Architect

Bridges Editorial and Visual Production.

For each narration unit defines:
- linked claim IDs
- explanatory objective
- what viewer must see/change/compare
- spatial object/system/component
- reconstruction level
- scale treatment
- preferred visual class, not vendor
- orientation/continuity anchor
- expected duration range
- whether sound cue is explanatory/optional

Does not decide exact Blender keyframes or Veo camera prompt; those belong downstream.

---

# 9. Editorial Gate

PASS when:
- central question locked
- major claims verified/qualified
- source conflicts handled
- story structure earns long-form duration
- script does not overstate evidence
- every major explanation has a visualizable objective
- audio beat intent exists
- glossary/pronunciation candidates identified

FAIL sends work to the smallest upstream role that can fix the cause.

---

# 10. Handoff to Video Director

The handoff packet contains:
- Episode Brief version
- Evidence Pack version
- Story Pack version
- Script ↔ Visual map
- hard factual locks
- qualifiers that must survive edit
- unknown/reconstructed zones
- expected emotional/pacing beats
- pronunciation/term glossary draft

Video Director may propose script timing changes but cannot silently alter factual meaning.

---

# 11. Handoff to Audio & Post

After appropriate script/timing maturity:
- narration performance notes
- pronunciation glossary
- Audio Beat Map
- critical silence/pause intents
- qualifiers that cannot be lost in edit

---

# 12. Physical-Agent Simplification

Phase 1 recommended grouping candidate:
- Editorial Director + Topic Strategist + Narrative Architect can be one creation context initially
- Research Specialist separate when research is deep
- Claim Verifier separate review context
- Script Editor separate review context or independent pass
- Script ↔ Visual Architect may be paired with Video Director only if factual locks remain explicit

Split further only when pilot evidence justifies it.