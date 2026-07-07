# Psychometric Validation Audit: The MINDCROUD Career Spectrum

**Audit Date:** 2026-07-07
**Instrument Version:** 1.0 (English master version)
**Methodology:** PhD-level simulated psychometric validation (8-stage pipeline with 120-persona stress test)
**Assessment Domain:** Career / vocational interest (Holland RIASEC)
**Evidence base:** Full stage analyses and all 12 batch result files are preserved in `validation/evidence/`.

---

## A. Executive Summary

**Overall Instrument Quality Rating: 6.5/10 as currently administered — 8/10 achievable with the v1.1 fixes identified in this audit (empirical ceiling ~9/10 after pilot validation).**

The item bank, theoretical grounding, and documentation are genuinely strong — design-grade work at or above commercial standards for a v1.0. The score is pulled down by the delivery layer (a WCAG-blocking, anchor-less response UI that converts the attention-check subsystem into a false-invalidation engine, and a combination-lookup bug that silently drops the career card for 7 of 15 combinations), an under-specified classification algorithm (no tie-breaking, no dominance floor, no invalid-profile suppression), and a validity system that catches careless responders but not strategic ones. Nearly everything wrong is fixable without new data.

**Top 3 Strengths:**
1. **Sound construct architecture on validated theory.** Stage 1 rated construct clarity 4–5/5 across all six scales; blueprint counts reconcile exactly with `items.json`/`scoring.json`; no scale-pair overlap exceeds flag thresholds. Batch testing confirmed it: rank-1 avatar accuracy was near-perfect across 120 personas, criterion anchor profiles behaved coherently at ceiling, and interest was correctly separated from job title (promoted machinist and farm owner both scored low Pioneer).
2. **Demographic robustness of the item layer.** Batch I/J (demographic diversity) scored 17.5/20 with zero failures attributable to gender, disability, non-Western context, or L2 status per se. Scoring is answer-only; no item references gender, physique, or capability.
3. **Honest documentation and layered validity screens.** The provisional-status labeling, non-selection prohibition, and attention + consistency + timing/long-string battery exceed category norms (no major commercial competitor combines them). Batch H proved attention checks and consistency pairs are non-redundant — each catches a failure class the other misses.

**Top 3 Critical Weaknesses:**
1. **The delivery UI defeats the instrument.** Response options render as bare numeric buttons (anchors only in hover tooltips and a scroll-away key); radio inputs are `display:none` (keyboard/screen-reader users cannot respond at all — WCAG 2.1.1/4.1.2 blocker); attention checks instruct by verbal label ("select Strongly disagree") that respondents never see — the defect the field report (a real user's Q33 confusion) already surfaced. Additionally, the combination-card lookup sorts pairs alphabetically against RIASEC-ordered keys: **7 of 15 combinations (MAK+EXP, MAK+GRD, VIS+MEN, VIS+PIO, VIS+GRD, MEN+GRD, PIO+GRD) silently render no career recommendations** (verified in code).
2. **The classification algorithm is under-specified at exactly the boundaries real profiles hit.** No tie-breaking exists in `scoring.json` (ties resolved by dictionary order — exact ties occurred in ~30% of realistic personas); there is no dominance floor (pure-type profiles get two phantom "Dominant" avatars scored 0; a 43-point scale was promoted to Dominant); flat-profile, low-elevation, and invalid profiles still receive fully-formed combination identities ("Max Chaos," failing every validity check, was still named "The Creative Director").
3. **The validity system is asymmetric: it catches carelessness, not strategy or style.** Impression managers (P52, P61, P76), acquiescent responders (P45, P53), and extreme responders (P60, P64, P119) all pass as "Valid." Reverse items arithmetically absorb contradictions instead of flagging them. Three verdict weights (mild consistency pair, long-string severity, flat-profile severity) are undocumented and outcome-determining (P69's coherent ADHD profile flips between "usable" and "discard" on an unwritten rule).

**Readiness Level:** **Ready with Revisions** — deploy for consultant-led guidance only after the v1.1 critical fixes; pilot study required before any self-directed premium report at scale.

**Comparison to Industry Standard:** Structurally a premium implementation of the same blueprint class as the O*NET Interest Profiler Short Form, with better interpretation engineering and delivery polish than the free scientific tools, and vastly better science than MBTI/DISC-genre products. Its evidentiary standing is below all validated comparators until the pilot runs (Stage 4: design-grade ~4.4/5, evidentiary grade ~3.6/5).

---

## B. Psychometric Scorecard

| Psychometric Criterion | Rating (1-5) | Key Evidence | Priority |
|---|---|---|---|
| Construct Validity | 4.0 | Stage 1: clarity 4–5/5 all scales; blueprint verified; NRG facet novel but unproven | Medium |
| Content Validity | 3.5 | Data-pole undersampled (no EXP math, no GRD numeric-clerical items); facet coverage otherwise complete | Medium |
| Item Quality | 3.5 | Stage 2: bank = B+; 18/65 items problematic (3 critical, 7 major); reverse-keyed items carry most defects | High |
| Structural Validity | 3.5 | Stage 3: six factors recoverable; engineered VIS–GRD bipolarity (Q16/Q45, Q50/Q58) distorts the hexagon | High |
| Discriminant Validity (dimensions) | 3.0 | 17/60 items predicted to cross-load; Mentor contaminated by Extraversion (Q21, Q40); Pioneer conflates ownership with temperament | High |
| Discriminant Validity (combinations) | 3.0 | Pair taxonomy sound but 2-D only: 3-way profiles unnameable; rank-2 ties flip the headline archetype | Medium |
| Scoring/Classification Algorithm | 2.5 | No tie rules, no dominance floor, no suppression on invalid; float rounding violates §6.4 (57.5→57); 11-pt gap mathematically unreachable | **Critical** |
| Fairness and Bias | 3.5 | Stage 5 conditional pass; DIF risk concentrated in reverse/NRG items (Q21, Q24, Q18, Q28, Q63, Q53); item layer otherwise demographically robust | High |
| Cross-Cultural Validity | 3.0 | Modesty-norm band compression (P84), collectivist PIO deflation (P96), precarity GRD inflation (P97) — invisible to QA | Medium |
| Criterion-Related Validity Potential | 4.0 | RIASEC congruence evidence base is deep; O*NET crosswalk in place | Low |
| Practical Utility | 4.0 | Combination engine + career families + consultant protocol are the product's strongest layer when they fire | Medium |
| Administration Design | 2.0 | Numeric-only anchors; `display:none` inputs (WCAG blocker); attention checks reference invisible labels; 3.5:1 contrast; hover-only tooltips | **Critical** |
| Report/Output Quality | 4.0 | 30 band narratives + 15 combination profiles well-written, non-deficit framing; but no confidence communication, facet data discarded | Medium |
| Theoretical Foundation | 5.0 | Holland RIASEC: five decades of evidence; correct continuous-profile (non-typological) use | — |

---

## C. Persona Testing Meta-Analysis

**Overall Classification Accuracy: 102.5/120 (85.4%)** — rank-1 avatar accuracy ~98%; nearly all misses occur at rank-2/3 boundaries, tie points, or verdict-weight ambiguities.

### Accuracy by Persona Category

| Category | Personas | Accuracy | Rate |
|---|---|---|---|
| A: Career Stage Spectrum | 1–20 | 16/20 | 80% |
| B: Industry & Function Diversity | 21–40 | 18/20 | 90% |
| C: Psychological Profile Variations | 41–60 | 15/20 | 75% |
| D: Edge Cases & Stress Tests | 61–80 | 18/20 | 90% |
| E: Demographic Diversity | 81–100 | 17.5/20 | 88% |
| F: Classification Stress Tests | 101–120 | 18/20 | 90% |

### Most Commonly Misclassified Persona Types
- **Compressed/low-differentiation profiles** (adolescents, returners, meta-aware correctors, genuine multipotentials): the relative-only third-dominant rule promotes noise or forces dominants from a 5-point band.
- **Response-style cases** (acquiescent, impression-managing, extreme): rank order survives but dominant sets and band labels distort with no flag (Category C's 75% is the floor of the run).
- **State-affected respondents** (burnout, depression, chronic illness): NRG drain items convert mood/health into apparent disinterest — including one case (P88) where illness *manufactured* false differentiation.

### Personas That Broke the Instrument
- **P101–106 (pure types):** all six received two phantom co-dominant avatars scored 0, selected by dictionary order, and a blend archetype whose second component scored zero.
- **P117 (all-neutral):** six-way tie at 50 — dominant selection entirely undefined; naive implementations output "MAK+EXP / The Diagnostician."
- **P120 ("Max Chaos"):** failed every validity gate yet the data layer still computed and named "The Creative Director" — suppression exists only as prose.
- **P88 (ME/CFS archivist):** drain items floored five scales, leaving an illness artifact as a confident, unflagged dominant profile.
- **P71 (scale inverter):** the numeric-only UI made full scale inversion produce a coherent, well-differentiated mirror profile — caught *only* because directional attention checks double as anchor-decoding probes.

### Underperforming Populations
Adolescents (midpoint inflation + work-framing), neurodivergent respondents (Q21/Q28/Q40/Q63 confounds + attention-check false flags under the current UI), chronically ill/burned-out respondents (NRG state confound), collectivist-culture respondents (PIO deflation), economically precarious respondents (GRD inflation), L2/dyslexic readers (reverse-item misreading — both a DIF and a false-flag source).

### 5 Most Revealing Persona Results
1. **P71 — Ernesto (scale inverter):** the anchor-labeling defect isn't cosmetic; it can invert an entire profile undetected except by the very attention checks the UI currently sabotages.
2. **P88 — Charlotte (ME/CFS):** the NRG facet can fabricate differentiation from illness; facet-level reporting is a safety requirement, not a nice-to-have.
3. **P52 — Charles (impression manager):** landed DI exactly 30 ("well-differentiated"), zero flags — the thresholds sit precisely where the hard cases fall.
4. **P115/P116 — Mei-Xin / Óscar (boundary pair):** the score lattice (all values ≡ 0 or 3 mod 5) makes an 11-point gap unreachable — the documented ≤10 rule operationally brackets 10-vs-12.
5. **P69 — Jasmine (ADHD producer):** one undocumented verdict weight (does a mild consistency diff count as a caution?) single-handedly decides whether her coherent profile is delivered or discarded.

### Response Bias Detection
- Impression Manager (inflated): **Not caught** (P52, P61, P76)
- Disengaged Completer (midpoint): **Caught** (P58, P62 — attention + long-string + flat)
- Acquiescent Responder: **Partially caught** (P63 via attention fails; P45/P53 passed clean)
- Extreme Responder (endpoints only): **Not caught** (P60/P64/P119 "Valid"; Q17's "Agree" target even false-flags legitimate extreme style)
- Random Responder: **Caught** (P73 via attention checks; note: periodic patterns defeat the consistency pairs by construction)

---

## D. Critical Issues Requiring Immediate Attention

| Priority | Issue | Evidence | Recommended Fix | Effort | Impact if Fixed |
|---|---|---|---|---|---|
| 1 | Response UI shows numbers only; anchors invisible; radios `display:none` (WCAG blocker); attention checks reference invisible labels | Field report (Q33); Stage 2/5; P71 | Label every option with number + anchor; visually-hidden (not `display:none`) inputs; item text in accessible name; dual-coded check wording ("select 1 – Strongly disagree") | Low | Eliminates false invalidations; restores accessibility; unblocks piloting |
| 2 | Combination lookup fails for 7/15 pairs (alphabetical sort vs RIASEC-ordered keys) | Verified in `spectrum-scoring-tool.html`; Batch K | Normalize pair key to canonical RIASEC order before lookup | Trivial | Restores career recommendations for ~half of all possible results |
| 3 | No tie-breaking rules; no dominance floor; no invalid/flat suppression in the data layer | Batches A–L convergent; P101–106, P117, P120 | Deterministic tie cascade, minimum-score gates, explicit precedence (validity → flat → combination), all encoded in `scoring.json` | Medium | Classification becomes deterministic and safe across implementations |
| 4 | Rounding spec silently violated by float implementations (57.5→57; banker's rounding) | Batches A, B, E, J (14 boundary hits in J alone) | Mandate integer arithmetic: spectrum = ((raw−10)×5+1)÷2 truncated, or equivalent exact half-up | Trivial | 1-point errors at dominance boundaries eliminated |
| 5 | Undocumented verdict weights (mild pair, long-string severity, flat severity) | P66, P69, P80 | Specify every signal's weight and the combination formula in `scoring.json` | Low | Verdicts become deterministic; stops discarding usable profiles |
| 6 | Engineered VIS–GRD bipolarity + reverse-item cross-loading cluster | Stages 1–3; Q16/Q45, Q50/Q58, Q19/Q29/Q31/Q43/Q57 | De-mirror one side of each pair; rewrite Q45, Q58 with construct-own content | Medium | Protects factor structure and the Curator profile |
| 7 | Mentor scale contaminated by Extraversion/introversion (Q21, Q40) | Stages 1, 2, 5; P41, P42 | Replace with helping-domain content | Medium | Removes worst DIF item (Q21) and cross-loading |
| 8 | No detection of strategic/style bias (acquiescence, elevation, extreme, single-scale faking) | Batch E/F/G/H | Add computed indices from existing responses: acquiescence, elevation, extreme-response, intra-scale coherence, modal-proportion long-string | Low | Closes the QA asymmetry at zero respondent cost |
| 9 | NRG facet state confound (mood/illness → false scores, even false differentiation) | P75, P88; Stage 1 | Facet-level subscores in output + report caveat + retest advice when NRG diverges from ACT/ENV | Low–Med | Prevents harmful misreads for vulnerable users |
| 10 | DIF-risk item wording (Q24, Q18, Q28, Q63, Q53, Q13, Q34, Q51) | Stage 5; Batches I/J | Rewrites per Section E table | Medium | Reduces predicted adverse impact pre-pilot |

---

## E. Improvement Roadmap

### Phase 1: Critical Fixes (implemented in v1.1 — see `CHANGELOG` section of master doc)

**Item Revisions (Top 20 Priority Items):**

| Item | Issue | Revision direction |
|---|---|---|
| Q17 (ACHK-1) | References invisible label; "Agree" target false-flags extreme responders | "To show you are reading each statement, select answer 4 ('Agree')" + UI anchors |
| Q33 (ACHK-2) | References invisible label | "For this statement, select answer 1 ('Strongly disagree')" |
| Q49 (ACHK-3) | "Neutral" least guessable from digits; trivially passed by 3-straight-liners | "This is a quality check. Select the middle answer, 3 ('Neutral')" |
| Q21 (MEN-09ʳ) | Introversion ≠ low Social; worst DIF item | Replace: helping-responsibility content ("I prefer work where I am not responsible for other people's progress") |
| Q40 (MEN-06) | Pure Extraversion marker | Replace: helping-energy content ("Helping someone solve a personal problem gives me energy") |
| Q45 (VIS-09ʳ) | Near-mirror of Q16 (GRD) on another scale | Rewrite: creative-freedom-own content ("I feel limited when I cannot bring my own ideas into my work" reversed appropriately) |
| Q58 (PIO-10ʳ) | Imports Guardian content ("calm, predictable") | Rewrite: competition-own content |
| Q28 (EXP-09ʳ) | ADHD attention confound | Interest framing: "Digging into the details of a problem does not appeal to me" |
| Q63 (GRD-10ʳ) | "Paperwork" idiom + dyslexia/ADHD + generational | "Keeping detailed records all day would drain my energy" |
| Q24 (PIO-08ʳ) | Power-distance/modesty DIF | "I am more comfortable supporting a plan than deciding it" |
| Q18 (PIO-03) | Competition valence non-equivalent across cultures | "Working toward a clear goal against a challenge brings out my best effort" |
| Q53 (MAK-10ʳ) | Stamina/age/disability confound | "Spending the whole day working with my hands would not suit me" |
| Q39 (MAK-09ʳ) | Imports I/A content ("ideas") | "Working with physical objects appeals to me less than other kinds of work" |
| Q65 (VIS-10ʳ) | Direct antonym of Q59 (predicted r > .85) + "from nothing" borderline idiom | Replace with distinct content ("I avoid tasks that have no template to follow") |
| Q31 (VIS-08ʳ) | Structure-axis cross-loader | Keep flagged for pilot item analysis |
| Q29 (GRD-08ʳ) | Structure-axis cross-loader | Keep flagged for pilot item analysis |
| Q43 (GRD-09ʳ) | Structure-axis cross-loader | Keep flagged for pilot item analysis |
| Q13 (EXP-03) | STEM/reading framing (SES + humanities DIF) | "I enjoy learning how and why things work" variant |
| Q34 (MEN-05) | Hearing-assumptive + FK 15.4 reading level | "I enjoy giving my full attention when someone shares a personal difficulty" |
| Q51 (PIO-06) | White-collar referent opacity | "Reaching an important goal I worked hard for gives me a strong feeling of excitement" |

**Structural Changes:** de-mirror the VIS–GRD axis; add facet subscores to output; normalize combination keys; add 2 reverse-keyed items among Q1–Q20 in the v1.2 pool (long-string screen currently blind there).

**Scoring Algorithm Modifications:** see Section F.

**Missing Validity Controls:** acquiescence index, elevation index, extreme-response index, intra-scale coherence check, modal-proportion long-string — all computable from existing 65 responses.

**Documentation Additions:** explicit tie rules; verdict weight table; flat/low-elevation precedence; state-confound (NRG) caveat; motivated-distortion limitation ("detects inattention, not faking"); student-context instruction for the 17 work-framed items.

### Phase 2: Pilot Validation Study Design

- **Sample:** N = 300 minimum (100 students 16–20, 100 working adults 21–45, 100 adults 45+; ≥40% non-university-educated; oversample trades and care professions).
- **Analyses:** CFA + ESEM (6-factor), randomization test of hypothesized circumplex order (RTHOR) and MDS, DIF (gender, age band, L2 status) via ordinal logistic/IRT, item-level distractor and cross-loading review of the 17 flagged items, α and ω per scale, 4-week test-retest (n ≥ 75) including **Dominant-set stability** (projected 45–60% pre-fix; target ≥70% post-fix), convergent validity vs. O*NET Interest Profiler (free), social-desirability correlation (Marlowe-Crowne short).
- **Minimum acceptable:** CFI > .90, RMSEA < .08, SRMR < .08; α ≥ .80/scale; retest r ≥ .80/scale; no large DIF (|ΔR²| > .035 or Δ > 1.0 logits); RTHOR CI ≥ .70.
- **Timeline:** ~10–14 weeks including recruitment.

### Phase 3: Norm Development
N ≥ 1,000 stratified by age, gender, education; replace the arbitrary 81/61/41/21 Resonance cutoffs with percentile-anchored bands; document gender-norms policy (combined norms with transparency notes recommended for guidance use); modesty/response-style calibration for cross-cultural deployments (start EN → RO per company roadmap, full ITC double-translation protocol).

### Phase 4: Publication & Deployment Readiness
Technical manual (include this audit as design-stage evidence); consultant training + debrief guide; ethical guidelines (non-selection prohibition, ND-specific and state-confound disclaimers); annual item review; re-norm at 3 years or 10k administrations.

---

## F. Scoring Algorithm Revision Proposal (implemented in v1.1)

### Dimension/Scale Scoring
- **Exact arithmetic mandate:** Spectrum = (raw − 10) × 2.5; when the result ends in .5, round half-up. Reference integer form: `spectrum = ((raw - 10) * 5 + 1) // 2`. Float `round()` and `floor(x+0.5)` are both non-conforming (banker's rounding; IEEE .5 representation).
- **Facet subscores:** report ACT / ENV / NRG means per scale. Flag any scale where |NRG − ACT| ≥ 1.5 scale points ("interest–energy divergence": possible burnout/state effect; retest advice).

### Classification Algorithm
1. Rank the six Spectrum Scores.
2. **Dominance gates:** rank-1 is always Dominant. Rank-2 is Dominant if score₂ ≥ 40; otherwise report a **Solo Peak** profile (single-avatar narrative + exploration guidance). Rank-3 is Dominant if score₂ − score₃ ≤ 10 **and** score₃ ≥ 50.
3. **Solo-peak flag:** if score₁ − score₂ ≥ 25, report the combination but lead with the rank-1 narrative.
4. **Tie-breaking (deterministic cascade):** (a) higher raw scale score (before rounding); (b) higher ACT-facet sum (activity preference is the most interest-central facet); (c) if still tied, present both candidate combinations explicitly as "twin readings" — never silently pick one.
5. **Combination lookup:** normalize the pair to canonical RIASEC order (MAK, EXP, VIS, MEN, PIO, GRD) before lookup.
6. **Precedence (hard rule):** validity verdict → elevation/flat gates → combination. *Potentially invalid* profiles: suppress dominants, combination, and career families entirely. *Flat* (DI < 15): breadth narrative instead of combination. *Low elevation* (score₁ < 50): exploration narrative, combination presented as tentative.

### Confidence Level Calculation
Report classification confidence from the score₂ − score₃ margin (and score₁ − score₂ for the pair): margin ≥ 15 = High, 8–14 = Moderate, < 8 = Low ("adjacent avatars are statistically interchangeable — explore both readings"). Grounded in the observed lattice (2.5-point steps) and projected SEM ≈ 5 spectrum points.

### Quality Assurance Protocols (all computable from existing responses)
| Index | Formula | Flag |
|---|---|---|
| Attention | Q17=4, Q33=1, Q49=3 exact | 1 fail = caution; ≥2 = invalid |
| Consistency pairs | \|Q1−Q41\|, \|Q10−Q56\| | diff 3–4 on any pair = invalid signal; **one** diff-2 alone = note only; **both** pairs diff ≥2 = caution |
| Long-string | max identical run ≥ 12 **or** modal response ≥ 80% of items | caution |
| Completion time | < 180 s | caution |
| Acquiescence | mean raw response across all 60 scored items ≥ 4.3 | caution ("agreement style") |
| Elevation | all six spectrum ≥ 70 with DI < 20 | caution ("uniformly high") |
| Extreme style | endpoints (1/5) ≥ 85% of responses | style note (not a validity signal) |
| Intra-scale coherence | on ≥ 3 scales, \|mean(positive coded) − mean(reverse coded)\| ≥ 2 | caution ("possible misreading of reversed statements") |
| Verdict | 0 signals = Valid; exactly 1 caution = Interpret with caution; any invalid signal or ≥2 cautions = Potentially invalid | — |

### Bias Detection Limits (documented, not solved)
Targeted single-scale faking remains undetectable by design (P76) — reinforce the non-selection prohibition. Collectivist PIO deflation and precarity GRD inflation are score-invisible; handled via consultant guidance and report language.

---

## G. Comparative Positioning Recommendation

**Recommended market position:** premium-experience, scientifically honest career *guidance* instrument — "built like a test, reads like a story, currently in active validation." Direct value vs. free O*NET IP is interpretation quality, the combination engine, and consultant workflow — not (yet) measurement superiority.

**Claims it can legitimately make:** grounded in Holland's RIASEC (most-validated career framework); professionally constructed to AERA/APA/NCME-informed design standards; built-in response-quality screening; transparent scoring; not a personality typing product.

**Claims it must NOT make until pilot data exist:** "scientifically validated/proven," any reliability or accuracy figure, predictive claims ("will find the career you'll love"), equivalence to SII/SDS, any selection/hiring use.

**Recommended language:** "The MINDCROUD Career Spectrum applies the most extensively researched model in career psychology through six Career Avatars. Your results are a structured, well-lit starting point for career exploration — refined continuously as our validation research grows."

---

## H. Final Verdict

The MINDCROUD Career Spectrum v1.0 is an unusually well-built first version of a vocational interest inventory. Its foundations are the right ones: Holland's RIASEC model, used correctly as a continuous six-score profile rather than a type label; a verified blueprint with facet-balanced scales; original items written to translation-robust, behavioral standards; and documentation whose honesty about validation status exceeds the norm of its commercial category. Simulated stress-testing with 120 personas returned 85.4% classification accuracy overall and near-perfect rank-1 accuracy — for a design-stage instrument with zero empirical data, that is a strong result, and it converges with the expert-stage judgment that the measurement core is sound.

The audit's central finding, however, is that the instrument's quality is currently *inverted across its layers*: the deepest layer (theory, blueprint, items) is the strongest, and each layer above it degrades the signal. The interpretation layer under-specifies exactly the decisions that determine what a client is told — ties, dominance floors, flat and invalid precedence — leaving the headline career narrative to be decided, in a meaningful fraction of cases, by the accidental ordering of keys in a JSON file. The delivery layer then actively damages measurement: an anchor-less numeric response interface that confused real users, disabled keyboard and screen-reader access, converted the attention-check subsystem into a generator of false invalidity flags, and — through a one-line lookup defect — silently withheld career recommendations from seven of the fifteen possible profile combinations. None of these are psychometric failures; all of them are engineering failures with psychometric consequences, and all are fixable immediately, which is why this audit pairs a 6.5/10 current rating with an 8/10 post-revision projection.

The genuinely psychometric findings cluster in three places. First, a structure-versus-flexibility content axis was inadvertently written into multiple scales, manufacturing the Artistic–Conventional opposition in item content rather than letting the data produce it; the cross-loading risk concentrates in reverse-keyed items, which also carry most of the fairness risk (introversion contaminating the Mentor scale, attention and stamina confounds, cultural valence on the Pioneer scale). Second, the validity system is asymmetric: it reliably catches careless responding — the attention checks and consistency pairs proved non-redundant, each catching failures the other misses — but passes strategic and stylistic distortion untouched, and its verdict arithmetic contains undocumented weights that flip real profiles between "usable" and "discarded." Third, the novel energy/drain facet, the instrument's most distinctive idea, is also its least protected: mood and illness load it directly, in one simulated case manufacturing confident false differentiation rather than the flat profile that honesty would have produced. Facet-level reporting converts this liability back into the differentiator it was designed to be.

Relative to established instruments, the Spectrum currently occupies an honorable but unproven position: structurally a peer of the O*NET Interest Profiler Short Form, with a markedly better interpretation and delivery concept, and with none of the categorical-typology weaknesses of the MBTI/DISC genre it will inevitably be compared to commercially. What separates it from its validated peers is evidence, and only evidence: every scientific claim it might make is currently a promissory note. The v1.1 revisions specified in this audit — item substitutions and rewrites for eighteen flagged items, a fully deterministic and gated classification algorithm, a symmetric validity battery computable from existing responses, and a delivery layer that shows respondents the words their answers mean — clear the path to a pilot study that the design deserves. A 300-person pilot with CFA, circumplex, DIF, and retest analyses, followed by norming that replaces the current round-number bands, would give MINDCROUD a defensible instrument of genuinely competitive quality.

**Recommendation:** revise (v1.1), deploy for consultant-led guidance with the documented caveats, pilot within one release cycle, and do not permit selection use under any circumstances. The gap between this instrument and a credible commercial product is measured in weeks of engineering and one honest study — not in redesign.

---

## Appendix: Methodology Notes

This audit combined expert-level theoretical analysis (Stages 1–5) with stress testing across 120 simulated personas in 12 parallel batches (Stages 6–7), executing the documented scoring algorithm in code against every simulated protocol. Stage analyses and complete batch results (response sheets, computed scores, per-persona findings) are in `validation/evidence/`.

**Limitations:** No real participant data was collected; reliability/DIF/factor results are predictions, not measurements; simulated respondents cannot fully replicate human behavior. This audit is a rigorous preliminary analysis that prioritizes empirical validation — it is not a substitute for it.

**Citation:** The MINDCROUD Career Spectrum Simulated Psychometric Validation Audit, 2026-07-07, 8-stage / 120-persona simulated protocol.
