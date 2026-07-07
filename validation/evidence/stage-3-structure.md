# Stage 3 — Dimensional Structure & Classification Validity
## The MINDCROUD Career Spectrum v1.0

**Reviewer role:** Quantitative psychologist (factor analysis, SEM, latent class analysis, circumplex models); journal-reviewer standard (JAP / Organizational Research Methods).
**Materials reviewed:** `MINDCROUD-Career-Spectrum.md` (Sections 2, 5–8, 9.2), `data/items.json`, `data/scoring.json`.
**Method:** Theoretical structural analysis based on item content; no respondent data exist (v1.0 is pre-pilot per Section 10.1).

Scale abbreviations: MAK = Maker (R), EXP = Explorer (I), VIS = Visionary (A), MEN = Mentor (S), PIO = Pioneer (E), GRD = Guardian (C). Hexagon order R–I–A–S–E–C; adjacent pairs R-I, I-A, A-S, S-E, E-C, C-R; opposite pairs R-S, I-E, A-C.

---

## A. Predicted Factor Structure Analysis

### A.1 Expected pattern matrix (summarized by dimension)

Predicted primary loadings assume a 6-factor oblique EFA (target-rotated), N ≥ 300, general population. Loadings are content-based estimates; cross-loadings listed only where predicted |λ| > .30 (sign follows the *scored* direction of the item).

**MAK (Realistic) — Q2, Q7, Q14, Q20, Q26, Q32, Q39ʳ, Q46, Q53ʳ, Q60**

| Item | Predicted primary λ | Predicted cross-loading | Rationale |
|---|---|---|---|
| Q2, Q7, Q14, Q20, Q26, Q32 | .60–.75 | — | Clean, prototypical R content (tools, materials, tangible results) |
| Q46 "proud when I fix something" | .40–.50 | — | Near-universal sentiment; ceiling effect will attenuate loading |
| Q53ʳ "full day of physical work drains me" | .45–.55 | — | Physical-stamina confound (age/fitness) adds unique variance; adequate loading but noisier |
| **Q60** "taking devices apart to learn how they work" | .50–.60 | **EXP +.35** | "To learn how they work" is Investigative epistemic motivation verbatim (cf. Q35). Strongest R→I bridge item |
| **Q39ʳ** "rather work with ideas than physical objects" | .40–.55 | **EXP −.30 to −.35; VIS −.30** | "Ideas" pole is I/A content. High-I and high-A respondents endorse the raw item for reasons unrelated to R, deflating their MAK score. Contaminated reversal |

**EXP (Investigative) — Q4, Q9, Q13, Q23, Q28ʳ, Q35, Q42, Q48, Q55ʳ, Q62**

| Item | Predicted primary λ | Predicted cross-loading | Rationale |
|---|---|---|---|
| Q4, Q9, Q13, Q35, Q42, Q48, Q62 | .60–.75 | — | Clean I content (why-questions, deep problems, investigation) |
| **Q23** "careful analysis matters more than speed" | .45–.55 | **GRD +.30; PIO −.30** | "Careful/not fast" is Conventional carefulness + anti-Enterprising pace content |
| **Q28ʳ** "lose interest when task requires long, detailed analysis" | .50–.60 | **GRD +.30** | "Detailed" pole is shared with GRD detail items (Q10, Q36, Q63ʳ); detail-aversion loads on both scales |
| **Q55ʳ** "prefer quick practical answer over deep investigation" | .45–.55 | **MAK −.30 (weak); PIO −.30 (weak)** | "Quick practical" pole is R/E-flavored; borderline cross-loads |

**VIS (Artistic) — Q6, Q11, Q19, Q25, Q31ʳ, Q38, Q45ʳ, Q52, Q59, Q65ʳ**

| Item | Predicted primary λ | Predicted cross-loading | Rationale |
|---|---|---|---|
| Q6, Q11, Q25, Q38, Q52, Q59, Q65ʳ | .55–.75 | — | Clean A content (creation, expression, aesthetics, invention) |
| **Q19** "best work in places with freedom and few fixed rules" | .45–.55 | **GRD −.40** | Pure structure-preference content; mirror image of GRD ENV items Q16/Q57 |
| **Q45ʳ** "work best when every step decided in advance" | .40–.50 | **GRD −.45 to −.50** | Raw item is a near-paraphrase of Q16 (GRD-03 "clear plan and fixed schedule"). Likely to load *primarily* on the structure factor, not on A |
| **Q31ʳ** "prefer tasks with one correct answer over many possible answers" | .40–.50 | **GRD −.30; EXP ±.25 (unstable)** | Ambiguity-tolerance content shared with C (closure) and partly I (convergent problem solving) |

**MEN (Social) — Q1, Q8, Q15, Q21ʳ, Q27, Q34, Q40, Q47, Q54ʳ, Q61**

| Item | Predicted primary λ | Predicted cross-loading | Rationale |
|---|---|---|---|
| Q1, Q8, Q15, Q34, Q47, Q54ʳ, Q61 | .55–.75 | — | Clean S content (teaching, helping, supporting); Q61 may show a mild EXP secondary (~.25, explaining difficult things) — below threshold |
| **Q21ʳ** "best work when I am alone for most of the day" | .40–.50 | **EXP −.30 to −.35** | Solitude preference is characteristic of I work style (cf. Q62 "long time investigating a single question"). Penalizes solitary investigators on MEN for introversion, not lack of care |
| **Q40** "conversations with people give me energy" | .55–.65 | **PIO +.30** | Trait-extraversion energy content shared with E sociability/persuasion; the main S–E bridge item |
| Q27 "workplaces where people cooperate closely" | .50–.60 | (PIO +.25, below threshold) | Team orientation mildly shared with E |

**PIO (Enterprising) — Q5, Q12, Q18, Q24ʳ, Q30, Q37, Q44ʳ, Q51, Q58ʳ, Q64**

| Item | Predicted primary λ | Predicted cross-loading | Rationale |
|---|---|---|---|
| Q5, Q12, Q18, Q24ʳ, Q44ʳ, Q51, Q64 | .55–.75 | — | Clean E content (persuasion, leadership, competition, ownership) |
| **Q30** "environments where things move quickly" | .45–.55 | **GRD −.30; EXP −.25** | Pace content; mirror of Q50/Q58 stability content and antithetical to Q23 |
| **Q58ʳ** "prefer calm, predictable role over competitive one" | .45–.55 | **GRD −.35 to −.40** | "Calm, predictable" pole is verbatim Guardian ENV content (Q50 "stable job... over a job that changes"). Double-barreled reversal: contrasts competitiveness (E) with predictability (C) |
| **Q37** "person who starts a new project" | .55–.65 | (VIS +.25, below threshold) | Initiation/novelty shared mildly with A |

**GRD (Conventional) — Q3, Q10, Q16, Q22, Q29ʳ, Q36, Q43ʳ, Q50, Q57, Q63ʳ**

| Item | Predicted primary λ | Predicted cross-loading | Rationale |
|---|---|---|---|
| Q3, Q10, Q22, Q36, Q63ʳ | .55–.75 | — | Clean C content (organizing, checking, records, completion); Q3 mild EXP secondary (~.25, information systems), below threshold |
| **Q16** "clear plan and a fixed schedule" | .55–.65 | **VIS −.35; PIO −.25** | Core member of the structure cluster; near-duplicate of Q45 (VIS-09) content |
| **Q57** "clear rules and procedures help me feel confident" | .55–.65 | **VIS −.30** | Structure cluster |
| **Q50** "stable job with clear duties over a job that changes" | .50–.60 | **PIO −.35** | Direct content mirror of Q58ʳ (PIO-10) |
| **Q29ʳ** "enjoy jobs where every day is different and unplanned" | .45–.55 | **VIS −.30; PIO −.30** | Variety-seeking pole is A/E content |
| **Q43ʳ** "rather improvise than follow a step-by-step plan" | .45–.55 | **VIS −.35** | Improvisation is A-flavored flexibility content |

### A.2 The "Structure vs. Flexibility" content cluster (principal structural risk)

Eight items across three scales are locally dependent through shared plan/structure/predictability content, forming a candidate bipolar method-content factor orthogonal to the intended six:

- **GRD pole:** Q16, Q50, Q57, Q29ʳ, Q43ʳ (5 of 10 GRD items)
- **VIS pole (reversed):** Q19, Q45ʳ, (Q31ʳ marginal)
- **PIO pole (reversed):** Q58ʳ, (Q30 marginal)

Predicted consequences: (a) correlated residuals Q16–Q45, Q50–Q58, Q19–Q57 in CFA; (b) VIS–GRD inter-scale correlation pushed strongly negative (see A.3), violating the quasi-circumplex expectation that even opposite RIASEC scales correlate near zero-to-mildly-positive under a general interest-elevation factor; (c) at 4–5-factor EFA solutions, VIS and GRD are the pair most likely to merge into a single bipolar "structure" factor.

A second, smaller cluster is **detail/carefulness** bridging EXP and GRD: Q23, Q28ʳ (EXP) with Q10, Q36, Q63ʳ (GRD). This inflates the I–C (alternate, distance-2) correlation and risks an hexagonal order violation (I–C exceeding one or more adjacent correlations).

A third is **sociability/extraversion energy** bridging MEN and PIO: Q40, Q27, Q21ʳ (MEN) with Q5, Q12, Q44ʳ (PIO) — consistent with S–E adjacency but likely to push that correlation toward the top of the adjacent range.

**Full list of items flagged for probable cross-loading (|λ| > .30): Q16, Q19, Q21, Q23, Q28, Q29, Q30, Q31, Q39, Q40, Q43, Q45, Q50, Q55, Q57, Q58, Q60 — 17 of 60 items (28%).** Of these, 10 are reverse-keyed (of 15 total reverse items), so wording-method variance and content cross-loading are confounded — the planned bifactor wording check (Section 9.2) will struggle to separate them.

### A.3 Predicted inter-dimension correlation matrix

Baseline: published RIASEC benchmarks (adjacent r ≈ .30–.50; alternate r ≈ .15–.30; opposite r ≈ .00–.20, rarely negative because of general interest elevation). Adjustments reflect the item-content bridges above.

| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| **MAK** | — | | | | | |
| **EXP** | **.45–.55** ⚠ | — | | | | |
| **VIS** | .05–.15 | .35 | — | | | |
| **MEN** | .00–.10 | .10–.15 † | .30 | — | | |
| **PIO** | .20 | .05–.10 | .25 | **.45–.55** ⚠ | — | |
| **GRD** | .30 | **.35–.40** ‡ | **−.30 to −.40** ‡‡ | .15 | **.05–.15** ‡ | — |

- **Flag r > .70 (poor discriminant validity): none predicted.** All six scales should remain empirically separable.
- **Flag r > .50 (concerning): MAK–EXP and MEN–PIO** may reach .50–.55 at the top of their ranges (⚠). MAK–EXP is inflated by Q60 and Q39ʳ/Q55ʳ; MEN–PIO by the extraversion-energy cluster. Both are *adjacent* pairs, so elevated correlation is theory-consistent — but above ~.55 the top-2 pair selection between them becomes unreliable (see C.3).
- **Circumplex order-violation risks:**
  - ‡ **EXP–GRD (I–C, alternate) predicted .35–.40** — likely to *exceed* the adjacent **PIO–GRD (E–C)** correlation, predicted only **.05–.15** because Q58ʳ/Q30 vs Q50/Q16 content is actively bipolar. Two order violations from one mechanism: an alternate pair above an adjacent pair. This will depress the RTHOR Correspondence Index (Section 9.2 target CI ≥ .70 is at risk specifically on the E–C edge).
  - ‡‡ **VIS–GRD (A–C, opposite) predicted −.30 to −.40** — far more negative than the circumplex norm (~0). Strong bipolarity here distorts the MDS configuration (A and C pushed to extreme opposition, compressing the rest of the hexagon) and partially undermines the Section 8.2 "Curator" (VIS+GRD) combination: the item content makes that profile *structurally* rarer than Holland's model alone implies. The consultant note under combination 12 acknowledges rarity but the instrument itself manufactures additional rarity via item design.
  - † EXP–MEN slightly *depressed* below the alternate norm by Q21ʳ (solitude penalization).

### A.4 Alternative factor structures

1. **Most likely EFA outcome at N = 300–600:** six interpretable factors *plus* instability in the VIS/GRD region. Parallel analysis will likely suggest 5–7 factors:
   - **7-factor solution:** six content factors + a wording/structure doublet factor (Q45, Q58, Q29, Q43 + other reverse items).
   - **5-factor solution:** VIS and GRD merge into one bipolar Structure(−)/Creativity(+) factor.
2. **2-factor (Prediger) solution:** Things–People (MAK vs MEN) and Data–Ideas (GRD/PIO vs VIS/EXP) axes — the most parsimonious defensible reduction, expected to reproduce cleanly and useful as an MDS check.
3. **1-factor + method:** a general interest-elevation/acquiescence factor is expected (all-positive manifold except VIS–GRD); its presence is diagnostic — if VIS–GRD stays strongly negative after controlling elevation, the structure cluster is confirmed as the cause.
4. **Scale-splitting risks (minor):** MEN could split into helping-content (Q8, Q15, Q34, Q47, Q54ʳ) vs sociable-energy (Q40, Q27, Q21ʳ, Q1, Q61) sub-factors; MAK into hands-on craft vs technical-mechanical (Q60, Q7). Neither split is likely to survive rotation at 10 items/scale, but facet-level CFA should test them.
5. **Most parsimonious structure the data would support:** six correlated first-order factors with (a) one wording/structure method factor and (b) 3–5 correlated residual pairs (Q16–Q45, Q50–Q58, Q10–Q23, Q1–Q61, Q28–Q63).

---

## B. Higher-Order Structure Analysis

1. **Proposed higher-order model:** Prediger's two orthogonal dimensions — **Things–People** and **Data–Ideas** — plus a general elevation factor. Mapping: MAK high-Things; MEN high-People; GRD/PIO high-Data (PIO People-leaning); EXP/VIS high-Ideas (EXP Things-leaning). This is the canonical RIASEC higher-order account and the instrument's items map onto it cleanly.
2. **Against established models:** Big Five bridges — PIO/MEN ↔ Extraversion (the shared Q40-type energy content makes this explicit); EXP/VIS ↔ Openness (intellect vs aesthetic aspects respectively); GRD ↔ Conscientiousness (orderliness aspect, over-represented in the ENV/structure items); MEN ↔ Agreeableness. The structure cluster imports more Conscientiousness-orderliness variance than a pure interest measure should carry.
3. **Most parsimonious higher-order explanation:** circular stochastic model (CIRCUM) on the six scales, equivalent to two dimensions + elevation. A hierarchical CFA with two orthogonal higher-order factors will fit approximately as well and is easier to communicate. The instrument is *not* over-factored at the higher-order level; the six-scale reporting layer is the correct interpretive grain for its use case.

---

## C. Classification/Typology System Validity

The typology has three layers: (1) 2–3 Dominant Avatars (Section 6.5 / `scoring.json.dominantAvatarRule`), (2) 15 two-avatar combination profiles (Section 8.2 / `scoring.json.combinations`), (3) third-avatar tiebreaker/flavor procedure (Section 8.3).

### C.1 Algorithm analysis — soundness of the core rule

- **Mathematical approach:** rank-order on linearly transformed sums; appropriate for interest data where within-person profile shape is the signal. The 0–100 transform is strictly monotone with raw scores and collision-free (raw steps map to distinct spectrum values 0, 3, 5, 8, …, 100), so **spectrum-score ties occur exactly when raw ties occur** — the transform itself introduces no tie artifacts. Verified against Section 6.4 worked examples (all correct, including 57.5 → 58 half-up).
- **The 10-point third-avatar threshold ≡ exactly 4 raw points.** Because a raw difference of 4 always maps to a spectrum difference of exactly 10 (4 × 2.5, parity-preserved under half-up rounding) and a raw difference of 5 maps to 12–13, the rule is internally coherent: spectrum gap ≤ 10 ⇔ raw gap ≤ 4, and a spectrum gap of 11 is *unreachable*. Good news: no rounding-dependent boundary flicker. Documentation should state the raw-score equivalent (≤ 4) so implementations on raw scores agree.
- **Threshold calibration vs measurement error:** at target α = .80 and a plausible spectrum-score SD of ~18–22, SEM ≈ 8–10 points, and the SEM of a *difference* between two scale scores ≈ 11–14 points. The 10-point band is therefore slightly *smaller* than one difference-SEM: many respondents whose "true" score2–score3 gap is inside the band will be observed outside it and vice versa. The threshold is defensible but should be described as a heuristic, not a boundary of meaning.

### C.2 Edge-case audit

**E1. Exact ties for rank 1 or rank 2 with 3+ scales (UNRESOLVED).** Section 6.5 handles a *two-way* tie at ranks 1–2 ("both are Dominant"). It is silent on three-way (or higher) ties at rank 1 — e.g., 80/80/80/60/55/50. All three tie for the top; the rule yields three Dominants (fine), but Section 8.1 requires "the top two" as the primary lens and Section 8.2 requires a unique pair lookup ("the higher-scoring Avatar of the pair colors the emphasis"). With three equal scores there is no principled pair, no higher-scoring member, and no documented tiebreaker. **The engine's output is undefined.** Same problem for scores like 90/70/70/...: which 70-scale joins the 90-scale in the pair lookup is arbitrary. Probability is non-trivial: with six scores on a 41-point lattice concentrated in the 40–85 range, at least one tie somewhere in the top three ranks is expected for roughly 15–25% of respondents.

**E2. Tie for rank 3 ("shared third strand") breaks the self-directed use case.** Section 6.5's resolution — "instructing the consultant to resolve the third slot in conversation" — is only executable in use case 1 (consultant-led). Use case 2 (Section 1.1) promises a fully automated premium narrative report; no automated resolution is specified. Either the automated report must render a documented "shared third strand" layout, or a deterministic tiebreaker is needed. Currently unspecified.

**E3. scoring.json omits tie handling entirely (SPEC/IMPLEMENTATION CONTRADICTION).** `dominantAvatarRule` contains only `alwaysDominant`, `thirdDominantIf`, `maxDominant`. None of Section 6.5's tie-breaking provisions, the shared-third-strand rule, or Section 8.3.3's secondary-pair (within-3-points) rule appear in the machine-readable spec. Any implementation built from `scoring.json` alone will resolve ties by accident of sort order — a silent, non-reproducible classification. This is the single most consequential documentation-to-implementation gap found in Stage 3.

**E4. Score1 far above score2 (solo-peak profiles).** E.g., 95/42/40/38/35/30. The top 2 are "always Dominant," so the engine reads a *pair* even when the second avatar is separated from ranks 3–4 by noise-level gaps (2–4 points ≪ difference-SEM). The combination profile — the entire recommendation layer — then hinges on an unreliable rank-2 identity, while the one robust fact (a single dominant interest) has no representation in the output space. There is no "single-avatar" profile, no minimum score2 level, and no score1–score2 gap qualifier. Recommend a dominance-gap flag (e.g., score1 − score2 ≥ 25 → interpret rank 1 as the engine and treat the pair label as provisional; consider reading both 1+2 and 1+3 lookups, generalizing Section 8.3.3).

**E5. Low-elevation profiles.** The rule ranks relative scores only: a respondent scoring 25/20/18/... (all "Low/Minimal Resonance") still receives two Dominant Avatars and an enthusiastic combination narrative ("You are built to…"). No minimum-elevation gate exists. Recommend suppressing or reframing combination narratives when score1 < ~40.

**E6. Flat / all-neutral profiles — three-way internal contradiction.**
- All-neutral responding (all 3s) → every raw = 30 → all six spectrum scores = 50 → a six-way tie. Ranking is undefined; Section 6.5 still mandates top-2 Dominants; the pair is arbitrary.
- Mitigations that *do* fire: Differentiation Index = 0 → flat-profile flag (Section 6.6); attention checks Q17 (needs 4) and Q33 (needs 1) both fail under straight-3 responding → 2 failures → "potentially invalid," blocking the automated report; the 12-item long-string screen also trips. Straight-4 and straight-5 lines similarly fail ≥ 2 attention checks and produce DI ≤ 5 → flat flag. **The validity layer catches pure straight-lining well.**
- But genuine near-flat responders (honest, attentive, DI = 8–14) pass all validity screens and still get Dominant badges plus a combination profile built on 1–3-point rank gaps. Sections are inconsistent about what happens next: Section 7.1 says the heatmap shows the flat-profile note "instead of the badges being emphasized"; Section 6.5 unconditionally assigns 2–3 Dominants; Section 8.1 unconditionally outputs a combination. No rule suppresses or conditions the recommendation engine on the flat flag. Specify precedence: flat flag → badges suppressed → combination narrative replaced by exploration guidance (Section 6.6 text) in both consultant and automated reports.

**E7. The max-3 cap and the rank-4 exclusion.** "The fourth-ranked Avatar is never Dominant, regardless of gaps" makes profiles like 80/75/74/73 classify as exactly three Dominants with the 73 excluded by fiat — a 1-point distinction ≪ SEM. Combined with the hard 10-point band at rank 3, single-item response changes (±1 raw point = 2–3 spectrum points) flip the 2-vs-3 classification and can swap rank-3/rank-4 identity. This is inherent to any hard-threshold rule; the mitigation is reporting proximity (print the score2–score3 and score3–score4 gaps) rather than presenting the Dominant set as categorical truth.

**E8. Combination coverage — COMPLETE.** The 15 profiles in Section 8.2 / `scoring.json.combinations` are exactly C(6,2) = 15; every unordered top-2 pair is covered, all pairs are reachable (scales are independent item sets), lookup is declared order-independent, and the 20 possible three-avatar sets are handled by the 2+1 procedure without needing enumeration. No unreachable or missing cells. The only way the lookup fails is via the undefined-tie cases in E1–E3.

**E9. Threshold pile-up across sections.** Three different closeness thresholds coexist: ≤ 10 (third Dominant, 6.5), ≤ 3 (secondary-pair cross-check, 8.3.3), and < 15 (flat profile, 6.6). They interact without a stated precedence (e.g., a profile can be simultaneously flat-flagged *and* have a secondary-pair instruction). 8.3.3's rule is absent from scoring.json (see E3). Consolidate into one decision tree.

**E10. Differentiation Index blind spot.** DI = max − min is dominated by the *lowest* score: 85/84/83/82/81/40 yields DI = 45 → "well-differentiated," yet the top five are statistically indistinguishable and the pair lookup is arbitrary within them. DI does not measure the differentiation that the classification actually depends on. Add a **Dominance Clarity index** (e.g., score2 − score3, and score1 − score4) alongside DI.

### C.3 Discriminant validity of the 15 types & predicted co-occurrence

Predicted relative frequency / confusability of pair-types follows the predicted correlation matrix (A.3):

- **Over-produced (adjacent, highly correlated scales):** MAK+EXP (Diagnostician), MEN+PIO (Motivator), EXP+GRD (Analyst — inflated beyond its circumplex entitlement by the detail cluster). These will be the modal profiles.
- **Under-produced (item-manufactured bipolarity):** VIS+GRD (Curator) and PIO+GRD (Executive) will be rarer than Holland-model base rates imply, because the structure cluster makes high-GRD respondents score artifactually low on VIS and (via Q58/Q30 vs Q50) on PIO. The Executive is a common real-world profile; its suppression is a substantive concern.
- **Most confusable type pairs** (small rank flips between correlated scales switch the label): Diagnostician ↔ Analyst (EXP shared; MAK vs GRD both correlate with EXP); Motivator ↔ Healer (MEN shared); Strategist ↔ Motivator (PIO shared). Adjacent-scale label swaps land in *related* career-family territory (graceful degradation); the damaging flips are those crossing the People–Things axis (e.g., Diagnostician ↔ Healer via EXP+rank-2 swap), predicted for ~5–10% of retests.

**Ambiguous-classification estimate:** exact ties in the top three ranks (~15–25%) + score2–score3 gaps within one difference-SEM of the 10-point boundary (~25–35%) + near-flat but valid profiles (~5–10%), with overlap, gives **roughly 35–45% of respondents receiving a classification that is boundary-dependent in at least one component** (pair identity, 2-vs-3 count, or third-avatar identity).

### C.4 Classification accuracy & retest stability prediction

- **Clearly dominant (all gaps comfortably outside error): ~55–65%** of respondents.
- **Top-1 avatar stable on 2–4-week retest:** ~80–85% (consistent with scale-level r ≥ .80 target).
- **Exact top-2 *pair* stable:** ~60–70% (two rank identities must both survive; adjacent-scale correlations of .45+ make rank-2 swaps common).
- **Exact Dominant *set* (including 2-vs-3 count and third identity) stable:** ~45–60%. The 2-vs-3 decision is the least stable element: a 1-raw-point shift on any single item of the rank-2 or rank-3 scale crosses the boundary whenever the observed gap is 8–13 points.
- Marketing/report framing should therefore attach confidence language to the *combination label*, not only to scores.

### C.5 Recommended algorithm improvements (prioritized)

1. **Add deterministic, documented tie-breakers to `scoring.json` and Section 6.5** (e.g., tie → higher score on the scale's ACT-facet subtotal; still tied → present as explicit co-equal pair/strand with a fixed, documented display order). Never allow sort-order-dependent output. (Fixes E1–E3.)
2. **Define the automated-report behavior for shared-third-strand and multi-way top ties** so use case 2 is fully specified. (Fixes E2.)
3. **Gate the combination engine on the flat-profile flag and a minimum elevation** (e.g., DI < 15 or score1 < 40 → exploration narrative instead of pair narrative), and state the precedence order of all flags. (Fixes E5, E6, E9.)
4. **Report gap diagnostics:** print score1−score2, score2−score3, score3−score4; add a Dominance Clarity index; flag solo-peak profiles (score1 − score2 ≥ 25) and read 1+2 plus 1+3 lookups when rank 2 and 3 are within 3 points (generalizing 8.3.3). (Fixes E4, E7, E10.)
5. **State the raw-score equivalent of the 10-point rule (raw gap ≤ 4)** to guarantee implementation agreement across raw- and spectrum-score codebases.
6. **Longer-term:** replace hard thresholds with SEM-banded classification (third avatar dominant if gap ≤ 1 difference-SEM once pilot reliabilities are known), and report a probabilistic profile (e.g., bootstrap over item responses) in the technical layer.

---

## D. Measurement Model Specification (for Phase 2 CFA)

1. **Hypothesized model (M1):** six correlated first-order factors, 10 indicators each, simple structure, no cross-loadings; factor correlations free.
2. **Competing models:**
   - **M2:** M1 + orthogonal negative-wording method factor loading on the 15 reverse-keyed items (per Section 9.2).
   - **M3:** M2 + correlated residuals / small cross-loadings for the structure cluster (Q16–Q45, Q50–Q58, Q19–Q57) and the local-dependence pairs (Q10–Q23, Q28–Q63, Q1–Q61 — note Q1 also has a *non-scored* near-duplicate at Q41, harmless to scale CFA but Q1–Q61 content overlap is scored).
   - **M4:** CIRCUM / circular stochastic process model on the six scale scores (the theory-true test), with RTHOR (target CI ≥ .70) and 2-D MDS as adjuncts.
   - **M5 (falsification):** five factors with VIS and GRD merged bipolar — must fit *worse* than M1/M3 for the six-scale claim to survive.
3. **Expected fit:** M1 will miss conventional cutoffs (CFI ~.85–.90, RMSEA ~.06–.08) — normal for RIASEC per Section 9.2's own caveat; M3 should reach CFI ≥ .92; verdict should rest on M4 (CI, circular order) and M3-vs-M5 comparison, not on M1's absolute fit.
4. **Sample size:** N ≥ 300 minimum for the 60-indicator model (≥ 5/item per Section 10.2 is the floor); N ≈ 500 preferred for stable modification-index behavior; ordinal estimators (WLSMV) on 5-point items.
5. **Expected modifications:** exactly the correlated residuals in M3, plus Q60→EXP, Q40→PIO, Q21→EXP(−) cross-loadings. If Q45 or Q58 load primarily off-scale, replace them from the reserve pool (positively keyed replacements exist per Section 9.2's mitigation plan) before Form 1.1.

---

## E. Structural Validity Verdict

1. **Is the dimensional structure defensible? YES, with qualifications.** Six RIASEC-aligned scales, 10 items each, balanced facets and keying, is a sound and appropriately dimensioned design — neither over- nor under-dimensioned for the guidance use case. Roughly 43 of 60 items are structurally clean with predicted simple structure.
2. **Most likely actual factor structure:** six recoverable correlated factors + a negative-wording/structure method factor, with the VIS–GRD region as the weak point (bipolar contamination via 8 structure/flexibility items) and two predicted hexagonal-order violations (EXP–GRD too high at .35–.40; PIO–GRD too low at .05–.15; VIS–GRD anomalously negative at −.30 to −.40). No scale pair approaches r = .70; discriminant validity at the scale level is safe. The RTHOR CI ≥ .70 target is achievable but at risk on the C-edge relations.
3. **How reliable is the classification system?** The 15-combination space is mathematically complete (C(6,2) = 15, all reachable) and the 0–100 transform is tie-neutral and rounding-coherent (10-point rule ≡ 4 raw points, gap of 11 unreachable). However, the Dominant Avatar rule is **under-specified at exactly the boundaries where it will be exercised**: multi-way top ties are undefined for the pair lookup, `scoring.json` carries no tie logic at all (spec–implementation contradiction), the shared-third-strand rule is unimplementable in the automated use case, and flat-profile handling contradicts itself across Sections 6.5, 7.1, and 8.1. An estimated 35–45% of respondents will sit boundary-dependent on some classification component; exact Dominant-set retest stability is projected at only ~45–60% versus ~80–85% for the top avatar alone.
4. **Structural changes with the highest yield:** (a) rewrite or replace the four worst structure-cluster items (Q45, Q58, and one of Q16/Q57; plus Q39) from the reserve pool; (b) codify tie-breaking and flag precedence in `scoring.json`; (c) gate the recommendation engine on flat/low-elevation flags; (d) add gap diagnostics and a Dominance Clarity index to the report.
5. **Overall Stage 3 rating: 3.5 / 5 — Adequate-to-Strong.** The measurement architecture is theory-true and correctly grained; the deductions are for item-manufactured circumplex distortion around the Conventional scale and for a classification algorithm whose written rules do not yet fully determine its output. Both are repairable before pilot without redesigning the blueprint.

*Analysis is predictive (pre-data); all loadings, correlations, and percentages are content-based estimates to be tested against Phase 1–2 empirical results per the Section 10 roadmap.*
