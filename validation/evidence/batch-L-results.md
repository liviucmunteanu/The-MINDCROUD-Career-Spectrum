# Batch L Results — Personas 111–120 (Classification Stress Tests)

Scored with `score_batch_L.py` (same directory), a naive literal implementation of
`/home/lm349882/orionDev/The-MINDCROUD-Career-Spectrum/data/scoring.json` cross-checked against
Section 6 of `MINDCROUD-Career-Spectrum.md` (lines 320–456). Naive tie handling = Python stable
sort over scoring.json scale order (MAK, EXP, VIS, MEN, PIO, GRD); this order silently becomes
the de facto tiebreak everywhere the documentation is silent.

## Pre-registered mathematical finding (applies to 113, 116, 119)

Spectrum Score = round((raw−10)/40×100) with raw ∈ {10..50} produces only values of the form
round(2.5k): **…63, 65, 68, 70, 73, 75, 78, 80, 83, 85, 88, 90, 93, 95, 98, 100** — i.e. every
Spectrum Score is ≡ 0 or 3 (mod 5). Consequences:

1. **Persona targets 72, 91, 92, 95(±) are unreachable.** Nearest lattice points used instead
   (documented per persona below).
2. **A score2−score3 gap of exactly 11 is impossible.** Differences between two lattice values are
   ≡ 0, 2, or 3 (mod 5); 11 ≡ 1 (mod 5). The smallest gap that EXCLUDES the third avatar is 12.
   The "10 vs 11" boundary described in the study design is really a "10 vs 12" boundary. The
   documentation's "within 10 points" rule is therefore never exercised at 11; boundary personas
   115/116 bracket it at 10 (include) vs 12 (exclude).
3. Under pure endpoint responding (only 1s and 5s), raw = 10+4a → Spectrum ∈ {0,10,20,…,100}
   (multiples of 10 only). Persona 119's specified 95/92/91 triple is unreachable for an
   extreme-style responder by construction.

---

## Persona 111 — Dr. Elena Vasquez ("Opposite Pair: Explorer+Pioneer")

**Response sheet Q1–65:**
`2 2 2 5 5 2 2 2 5 2 2 5 5 2 2 2 4 5 2 2 5 2 5 2 2 2 2 2 4 5 5 2 1 2 5 2 5 2 5 2 2 5 5 2 5 2 1 5 3 2 5 2 5 5 2 2 2 2 2 2 1 4 5 4 4`

- Raw: MAK 18, EXP 47, VIS 18, MEN 16, PIO 46, GRD 18
- Spectrum: MAK 20, **EXP 93**, VIS 20, MEN 15, **PIO 90**, GRD 20
- Dominant: EXP + PIO → **The Strategist (IE)**; third excluded (90−20 = 70)
- DI = 78 (well-differentiated); attention 3/3 pass; pairs A=0, B=0
- Verdict: **Valid**

**Expected vs computed:** Expected EXP≈92 / PIO≈90 → EXP 93 used (92 unreachable, see lattice
finding). Classification matches expectation exactly: MATCH.

**Reveals:** The opposite-pair I–E profile is handled cleanly; nothing in the algorithm notices
or comments that the two dominants are hexagon opposites (no consistency-of-profile metric à la
Holland congruence — a silent omission, not an error).

---

## Persona 112 — Tobias Ambühl ("Opposite Pair: Visionary+Guardian")

**Response sheet Q1–65:**
`2 2 5 2 2 5 2 2 2 5 5 2 2 2 2 5 4 2 5 2 5 5 2 5 5 2 2 4 2 2 2 2 1 2 2 5 2 5 5 2 2 2 3 5 2 1 2 2 3 5 1 5 5 5 4 5 5 4 5 1 2 2 3 1 3`

- Raw: MAK 16, EXP 20, VIS 46, MEN 18, PIO 16, GRD 45
- Spectrum: MAK 15, EXP 25, **VIS 90**, MEN 20, PIO 15, **GRD 88**
- Dominant: VIS + GRD → **The Curator (AC)**; DI = 75; all checks pass (Q10=5/Q56=5 as scripted)
- Verdict: **Valid**

**Expected vs computed:** MATCH (VIS 90, GRD 88 hit exactly).

**Reveals:** A–C opposite pair scores and labels without complaint; the combinations table does
contain all 15 pairs, so no opposite pair is unmappable. Companion to organic persona 70 confirmed.

---

## Persona 113 — Anouk Deschamps ("Exact Tie at Rank 2/3")

**Response sheet Q1–65:**
`4 2 2 5 3 4 2 4 5 3 4 3 5 2 4 2 4 3 4 2 2 2 5 4 4 2 4 4 3 3 2 2 1 4 5 2 3 4 2 4 4 5 3 4 2 2 4 5 3 2 3 4 2 3 3 3 2 5 4 2 4 5 3 3 3`

- Raw: MAK 24, EXP 45, **VIS 39, MEN 39 (identical raw sums)**, PIO 26, GRD 24
- Spectrum: EXP 88, **VIS 73, MEN 73**, PIO 40, MAK 35, GRD 35
- Naive dominant: **[EXP, VIS, MEN]** — 3 avatars; s2−s3 = 0 ≤ 10 → third included
- Primary combination emitted: **The Idea Architect (EXP+VIS)** — because VIS precedes MEN in
  scoring.json scale order, nothing else
- DI = 53; all validity checks pass → **Valid**

**Expected vs computed:** Persona spec said VIS = MEN = 72; 72 is unreachable (lattice), so the
tie was built at 73 (raw 39 = raw 39 — the tie itself, the point of the test, is exact). MATCH
on the classification question (3 Dominant Avatars).

**Documentation vs implementation:**
- Doc 6.5 tie-breaking: "A tie for rank 1 or rank 2: both are Dominant." VIS/MEN tie for rank 2
  → both Dominant → 3 avatars. Naive implementation agrees, so the *count* is well-defined.
- **Undefined:** which tied scale is "rank 2" (and therefore names the primary pair). The naive
  sort answers "whichever appears first in the scales dict" — EXP+VIS "Idea Architect" rather
  than EXP+MEN "The Healer". Two different, career-steering combination reports hinge on JSON key
  order. Reproducible across reruns of the same implementation, but NOT specified anywhere; a
  reimplementation sorting alphabetically (EXP, GRD, MAK, MEN, PIO, VIS) would report The Healer.

---

## Persona 114 — Yusuf Demir ("Three-Way Tie at the Top")

**Response sheet Q1–65:**
`3 5 3 3 4 5 5 3 3 3 4 4 3 4 3 3 4 4 4 4 5 3 3 1 4 4 3 5 5 4 1 4 1 3 3 3 4 4 2 3 3 3 4 1 2 4 3 3 3 3 4 4 2 5 5 3 3 2 4 4 3 3 4 4 2`

- Raw: **MAK 42, VIS 42, PIO 42 (identical)**; EXP 26, MEN 26, GRD 26
- Spectrum: **MAK 80 = VIS 80 = PIO 80**; EXP/MEN/GRD 40
- Naive dominant: **[MAK, VIS, PIO]**, primary combination **The Artisan (MAK+VIS)**
- DI = 40; all checks pass → **Valid**

**Expected vs computed:** MATCH on count (3 avatars). Targets hit exactly (80/80/80, 40/40/40).

**Documentation vs implementation:**
- Doc 6.5 covers "a tie for rank 1 or rank 2" phrased for TWO-way ties ("both are Dominant"). A
  THREE-way top tie is not addressed at all. All three end up Dominant under any reading, but the
  "primary" ordering (which pair names the combination, which avatar leads the report) is
  entirely emergent: naive output is MAK > VIS > PIO purely by dict order. Stable across reruns
  of this implementation; undefined as a specification. An alphabetical implementation would
  lead with MAK+PIO ("The Groundbreaker"). Three plausible primary combinations (Artisan,
  Groundbreaker, Creative Director) — the report identity is implementation-defined.

---

## Persona 115 — Mei-Xin Loh ("The Exact 10-Point Boundary")

**Response sheet Q1–65:**
`5 3 4 4 3 3 3 5 4 4 3 3 4 3 5 4 4 3 3 3 2 4 4 4 3 3 5 4 1 3 3 3 1 5 4 4 3 3 5 5 5 4 2 4 4 3 4 4 3 4 3 3 5 2 3 4 4 5 3 3 4 4 2 3 4`

- Raw: MAK 26, EXP 37, VIS 28, MEN 46, PIO 26, GRD 41
- Spectrum: **MEN 90, GRD 78, EXP 68** — s2−s3 = 78−68 = **10 exactly**; others ≤ 45
- Naive dominant: **[MEN, GRD, EXP]** — 3 avatars (boundary is INCLUSIVE)
- Primary combination: **The Anchor (MEN+GRD)**
- DI = 50; pairs Q1=5/Q41=5, Q10=4/Q56=4; all checks pass → **Valid**

**Expected vs computed:** MATCH. Both scoring.json (`"thirdDominantIf": "score2 - score3 <= 10"`)
and Section 6.5 ("within 10 points... i.e., Score₂ − Score₃ ≤ 10") agree the boundary is
inclusive, and the naive implementation includes EXP at exactly 10. This boundary is one of the
few places where JSON and prose are unambiguous AND consistent.

---

## Persona 116 — Óscar Fuentes ("The 11-Point Control")

**Response sheet Q1–65:**
`2 5 4 3 5 2 5 2 3 4 2 5 3 4 2 4 4 5 2 4 2 4 3 2 2 4 2 5 2 5 2 4 1 2 3 3 5 2 2 2 2 3 2 2 3 4 2 3 3 3 5 2 2 2 5 4 4 2 2 4 2 3 3 5 3`

- Raw: MAK 42, EXP 26, VIS 24, MEN 24, PIO 47, GRD 37
- Spectrum: **PIO 93, MAK 80, GRD 68** — s2−s3 = **12**; others ≤ 40
- Naive dominant: **[PIO, MAK] only** — GRD excluded → **The Groundbreaker (MAK+PIO)**
- DI = 58; all checks pass → **Valid**

**Expected vs computed:** DELIBERATE DEVIATION, fully documented: the specified PIO = 92 and
score2−score3 = 11 are both mathematically unreachable (lattice finding above; 11 ≡ 1 mod 5 is
not a difference of two lattice values). Nearest realizable control is PIO 93 / MAK 80 / GRD 68 →
gap 12 → exclusion, which serves the identical control purpose. Paired with 115, the boundary is
bracketed at 10 (include) / 12 (exclude); **no respondent can ever produce a gap of 11**, so the
documented rule's behavior "at 11" is vacuously untestable. MATCH on the control outcome
(exactly 2 Dominant Avatars).

---

## Persona 117 — Sandra Milosevic ("The All-Neutral Responder")

**Response sheet Q1–65:** all 65 responses = 3.

- Raw: all six = 30; Spectrum: **all six = 50** (six-way tie)
- DI = **0** → flat-profile flag; long-string run = **65** (screen threshold 12)
- Attention: Q17=3 FAIL, Q33=3 FAIL, Q49=3 pass-by-definition → 2/3 failed → invalid-level
- Pairs: A=0, B=0 (consistent by default — consistency screen is blind to this pattern)
- Verdict: **Potentially invalid** ✓
- Naive dominant output: **[MAK, EXP, VIS] → "The Diagnostician"** — pure dict-order artifact

**Expected vs computed:** MATCH on verdict and on no-crash (no NaN/division issues: DI and
ranking are pure integer ops). Targets hit exactly.

**Documentation vs implementation:**
- Six-way tie: doc 6.5's tie rules ("tie for rank 1 or rank 2 → both Dominant"; "tie for rank 3
  → shared third strand") cannot even be parsed for a six-way tie — read literally, all six tie
  for rank 1, which would make all six "Dominant." The naive implementation instead emits an
  arbitrary top-3 (MAK, EXP, VIS) and confidently names "The Diagnostician" for a person who
  expressed zero preference about anything. Nothing in scoring.json suppresses dominant
  computation for invalid profiles.
- Note Q49=3 means an all-neutral responder can only ever fail 2 of 3 attention checks — the
  instrument's own neutral-anchored check guarantees this pattern lands at exactly the 2-fail
  invalid threshold, not above it. Fragile but sufficient here.

---

## Persona 118 — Prof. Adaora Ekwueme ("The Flat-but-Elevated Polymath")

**Response sheet Q1–65:** all positives = 4, all 15 reverses = 2, attention Q17=4/Q33=1/Q49=3,
Q41=4, Q56=4:
`4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 2 4 4 2 4 4 4 2 2 4 2 4 1 4 4 4 4 4 2 4 4 4 2 2 2 4 4 4 3 4 4 4 2 2 2 4 4 2 4 4 4 4 2 4 2`

- Raw: all six = 40; Spectrum: **all six = 75** (six-way tie, elevated)
- DI = 0 → flat-profile flag; attention 3/3 pass; pairs A=0, B=0
- Long-string: **run of 20 identical responses (Q1–Q20 all "4")** → screen fires at threshold 12
- Naive verdict: **Interpret with caution** — but ONLY because of the long-string screen
- Naive dominant output: [MAK, EXP, VIS] → "The Diagnostician" (dict-order artifact again)

**Expected vs computed:** Expected VALID-WITH-FLAG. Computed "Interpret with caution" — the right
neighborhood but **for the wrong reason**, which is itself a double finding:

1. **The flat-profile flag does not feed the validity verdict at all.** Section 6.7C defines the
   combined verdict only over attention, consistency, and the automated screens; the DI flag
   lives in 6.6 as report guidance. scoring.json likewise keeps `"flag": "flat-profile"` outside
   `validity.verdicts`. A pure flat-elevated profile with no long-string would come back plain
   "Valid" with no caution — the persona's hypothesized detection gap is real in the JSON.
2. **The long-string screen structurally false-positives on uniform genuine responders**, because
   the first reverse-keyed item is Q21 — items Q1–Q20 are all positively keyed (plus Q17's
   "Agree" check, which a uniform-4 responder also matches). Any consistent mild-agree profile
   emits a 20-run and gets flagged. The screen intended for disengagement fires on the most
   engaged, most internally consistent respondent in the batch.
3. Nothing distinguishes 118 (flat-high, attentive, valid) from 117 (flat-mid, inattentive,
   invalid) in the *profile* output itself — same arbitrary [MAK, EXP, VIS] "Diagnostician"
   dominants at different elevations. Only the validity block separates them; elevation
   (all-75 vs all-50) is never interpreted.

Scored as a MISMATCH against the persona's expected outcome (flag fired from the wrong
mechanism; flat flag itself contributes nothing to the verdict).

---

## Persona 119 — Nikolai Sørensen ("The Polarized Triple-High")

**Response sheet Q1–65:**
`1 5 1 1 5 5 5 1 1 1 5 5 1 5 1 1 4 5 5 5 5 1 1 1 5 5 1 5 5 5 5 5 1 1 1 1 5 5 1 1 1 1 5 1 1 5 1 1 3 1 5 5 1 5 5 1 1 5 5 5 1 1 5 5 1`
(only endpoints except the three obeyed attention checks 4/1/3; anti-items Q31=5, Q58=5 create
the VIS/PIO separation from MAK)

- Raw: MAK 50, VIS 46, PIO 46; EXP 10, MEN 10, GRD 10
- Spectrum: **MAK 100, VIS 90, PIO 90; EXP 0, MEN 0, GRD 0**
- Naive dominant: **[MAK, VIS, PIO]** (s2−s3 = 0) → primary **The Artisan (MAK+VIS)**
- DI = **100** (maximum possible); attention pass; pairs 1/1 and 1/1; longest run = 5
- Verdict: **Valid** — with no notation of any kind about response style

**Expected vs computed:** Persona specified ≈95/92/91. Under endpoint-only responding, Spectrum
Scores can only be multiples of 10 (raw = 10+4a), so 95/92/91 is unreachable *by the persona's
own response style*; realized as 100/90/90, which preserves every property under test (three-way
dominant cluster within 10 points, extreme DI). MATCH on classification (MAK+VIS+PIO, 3 avatars).

**Reveals:**
- The top-3 rule behaves correctly under polarization; the VIS/PIO tie at rank 2/3 is absorbed
  because both are within 10 of rank 2 anyway.
- **No extreme-response-style detection exists anywhere** in scoring.json: 62 of 65 answers at
  the endpoints, DI = 100, and the output is indistinguishable from a calm, moderate profile
  with the same ranks. DI has no upper sanity band — "≥ 30" is one undifferentiated bucket
  whether DI is 35 or 100.
- Report coherence for the non-adjacent triple R–A–E: the primary pair is again chosen by dict
  order (MAK+VIS "Artisan"), silently preferring one of three defensible identities.

---

## Persona 120 — "Max Chaos" ("The Every-Flag Protocol")

**Response sheet Q1–65** (completion time 90 s):
`5 5 5 5 5 5 5 5 5 1 5 5 5 5 5 5 1 5 5 5 5 5 5 5 5 5 5 5 5 5 1 1 5 1 1 5 1 1 5 1 1 1 5 1 5 1 1 1 5 5 1 1 5 1 1 5 3 3 3 3 3 3 3 3 3`
Construction: Q1=5; straight-5 run Q2–Q16 (broken only by required Q10=1); Q17=1 FAIL;
straight-line Q18–Q30 = **13 consecutive 5s** (long-string); mixed 1/5 blocks Q30–Q55 with
Q33=5 FAIL and Q49=5 FAIL embedded; Q41=1 (pair A diff 4), Q56=5 (pair B diff 4); all-3s Q57–65.
(Persona script said "Q2–Q16 all 5" AND "Q10=1" — contradictory; the consistency-pair
requirement was honored and the ≥12 run placed at Q18–Q30.)

- Raw: MAK 32, EXP 32, VIS 34, MEN 32, PIO 34, GRD 34
- Spectrum: MAK 55, EXP 55, **VIS 60**, MEN 55, **PIO 60**, **GRD 60** → compressed band 55–60 ✓
- DI = **5** → flat flag ✓
- Attention: **0/3 (Q17, Q33, Q49 all failed)** → invalid-level ✓
- Consistency: **A = 4, B = 4** → invalid-level (both maximally discordant) ✓
- Long-string: run = 13 ≥ 12 → screen fires ✓; completion 90 s < 180 s → screen fires ✓
- Verdict: **Potentially invalid** ✓ (2 invalid-level + 2 undefined-level + flat, all at once)
- Naive dominant output: **[VIS, PIO, GRD] → "The Creative Director"** — computed and labeled
  despite every validity mechanism firing

**Expected vs computed:** MATCH on verdict; **FAIL on suppression** — the critical finding the
persona was designed to catch. Nothing in scoring.json expresses "do not compute/deliver
dominants for potentially-invalid profiles"; that instruction exists only as prose in 6.7A
("Do not deliver an automated report") and 6.7C. A literal implementer of the JSON produces a
named career identity ("The Creative Director", VIS+PIO+GRD — itself a nonsense triple resting
on a 5-point DI and a 3-way tie at 60 over a 3-way tie at 55) for a 90-second adversarial
protocol. Precedence of invalidity reasons over score display is entirely unimplemented in the
data layer.

**Also undefined:** what severity level long-string and completion-time flags carry. 6.7C names
them "automated screens" and the verdict formula counts "caution-level signals" — but neither
document says whether these screens are caution-level or invalid-level. The naive implementation
had to guess (caution). Two guessed screens alone (fast + long-string, with clean attention/
consistency) would tip a verdict from Valid to Potentially invalid under the "two or more
caution-level signals" rule — a materially different outcome resting on an undocumented choice.

---

# Batch Summary

**Classification accuracy: 8/10** exact matches (111, 112, 113, 114, 115, 116, 117, 119);
118 mismatch (flag fired from wrong mechanism; flat flag inert in verdict); 120 verdict correct
but score-suppression requirement unmet. Note: 3 of the 8 matches (113, 116, 119) required
adjusting persona score targets to the nearest mathematically reachable values.

**Patterns of failure:**
1. Every tie is resolved by implementation accident (dict/sort order), never by documented rule —
   affects 113, 114, 117, 118, 120.
2. Profile-shape flags (flat, elevation, extreme style) never influence the validity verdict —
   only attention/consistency/screens do (118, 119).
3. Invalid profiles still receive fully-formed dominant identities (117, 120).

**Algorithm weaknesses exposed:**
- Spectrum lattice: only values ≡ 0 or 3 (mod 5) exist; gap of exactly 11 is impossible, so the
  documented ≤10 boundary is really a 10-vs-12 boundary (115/116).
- Tiebreak for WHICH tied avatar ranks higher (and thus names the primary combination) is
  unspecified; report identity depends on JSON key order (113: Idea Architect vs Healer;
  114: Artisan vs Groundbreaker vs Creative Director).
- Doc 6.5's tie rules are written for two-way ties only; three-way and six-way ties are
  syntactically outside the rules (114, 117).
- Long-string screen structurally false-positives on uniform genuine responders because items
  Q1–Q20 contain no reverse-keyed item (118).
- No extreme-response-style detection; DI ≥ 30 is one bucket up to 100 (119).
- Screen severity levels (long-string, completion time) undefined → verdicts near the caution
  threshold are implementation-defined (120).
- No score-suppression mechanism in the data layer for invalid profiles (117, 120).

**Top 3 findings:**
1. **Invalid protocols still get named career identities.** Max Chaos (0/3 attention, both
   consistency pairs maximally discordant, 90-second completion, flat profile) is verdict-flagged
   correctly, but the scoring data model happily outputs "The Creative Director"; suppression
   exists only as prose, not as rule — a critical report-safety gap.
2. **The rank-2/3 tiebreak is undefined and career-steering.** With score2 = score3 (Anouk, 113)
   the primary combination — the headline of the entire report — flips between "The Idea
   Architect" and "The Healer" depending on nothing but scale iteration order. Same defect
   scales up in 114 (three candidate identities) and degenerates completely in 117/118.
3. **The 10-point inclusion boundary can never be probed at 11.** The Spectrum transformation's
   value lattice (all scores ≡ 0 or 3 mod 5) makes an 11-point gap mathematically impossible;
   the true operational boundary is inclusive-at-10 vs exclusive-at-12, and the documentation's
   worked boundary is confirmed inclusive (115 → 3 avatars, 116 → 2 avatars).
