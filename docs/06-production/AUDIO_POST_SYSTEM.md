# Audio & Post System

Status: **Selected production design — no implementation code**

## North Star

Civilization X-Ray의 소리는 배경 장식이 아니다.

> **Narration이 의미를 전달하고, 음악이 감정과 구조를 지지하며, SFX가 공간/물리 상태를 보조하고, 편집이 이 모든 것을 하나의 이해 가능한 시간축으로 만든다.**

우선순위:
1. Meaning
2. Narration intelligibility
3. Editorial rhythm
4. Visual/audio sync
5. Emotional support
6. Spectacle

---

# 1. Post-Production Director

Owns:
- rough cut / fine cut / picture lock
- cross-media timing
- voice/music/SFX handoff
- final master readiness

Does not own:
- factual truth
- claim scope
- rights approval

If an edit changes meaning, send upstream to Editorial.

---

# 2. Narration & TTS Specialist

## Inputs
- locked script version
- pronunciation glossary
- voice bible
- beat map
- emphasis/pause notes

## Outputs
- Voice Pack
- timing map
- pronunciation exceptions
- retake/re-generation notes

## Voice Bible fields
- narrator identity/character
- perceived age range if relevant
- tone
- pace range
- energy range
- sentence ending style
- emphasis pattern
- emotional restraint rules
- forbidden mannerisms
- technical-term pronunciation policy

## Rules
- do not finalize voice before script lock
- major factual sentence change invalidates relevant voice segment
- avoid exaggerated commercial trailer delivery unless episode grammar requires it
- consistency across episodes matters more than novelty

---

# 3. Music Supervisor / Score Designer

## Purpose
Music maps story beats to emotional/attention states.

Music is planned from the **Audio Beat Map**, not pasted onto the final cut arbitrarily.

## Cue functions
- CURIOSITY
- SCALE / AWE
- PROBLEM / TENSION
- INVESTIGATION
- MECHANISM BED
- HISTORICAL SHIFT
- REVEAL
- PAYOFF
- RESOLUTION
- SILENCE / SPACE

## Cue Sheet minimum fields
- cue id
- linked story beat ids
- narrative function
- in/out intent
- energy curve
- density
- tonal/emotional description
- transition relationship
- narration priority notes
- source route
- rights status
- reconstruction/period-truth status if relevant

## Source routes
- generated original cue
- licensed library cue
- commissioned cue
- approved reusable channel motif

No source route is automatically preferred before pilot cost/quality/rights validation.

## Music rules
- dialogue always wins
- high information density often means lower musical density
- no constant wall-to-wall scoring by default
- silence is valid score design
- reveal does not always require an impact hit
- period-sounding music must not imply historical certainty unless supported
- avoid reusing identical cue patterns until the channel feels mechanically generated

---

# 4. Sonic Bible

Channel-level reusable language.

Possible fields:
- opening sonic signature
- X-Ray reveal motif
- scale transition texture
- technical explanation bed language
- historical transition texture
- resolution language
- silence policy
- frequency/density restraint principles

The Sonic Bible defines **functions and character**, not one mandatory song.

---

# 5. Sound Designer

Owns:
- environmental beds
- mechanism sounds
- transition sound support
- tactile impacts where useful
- spatial sound continuity

## Sound Truth Classes

### S0 — Documented / recorded
Directly recorded or strongly attributable real sound.

### S1 — Strong plausible reconstruction
Likely sound based on known materials/mechanism but not direct recording.

### S2 — Illustrative design sound
Used to clarify action, not claimed as historical/physical documentation.

### S3 — Abstract semantic sound
Pure UI/transition/attention cue.

S1–S3 must not be mixed/presented in a way that falsely implies documentary recording.

---

# 6. Picture Editor

## Edit states
1. Assembly
2. Rough Cut
3. Pacing Cut
4. Fine Cut
5. Picture Lock Candidate
6. Picture Lock

## Responsibilities
- map narration timing to approved shots
- maintain spatial orientation
- preserve explanation order
- remove redundant visual information
- keep breathing room after dense explanations
- coordinate transition timing with Video Director

## Cannot silently
- remove qualifiers such as “추정된다”, “가능성이 있다”
- reorder causality
- replace an explanatory shot with decorative footage that weakens proof

---

# 7. Music ↔ Edit Workflow

Recommended sequence:

```text
Story Beat Map
   ↓
Audio Beat Map
   ↓
Scratch Voice
   ↓
Visual Previs / Rough Cut
   ↓
Temp/Scratch Music Cues
   ↓
Pacing Review
   ↓
Picture Lock Candidate
   ↓
Final Voice
   ↓
Final Cue Production / Selection
   ↓
SFX
   ↓
Fine Mix
```

Exact lock ordering may vary, but final expensive music/voice generation should not happen before timing is sufficiently stable.

---

# 8. Mix / Master Specialist

Priority hierarchy:
1. narration
2. critical explanatory sound
3. music
4. atmosphere/decorative sound

Checks:
- narration intelligibility
- no abrupt level jumps across sections
- music ducking/space around speech
- SFX does not mask terms
- mobile-speaker legibility
- headphone legibility
- no accidental clipping/distortion
- final delivery profile recorded

Exact platform loudness targets are implementation/delivery configuration and should be versioned separately from creative design rules.

---

# 9. Captions / Subtitles

Captions are a production artifact, not an automatic upload checkbox.

Inputs:
- final voice timing
- glossary
- final script

Checks:
- technical names
- foreign place/person names
- numbers/units
- punctuation/readability
- sync after final edit

If multilingual expansion occurs later, translation/subtitle adaptation is a separate localized artifact, not raw machine translation by default.

---

# 10. Audio Rights Manifest

Every external/generated audio asset must link to provenance.

Minimum metadata:
- asset id
- source/tool/provider
- creator or generation identity where known
- creation/acquisition date
- license/terms review date
- commercial-use allowed?
- modification allowed?
- attribution required?
- exclusivity/content-ID concern if relevant
- episode usage
- superseded/deprecated status

Rights status unresolved => publish BLOCK.

---

# 11. Audio QA Gates

## Voice Gate
FAIL if:
- wrong pronunciation changes credibility
- pace hurts comprehension
- voice identity drifts materially
- script version mismatch

## Music Gate
FAIL if:
- cue competes with narration
- emotional cue contradicts story function
- rights unclear
- period-specific implication unsupported where consequential

## SFX Gate
FAIL if:
- false physical/historical certainty
- distracting repetition
- transition gimmicks exceed explanatory value

## Mix Gate
FAIL if:
- speech is not consistently intelligible
- section levels feel disconnected
- key terms are masked

## Caption Gate
FAIL if:
- proper nouns/technical terms materially wrong
- timing reflects stale cut

---

# 12. Phase 1 Physical-Agent Simplification

Logical roles remain separate, but early runtime may combine:

- Post Director + Picture Editor
- Music Supervisor + Sound Designer
- Mix + Caption Specialist

Narration/TTS may be separate due to tool/voice context.

Rights verdict remains independent from creator roles.

---

# 13. Pilot Validation

Test one 8–12 minute paper/proxy episode with:
- two narration styles
- three music density approaches: sparse / balanced / dense
- at least one deliberate silence/reveal moment
- sound-truth labels
- rough/fine cut handoff

Measure/review:
- comprehension
- perceived quality
- fatigue
- narration clarity
- cue usefulness
- rework caused by late script changes
- rights/provenance burden

Use evidence to set default sonic density and physical role split.