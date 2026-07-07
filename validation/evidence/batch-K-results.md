# Batch K Results — Personas 101–110 (Classification Stress Tests: Pure Types + Pair Profiles)

Scored with `score_batch_K.py` (same directory), a literal implementation of `data/scoring.json`:
reverse = 6 − raw for Q21,24,28,29,31,39,43,44,45,53,54,55,58,63,65; raw = scale sum;
spectrum = round-half-up(((raw−10)/40)×100); dominant = top 2 + third if score2−score3 ≤ 10;
naive tie handling = Python stable sort with scale-dict insertion order (MAK, EXP, VIS, MEN, PIO, GRD);
DI = max−min, flat flag if DI < 15; attention Q17=4/Q33=1/Q49=3; consistency |Q1−Q41|, |Q10−Q56|
(invalid if any diff ≥3 or both ≥2); long-string screen ≥12 identical consecutive responses;
verdicts per scoring.json `validity.verdicts` + manual §6.7.

All 10 protocols: 3/3 attention checks passed, both consistency pairs diff = 0, no long-string ≥12,
all engineered score targets hit within ±3 on first run (no response adjustments needed).

Legend for response sheets: 65 space-separated answers, Q1→Q65 in order.

---

## Persona 101: Piotr Wozniak — Pure Maker

**Response sheet (Q1–Q65):**
`1 5 1 1 1 1 5 1 1 1 1 1 1 5 1 1 4 1 1 5 5 1 1 5 1 5 1 5 5 1 5 5 1 1 1 1 1 1 1 1 1 1 5 5 5 5 1 1 3 1 1 1 1 5 5 1 1 5 1 5 1 1 5 1 5`
(All 8 MAK positives = 5, MAK reverses Q39/Q53 = 1; every other avatar's positives = 1, reverses = 5. Q17=4, Q33=1, Q49=3; Q1=1/Q41=1, Q10=1/Q56=1.)

**Computed:** raw MAK 50, all others 10 → spectrum MAK **100**, EXP/VIS/MEN/PIO/GRD **0**.
Dominant = **MAK + EXP + VIS** (3 avatars). DI = 100. Attention 0 fails; pairs 0/0. Verdict **VALID**.
Top-2 combination lookup: MAK+EXP → "The Diagnostician".

**Expected vs computed:** Expected MAK=100, others ≤5, "Dominant = MAK + a meaningless forced #2." Computed is *worse than expected*: because score2 − score3 = 0 − 0 = 0 ≤ 10, the third-inclusion rule fires and the algorithm names **three** Dominant Avatars, two of them at spectrum 0. The identity of the #2/#3 (EXP, VIS) is pure sort-order artifact (dict insertion order), not documented tie-breaking — §6.5 covers ties at rank 1/2 and a tie *for rank 3*, but not a 5-way tie spanning ranks 2–6.

**Reveals:** (a) No minimum-score threshold for dominance — a 0-score avatar can be "Dominant"; (b) the ≤10 third-inclusion rule fires on floor ties; (c) combination naming produces a spurious "Diagnostician" (RI) profile for a respondent with zero Investigative signal; (d) longest identical run = 10, just under the 12 long-string threshold — engineered floors approach but do not trip auxiliary screens.

---

## Persona 102: Dr. Amara Nwosu — Pure Explorer

**Response sheet (Q1–Q65):**
`1 1 1 5 1 1 1 1 5 1 1 1 5 1 1 1 4 1 1 1 5 1 5 5 1 1 1 1 5 1 5 1 1 1 5 1 1 1 5 1 1 5 5 5 5 1 1 5 3 1 1 1 5 5 1 1 1 5 1 1 1 5 5 1 5`

**Computed:** raw EXP 50, others 10 → EXP **100**, others **0**. Dominant = **EXP + MAK + VIS** (3). DI = 100. 0 attention fails; pairs 0/0. Verdict **VALID**. Top-2 combo: EXP+MAK → "The Diagnostician".

**Expected vs computed:** EXP=100 hit exactly. Same forced-third artifact as 101; the arbitrary #2 is MAK purely because MAK is first in the scales dict.

**Reveals:** Confirms the tie artifact is systematic, not MAK-specific: whichever avatars appear earliest in implementation order are promoted from a 0-score five-way tie.

---

## Persona 103: Camille Renard — Pure Visionary

**Response sheet (Q1–Q65):**
`1 1 1 1 1 5 1 1 1 1 5 1 1 1 1 1 4 1 5 1 5 1 1 5 5 1 1 5 5 1 1 1 1 1 1 1 1 5 5 1 1 1 5 5 1 1 1 1 3 1 1 5 5 5 5 1 1 5 5 1 1 1 5 1 1`

**Computed:** VIS raw 50 → **100**, others 10 → **0**. Dominant = **VIS + MAK + EXP** (3). DI = 100. Verdict **VALID**. Top-2 combo: VIS+MAK → "The Artisan".

**Expected vs computed:** VIS=100 hit. Spurious second/third again; a pure Artistic profile is labeled with an RA "Artisan" combination despite MAK = 0.

**Reveals:** Combination-profile assignment is driven entirely by rank order with no strength gate — the report layer would present a blend that half does not exist.

---

## Persona 104: Grace Mwangi — Pure Mentor

**Response sheet (Q1–Q65):**
`5 1 1 1 1 1 1 5 1 1 1 1 1 1 5 1 4 1 1 1 1 1 1 5 1 1 5 5 5 1 5 1 1 5 1 1 1 1 5 5 5 1 5 5 5 1 5 1 3 1 1 1 5 1 5 1 1 5 1 1 5 1 5 1 5`
(Q1=5/Q41=5 stresses pair A at ceiling; Q10=1/Q56=1.)

**Computed:** MEN raw 50 → **100**, others **0**. Dominant = **MEN + MAK + EXP** (3). DI = 100. Pair diffs 0/0 (ceiling consistency handled cleanly). Verdict **VALID**. Top-2 combo: MEN+MAK → "The Responder".

**Expected vs computed:** MEN=100 hit; pair-A-at-ceiling works. Forced third again. Notably the spurious top-2 combo is the RIASEC *opposite-pole* pair (Social+Realistic) purely by sort accident.

**Reveals:** Consistency pair scoring is symmetric and safe at the 5/5 ceiling; dominance/combination logic remains the sole failure surface for pure types.

---

## Persona 105: Diego Paredes — Pure Pioneer

**Response sheet (Q1–Q65):**
`1 1 1 1 5 1 1 1 1 1 1 5 1 1 1 1 4 5 1 1 5 1 1 1 1 1 1 5 5 5 5 1 1 1 1 1 5 1 5 1 1 1 5 1 5 1 1 1 3 1 5 1 5 5 5 1 1 1 1 1 1 1 5 5 5`

**Computed:** PIO raw 50 → **100**, others **0**. Dominant = **PIO + MAK + EXP** (3). DI = 100. Verdict **VALID**. Top-2 combo: PIO+MAK → "The Groundbreaker".

**Expected vs computed:** PIO=100 hit; same triple-dominant artifact.

**Reveals:** Nothing new beyond 101–104; consistent replication across all six scales confirms the defect is structural.

---

## Persona 106: Hana Novotná — Pure Guardian

**Response sheet (Q1–Q65):**
`1 1 5 1 1 1 1 1 1 5 1 1 1 1 1 5 4 1 1 1 5 5 1 5 1 1 1 5 1 1 5 1 1 1 1 5 1 1 5 1 1 1 1 5 5 1 1 1 3 5 1 1 5 5 5 5 5 5 1 1 1 1 1 1 5`
(Q10=5/Q56=5 stresses pair B at ceiling; Q1=1/Q41=1.)

**Computed:** GRD raw 50 → **100**, others **0**. Dominant = **GRD + MAK + EXP** (3). DI = 100. Pair diffs 0/0. Verdict **VALID**. Top-2 combo: GRD+MAK → "The Steady Hand".

**Expected vs computed:** GRD=100 hit; pair B at ceiling clean. All six pure types (101–106) classify the correct primary avatar at rank 1 — **6/6 primary accuracy** — and all six emit two spurious 0-score co-dominants.

**Reveals:** Pure-type suite verdict: scale construction and reverse keys are airtight at the extremes (exactly 100 vs 0, no bleed between scales), but the Dominant Avatar rule has no floor guard and no documented tie policy for the degenerate all-tied tail.

---

## Persona 107: Lars Björkman — Adjacent Pair MAK–EXP

**Response sheet (Q1–Q65):**
`2 5 2 5 2 2 5 2 5 2 2 2 4 5 2 2 4 2 2 5 4 2 4 4 2 5 2 2 4 2 4 5 1 2 5 2 2 2 2 2 2 5 4 4 4 5 2 4 3 2 2 2 3 4 2 2 2 4 2 4 2 4 4 2 4`
(MAK positives seven 5s + one 4, Q39=2/Q53=3; EXP mixed 5s/4s, Q28=Q55=2; all other positives 2, reverses 4.)

**Computed:** raw MAK 46, EXP 44, others 20 → spectrum **MAK 90, EXP 85**, VIS/MEN/PIO/GRD 25.
Dominant = **MAK + EXP** (gap 2→3 = 60, third excluded). DI = 65. Verdict **VALID**. Combo: "The Diagnostician" (RI) — correct.

**Expected vs computed:** Expected MAK 90 / EXP ≈86. Computed EXP = 85 because **86 is unreachable**: spectrum quantization maps raw 44→85 and raw 45→88; the 0–100 scale has only 41 attainable values, so 86/87 (and many other "target" scores in the persona specs) cannot exist. Rank order MAK > EXP is stable and correct.

**Reveals:** (a) Adjacent hexagon pair discriminated cleanly, no collapse; (b) spectrum-score granularity is 2.5 points — documentation implies a continuous 0–100 scale; (c) a four-way tie at rank 3 (all 25) is handled harmlessly here only because the 10-point rule excludes it.

---

## Persona 108: Rebecca Osei — Adjacent Pair MEN–PIO

**Response sheet (Q1–Q65):**
`5 2 2 2 5 2 2 5 2 3 2 5 2 2 5 2 4 5 2 2 1 2 2 2 2 2 5 4 4 4 4 2 1 5 2 2 4 2 4 5 5 2 4 2 4 2 4 2 3 2 4 2 4 2 4 3 2 1 2 2 4 2 3 4 4`

**Computed:** raw MEN 47, PIO 44, GRD 22, MAK/EXP/VIS 20 → **MEN 93, PIO 85**, GRD 30, others 25.
Dominant = **MEN + PIO** (gap 55, third excluded). DI = 68. Verdict **VALID**. Combo: "The Motivator" (SE) — correct.

**Expected vs computed:** Expected MEN ≈92 / PIO ≈86; computed 93/85 — both off by ±1 due to the same quantization (raw 47 → 92.5 → 93 under round-half-up; 92 exactly is unattainable). Classification exact.

**Reveals:** Round-half-up at the .5 boundary works as documented (92.5→93); helper-leader adjacency separates correctly.

---

## Persona 109: Dieter Falk — Adjacent Pair GRD–MAK

**Response sheet (Q1–Q65):**
`2 5 5 2 1 1 5 2 2 5 1 1 2 5 2 5 4 2 1 5 5 5 2 4 1 4 2 3 1 1 4 4 1 2 2 5 1 1 1 2 2 2 2 4 4 4 2 2 3 4 2 1 3 5 3 5 4 3 1 4 2 2 2 1 3`

**Computed:** raw GRD 46, MAK 44, EXP 22, MEN 18, PIO 16, VIS 14 → **GRD 90, MAK 85**, EXP 30, MEN 20, PIO 15, VIS 10.
Dominant = **GRD + MAK** (gap 55). DI = 80. Verdict **VALID**. Combo: "The Steady Hand" (RC-inverse, listed as MAK+GRD) — correct pair.

**Expected vs computed:** Expected GRD ≈90 / MAK ≈84; computed 90/85 (84 unattainable — raw 43→83, 44→85). Classification exact; GRD ranks first as intended.

**Reveals:** Combination table is keyed as unordered pairs in my implementation (frozenset), but `scoring.json` keys them as ordered strings ("MAK+GRD"); a literal string-keyed implementation would miss "GRD+MAK" — an implementation hazard worth documenting.

---

## Persona 110: Sister Maria Aparecida — Opposite Pair MAK+MEN, all else floored

**Response sheet (Q1–Q65):**
`5 5 2 1 1 1 5 5 1 2 1 1 2 5 5 1 4 1 1 5 3 2 1 4 2 5 5 4 4 2 4 4 1 5 1 1 1 1 1 5 5 1 4 4 4 4 4 1 3 2 1 2 2 2 4 2 1 4 1 4 4 2 4 2 4`

**Computed:** raw MAK 46, MEN 45, GRD 17, VIS 15, PIO 15, EXP 14 → **MAK 90, MEN 88**, GRD 18, VIS 13, PIO 13, EXP 10.
Dominant = **MAK + MEN** (gap 70, third excluded). DI = 80. Verdict **VALID**. Combo: MAK+MEN → **"The Responder" (RS)** — the "impossible" hexagon-opposite pair resolves to a real, coherent combination profile.

**Expected vs computed:** Expected MAK ≈90 / MEN ≈88 — hit exactly. Confirms the rule is purely rank-based: no hexagon-coherence override suppresses or reorders an opposite-pole pair, and the combinations table covers all 15 unordered pairs, so opposite pairs are first-class citizens.

**Reveals:** The classifier is agnostic to RIASEC geometry — a strength (honest profiles like carpenter-nurse classify cleanly) documented here as intended behavior, matching persona 78/67's organic versions.

---

## Batch verification table

| P | Target | Computed | Dominant (computed) | DI | Verdict | Match |
|---|---|---|---|---|---|---|
| 101 | MAK 100, rest ≤5 | MAK 100, rest 0 | MAK+EXP+VIS | 100 | VALID | primary yes / dominant-set artifact |
| 102 | EXP 100 | EXP 100, rest 0 | EXP+MAK+VIS | 100 | VALID | primary yes / artifact |
| 103 | VIS 100 | VIS 100, rest 0 | VIS+MAK+EXP | 100 | VALID | primary yes / artifact |
| 104 | MEN 100 | MEN 100, rest 0 | MEN+MAK+EXP | 100 | VALID | primary yes / artifact |
| 105 | PIO 100 | PIO 100, rest 0 | PIO+MAK+EXP | 100 | VALID | primary yes / artifact |
| 106 | GRD 100 | GRD 100, rest 0 | GRD+MAK+EXP | 100 | VALID | primary yes / artifact |
| 107 | MAK 90 / EXP ~86 | 90 / 85 | MAK+EXP | 65 | VALID | exact |
| 108 | MEN ~92 / PIO ~86 | 93 / 85 | MEN+PIO | 68 | VALID | exact |
| 109 | GRD ~90 / MAK ~84 | 90 / 85 | GRD+MAK | 80 | VALID | exact |
| 110 | MAK ~90 / MEN ~88 | 90 / 88 | MAK+MEN | 80 | VALID | exact |

Validity subsystem: 10/10 correctly VALID (all attention checks passed, all pairs consistent, no false flags; longest identical run peaked at 10 in P101, below the 12 threshold).

## Batch findings

1. **Forced-dominance defect (systematic, 6/6 pure types).** The "top 2 always Dominant" rule plus "third if score2−score3 ≤ 10" has no minimum-score guard: a pure type emits two spurious co-dominant avatars at spectrum 0, and the tie among five 0-scores is resolved by undocumented implementation order (§6.5 covers rank-1/2 and rank-3 ties, not a tie spanning ranks 2–6). Recommend: minimum spectrum (e.g., ≥40) or minimum gap-to-#1 for dominance eligibility, plus explicit degenerate-tie policy.
2. **Spurious combination profiles.** Because combination naming keys off the top-2, every pure type receives a blend label ("Diagnostician", "Artisan", "Responder"…) whose second component scored 0. Report layer must gate combination narratives on #2 strength.
3. **Spectrum quantization.** Only 41 attainable spectrum values (2.5-pt steps); persona targets of 84/86/92 are unrepresentable. Harmless for classification, but documentation should not imply integer-continuous 0–100 precision, and the DI/10-point boundaries interact with this lattice (score2−score3 can only change in 2.5-then-rounded increments).
4. **Pair/opposite handling is sound.** Adjacent pairs (107–109) and the hexagon-opposite pair (110) all classified exactly; rank ordering is stable; round-half-up confirmed at 92.5→93; consistency pairs behave correctly at ceiling (104, 106) and floor (101–103, 105).
5. **Implementation hazard.** `combinations` in scoring.json is keyed by ordered strings ("MAK+GRD"); rank order can produce "GRD+MAK" (persona 109). Implementations must normalize pair order or the lookup silently fails.
