# Audio / Post Timeline Contract v1

Status: **Design Closure 0.6 / no-code production contract**

Purpose: 음악·TTS·SFX·편집이 각각 독립적으로 좋은 결과를 만들고도 최종 영상에서 충돌하는 문제를 막는다.

North Star:
> Narration carries meaning. Picture proves. Music shapes attention. SFX supports space/action. Silence is an intentional state. Post owns the final temporal relationship.

---

# 1. Timeline Ownership

`Post-Production Director`가 final timeline의 owner다.

Video Director owns:
- shot meaning
- camera/transition intent
- visual pacing intent

Post Director owns:
- actual temporal assembly
- picture timing
- voice/music/SFX relationships
- final transition timing

If editing changes factual meaning or explanatory causality → Editorial/Fact Governance로 rollback.

---

# 2. Audio Timeline Row Contract

각 beat 또는 편집 구간은 최소 다음 필드를 갖는다.

- `segment_id`
- `time_intent` or relative duration band
- `beat_id`
- `narration_unit_ids[]`
- `visual_shot_ids[]`
- `meaning_priority`: HIGH | MED | LOW
- `narration_state`: FULL | LIGHT | NONE
- `music_function`: CURIOSITY | SCALE | TENSION | INVESTIGATION | MECHANISM | HISTORICAL | REVEAL | PAYOFF | RESOLUTION | SILENCE
- `music_density`: NONE | SPARSE | BALANCED | DENSE
- `music_energy_curve`
- `music_in_out_intent`
- `sfx_intent[]`
- `sound_truth_class[]`
- `ambient_bed`
- `silence_window`
- `audio_transition`: CUT | FADE | J_CUT | L_CUT | BRIDGE | NONE
- `caption_density_note`
- `risk_note`

Exact dB, LUFS, compressor settings는 implementation/delivery profile에서 정한다.

---

# 3. Priority Arbitration

충돌 시 기본 우선순위:
1. factual meaning
2. narration intelligibility
3. visual proof reading time
4. editorial rhythm
5. critical explanatory SFX
6. music emotion
7. decorative ambience/effects

즉 음악이 narration을 이기지 않는다.

---

# 4. Narration State Rules

## FULL
새 claim/원리 설명.
- music density SPARSE/BALANCED 권장
- key technical word 주변 SFX 최소화

## LIGHT
orientation/transition/recap.
- music may carry more rhythm

## NONE
visual proof, reveal, scale read, deliberate silence.
- music or ambience may lead
- silence may be strongest option

---

# 5. Music Function Rules

## CURIOSITY
초반 질문 형성. 답을 이미 웅장하게 선언하지 않음.

## SCALE
규모를 느끼게 하지만 narration 숫자를 가리지 않음.

## TENSION
공학적 제약/문제. 공포 trailer처럼 과장하지 않음.

## INVESTIGATION
표면 아래로 내려가거나 원인을 추적.

## MECHANISM
정보밀도 높은 설명 구간. 낮은 밀도/반복 안정성 우선.

## HISTORICAL
시간 이동을 표시. 시대 악기/양식을 사실적 기록처럼 오인시키지 않음.

## REVEAL
첫 X-Ray payoff. 항상 impact hit가 필요한 것은 아님.

## PAYOFF
앞선 motif/질문 회수.

## RESOLUTION
재조립 및 의미 정리.

## SILENCE
시청자가 구조를 읽거나 핵심 reveal을 소화하도록 공간 제공.

---

# 6. SFX Truth Contract

- S0 Documented/Recorded
- S1 Strong plausible reconstruction
- S2 Illustrative design sound
- S3 Abstract semantic sound

Each important SFX records class.

Examples:
- modern canal ambience recorded/approved → S0 candidate
- historic timber pile driving recreation → S1/S2 depending evidence
- load-path pulse sound → S3

Never mix S1–S3 as if they are archival recordings.

---

# 7. Silence Policy

Silence/near-silence is deliberately considered at:
- just before first internal reveal
- immediately after a dense mechanism explanation
- visual scale comparison
- final reassembly before payoff sentence

`SILENCE` is a valid music_function, not missing work.

---

# 8. Picture Lock Dependency

Recommended states:
1. Assembly
2. Rough Cut
3. Pacing Cut
4. Picture Lock Candidate
5. Fine Cut
6. Picture Lock

Before Picture Lock Candidate:
- use scratch voice/temp cues
- avoid expensive final cue production unless reusable

After major script meaning change:
- affected voice segment STALE
- captions STALE
- edit timing REVIEW/STALE
- linked music cue timing REVIEW
- SFX sync REVIEW

---

# 9. Audio Bridge Grammar

## A-TR-01 J-CUT
Next ambience/narration begins before visual cut.
Use to prepare scale/location shift.

## A-TR-02 L-CUT
Previous sound continues over next visual.
Use to preserve semantic continuity.

## A-TR-03 MOTIF_BRIDGE
Shared music motif connects different scale/era.

## A-TR-04 AMBIENCE_BRIDGE
Water/wind/room tone carries across visual representation.
Must not imply same physical location if not true.

## A-TR-05 SILENCE_CUT
Sound drops intentionally at a reveal/causal comparison.

---

# 10. Venice Pilot Audio Beat Map

Paper target 9–11 min, exact timing not locked.

### S01 Cold Open
- narration: LIGHT → FULL
- music: CURIOSITY / SPARSE
- ambience: modern lagoon/city context
- avoid: instant epic score

### S02 Question / waterline descent
- narration: FULL
- music: INVESTIGATION
- transition: ambience narrows as visual enters section

### S03 Soft ground problem
- narration: FULL
- music: TENSION low density
- SFX: abstract settling/weight cue only if clearly S3

### S04 First pile reveal
- narration: brief pause possible
- music: REVEAL or SILENCE
- key rule: give visual reading time

### S05 Foundation mechanism
- narration: FULL
- music: MECHANISM / SPARSE
- SFX: subtle component/load-path semantic cues S3

### S06 Historical construction context
- narration: LIGHT/FULL
- music: HISTORICAL / BALANCED
- generated historical ambience classified reconstruction

### S07 Wood preservation caveat
- narration: FULL
- music: reduced density
- no magical “wood turned to stone” sonic trope

### S08 Variability / decay / settlement caveat
- narration: FULL
- music: TENSION restrained
- goal: nuance, not disaster trailer

### S09 Reassembly / payoff
- narration: LIGHT → PAYOFF line
- music: PAYOFF then RESOLUTION
- optional near-silence immediately before final answer

---

# 11. Caption Contract

Caption source must match final voice/script version.
Critical verification:
- Venice/Venezia place names
- zatterone terminology if used
- wood species if named
- units/ranges
- qualifier words: 대표적, 일부, 조사된, 약, 가능성, 사례

Removing qualifiers in captions is a factual error.

---

# 12. Audio/Post QA

PASS requires:
- narration understandable on ordinary mobile speaker conceptually
- music density follows information density
- no wall-to-wall score default
- at least one intentional breathing/silence opportunity considered
- SFX truth classes exist for consequential reconstructed sounds
- picture edit does not remove claim qualifiers
- captions linked to final version
- rights status can be resolved before publish

---

# Closure Decision

Audio/Post no longer needs a new top-level orchestra or additional design layer before Phase 1 planning.
Further sonic details should be learned from the pilot and actual rendered/timed prototype, not guessed in documentation.
