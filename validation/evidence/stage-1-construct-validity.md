# Stage 1 — Construct & Content Validity Analysis
## The MINDCROUD Career Spectrum, Version 1.0 (English master)

**Reviewer role:** PhD psychometrician (I-O Psychology), construct validity / factor analysis / assessment methodology specialization.
**Materials reviewed:** Full master document (`MINDCROUD-Career-Spectrum.md`, Sections 1–11 + Appendix), `data/items.json` (65 administered items), `data/scoring.json`.
**Standards applied:** AERA/APA/NCME *Standards for Educational and Psychological Testing* (2014), esp. Standards 1.1–1.25 (validity), 4.1–4.12 (design/development); SIOP *Principles* (5th ed.) as secondary reference; EFPA Test Review Model criteria referenced by the instrument itself.
**Rating scale:** 1 = Critical Deficiency, 2 = Significant Concern, 3 = Adequate, 4 = Strong, 5 = Exemplary.
**Status caveat:** All judgments here are design-stage (a priori) evaluations. The instrument correctly self-declares zero empirical evidence (Section 10.1); nothing below substitutes for the pilot and structural studies in its own roadmap.

---

## A. Construct Definition Clarity

### A.1 Dimension-by-dimension evaluation

Each Avatar is defined in three places that were checked for internal consistency: the construct table (§1.2), the blueprint facet structure (§2.1–2.2), and the 30 band narratives (§7.3). Definitions are consistent across all three layers for all six scales — a discipline many commercial instruments fail.

| # | Dimension | Definition precision | Conceptual discriminability | Literature mapping | Clarity rating (1–5) |
|---|---|---|---|---|---|
| 1 | **The Maker (R)** | Precise: tools/machines/materials, tangible results; drains specified (ambiguity, politics, pure theory) | High — "Things" pole of Prediger's axis; least confusable scale | Holland Realistic; Prediger Things; ACT Map region 6 | **5** |
| 2 | **The Explorer (I)** | Precise: analysis, research, discovery, depth-over-speed | High conceptually; operationally shares "solitary/deep work" space with low-Social (see Q21) | Holland Investigative; Openness-Intellect; need for cognition / TIE | **5** |
| 3 | **The Visionary (A)** | Clear core (originality, expression, aesthetics) but the definition leans heavily on *absence of structure* ("drained by rigid rules and standardization") | Moderate — the anti-structure component is defined as the mirror image of Guardian rather than as positive Artistic content (see A.3) | Holland Artistic; Openness-Aesthetics; creative self-concept | **4** |
| 4 | **The Mentor (S)** | Clear: teaching, helping, developing people | Moderate–High — item-level operationalization drifts into general sociability/extraversion (Q40) and solitary-work aversion (Q21r), which are temperament, not vocational interest | Holland Social; Extraversion + Agreeableness compound; empathic concern (IRI); SCCT social self-efficacy | **4** |
| 5 | **The Pioneer (E)** | Clear but deliberately heterogeneous: leadership + persuasion + competition + venture-building — faithful to Holland's E, which is itself the most heterogeneous RIASEC domain | Moderate–High; "starting new projects" (Q37) sits near Visionary origination; "The Pioneer/Visionary" brand names themselves overlap semantically more than the constructs do | Holland Enterprising; Extraversion-Assertiveness; proactive personality; entrepreneurial intent | **4** |
| 6 | **The Guardian (C)** | Clear: order, accuracy, systems, stability | Moderate — operationalized almost entirely as *structure/predictability preference*; classic Conventional content (numeric-clerical, data processing, compliance with hierarchy) is thin, and the structure-preference core is the engineered opposite of Visionary | Holland Conventional; Conscientiousness-Orderliness; routine-seeking | **4** |

**Section A mean: 4.33 — Strong.**

### A.2 Mapping to established constructs

The instrument makes no pretense of construct novelty: it is an explicit re-operationalization of Holland's RIASEC (§1.2) with a three-facet blueprint (ACT/ENV/NRG). This is a *strength* under Standard 1.1 — the intended interpretation is anchored to five decades of RIASEC evidence, and the differentiation claim is confined to reporting UX (Spectrum Heatmap, blend-based interpretation) rather than to new constructs. The ACT and ENV facets correspond directly to Holland's activities/competencies and environment-typology components. The **NRG (energy/drain) facet is the one genuinely novel element**: "what energizes vs. depletes" is closer to work-engagement/vigor language (temperament- and affect-laden) than to classic interest content. It is defensible as an interest indicator but is the facet most likely to import Big Five variance (e.g., Q40, Q18) and should be watched in the pilot's cross-loading analysis.

### A.3 Construct redundancy screen (flag threshold: >60% conceptual overlap)

Estimated conceptual overlap between all 15 scale pairs, judged from definitions AND item operationalizations:

| Pair | Hexagon relation | Estimated conceptual overlap | Flag? |
|---|---|---|---|
| MAK–EXP | Adjacent | ~30% (things + investigation share "technical" space; Q60 is deliberately R-I blended) | No |
| MAK–VIS | Alternate | ~15% (craft/making) | No |
| MAK–MEN | Opposite | <10% | No |
| MAK–PIO | Alternate | <10% | No |
| MAK–GRD | Adjacent | ~15% | No |
| EXP–VIS | Adjacent | ~25% (ideas, originality of thought) | No |
| EXP–MEN | Alternate | ~10% (teaching/explaining: Q61 vs. EXP content) | No |
| EXP–PIO | Alternate | <10% | No |
| EXP–GRD | Alternate | ~20% (analysis + precision) | No |
| VIS–MEN | Adjacent | ~15% | No |
| VIS–PIO | Alternate | ~25% (origination/novelty: Q37 vs. Q6/Q38) | No |
| **VIS–GRD** | Opposite | **~45–55% (negative/bipolar)** — see below | **Watch (below threshold, but structural)** |
| MEN–PIO | Adjacent | ~30% (people-orientation, extraversion; both draw on sociability) | No |
| MEN–GRD | Adjacent | ~10% | No |
| PIO–GRD | Adjacent | ~20% (Q58r imports "calm, predictable" — Guardian language — into Pioneer) | No |

**No pair exceeds the 60% flag threshold.** However, VIS–GRD warrants a formal watch flag of a different kind: the two scales are not redundant (they measure *opposite* content) but a **structure-vs-freedom bipolar axis has been written into both scales' items**, which will manufacture a negative manifold beyond what the hexagon predicts (Holland opposites correlate near zero to mildly positive in real data, not strongly negatively — Tracey & Rounds, 1993). Items on this single axis: Q16 (GRD+ "clear plan and a fixed schedule"), Q45r (VIS− "every step decided in advance"), Q19 (VIS+ "freedom and few fixed rules"), Q29r (GRD− "every day different and unplanned"), Q43r (GRD− "improvise rather than follow a step-by-step plan"), Q31r (VIS− "one correct answer over many possible answers"), Q50 (GRD+ "stable job with clear duties"). Q16 and Q45 are near-mirror statements scored on *different* scales. Consequences if unaddressed: (a) artifactually strong negative VIS–GRD correlation that will distort the MDS/RTHOR circumplex tests the instrument itself plans; (b) cross-loadings that depress the six-factor solution; (c) the "Curator" (VIS+GRD) combination — which §8.2 correctly notes is rare — becomes rarer still for measurement rather than substantive reasons.

**Section A rating: 4 (Strong).** Definitions are clear, layered consistently, and honestly mapped to the literature; the deduction reflects the engineered VIS–GRD bipolarity and temperament leakage into MEN and the NRG facet.

---

## B. Content Validity Assessment

### B.1 Content coverage matrix (facet × Avatar)

Counts verified item-by-item against `items.json`; the blueprint table (§2.2) is **accurate** — every claimed count reconciles.

| Facet | MAK (R) | EXP (I) | VIS (A) | MEN (S) | PIO (E) | GRD (C) | Row total |
|---|---|---|---|---|---|---|---|
| **ACT** (activity) | 5 (Q2,7,14,39r,60) | 5 (Q4,9,13,28r,42) | 4 (Q6,11,31r,38) | 4 (Q1,8,34,61) | 4 (Q5,12,24r,37) | 4 (Q3,10,36,43r) | 26 |
| **ENV** (environment) | **2** (Q20,26) | **2** (Q23,62) | 3 (Q19,45r,52) | 3 (Q21r,27,47) | 3 (Q30,58r,64) | 3 (Q16,29r,50) | 16 |
| **NRG** (energy/drain) | 3 (Q32,46,53r) | 3 (Q35,48,55r) | 3 (Q25,59,65r) | 3 (Q15,40,54r) | 3 (Q18,44r,51) | 3 (Q22,57,63r) | 18 |
| **Total** | 10 | 10 | 10 | 10 | 10 | 10 | 60 |
| Keying (+/−) | 8/2 | 8/2 | 7/3 | 8/2 | 7/3 | 7/3 | 45/15 |

Structural observations:
- Distribution is balanced (10 per scale) and matches the ≥5-items-per-scale reliability benchmark comfortably.
- **ENV is thin for MAK and EXP (2 items each).** No facet subscores are reported, so this is not fatal, but it means the "environment preference" content claim for those two scales rests on two items apiece, and one of them (Q26, "see the physical results at the end of the day") is arguably an outcome-preference (ACT/NRG-like) rather than an environment item. Same question for Q62 (EXP ENV — "work that lets me spend a long time investigating" reads as activity pacing, not setting).
- Keying: 75/25 positive/negative overall, antonym-based (never "not"-negation) — exemplary design choice, with a documented replacement plan for misbehaving negative items (§9.2). All first-quarter items positively keyed per sequencing rules — verified true (first reverse item is Q21).

### B.2 Domain sampling gaps (content underrepresentation)

Judged against the canonical content domains of each RIASEC type (Holland, 1997; O*NET IP content; Armstrong et al. 2008 markers):

| Scale | Missing / underrepresented facets | Severity |
|---|---|---|
| MAK (R) | Nature/outdoors/animals reduced to one word inside Q20; no physical-athletic content; no operating vehicles | Minor–Moderate (classic R content is broader than "workshop + repair + build") |
| **EXP (I)** | **No mathematics/quantitative/data content whatsoever** — no item mentions numbers, data, math, or statistics. Scientific-curiosity and deep-analysis facets are well covered; the math facet of Investigative is entirely absent | **Moderate** — math interest is a core I marker in every major RIASEC inventory and drives the Ideas/Data axis placement |
| VIS (A) | Performing arts (acting, performing, playing music for others) absent; coverage is creation/origination-heavy, aesthetics-adequate (Q25, Q52) | Minor |
| MEN (S) | Community service/volunteering and care for the vulnerable absent; teaching + counseling + supporting well covered | Minor |
| PIO (E) | Explicit selling of products/services absent (Q51 "winning an important agreement" is the closest); no risk-tolerance content | Minor–Moderate |
| **GRD (C)** | **Numeric-clerical facet absent** — no working-with-numbers, budgets, calculations, or financial-records content. Coverage is order/detail/procedure-heavy | **Moderate** — same issue as EXP: the "Data" pole of Prediger's axis is undersampled instrument-wide |

**Instrument-level consequence:** because *both* the I-math and C-numeric facets are missing, the **Data pole of the Things/People–Data/Ideas circumplex is systematically undersampled**. This may compress the hexagon on one axis in the planned MDS analysis and weaken convergence with O*NET IP I and C scales (both of which carry math/data items). Recommended: swap in reserve-pool items covering math/data for EXP-and/or-GRD in Form 1.1.

### B.3 Item–dimension misalignment screen (conceptual cross-loading candidates)

| Q# | Scale (keying) | Text (abbrev.) | Likely secondary loading | Concern level |
|---|---|---|---|---|
| Q45r | VIS (−) | "every step decided in advance" | GRD (+, near-mirror of Q16) | **High** |
| Q43r | GRD (−) | "rather improvise than follow a plan" | VIS (+) — improvisation is Artistic content | **High** |
| Q29r | GRD (−) | "every day different and unplanned" | VIS/PIO (+, variety-seeking) | Moderate–High |
| Q58r | PIO (−) | "calm, predictable role over a competitive one" | GRD (+) — "calm, predictable" is Guardian language; also compound (calm + predictable vs. competitive) | Moderate–High |
| Q31r | VIS (−) | "one correct answer over many possible answers" | GRD (+) and EXP (ambiguous: scientists often prefer determinate answers) | Moderate |
| Q21r | MEN (−) | "work best when I am alone most of the day" | Introversion marker; negatively contaminates MEN with EXP-typical solitary preference — Explorers get penalized on Mentor for a preference that is not low-Social | Moderate |
| Q40 | MEN (+) | "Conversations with people give me energy" | Pure Extraversion-sociability; no helping/serving content | Moderate |
| Q39r | MAK (−) | "rather work with ideas than with physical objects" | EXP/VIS (+) — "ideas" is their shared territory | Moderate (defensible as Things–Ideas anchor, but contaminates) |
| Q55r | EXP (−) | "quick practical answer over a deep investigation" | MAK (+, "practical") | Moderate |
| Q3 | GRD (+) | "organizing information into clear systems" | EXP (information work) | Low |
| Q37 | PIO (+) | "being the person who starts a new project" | VIS (origination) | Low |
| Q61 | MEN (+) | "explaining difficult things" | EXP (subject-matter mastery implied) | Low |
| Q60 | MAK (+) | "taking devices apart to learn how they work" | EXP ("to learn how they work" is investigative motive) | Low (acceptable R–I bridge) |

Pattern worth naming: **the cross-loading risk is concentrated in the reverse-keyed items** (7 of the 9 Moderate+ flags are reverse-keyed). This means the planned wording-factor check (§9.2) will be confounded: a "negative-wording method factor" and a "cross-loading content factor" will be partially the same items. The reserve-pool replacement plan is the right remedy, but replacements should fix *content*, not just keying.

### B.4 Domains critical to purpose that are absent

- **Prestige/complexity dimension** (the vertical dimension in Tracey's spherical model): absent, acceptable for a six-scale RIASEC instrument, but consultants recommending across career families from trades to professions should know the instrument is silent on it. Documented nowhere — worth a consultant-guide note.
- **Basic-interest granularity**: recommendations map pairs → O*NET job families; the instrument correctly delegates occupation-level drill-down to O*NET rather than overclaiming. Adequate.
- Quality/validity content (attention checks Q17/Q33/Q49, consistency pairs Q41/Q56) is properly excluded from all scale scores — verified in `scoring.json` (`scales` arrays contain none of 17, 33, 41, 49, 56).

**Section B rating: 4 (Strong).** Balanced blueprint, verified counts, disciplined item writing; deductions for the missing math/data content (EXP, GRD), 2-item ENV cells (MAK, EXP), and the cluster of cross-loading reverse-keyed items.

---

## C. Face Validity and Social Desirability

### C.1 Transparency and fakability by dimension

Vocational-interest items are inherently transparent — this is normal and, for a guidance instrument, mostly benign (respondents have little incentive to fake against their own career exploration). Ratings reflect vulnerability *if* a respondent wanted to steer results:

| Dimension | Faking vulnerability | Rationale |
|---|---|---|
| MAK (R) | **Low** | Hands-on preference carries little differential desirability; items are neutral in valence |
| EXP (I) | **Medium** | Intellectual curiosity is socially desirable; Q28r requires admitting one "loses interest" in analysis — mild self-derogation barrier |
| VIS (A) | **Medium** | "Creativity" is culturally prized; Q38/Q59 easy to inflate; Q65r requires admitting creation drains you |
| MEN (S) | **Medium–High** | Helping/empathy items (Q8, Q34, Q15) are the most SD-loaded content in the form; Q54r ("helping people would exhaust me") is hard to endorse honestly |
| PIO (E) | **Medium–High** | Leadership/ambition desirable in career contexts; Q24r ("prefer to follow a leader") carries status cost to endorse |
| GRD (C) | **Low–Medium** | "Reliable/organized" mildly desirable; several items neutral or even mildly counter-desirable (Q63r lets people freely admit paperwork drains them) |

### C.2 Most SD-susceptible items

Q8, Q34, Q15, Q40 (Mentor — communal desirability); Q9, Q42, Q48 (Explorer — competence desirability); Q12, Q37, Q64 (Pioneer — agency desirability); reverse-keyed confessions Q24r, Q54r, Q28r. None reaches the "answer so obvious the item is worthless" level — the 5-point preference format ("I enjoy…") keeps even desirable items discriminating, because the SD pull is toward *agreement*, not toward a specific profile.

### C.3 The real SD risk: differential desirability × rank-order scoring

Because interpretation is **within-person rank order** (Dominant Avatars, §6.5), uniform acquiescence or uniform SD inflation largely cancels out — a genuine structural protection. The residual risk is **differential** desirability: S-, E-, and I-flavored content is more socially desirable than R- and C-flavored content in most modern samples, so SD-prone respondents may see Mentor/Pioneer/Explorer artificially promoted into their Dominant pair at the expense of Maker/Guardian. This is exactly the distortion that matters most for this instrument's output, and it is currently unmeasured.

### C.4 Controls present and absent

- **Present:** 3 attention checks with graded flagging; 2 unscored consistency pairs; long-string and completion-time screens; 15 antonym-reversed items; instructions explicitly de-biasing ("answer for who you are, not who you think you should be"; ignore salary/status). This is a genuinely strong careless-responding battery for a 65-item form.
- **Absent:** any social-desirability/impression-management index, and any infrequency (bogus-item) scale beyond the instructed-response checks. The attention/consistency battery detects *inattention*, not *faking* — these are different threats, and the documentation (§6.7) does not distinguish them.
- **Impact judgment:** for the stated medium-stakes, self-benefit use case, the absence of an SD scale is acceptable (adding one would lengthen the form and SD scales have their own validity problems). But §11.3's prohibition on selection use becomes ever more load-bearing: a moderately sophisticated test-taker could produce any target profile at will. The manual should state plainly that the validity indicators do **not** detect motivated distortion.

### C.5 Could a moderately sophisticated respondent manipulate results?

Yes, trivially — item intent is transparent by design, and the consistency pairs are both positively-keyed near-duplicates that a faker would answer consistently anyway. This is true of every major interest inventory (SII, SDS, O*NET IP) and is tolerable at these stakes. Verdict: fit-for-purpose.

**Section C rating: 4 (Strong)** for the guidance context (would be 2 if repositioned for selection — the document's own use restrictions are what sustain the 4).

---

## D. Nomological Network Analysis

### D.1 Expected external relationships (testable predictions for Phase 3)

| Dimension | Expected convergent (r ≥ .50 unless noted) | Expected Big Five pattern (meta-analytic anchors: Larson et al., 2002; Barrick et al., 2003) | Expected discriminant / near-zero |
|---|---|---|---|
| MAK (R) | O*NET IP Realistic; SDS R; Things pole of Prediger axes | Near-zero with all Big Five (R is the least trait-saturated type) | Mentor scale; agreeableness |
| EXP (I) | O*NET IP Investigative; need for cognition (~.4–.5); TIE | Openness-Intellect ~.25–.35 | Extraversion; Pioneer scale beyond hexagon-predicted level |
| VIS (A) | O*NET IP Artistic; creative self-efficacy; aesthetic interest | Openness ~.40–.48 (largest interest–trait link in the literature) | Conscientiousness (small negative acceptable; large negative would confirm the A.3 bipolarity artifact) |
| MEN (S) | O*NET IP Social; empathic concern (IRI); prosocial motivation | Extraversion ~.25–.30, Agreeableness ~.15–.25 | If MEN–Extraversion exceeds ~.40, the Q40/Q21 temperament contamination is confirmed |
| PIO (E) | O*NET IP Enterprising; proactive personality; entrepreneurial intent (~.4+) | Extraversion ~.40 | Neuroticism |
| GRD (C) | O*NET IP Conventional; orderliness facet | Conscientiousness ~.20–.25 | Openness (small negative expected; large negative again flags the bipolarity artifact) |

The instrument's own convergence targets (§9.2: same-named r ≥ .60, off-diagonals following hexagonal distance) are well-calibrated against published cross-inventory benchmarks (median ≈ .59, Savickas et al., 2002) — honest and appropriately ambitious.

### D.2 Weak or unclear network nodes

1. **NRG facet:** "energizes/drains" language has no established measurement tradition inside interest inventories; its nearest neighbors are vigor/engagement (Shirom, Schaufeli) and behavioral activation. Predicted consequence: NRG items will show slightly higher loadings on temperament (extraversion/neuroticism) than ACT items. Not disqualifying — but the technical manual should register NRG as an innovation requiring its own convergent evidence, not treat the three facets as interchangeable interest indicators.
2. **Q40** is the single weakest nomological node: "Conversations with people give me energy" is a textbook Extraversion-vigor marker with zero helping content — it belongs in the network of sociability, not Social vocational interest.

### D.3 Incremental validity over existing models

Honestly, none is claimed and none should be expected at the construct level: the instrument measures the same six constructs as free alternatives (O*NET IP, public-domain markers). Its legitimate differentiation is delivery-layer: full-spectrum reporting (vs. single 3-letter code), the Differentiation Index with a flat-profile protocol, an unusually complete validity-flag battery for this category, and consultant-ready combination narratives. Under Standard 1.1 this is fine *because the documentation never claims construct-level novelty*. The one caveat: branding constructs as proprietary "Avatars" must not obscure, in client-facing material, that these are RIASEC dimensions — §1.2 discloses this clearly, which is the correct handling.

### D.4 Theoretical coherence of the overall model

Strong. The six dimensions form Holland's closed circumplex system; the instrument explicitly commits to the hexagon (calibration of opposite-type rarity in §8.2 combination 12; circular-order structural tests RTHOR/MDS/CIRCUM in §9.2 — methodologically sophisticated choices that most commercial developers omit); combination-based interpretation follows Holland's congruence logic; and the criterion expectations are anchored to the correct meta-analyses (Nye et al., 2012/2017; Van Iddekinge et al., 2011) with effect sizes quoted accurately and framed non-deterministically ("raises probability"). The design contains one internal tension already noted: the item-level engineering of VIS–GRD opposition risks *over-fitting the hexagon* — building the expected structure into item content rather than letting it emerge, which weakens the evidential value of a confirmed circumplex.

**Section D rating: 4.5 → reported as 4 (Strong, bordering Exemplary).**

---

## E. Overall Construct Validity Judgment

### E.1 Summary table

| Dimension | Overall construct validity rating (1–5) | Primary concern | Primary strength | Confidence |
|---|---|---|---|---|
| **The Maker (R)** | **4** | Narrow R sampling (no nature/outdoor/athletic content; ENV facet = 2 items); Q39r bridges to I/A | Cleanest, most distinctive construct; concrete behavioral items (Q2, Q14, Q46, Q60) | High |
| **The Explorer (I)** | **4** | Math/quantitative facet entirely missing; Q55r cross-loads on R | Excellent depth-vs-speed operationalization (Q23, Q62); strong NRG items (Q35, Q48) | High |
| **The Visionary (A)** | **3.5** | Anti-structure items (Q19, Q31r, Q45r) define A partly as not-C, manufacturing bipolarity | Origination/aesthetics core well sampled (Q6, Q11, Q25, Q38, Q52, Q59) | Medium |
| **The Mentor (S)** | **3.5** | Temperament contamination: Q40 (extraversion), Q21r (introversion penalty); highest SD load in form | Teaching/helping/supporting facets well differentiated (Q1, Q8, Q34, Q47, Q61) | Medium |
| **The Pioneer (E)** | **4** | Q58r imports Guardian language; selling facet thin; heterogeneity inherent to E | Full E span sampled (lead Q12, persuade Q5/Q44r, compete Q18, own Q64); Q24r a strong reversal | High |
| **The Guardian (C)** | **3.5** | Numeric-clerical facet missing; two of three reverse items (Q29r, Q43r) are really low-A content | Order/accuracy/stability core clear (Q3, Q10, Q22, Q36, Q57); Q63r a good drain reversal | Medium |
| **Instrument overall** | **4** | Structure-preference axis written into both VIS and GRD; Data-pole undersampling; reverse-keyed items carry most cross-loading risk | Faithful, honestly documented RIASEC implementation with exemplary transparency about its evidential status | High |

### E.2 Section ratings recap

| Section | Rating |
|---|---|
| A. Construct definition clarity | 4 |
| B. Content validity | 4 |
| C. Face validity / social desirability (for stated stakes) | 4 |
| D. Nomological network | 4 |
| **Overall Stage 1 verdict** | **4 / 5 — Strong construct validity architecture, contingent on empirical confirmation** |

### E.3 Narrative synthesis

The MINDCROUD Career Spectrum enters the assessment landscape as a deliberately conservative instrument: six well-worn, heavily evidenced RIASEC constructs, re-skinned as Avatars, operationalized through a disciplined 3-facet blueprint with verified item counts, antonym-based reversal, interleaved sequencing, and a validity-flag battery that exceeds category norms. Its documentation practices — the honest status statement (§10.1), correctly quoted meta-analytic benchmarks, EFPA/ITC/AERA-APA-NCME alignment, mandatory provisional-status notice, and hard prohibition on selection use — are the strongest part of the package and satisfy the disclosure spirit of Standards 1.1–1.4 and 7.1–7.14 at a level rarely seen pre-validation.

Its construct-validity exposure is concentrated in three places. First, the **structure-vs-freedom axis is written into both the Visionary and Guardian scales** (Q16/Q45r near-mirrors; Q19, Q29r, Q31r, Q43r on the same axis), which risks manufacturing the hexagon's A–C opposition in item content rather than observing it — degrading the evidential value of the planned RTHOR/MDS confirmation and inflating cross-loadings. Second, the **Data pole is undersampled**: no math/quantitative content in Explorer and no numeric-clerical content in Guardian, which will likely show up as weakened convergence with O*NET IP's I and C scales. Third, **temperament leakage** — chiefly Q40 and Q21r on Mentor, and the NRG facet generally — blurs the interest/trait boundary in the scales where social desirability pressure is also highest. All three exposures are correctable from the existing 60-item reserve pool before Phase 1, at zero blueprint cost, and the misbehaving-item replacement mechanism in §9.2 is already designed for exactly this.

Judgment: **proceed to Stage 2 (item-level analysis) and the instrument's own Phase 0–1 roadmap without structural redesign**, with the recommended pre-pilot substitutions: (1) replace or de-mirror one side of the Q16/Q45r pair; (2) introduce one math/data item into EXP and one numeric-clerical item into GRD; (3) replace Q40 with a helping-specific energy item; (4) re-anchor Q58r without "calm, predictable" Guardian phrasing. Ratings above assume the guidance-only, consultant-supported use case; any drift toward selection stakes would drop Section C to a 2 and the overall verdict to Significant Concern.

---
*Stage 1 complete. Output prepared for pipeline aggregation. Analyst: Stage 1 construct-validity agent, 2026-07-07.*
