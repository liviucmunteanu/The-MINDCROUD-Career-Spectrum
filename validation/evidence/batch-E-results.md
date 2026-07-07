# Batch E Validation Results — Personas 41–50 (Big Five extremes & response-style cases)

Instrument: The MINDCROUD Career Spectrum v1.0. Scoring implemented per `data/scoring.json`
and MINDCROUD-Career-Spectrum.md §6. Script: `score_batch_E.py` (integer exact half-up
rounding; naive stable sort by avatar insertion order MAK,EXP,VIS,MEN,PIO,GRD for ties).

Reverse items: 21,24,28,29,31,39,43,44,45,53,54,55,58,63,65 (coded = 6 − raw).
Attention: Q17=4, Q33=1, Q49=3. Consistency pairs: |Q1−Q41|, |Q10−Q56|.

**Ambiguities resolved in implementation:**
- **Rounding.** Spec mandates round-half-up (worked example 77.5→78). Python's `round()`
  is banker's rounding and a naive float `floor(x+0.5)` under-rounds some exact-.5 values
  because of binary float error. I used exact integer arithmetic `(2n+40)//80`. See the
  ROUNDING finding below — this is not cosmetic; it flips raw 33 between 57 and 58.
- **Flat-profile flag.** DI<15 is labeled a "flag" in §6.6 but is an interpretive signal,
  not one of the §6.7 validity caution/invalid signals. I did NOT fold it into the validity
  verdict. No Batch-E persona was flat anyway (min DI = 38, Agnes).
- **Reverse-item internal contradiction is NOT a QA signal.** The only consistency checks
  are the two positively-worded pairs (A: Q1/Q41, B: Q10/Q56) plus the three attention
  items. A respondent who endorses both a positively-keyed item and its reverse-keyed
  sibling (e.g. Agnes on MEN) produces NO validity flag — the contradiction is silently
  absorbed into the scale sum. This is the central weakness Batch E exposes.

---

## Persona 41 — Rocco Esposito (Extraversion Very High)

**Testing purpose:** Does extreme extraversion inflate MEN/PIO *NRG* (energy) items and
masquerade as vocational Social/Enterprising interest? Facet divergence (people-energy high,
helping-ACT only moderate) is the designed signal.

**Response sheet (key rationale):**
Q1 MEN-ACT 4 (enjoys showing people things), Q5 PIO 5, Q8 MEN-help 3 (likes people, not
counseling — ACT divergence), Q12 PIO lead 5, Q18 comp 4, Q21ʳ 1 (hates being alone — strong
disagree), Q27 coop 5, Q28ʳ 5 (loses interest in long analysis → low EXP), Q30 fast 5,
Q34 listen-to-problems 3 (not his thing), Q40 conversations-energize 5, Q41 4 (pair w/Q1),
Q44ʳ 1 (persuading energizes him), Q47 support-growth 3, Q51 winning 5, Q54ʳ 3, Q55ʳ 4,
Q58ʳ 1 (loves competitive), Q61 explain 4, Q64 run-a-team 5. EXP items floored (Q4 2, Q9 2,
Q13 2, Q23 1, Q42 3, Q48 2, Q62 1). Minor inconsistencies: Q59 VIS 3, Q52 VIS 4 (mild noise).
Checks Q17=4, Q33=1, Q49=3 all correct; pairs A/B both diff 0.

**Full responses:** 1:4 2:2 3:3 4:2 5:5 6:3 7:2 8:3 9:2 10:3 11:3 12:5 13:2 14:2 15:4 16:3
18:4 19:4 20:3 21:1 22:3 23:1 24:2 25:3 26:3 27:5 28:5 29:4 30:5 31:2 32:2 34:3 35:3 36:2
37:4 38:3 39:3 40:5 42:3 43:4 44:1 45:2 46:3 47:3 48:2 50:2 51:5 52:4 53:3 54:3 55:4 57:2
58:1 59:3 60:2 61:4 62:1 63:4 64:5 65:3 (checks 17:4 33:1 41:4 49:3 56:3).

**Raw / Spectrum:** MAK 25/38 · EXP 19/23 · VIS 34/60 · MEN 39/73 · PIO 47/93 · GRD 24/35.
**Dominant:** PIO + MEN. **DI:** 70 (well-differentiated). **Validity:** Valid (0 fails, pairs 0/0).
**Expected vs actual:** Expected PIO+MEN — **MATCH.**
**What it reveals:** The facet design *partially* worked: MEN landed second (73) not first,
tempered below PIO (93). But MEN 73 is still "Strong Resonance" driven almost entirely by NRG
people-energy items (Q40,Q27,Q21ʳ) while his helping-ACT items sat at 3. The scale cannot
separate "likes being around people" from "wants to help people" — MEN reads as a genuine
vocational Social interest when it is really trait extraversion. Exactly the confound the
persona was built to expose, and the instrument does not surface it.

---

## Persona 42 — Solveig Dahl (Extraversion Very Low)

**Testing purpose:** Does extreme introversion drag down avatars *beyond* MEN? Q21ʳ (best
alone) should depress only MEN, not GRD/EXP.

**Response sheet:** 5s on GRD (Q3,Q10,Q16,Q22,Q36,Q50,Q57; reverse Q29=1,Q43=1,Q63=1 → all
add 5), Q21ʳ=5 (alone all day = best → after reverse adds only 1 to MEN), EXP analysis 4–5
(Q9 4, Q23 5, Q42 4, Q62 5), MEN/PIO NRG floored (Q40 1, Q27 2, Q51 1, Q18 1, Q30 1, Q44ʳ 5,
Q58ʳ 5). Checks correct; pairs 0/0. Minor: Q13 4 (reads about tech), Q31ʳ 4.

**Raw / Spectrum:** MAK 29/48 · EXP 43/83 · VIS 22/30 · MEN 20/25 · PIO 12/5 · GRD 50/100.
**Dominant:** GRD + EXP. **DI:** 95. **Validity:** Valid.
**Expected vs actual:** Expected GRD+EXP — **MATCH.** Introversion floored MEN (25) and PIO (5)
without touching GRD (100) or EXP (83), confirming that Q21ʳ + the NRG people-items localize
the introversion penalty to the two social-facing avatars. Clean discriminant behavior.
**Reveals:** The NRG facet correctly routes an interpersonal-energy trait to MEN/PIO only —
the positive contrast case to Rocco.

---

## Persona 43 — Yusuf Demir (Conscientiousness Very High)

**Testing purpose:** Does hyper-conscientiousness inflate GRD beyond true vocational
preference (trait–interest confound)? His MAK is genuine (site work), so a valid profile
should read GRD+MAK, not GRD-only.

**Response sheet:** 5s on every order/planning item regardless of avatar (Q16,Q22,Q36,Q50,Q57
GRD; reverse Q29=1,Q43=1,Q63=1). MAK precision real: Q7 5, Q14 5, Q20 5, Q26 5, Q46 5, Q2 4,
Q32 4. VIS floored (Q6 2, Q11 2, Q19 1, Q38 2, Q52 1; Q31ʳ 5, Q45ʳ 5, Q65ʳ 4). Checks correct;
pairs 0/0. Minor: Q9 EXP 4, Q42 4 (methodical analysis).

**Raw / Spectrum:** MAK 45/88 · EXP 38/70 · VIS 16/15 · MEN 31/53 · PIO 25/38 · GRD 50/100.
**Dominant:** GRD + MAK. **DI:** 85. **Validity:** Valid.
**Expected vs actual:** Expected GRD+MAK — **MATCH.** GRD hits ceiling (100) but MAK (88) rides
alongside, so the profile is not a pure conscientiousness scale.
**Reveals:** GRD *is* partly a conscientiousness proxy — every cross-avatar order/precision
item he endorsed fed GRD, pushing it to a perfect 100. The instrument cannot tell "I value
order as a work interest" from "I am a highly conscientious person." Because his Realistic
interest was authentic, the confound didn't distort the *ranking* here — but a hyper-C person
with no genuine second interest would get a spuriously inflated GRD.

---

## Persona 44 — Poppy Whelan (Conscientiousness Very Low) — ATTENTION-CHECK FAIL CASE

**Testing purpose:** Low-C skimming; does the VIS signal survive careless responding, and
does the designed Q49 miss trip the QA correctly?

**Response sheet:** Strong VIS 5s (Q6 5, Q11 5, Q25 5, Q38 5, Q52 5, Q59 5; reverse Q31 1,
Q45 1, Q65 1). Improvise/unplanned reverse agreed (Q29 5, Q43 5 → GRD floor). MAK hands-on
4s (Q7 4, Q14 4, Q20 4, Q32 5, Q46 4). **Q49=4 (FAIL — instructed Neutral, skimmed).**
Q17=4 pass, Q33=1 pass. Pairs A |4−4|=0, B |2−3|=1 — still aligned despite carelessness.

**Raw / Spectrum:** MAK 39/73 · EXP 23/33 · VIS 50/100 · MEN 28/45 · PIO 26/40 · GRD 12/5.
**Dominant:** VIS + MAK. **DI:** 95. **Validity:** **Interpret with caution** (1 attention fail).
**Expected vs actual:** Expected VIS+MAK with one failed attention check → caution. **MATCH.**
**Reveals:** The QA worked *as designed* for careless responding: the single Q49 miss produced
exactly a caution (not invalid), and the profile is still scorable and correct (VIS 100). The
attention checks catch genuine skimming. Contrast with Agnes (45), where a *deliberate* bias
slid straight through — attention checks catch inattention, not motivated response styles.

---

## Persona 45 — Agnes Nakato (Agreeableness Very High) — **CLASSIFICATION MISS**

**Testing purpose:** A-driven acquiescence/politeness elevation — rates people-items 5, but
also 4s items she has no interest in (disagreeing feels rude), AND 4s the reverse "helping
would exhaust me" out of politeness → designed internal contradiction that *should* trip a
soft QA warning.

**Response sheet:** MEN genuine 5s (Q1 5, Q8 5, Q15 5, Q34 5, Q40 5, Q47 5, Q61 5). But
across-the-board 4s on unrelated items (EXP Q4 4, Q9 4, Q42 4; VIS Q6 4, Q11 4, Q25 4, Q52 4,
Q59 4; PIO Q5 4, Q37 4, Q64 4; GRD Q3 4, Q10 4, Q22 4, Q36 4, Q50 4, Q57 4). **Politeness
contradiction: Q54ʳ = 4** ("helping all day would exhaust me" — agreed to be agreeable; reverse-
scores to 2, quietly lowering MEN). Also Q21ʳ 3, Q28ʳ 3, Q43ʳ 3, Q29ʳ 4. Checks Q17=4, Q33=1,
Q49=3 all correct (she reads carefully — politeness, not carelessness). Pairs A |5−5|=0,
B |4−4|=0.

**Raw / Spectrum:** MAK 30/50 · EXP 36/65 · VIS 35/63 · MEN 45/88 · PIO 31/53 · GRD 35/63.
**Ranked:** MEN 88 > EXP 65 > VIS 63 = GRD 63 > PIO 53 > MAK 50.
**Dominant (computed):** MEN + EXP + VIS (score2−score3 = 65−63 = 2 ≤ 10 → third added).
**Note the rank-3 tie:** VIS and GRD both = 63. Naive sort put VIS at rank 3 (insertion order
VIS before GRD) and GRD at rank 4. Per §6.5 tie rule this is a **"shared third strand"**
situation (two avatars tied at the rank-3 boundary that qualifies) — my naive implementation
silently picked VIS and dropped GRD; the documentation says to report *both* as a shared third
and have the consultant resolve. Naive output: **MEN+EXP+VIS**; doc-correct output:
**MEN+EXP+(VIS/GRD shared third).**
**DI:** 38 (well-differentiated, barely). **Validity:** **Valid** — no flag fired.
**Expected vs actual:** Expected **MEN+GRD** with a soft QA warning. Actual **MEN+EXP+VIS**
(GRD not even dominant), verdict **Valid**. **MISMATCH — the primary failure of the batch.**
**Reveals (key finding):** Two failures at once. (1) Her uniform-4 acquiescence lifted EXP (65)
and VIS (63) above GRD (63) so the expected MEN+GRD pairing never formed; acquiescent elevation
reorders the secondary avatars. (2) Her *designed* internal contradiction — endorsing helping
AND endorsing "helping exhausts me" — produced **no QA flag whatsoever**, because the only
consistency checks are the two positively-worded pairs (both 0 here) and attention (all passed).
The 15 reverse items absorb such contradictions arithmetically instead of detecting them. A
respondent can hold internally impossible positions and still be reported "Valid." This is the
instrument's largest exposed weakness.

---

## Persona 46 — Viktor Baranov (Agreeableness Very Low)

**Testing purpose:** Helping PROFESSION (surgeon) + non-helping TEMPERAMENT. MEN must be LOW
despite medicine — if MEN comes out high the scale measures occupation stereotype, not interest.

**Response sheet:** MAK precision-hands 5s (Q7 5, Q10-adjacent, Q26 5, Q32 5, Q46 5, Q2 5,
Q14 4). EXP 5s (Q4 5, Q9 5, Q13 5, Q35 5, Q42 5, Q48 5). **MEN empathy floored honestly**
(Q8 1, Q34 1, Q15 2, Q27 2, Q40 2, Q47 1); **Q54ʳ = 5** ("helping all day would exhaust me" —
strong agree, reverse-scores to 1). PIO moderate (Q12 4, Q18 4, Q30 4, Q64 4; Q24ʳ 1). GRD high
(Q10 5, Q22 5, Q36 4, Q57 4). Checks correct; pairs 0/0.

**Raw / Spectrum:** MAK 45/88 · EXP 48/95 · VIS 21/28 · MEN 17/18 · PIO 36/65 · GRD 42/80.
**Dominant:** EXP + MAK + GRD (MAK−GRD = 88−80 = 8 ≤ 10 → third added).
**DI:** 77. **Validity:** Valid.
**Expected vs actual:** Expected MAK+EXP with GRD tertiary → set {MAK,EXP,GRD}. Actual
{EXP,MAK,GRD} (top-2 order flipped, same set + GRD as qualified third). **MATCH.**
**Reveals (positive result):** MEN correctly floored to 18 — the scale profiled him by
*interest*, not by his helping occupation. This is the instrument working exactly right:
occupation stereotype did NOT leak into MEN. Strong discriminant-validity anchor.

---

## Persona 47 — Imogen Hartley-Price (Neuroticism Very High)

**Testing purpose:** Does trait negative affect make her endorse *all* drain-worded reverse
items (Q44,Q53,Q54,Q63,Q65), deflating every avatar's NRG facet? True VIS/EXP interest should
survive if facet structure is robust.

**Response sheet:** ACT interests true (VIS Q6 5, Q11 5, Q25 5, Q38 5, Q52 4, Q59 4; EXP Q4 4,
Q9 4, Q13 4, Q42 4, Q48 2, Q62 4). **Drain reverse items nearly all agreed:** Q44ʳ 5, Q53ʳ 4,
Q54ʳ 5, Q63ʳ 4, Q65ʳ 2 (mild), Q58ʳ 5 — everything drains an anxious respondent → each
reverse-scores low, depressing NRG. Checks correct; pairs A 0, B 0. Minor inconsistency: Q28ʳ 2,
Q55ʳ 2 (kept EXP partly up).

**Raw / Spectrum:** MAK 21/28 · EXP 38/70 · VIS 43/83 · MEN 28/45 · PIO 15/13 · GRD 33/58.
**Dominant:** VIS + EXP. **DI:** 70. **Validity:** Valid.
**Expected vs actual:** Expected VIS+EXP, globally depressed. **MATCH.** VIS 83 and EXP 70 still
rank-order correctly, but her drain endorsements shaved the NRG contribution across the board.
**Reveals:** Profile *shape* survived trait neuroticism (right dominants) but *elevation* is
suppressed — her VIS 83 would be ~95+ without the anxiety-driven drain agreement. Because the
instrument reports absolute Spectrum bands (Core/Strong Resonance), a high-N respondent gets
systematically lower band labels for the same underlying interest. See the 47↔48 contrast.

---

## Persona 48 — Etienne Beaulieu (Neuroticism Very Low)

**Testing purpose:** Mirror of 47 — rejects ALL drain reverse items (nothing rattles him). Do
uniformly low drain endorsements inflate every avatar's NRG facet? Differentiation must come
from ACT/ENV.

**Response sheet:** MAK/GRD ACT 5s (Q2 5, Q7 5, Q14 5, Q20 5, Q26 5, Q32 5, Q60 5; GRD Q10 5,
Q16 5, Q22 5, Q36 5, Q50 5, Q57 5). VIS/PIO ACT floored (Q6 1, Q11 2, Q19 2, Q38 2; Q5 2,
Q12 2, Q37 2). **All drain reverse items rejected:** Q53ʳ 1, Q54ʳ 2, Q63ʳ 2, Q44ʳ 2, Q65ʳ 2,
Q58ʳ 5→ note Q58 disagree "calm predictable" = he *is* calm, answered 5, reverse to 1 lowering
PIO (authentic). Checks correct; pairs 0/0.

**Raw / Spectrum:** MAK 50/100 · EXP 41/78 · VIS 21/28 · MEN 33/58 · PIO 21/28 · GRD 46/90.
**Dominant:** MAK + GRD. **DI:** 72. **Validity:** Valid.
**Expected vs actual:** Expected MAK+GRD. **MATCH.** MAK hit a perfect 100.
**Reveals (paired with 47):** NRG-facet trait contamination quantified. Etienne's rejection of
all drain items pushed MAK to the ceiling (100); Imogen's endorsement of all drain items held
her top avatar to 83. Same reverse-item architecture, opposite trait poles → a systematic band
shift driven by Neuroticism, not by vocational interest. The NRG facet is contaminated by trait
negative affect in both directions; differentiation (ranking) survives but absolute elevation
does not. **The instrument has no correction for this and reports raw absolute bands.**

---

## Persona 49 — Ximena Reyes-Toledo (Openness Very High)

**Testing purpose:** O-driven legitimate breadth across VIS + EXP + MAK; sharp lows on GRD
stability items prove she is discriminating, not acquiescent (contrast with Marites, 53).

**Response sheet:** VIS 5s (Q6 5, Q11 5, Q19 5, Q25 5, Q38 5, Q52 5, Q59 5; Q31ʳ 1, Q45ʳ 1,
Q65ʳ 1). EXP 5s (Q4 5, Q9 5, Q13 5, Q35 5, Q42 5, Q48 5). MAK tinkering (Q60 5 take-apart,
Q7 5, Q2 4, Q14 5, Q32 5). **Sharp GRD lows** (Q50 1 stability, Q16 1, Q3 2, Q57 1; Q29ʳ 5,
Q43ʳ 5, Q63ʳ 5 → GRD floor). Checks correct; pairs A 0, B 0. Minor: Q26 4, Q46 4.

**Raw / Spectrum:** MAK 43/83 · EXP 46/90 · VIS 50/100 · MEN 32/55 · PIO 34/60 · GRD 13/8.
**Dominant:** VIS + EXP + MAK (EXP−MAK = 90−83 = 7 ≤ 10 → third). **DI:** 92. **Validity:** Valid.
**Expected vs actual:** Expected 3-way VIS+EXP+MAK. **MATCH.** GRD floored to 8.
**Reveals:** The instrument *can* represent legitimate multi-avatar breadth (three dominants,
DI 92 well-differentiated) while still discriminating — her GRD 8 proves the 3-way top is real
interest, not yea-saying. This is the correct-answer contrast case for the acquiescence
personas: high-O breadth and acquiescence look different in the data (sharp lows vs uniform
highs), and the profile geometry distinguishes them — *if* a human reads the whole profile.
The automated verdict alone (both "Valid") would not.

---

## Persona 50 — Gordon McAllister (Openness Very Low)

**Testing purpose:** Low-O dignity — VIS near zero, change-items rejected. Does the report give
meaningful guidance when 4 of 6 avatars are low?

**Response sheet:** VIS floored (Q6 1, Q11 1, Q19 1, Q25 1, Q38 1, Q52 1, Q59 1; Q65ʳ 4 agree
"creating from nothing drains me"). GRD stability 5s (Q50 5, Q16 5, Q22 5, Q57 5; Q29ʳ 1,
Q43ʳ 1). MAK vehicle/physical 4s (Q2 4, Q7 4, Q20 4, Q26 4, Q46 4). EXP low (Q4 2, Q9 2, Q13 2;
Q28ʳ 4, Q55ʳ 5). Checks correct; pairs A |2−2|=0, B |4−4|=0.

**Raw / Spectrum:** MAK 39/73 · EXP 21/28 · VIS 12/5 · MEN 20/25 · PIO 14/10 · GRD 44/85.
**Dominant:** GRD + MAK. **DI:** 80. **Validity:** Valid.
**Expected vs actual:** Expected GRD+MAK. **MATCH.** Both dominants real; four avatars low.
**Reveals:** Despite four low avatars the profile is *well-differentiated* (DI 80) and returns
two genuine, dignified dominants (GRD 85, MAK 73). The 0–100 scaling did NOT compress him into
a flat low blob — low-O honest narrowness reads as clean signal, not deficit. Reporting-tone is
the only open question (does the narrative dignify a Guardian/Maker lorry driver?), which is a
copy issue, not a scoring one.

---

## Cross-persona findings

**Rounding fragility (implementation finding).** Eight avatar scores in this batch land on an
exact .5 boundary (raws 15,19,31,33,35,39,43,47 → e.g. 57.5, 72.5, 92.5). Spec §6.4 mandates
round-half-up (77.5→78). A naive implementation using Python `round()` (banker's) OR a float
`floor(x+0.5)` gives the WRONG value on some of these:
- Python `round()` under-rounds every .5 case (22.5→22, 72.5→72, 92.5→92, 57.5→57...).
- Even float `floor(x+0.5)` fails on **raw 33 → 57.5**: `(33-10)/40*100 = 57.4999…` in binary
  float → 57 instead of 58. This hit **Persona 47 GRD** (57 vs 58) and **Persona 48 MEN**
  (57 vs 58). Only an integer/decimal implementation `(2n+40)//80` matches the spec.
- Neither error changed a dominant classification in this batch, but both would routinely
  mislabel scores near a Resonance-band edge (e.g. 60/61) and near a dominance cutoff.

**Rank-3 tie handling (Persona 45).** VIS and GRD tied at 63 with EXP at 65. `scoring.json`
gives no tie rule; a naive stable sort arbitrarily promotes whichever avatar comes first in
insertion order (VIS) and drops the other (GRD). §6.5 of the MD says a qualifying rank-3 tie
must be reported as a **"shared third strand"** for consultant resolution. The JSON-only
implementation silently violates the documented rule.

---

## Batch E summary

**Classification accuracy: 9/10.**
Matches: 41,42,43,44,46,47,48,49,50. Miss: **45 (Agnes / Agreeableness Very High).**

**Pattern of the one failure:** Motivated response styles that are neither careless nor
internally-worded-inconsistent slip through untouched. Agnes's politeness produced (a) uniform
4s that reordered her secondaries so the expected GRD dropped out of dominance in favor of
acquiescence-inflated EXP/VIS, and (b) a genuine logical contradiction (endorsing helping AND
"helping exhausts me") that generated zero QA flags. Verdict came back "Valid."
