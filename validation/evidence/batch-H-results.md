# Batch H Results — Personas 71–80 (Category D: Edge Cases & Stress Tests)

Instrument: The MINDCROUD Career Spectrum v1.0. Scored with `score_batch_H.py`, a direct
implementation of `data/scoring.json` + Section 6 of the manual.

## Scoring-engine notes / documented ambiguities
- Spectrum = round((raw−10)/40×100), half-up via floor(x+0.5). Reverse = 6−raw on Q21,24,28,29,31,39,43,44,45,53,54,55,58,63,65.
- **Verdict vocabulary mapping.** scoring.json §6.7 gives three combined verdicts: *Valid* / *Interpret with caution* (exactly one caution signal) / *Potentially invalid* (any invalid-level signal, or ≥2 cautions). The persona sheets use VALID / VALID-WITH-FLAG / REVIEW / INVALID. I map: VALID-WITH-FLAG ≈ Interpret-with-caution; REVIEW/INVALID ≈ Potentially-invalid. Accuracy is judged on this mapping.
- **Flat-profile flag (DI<15)** is nowhere assigned a severity in the JSON. My naive engine treats it as **one caution-level signal**. Consequence: a flat profile alone → Interpret-with-caution; flat + any other caution → Potentially-invalid. This is a real design gap (see findings).
- **Long-string ≥12 / completion <180 s** are "recommended" screens; I treat each as one caution signal, and only when a completion time is stated by the persona narrative (73,74,79,80).
- **Dominant rule** applied literally: stable sort in scale order [MAK,EXP,VIS,MEN,PIO,GRD]; top-2 always dominant; 3rd added if score2−score3 ≤ 10. The §6.5 "shared third strand" rank-3 tie handling is NOT in scoring.json and NOT implemented — naive sort-order tie-break used, with a note emitted when a rank-3 tie occurs.

---

## Verdict scoreboard (10/10 match)

| # | Persona | Expected verdict | Computed verdict | Match |
|---|---|---|---|---|
| 71 | Ernesto Quispe (scale inverter) | INVALID | Potentially-invalid | ✓ |
| 72 | Margaret Ellison (mid-test flip) | REVIEW/INVALID (consistency) | Potentially-invalid (consistency) | ✓ |
| 73 | Pat Randall (random cycle) | INVALID | Potentially-invalid | ✓ |
| 74 | Marcus Bell (straight-liner) | INVALID | Potentially-invalid | ✓ |
| 75 | Katrine Holm (depressed HP) | VALID-WITH-FLAG | Interpret-with-caution | ✓ |
| 76 | Dane Whitcombe (targeted faker) | VALID | Valid | ✓ |
| 77 | Siobhán Gallagher (dyslexic) | VALID | Valid | ✓ |
| 78 | Hakim Ben Salah (teaching tradesman) | VALID | Valid | ✓ |
| 79 | Lena Kovács (near-straight-line) | INVALID | Potentially-invalid | ✓ |
| 80 | Dr. Femi Adeyemi (over-deliberator) | VALID-WITH-FLAG | Interpret-with-caution | ✓ |

Dominant-avatar deviations (both benign, rule applied correctly): **77** and **80** gained a
literal 3rd dominant (within-10 rule) that the persona author listed as 2. Not a scoring error —
the author's "expected" was looser than the documented ≤10 rule.

---

## Persona 71 — Ernesto Quispe · "Confused by the Numeric UI (Scale Inverter)"
**Response pattern:** answers honestly but with a fully inverted anchor map (1 = "first place / most true"). True-Maker items get 1s; abstract avatars get high numbers. Q17("Agree")→2, Q33("Str. disagree")→5, Q49(Neutral)→3. Pairs internally consistent in his inverted frame (Q1=2/Q41=2, Q10=1/Q56=1).

- Raw: MAK 11, EXP 36, VIS 42, MEN 21, PIO 28, GRD 16
- Spectrum: **MAK 3, EXP 65, VIS 80, MEN 28, PIO 45, GRD 15**
- Ranked: VIS 80 > EXP 65 > PIO 45 > MEN 28 > GRD 15 > MAK 3
- Dominant: **VIS+EXP** · DI **77** (well-differentiated) · flat=No
- Attention: **2/3 FAIL** (Q17,Q33) · Consistency: A=0, B=0 (pass) · longest run 3
- **Verdict: Potentially-invalid** (attention). Matches expected INVALID.
- **Reveals:** The mirror image is a *coherent, well-differentiated, internally-consistent* profile (a strong Visionary/Explorer with DI 77 and both consistency pairs passing). Nothing except the two directional attention checks distinguishes it from a genuine artistic-investigative respondent. Attention checks double as anchor-decoding probes — confirms the finding: show anchor labels, not numbers only.

## Persona 72 — Margaret Ellison · "Mid-Test Scale Flip"
**Response pattern:** correct mapping Q1–35, inverts from ~Q36. Attention checks are verbal imperatives she obeys correctly all three (4/1/3). Q1=5 (early) vs Q41=2 (post-flip); Q10=4 vs Q56=2.

- Raw: MAK 27, EXP 33, VIS 29, MEN 34, PIO 31, GRD 29
- Spectrum: **MAK 43, EXP 57, VIS 48, MEN 60, PIO 53, GRD 48**
- Ranked: MEN 60 > EXP 57 > PIO 53 > VIS 48 = GRD 48 > MAK 43
- Dominant: **MEN+EXP+PIO** · DI 17 (moderate) · flat=No
- Attention: **3/3 PASS** · Consistency: **A=3 (strong), B=2 (mild) → INVALID** · longest run 3
- **Verdict: Potentially-invalid** (consistency). Matches expected.
- **Reveals:** The single most important contrast in the batch — attention checks pass completely, and only the consistency pairs catch the corruption (pair A diff 3 alone triggers invalidity). Direct argument for keeping *both* mechanisms; attention checks are blind to a mid-test reinterpretation because they are self-labeling instructions, not scale items.

## Persona 73 — "Pat Randall" · "The Random Responder"
**Response pattern:** deterministic cycle 2,4,5,1,3 from Q1. Yields Q17=4 (pass by luck), Q33=5 (FAIL), Q49=1 (FAIL). Q1=2/Q41=2 (diff 0), Q10=3/Q56=2 (diff 1). Completion 120 s.

- Raw: MAK 29, EXP 32, VIS 28, MEN 33, PIO 33, GRD 30
- Spectrum: **MAK 48, EXP 55, VIS 45, MEN 57, PIO 57, GRD 50**
- Dominant: MEN+PIO+EXP · DI **12 (flat)** · flat=Yes
- Attention: **2/3 FAIL** · Consistency: A=0, B=1 (both pass!) · longest run 1 · time 120 s (<180)
- **Verdict: Potentially-invalid** (attention invalid + flat + fast cautions). Matches expected.
- **Reveals:** A structured-random cycle **evades both consistency pairs** (cycle math makes Q1/Q41 land identically and Q10/Q56 within tolerance) and sneaks past one attention check. Only the 2/3 attention majority + flat/fast auxiliaries flag it. Confirms: a single passing check must never rehabilitate a protocol; consistency pairs are defeated by any periodic pattern whose period divides the item spacing.

## Persona 74 — Marcus Bell · "The Straight-Liner"
**Response pattern:** 5 on all 65 items, <3 min. All three attention checks fail (need 4/1/3).

- Raw: MAK 42, EXP 42, VIS 38, MEN 42, PIO 38, GRD 38
- Spectrum: **MAK 80, EXP 80, MEN 80, VIS 70, PIO 70, GRD 70** (reverse items recode 5→1, so scales with 3 reverses = 70, with 2 reverses = 80)
- Dominant: MAK+EXP+MEN · DI **10 (flat)** · flat=Yes
- Attention: **3/3 FAIL** · Consistency: A=0,B=0 ("consistent" trivially) · **longest run 65** · time 165 s
- **Verdict: Potentially-invalid** (attention + long-string + flat + fast). Matches expected.
- **Reveals:** Reverse items successfully dampen all-max responding (elevated-but-flat 70–80, not a clean 100). Detected four ways over. Note the artifact: the "dominant" trio (MAK/EXP/MEN) is purely an accident of *how many reverse items each scale has* (2 vs 3) — a straight-line profile still names dominants, which a naive report front-end could display.

## Persona 75 — Katrine Holm · "The Depressed High-Performer"
**Response pattern:** state depression loads the NRG facet — every "drains my energy" reverse endorsed 4, every "gives me energy" item 1–2; ACT/ENV items answered near-normally. All checks pass; pairs consistent.

- Raw: MAK 25, EXP 30, VIS 29, MEN 25, PIO 25, GRD 29
- Spectrum: **EXP 50, VIS 48, GRD 48, MAK 38, MEN 38, PIO 38**
- Dominant: **EXP+VIS+GRD** (mild EXP/VIS lead as expected) · DI **12 (flat)** · flat=Yes
- Attention 0 fail · Consistency pass · **Verdict: Interpret-with-caution** (flat only). Matches VALID-WITH-FLAG.
- **Reveals:** State (mood) contaminates the NRG-facet reverse items and suppresses *every* scale toward the middle, manufacturing a flat profile from a normally mastery-driven person. The flag fires correctly but for the wrong reason. Report must offer "retest when circumstances change," not "no clear interests." Facet-level reporting (separating ACT/ENV from NRG) would let the truer ACT/ENV signal show through.

## Persona 76 — Dane Whitcombe · "The Targeted Faker"
**Response pattern:** all PIO positives 5, PIO reverses (Q24,44,58) 1; everything else honest (genuine quiet Explorer, EXP 4s). All checks pass; pairs consistent.

- Raw: MAK 29, EXP 41, VIS 35, MEN 26, PIO **50**, GRD 31
- Spectrum: **PIO 100, EXP 78, VIS 63, GRD 53, MAK 48, MEN 40**
- Dominant: **PIO+EXP** · DI **60 (well-differentiated)** · flat=No
- Attention 0 fail · Consistency pass · long run 3 · **Verdict: Valid — zero flags.** Matches expected.
- **Reveals:** The documented undetectable case. Single-scale impression management produces a *healthy, well-differentiated, fully valid* profile — elevation-based and variance-based screens see nothing because only one scale is inflated and the rest are honest. Hard evidence for the manual's "not a selection tool / not faking-resistant" caveat.

## Persona 77 — Siobhán Gallagher · "The Dyslexic Reader (Reverse-Item Load)"
**Response pattern:** positively-worded items accurate (MAK positives 5); ~half the reverse items misparsed (read "drains" as "sustains"), so Q21,39,44,53,54,58,65 answered high. Short imperative attention checks pass.

- Raw: MAK 43, EXP 28, VIS 30, MEN 31, PIO 28, GRD 32
- Spectrum: **MAK 83, GRD 55, MEN 53, VIS 50, EXP 45, PIO 45**
- Dominant: **MAK+GRD+MEN** (MAK clearly primary) · DI **38 (well-differentiated)** · flat=No
- Attention 0 fail · Consistency pass · **Verdict: Valid.** Matches expected (VALID but distorted).
- **Reveals:** A pure-Maker who should score ~95 is attenuated to 83 purely by misread reverse items — the profile is *valid by every screen yet measurably wrong*. The unexploited QA signal is **within-scale positive/reverse divergence**: MAK's positive items say 5 while its reverse items (misread) say the opposite. No current check inspects intra-scale coherence. Recommend plain-language rewrite of reverse items ("I do NOT like…") and a positive/reverse-divergence screen.

## Persona 78 — Hakim Ben Salah · "The Teaching Tradesman (Genuine Opposites #2)"
**Response pattern:** MAK positives 5, MEN positives 5, VIS/PIO 2–3, GRD 3. All checks pass; pairs Q1=5/Q41=5, Q10=3/Q56=4.

- Raw: MAK 48, EXP 31, VIS 26, MEN 47, PIO 28, GRD 33
- Spectrum: **MAK 95, MEN 93, GRD 57, EXP 53, PIO 45, VIS 40**
- Dominant: **MAK+MEN** (opposites; 3rd GRD 57 is 36 pts below MEN → excluded) · DI **55** · flat=No
- Attention 0 fail · Consistency A=0,B=1 pass · **Verdict: Valid.** Matches expected.
- **Reveals:** A clean RIASEC-opposite (Realistic+Social) dominance from an integrated real role, rule-based and coherent. Cross-check with persona 67 (aspirational MAK+MEN): the same dominant pair must receive consistent "The Responder" (RS) framing regardless of whether it's arrived at currently or aspirationally. Confirms the classifier is purely rank-based with no hexagon-coherence override — correct behavior here.

## Persona 79 — Lena Kovács · "The Speed-Runner (Near-Straight-Line)"
**Response pattern:** ~85% 4s with scattered 5s at trainer-relevant items, ~3 min, one-thumbed. Q17=4 (pass by habit), Q33=4 (FAIL), Q49=4 (FAIL). Pairs 4/4, 4/4.

- Raw: MAK 39, EXP 36, VIS 35, MEN 37, PIO 38, GRD 34
- Spectrum: **MAK 73, PIO 70, MEN 68, EXP 65, VIS 63, GRD 60**
- Dominant: MAK+PIO+MEN · DI **13 (flat)** · flat=Yes
- Attention: **2/3 FAIL** · Consistency pass · **longest run 11** · time 175 s (<180)
- **Verdict: Potentially-invalid** (attention + flat + fast). Matches expected INVALID.
- **Reveals:** The near-straight-line **evades the long-string screen by exactly one** (longest run 11, threshold 12) — jitter defeats the variance screen that catches persona 74. Detection collapses onto the attention checks (2/3) plus flat/time auxiliaries. If completion time weren't captured and the respondent had passed one more attention check, this profile would slip to "Interpret-with-caution." Argues for a *proportion-of-modal-response* screen rather than a strict consecutive-run counter.

## Persona 80 — Dr. Femi Adeyemi · "The Over-Deliberator"
**Response pattern:** ~60% 3s with justified 4s on EXP/MEN items; 40+ minutes. All checks pass; pairs consistent (4/4, 3/3). (Sheet tuned so no accidental 12+ run of 3s — see note below.)

- Raw: MAK 29, EXP 34, VIS 31, MEN 33, PIO 29, GRD 32
- Spectrum: **EXP 60, MEN 57, GRD 55, VIS 53, MAK 48, PIO 48**
- Dominant: **EXP+MEN+GRD** (GRD 55 within 10 of MEN 57 → 3rd strand; author expected EXP+MEN only) · DI **12 (flat)** · flat=Yes
- Attention 0 fail · Consistency pass · longest run 10 · **Verdict: Interpret-with-caution** (flat only). Matches VALID-WITH-FLAG.
- **Reveals:** The intended contrast case — a *maximally attentive* respondent trips the exact same flat flag as apathetic persona 62 and random persona 73. The flag has no way to tell "thoughtful clustering near neutral" from "disengagement." Report language must offer "differentiation may sharpen with forced-choice reflection," never a carelessness accusation. Also note: during sheet construction a genuine 60%-neutral responder produced a **14-item run of identical 3s** — a real false-positive vulnerability of the long-string screen against attentive midpointers; the honest fix is a modal-proportion screen, not a consecutive-run counter.

---

## Batch-level analysis

**Detection map (who caught what):**

| # | Attention | Consistency | Flat | Long-string | Time | Only thing that caught it |
|---|---|---|---|---|---|---|
| 71 | 2/3 | pass | no | no | – | attention checks (as anchor probe) |
| 72 | pass | **A=3** | no | no | – | **consistency pair alone** |
| 73 | 2/3 | pass | flat | no | fast | attention majority (+aux) |
| 74 | 3/3 | pass | flat | **65** | fast | everything |
| 75 | pass | pass | flat | no | – | flat only (state confound) |
| 76 | pass | pass | no | no | – | **nothing (targeted fake)** |
| 77 | pass | pass | no | no | – | **nothing (distorted-but-valid)** |
| 78 | pass | pass | no | no | – | n/a (genuinely valid) |
| 79 | 2/3 | pass | flat | no (11) | fast | attention majority (+aux) |
| 80 | pass | pass | flat | no | – | flat only (valid deliberator) |

**Verdict accuracy: 10/10.** Every persona's computed combined verdict matched its expected verdict under the VALID-WITH-FLAG↔Interpret-with-caution / INVALID↔Potentially-invalid mapping. Two personas (77, 80) picked up a literal 3rd dominant avatar via the ≤10-point rule where the author's prose listed two; this is the rule behaving correctly, not a mis-score.
