# Batch G Results — Personas 61–70 (Edge Cases & Stress Tests)

Scoring engine: `score_batch_G.py` implements `data/scoring.json` exactly. Spectrum
= round_half_up((raw−10)/40×100), computed in exact integer arithmetic
`((raw−10)*5+1)//2`. Reverse items {21,24,28,29,31,39,43,44,45,53,54,55,58,63,65}
coded 6−raw. Dominant = top-2 + third if score2−score3 ≤ 10 (naive stable sort,
dict-insertion order MAK,EXP,VIS,MEN,PIO,GRD breaks ties). DI = max−min; flat < 15.

## Documented ambiguities in the naive implementation (affect verdicts below)

1. **Mild consistency (diff=2) verdict weight — UNSPECIFIED.** Section 6.7B defines
   a diff=2 as "mild inconsistency" and gives an `invalidIf` rule (any pair ≥3, or
   both pairs ≥2), but the combined-verdict formula (6.7C) never states that a single
   *mild* pair is a caution-level signal. **Naive choice: count a single diff=2 pair
   as one caution-level signal.** This choice alone flips P66 and P69 (see below).
2. **Long-string screen level — UNSPECIFIED.** 6.7C lists `longStringFlag: 12` as a
   recommended online screen but assigns it no level. **Naive choice: count ≥12 as
   one caution-level signal.** This drives P65's verdict.
3. **Flat-profile flag NOT in the verdict.** 6.6 is a profile descriptor; the 6.7C
   verdict formula never references it. **Naive: flat does not affect VALID/INVALID.**
   So an elevated *or* midpoint flat profile can still score "VALID" (P61) unless
   another screen fires.
4. **Float pitfall confirmed.** `int(((raw−10)/40)*100+0.5)` returns 57 for raw=33
   (57.4999… in binary float) where exact arithmetic gives 58 (P68 MAK). Engine uses
   exact integer form; noted as an implementation trap the JSON formula invites.

---

## P61 Ricardo Salazar — The Impression Manager

Responses Q1–65: 5,5,5,5,5,4,4,5,5,5,5,5,4,5,5,4,**4**,5,4,4,2,5,4,1,5,5,5,2,2,5,2,4,**1**,4,5,4,5,5,2,5,5,4,2,2,2,5,5,5,**3**,4,5,4,1,1,2,5,5,2,5,4,5,4,2,5,1
Key rationale: 4–5 on every positively-worded item across all six scales; correctly
deflates every reverse item to 1–2 (he decodes them — Q21=2, Q24=1, Q39=2, Q53=1,
Q54=1, Q58=2, Q63=2, Q65=1). Attention checks answered exactly (Q17=4, Q33=1, Q49=3).
Consistency pairs deliberately matched (Q1=5/Q41=5, Q10=5/Q56=5).

- Raw: MAK 45, EXP 44, VIS 45, MEN 48, PIO 48, GRD 44
- Spectrum: MAK 88, EXP 85, VIS 88, MEN 95, PIO 95, GRD 85
- Dominant: **MEN + PIO + MAK** (rank-3 tie: MAK & VIS both 88; naive sort picked MAK;
  doc 6.5 says report both as "shared third strand")
- DI = 10 → **flat-profile flag**. Attn 0 fails. Pairs 0/0. Long-string 5.
- **Verdict computed: VALID.** Expected: VALID-WITH-FLAG on elevation/low differentiation.
- **Match: YES — and this is the documented detection gap.** The instrument has no
  social-desirability/elevation index. A savvy inflator who decodes reverse keys and
  passes attention + consistency produces a ceiling-level, near-flat profile that the
  verdict engine calls plain VALID. The only surviving signal is the flat flag, which
  by design does not touch the verdict. Reveals: **no elevation/impression-management
  screen exists; reverse-keying is defeated by any respondent who recognises it.**

## P62 Greg Palmer — The Disengaged Completer

Responses: mostly 3s with sporadic 2s/4s (Q5=2,Q9=4,Q14=2,Q22=4,Q27=2,Q31=4,Q38=2,
Q44=4,Q50=4,Q57=2,Q60=4,Q63=2); Q17=3 (FAIL), Q33=3 (FAIL), Q49=3 (pass by luck).
Pairs 3/3, 3/3.

- Spectrum: MAK 50, EXP 53, VIS 45, MEN 48, PIO 45, GRD 55
- Dominant: GRD+EXP+MAK. DI = 10 → flat flag. **Attn 2 fails [17,33]** → invalid-level.
- **Verdict: POTENTIALLY INVALID.** Expected: INVALID. **Match: YES.**
- Reveals: attention checks correctly catch skim-reading apathy — the profile is
  invalidated on attention, not merely flat-flagged. This is the intended contrast to P65.

## P63 Rosamie Dela Cruz — The Acquiescent Agree-er

Responses: 4–5 on nearly everything **including reverse items** (Q21=4,Q29=5,Q43=5,
Q54=4,Q63=4…); Q17=4 (pass by habit), Q33=4 (FAIL), Q49=4 (FAIL). Pairs 5/5, 4/4.

- Spectrum: MAK 68, EXP 70, VIS 70, MEN 83, PIO 65, GRD 68
- Dominant: MEN+EXP+VIS. DI = 18 (moderately differentiated — NOT flat).
- **Attn 2 fails [33,49]** → **Verdict: POTENTIALLY INVALID.** Expected INVALID. **Match: YES.**
- Reveals: **reverse-keying works as designed here** — because she agrees (4–5) with
  reverse items, they recode to 1–2 and pull every scale off the ceiling to ~65–83
  instead of ~85–95. But note MEN still reaches 83 (Core Resonance): reverse keys
  *dampen* but do not fully neutralise acquiescence. The directional attention checks
  (Q33 "strongly disagree", Q49 "neutral") are what actually catch the yea-sayer;
  Q17 ("agree") does not, because agreeing is her default. Finding: **only
  non-"agree" attention anchors detect acquiescence.**

## P64 Bogdan Ilie — The Extreme Responder

Responses: every scored answer 1 or 5 tracking genuine Realistic interests (MAK/GRD
positives 5, their reverses 1; MEN/VIS/PIO positives 1). Attention answers are his only
non-endpoints (Q17=4, Q33=1, Q49=3). Pairs 1/1, 5/5.

- Spectrum: MAK 100, EXP 10, VIS 0, MEN 0, PIO 0, GRD 90
- Dominant: **MAK + GRD** (adjacent RC pair — coherent). DI = **100**. All checks pass.
- **Verdict: VALID.** Expected VALID (ideally with extreme-style note). **Match: YES.**
- Reveals: content-valid extreme responding scores cleanly. **But DI has no upper
  sanity bound** — a DI of 100 (theoretical max) passes silently with no "extreme
  response style" note anywhere in the schema. Floor/ceiling handled correctly (0 and
  100 both reachable and legal).

## P65 Anneke van Dijk — The Deliberate Midpointer

Responses: almost all 3s; honest 4s on EXP items (Q4,Q9,Q35,Q48,Q62); Q29=2. Attention
all pass (Q17=4, Q33=1, Q49=3). Pairs 3/3, 3/3.

- Spectrum: MAK 50, EXP 63, VIS 50, MEN 50, PIO 50, GRD 53
- Dominant: EXP+GRD+MAK (rank-3 tie MAK/VIS at 50). DI = 13 → **flat flag**.
- Attn 0 fails, pairs 0/0, **long-string run = 13 → caution (naive)**.
- **Verdict computed: INTERPRET WITH CAUTION** (driven by long-string). Expected:
  VALID-WITH-FLAG (flat). **Match: label YES, mechanism NO.**
- **Critical finding / weakness:** This fully attentive, honest respondent trips the
  **long-string screen (13 identical consecutive "3"s)** — the very screen meant to
  catch careless straight-lining. The intended, benign signal (flat-profile) is not in
  the verdict; the accusatory signal (long-string ⇒ carelessness) is. So the instrument
  reaches a caution verdict for exactly the wrong reason, and P65 is meant to be the
  *valid* contrast to disengaged P62 — yet the automated screens cannot tell them apart
  by response pattern alone (both are near-flat; the only true discriminator is that P62
  fails attention checks and P65 does not). **Midpoint straight-lining defeats the
  long-string screen regardless of engagement.** Also: report language must not accuse
  her of carelessness — but the long-string flag literally does.

## P66 Priyanka Nair — The Career Changer (Frame Conflict)

Responses: MAK 4–5 throughout (Q2=5,Q14=5,Q26=5,Q46=5,Q60=4). Early GRD from accountant
frame (Q10=4, Q16=4, Q22=4); late GRD from burned-out frame (Q56=2). All attention pass.
Q1=4/Q41=4 (consistent); **Q10=4/Q56=2 → diff 2**.

- Spectrum: MAK 85, EXP 55, VIS 53, MEN 50, PIO 38, GRD 60
- Dominant: **MAK + GRD + EXP** (GRD 60, EXP 55 within 10 → third strand). Expected MAK+GRD.
- DI = 47 (well-differentiated). Pair B diff = 2 → mild (one caution, naive).
- **Verdict computed: INTERPRET WITH CAUTION.** Expected: REVIEW. **Match: NO (softer).**
- **Finding + ambiguity:** Genuine temporal ambivalence (competence vs aspiration) does
  trip the Q10/Q56 pair — a **false-positive carelessness signal on an attentive
  respondent**, exactly as the persona predicts. But the *severity* is only "mild": a
  single diff=2 pair never reaches invalid-level (needs ≥3 or both pairs ≥2), so the
  literal 6.7C formula would call this VALID unless one chooses to weight a mild pair as
  caution. The instrument cannot distinguish "meaningful frame shift" from "careless
  discrepancy"; and whether it flags at all depends on an **undocumented weighting
  choice** (ambiguity #1). Dominant classification: MAK+GRD recovered correctly, EXP
  added as a coherent third.

## P67 Douglas MacLeod — The Career Changer (Opposite Poles)

Responses: MAK positives 4–5, MEN positives 4–5 (Q61=5 explaining), everything else 2–3.
All attention pass. Pairs Q1=5/Q41=5, Q10=3/Q56=3.

- Spectrum: MAK 90, EXP 50, VIS 40, MEN 85, PIO 45, GRD 55
- Dominant: **MAK + MEN** (RIASEC opposites, arrived at honestly). DI = 50. No flags.
- **Verdict: VALID.** Expected VALID. **Match: YES.**
- Reveals: engine produces a clean non-adjacent (hexagon-opposite RS) dominant pair with
  healthy DI. Scoring is coherent; the interpretive burden of an opposite-pole pair falls
  on the report/`combinations` table — MAK+MEN maps to "The Responder" (RS), which does
  fit a hands-on-teacher, so the combination catalogue covers this case.

## P68 Tomás Herrera — The Autistic Professional

Responses: EXP/GRD positives 5 (Q9=5,Q13=5,Q35=5,Q42=5,Q48=5,Q62=5; Q3=5,Q10=5,Q16=5,
Q22=5,Q50=5,Q57=5); MEN positives 1–2; Q21=5 ("best work alone"), Q40=1, Q54=5. Attention
exact. Pairs Q1=2/Q41=2, Q10=5/Q56=5.

- Spectrum: MAK 58, EXP 98, VIS 43, MEN 8, PIO 18, GRD 95
- Dominant: **EXP + GRD** (IC, "The Analyst"). DI = 90. All checks pass.
- **Verdict: VALID.** Expected VALID. **Match: YES.**
- Reveals: low-Social/high-structure neurodivergent profile scores cleanly; MEN 8 is a
  legitimate floor. Note the float pitfall surfaced here (MAK raw 33 → 58 exact vs 57
  naive-float). **Audit point unresolved by scoring engine:** whether the *report*
  frames MEN 8 as preference vs deficit is a narrative-layer concern the JSON does not
  govern — the score itself is correct and non-pathologising.

## P69 Jasmine Whitfield — The ADHD Professional

Responses: VIS/PIO positives 5 (Q6=5,Q11=5,Q19=5,Q25=5,Q59=5; Q5=5,Q37=5), GRD positives
1–2 (Q3=2,Q10=2,Q16=1,Q36=1,Q50=1,Q57=2), Q43=5 ("rather improvise"). Q17=4 (pass),
Q33=4 (**FAIL** — autopilot agree), Q49=3 (pass). Q1=4/Q41=4; **Q10=2/Q56=4 → diff 2**.

- Spectrum: MAK 48, EXP 40, VIS 93, MEN 70, PIO 85, GRD 10
- Dominant: **VIS + PIO** (AE, "The Creative Director"). DI = 83. Coherent, well-differentiated.
- Signals: 1 attn fail (caution) + 1 mild consistency diff=2 (caution, naive) →
  **two caution-level signals**.
- **Verdict computed: POTENTIALLY INVALID.** Expected: REVIEW (not hard invalid). **Match: NO (harder).**
- **Critical finding:** The persona probes whether "one attention fail is forgivable
  when the profile is coherent." Per the literal 6.7C rule ("two or more caution-level
  signals → potentially invalid"), **NO** — the single attention slip stacks with a
  single mild consistency diff to escalate a perfectly coherent, well-differentiated
  VIS+PIO profile into *potentially invalid*, discarding an interpretable result. And
  again this hinges on ambiguity #1: if a mild diff=2 pair is *not* weighted, Jasmine has
  only one caution (attention) → INTERPRET WITH CAUTION, which matches the expected soft
  outcome. **The verdict for a genuine, valid ADHD profile is decided entirely by an
  undocumented scoring choice.** No graduated logic exists to protect a coherent profile.

## P70 Ingrid Baumgartner — The Structured Creative

Responses: VIS positives 5 (Q6=5,Q11=5,Q25=5,Q38=5,Q52=5,Q59=5) AND GRD positives 5
(Q3=5,Q10=5,Q16=5,Q22=5,Q57=5); nuanced reverses (Q29=2,Q45=3,Q19=3). Attention pass.
Pairs Q1=4/Q41=4, Q10=5/Q56=5.

- Spectrum: MAK 63, EXP 73, VIS 85, MEN 53, PIO 45, GRD 88
- Dominant: **GRD + VIS** (AC, "The Curator" — hexagon opposites, both high). DI = 43. No flags.
- **Verdict: VALID.** Expected VALID. **Match: YES.**
- Reveals: someone genuinely high on both Artistic and Conventional yields a coherent
  opposite-pole dominant pair mapped to a real combination ("The Curator"). The presumed
  VIS–GRD dichotomy is not enforced by scoring; opposite-pole dominance is reported
  normally, not as an error.

---

## Accuracy tally

| P | Expected verdict | Computed verdict | Dominants match | Overall |
|---|---|---|---|---|
| 61 | VALID-WITH-FLAG (gap→VALID) | VALID | predicted-unstable ✓ | ✓ (gap confirmed) |
| 62 | INVALID | POTENTIALLY INVALID | n/a | ✓ |
| 63 | INVALID | POTENTIALLY INVALID | ✓ | ✓ |
| 64 | VALID | VALID | ✓ MAK+GRD | ✓ |
| 65 | VALID-WITH-FLAG | INTERPRET WITH CAUTION | ✓ | ✓ label (wrong reason) |
| 66 | REVIEW | INTERPRET WITH CAUTION | ✓ core MAK+GRD | ✗ softer |
| 67 | VALID | VALID | ✓ MAK+MEN | ✓ |
| 68 | VALID | VALID | ✓ EXP+GRD | ✓ |
| 69 | REVIEW (not hard invalid) | POTENTIALLY INVALID | ✓ VIS+PIO | ✗ harder |
| 70 | VALID | VALID | ✓ VIS+GRD | ✓ |

**Verdict/classification accuracy: 8/10.** Both misses (P66, P69) stem from the *same*
undocumented ambiguity — the verdict weight of a single mild (diff=2) consistency pair.
Dominant-avatar classification matched expectation in all 10 (P61's instability was
itself the prediction).
