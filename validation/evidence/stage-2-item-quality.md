# Stage 2 — Item-Level Quality Analysis
## The MINDCROUD Career Spectrum v1.0

**Analyst role:** Psychometrician (PhD, quantitative psychology; IRT/CTT/scale development)
**Date:** 2026-07-07
**Materials reviewed:** `MINDCROUD-Career-Spectrum.md` (full specification), `data/items.json` (item bank), `tools/spectrum-scoring-tool.html` (delivery UI), item-construction standards (`item-construction.md`)
**Scope:** All 65 administered items (60 scored, 3 attention checks, 2 consistency duplicates), per Stage Prompts Section 2 (A–F).

---

## 0. Delivery-Context Finding (read first — it conditions every rating below)

The specification (Section 3.2) requires: *"always show the full 5-point scale with its verbal anchors."* The delivery UI violates its own specification:

- **`tools/spectrum-scoring-tool.html` line ~410** renders each response option as a bare numeric button (`<span>${v}</span>`, values 1–5). Verbal anchors exist only as a `title` attribute (`ANCHOR_TITLES`) — a **hover-only tooltip that does not exist on touch devices** (the majority of self-directed respondents) and is exposed inconsistently to screen readers.
- **Line ~153**: the verbal key ("1 = Strongly disagree … 5 = Strongly agree") is a **static, non-sticky `.scale-key` div** at the top of a 65-item single page. It scrolls out of view after roughly the third item.

Consequences:

1. **All 65 items** are administered with effectively numbered-only response options. The item-construction standard is explicit: *"Always fully label every point — numbered-only or endpoint-only labels reduce reliability."* This is a reliability tax on the entire instrument, and it invalidates the anchor-symmetry assumptions of the Likert format (respondents map 1–5 onto private, non-standardized internal scales; some will read it as a 1–5 intensity/"how much like me" scale rather than an agreement scale).
2. **The three attention checks (Q17, Q33, Q49) instruct respondents to select verbal labels ("Agree", "Strongly disagree", "Neutral") that appear nowhere on the response controls.** An attentive respondent on a tablet sees the instruction *choose "Agree"* and five buttons labeled 1–5, with no visible legend. The item no longer measures attention; it measures **recall of a label→number mapping shown once, dozens of items earlier**. User reports that the items "make no sense" are the predictable phenomenology of this mismatch.
3. Because the validity rule (Section 6.7) invalidates a profile at 2–3 attention failures, this defect produces **systematic false invalidation of attentive respondents** — the validity subsystem currently has a false-positive architecture, the worst possible failure mode for a screening scale.
4. Accessibility: the radiogroup carries `aria-label="Question N"` but the options are announced only as "1"–"5"; a screen-reader user has **no reliable access to the anchors at all**, and cannot pass Q17/Q33/Q49 except by luck. This also fails the instrument's own accessibility commitments (Section 7.1).

**Verdict on delivery:** the item *bank* and the item *as administered* are different instruments. Ratings below distinguish text quality from as-rendered quality.

---

## A. Item Quality Audit (all 65 items, grouped by dimension)

Criteria per Stage 2A: (1) Clarity, (2) Specificity, (3) Temporal frame, (4) Dimensional purity, (5) Expected response distribution (estimated population mean on 1–5), (6) Discrimination potential, (7) Within-dimension redundancy, (8) Reverse scoring.

Legend: **OK** = passes all criteria; flags name the failed criterion. Est. M = estimated mean in a general adult population. Keying: (+) positive, (−) reverse.

### The Maker (MAK / Realistic) — Q2, Q7, Q14, Q20, Q26, Q32, Q39−, Q46, Q53−, Q60

| Q | Text (abbrev.) | Est. M | Audit |
|---|---|---|---|
| 2 | Repairing broken objects with my hands | 3.1 | **OK — exemplary.** Concrete, behavioral, discriminating, translation-robust. |
| 7 | Using tools or machines to complete a task | 3.4 | OK. "Tools or machines" is a benign compound (same category), not double-barreled. |
| 14 | Building things I can touch when finished | 3.3 | OK, but conceptual sibling of Q26 (predicted r ≈ .70–.80, below the .85 flag line — monitor). |
| 20 | Comfortable in a workshop, on a work site, or outdoors | 3.5 | **Flag: clarity (triple-listed settings).** Workshop, construction site, and outdoors are heterogeneous environments; an avid hiker who has never held a tool can endorse via "outdoors," diluting R saturation. Minor. |
| 26 | Jobs where I can see physical results at end of day | 3.7 | OK. Slight positive skew; redundancy with Q14 monitored. |
| 32 | Working with physical materials gives me energy | 3.2 | OK. Clean NRG facet item. |
| 39− | Would rather work with ideas than physical objects | 3.4 | **Flag: dimensional purity (Major).** Comparative stem imports a second construct: agreement is not merely low-R, it is high-I/high-A content ("ideas"). The item will cross-load negatively on MAK and positively on EXP/VIS, distorting the R scale and the inter-scale structure. Antonym reversal is the right technique; the chosen antonym is the wrong one. |
| 46 | Proud when I fix something that was not working | 4.2 | **Flag: distribution (ceiling).** Pride in fixing things is near-universal; expected mean >4, compressed variance, weak discrimination at the high end of R. |
| 53− | Full day of physical hands-on work leaves me drained | 3.2 | **Flag: dimensional purity + fairness (Major).** Confounds vocational interest with physical stamina, fitness, age, health, and disability. An older or physically limited respondent with strong R interests is scored down. DIF risk (age/disability); pre-flag for Stage 5. |
| 60 | Taking devices apart to learn how they work | 3.0 | OK; mild intentional R–I bridge ("to learn how") — acceptable, monitor cross-loading. |

**Reverse scoring:** 2 of 10 (−), antonym-based — meets the ~25% standard at scale level. Temporal frame consistent (general tendency, present tense).

### The Explorer (EXP / Investigative) — Q4, Q9, Q13, Q23, Q28−, Q35, Q42, Q48, Q55−, Q62

| Q | Text (abbrev.) | Est. M | Audit |
|---|---|---|---|
| 4 | Studying information to find out why something happens | 3.6 | OK. Clean, behavioral, translatable. |
| 9 | Solving problems that require deep thinking | 4.0 | **Flag: distribution + desirability (Minor).** "Deep thinking" is mildly evaluative and flattering; few people disclaim it. Ceiling pressure. |
| 13 | Reading about science, technology, or new discoveries | 3.5 | OK. Concrete behavior; benign category list. |
| 23 | Settings where careful analysis matters more than speed | 3.4 | **OK — exemplary.** Evaluatively neutralized comparative (both poles respectable); clean ENV facet. |
| 28− | Lose interest when a task requires long, detailed analysis | 3.0 | OK as reversal; watch secondary negative loading on GRD ("detailed"). |
| 35 | Understanding how something truly works gives deep satisfaction | 4.2 | **Flag: distribution (ceiling, Minor).** "Truly," "deep satisfaction" — intensified but universally endorsable; poor discrimination. Fails the "I breathe air regularly" test at the margin. |
| 42 | Keep asking questions until I fully understand | 3.8 | OK; slight desirability tilt, acceptable. |
| 48 | Energized when I face a complicated problem | 3.6 | OK. Good NRG item. |
| 55− | Prefer a quick practical answer over a deep investigation | 3.3 | **Flag: purity (Minor).** "Practical" makes agreement partly R-positive content, not just I-negative. Lesser version of the Q39 defect. |
| 62 | Work that lets me spend a long time on a single question | 3.0 | **OK — exemplary.** Distinctive, discriminating at the high-I end; low desirability contamination. |

**Reverse scoring:** 2 (−), antonym-based, adequate.

### The Visionary (VIS / Artistic) — Q6, Q11, Q19, Q25, Q31−, Q38, Q45−, Q52, Q59, Q65−

| Q | Text (abbrev.) | Est. M | Audit |
|---|---|---|---|
| 6 | Creating original work (design, story, music) | 3.2 | OK. Example list clarifies rather than barrels; keeps construct broad. |
| 11 | Finding new ways to express an idea | 3.4 | OK. |
| 19 | Best work in places with freedom and few fixed rules | 3.4 | **Flag: purity (Minor).** Structure-avoidance content; will cross-load negatively on GRD (~−.4). Partly inherent to the RIASEC A–C opposition, but the item is autonomy-generic rather than aesthetically specific. |
| 25 | Making something beautiful gives me energy | 3.4 | OK. Distinctively aesthetic — good. |
| 31− | Prefer tasks with one correct answer over many possible answers | 3.1 | **Flag: purity (Minor).** Taps ambiguity tolerance; agreement is substantively C- and I-flavored, not just low-A. Monitor cross-loading. |
| 38 | Imagining things that do not exist yet | 3.5 | OK alone; member of the 38/59/65 novelty-invention cluster (see redundancy). |
| 45− | Best work when every step is decided in advance | 2.9 | **Flag: purity + redundancy across scales (Major).** Near-paraphrase of GRD Q16 ("clear plan and a fixed schedule") keyed in the opposite direction on a different scale. Manufactures an artifactual VIS–GRD negative correlation and effectively double-scores one bit of information on two scales. |
| 52 | Drawn to work where personal style and taste matter | 3.3 | OK. Good breadth contributor. |
| 59 | Full of energy when inventing something new | 3.5 | OK alone; redundancy cluster member. |
| 65− | Work that asks me to create something from nothing drains me | 3.0 | **Flag: redundancy (Major) + clarity (Minor).** Direct antonym of Q59 within the same scale and facet (predicted |r| ≈ .85+ absent method variance — the reversal pair adds keying balance but almost no construct information). "Create something from nothing" is borderline idiomatic; literal translation risk ("ex nihilo" readings). |

**Reverse scoring:** 3 (−), antonym-based. Facet coverage nominally 4/3/3 but the ACT/NRG items over-sample the *novelty-invention* facet (6, 11, 38, 59, 65 are one family); aesthetic (25, 52) and autonomy (19, 45) facets carry two items each. Breadth is narrower than the blueprint implies.

### The Mentor (MEN / Social) — Q1, Q8, Q15, Q21−, Q27, Q34, Q40, Q47, Q54−, Q61

| Q | Text (abbrev.) | Est. M | Audit |
|---|---|---|---|
| 1 | Teaching someone a new skill | 3.9 | OK. Warm opener per sequencing plan; mild positive skew (teaching is prosocially desirable). Consistency anchor (pairs Q41). |
| 8 | Helping people find a way through their problems | 3.9 | OK; desirability tilt inherent to S measurement, phrasing acceptably behavioral. |
| 15 | Seeing a person grow because of my support = meaningful | 4.0 | **Flag: distribution (Minor).** Almost no one disagrees that helping feels meaningful; ceiling pressure. Wordy stem but single idea. |
| 21− | Best work when I am alone for most of the day | 2.9 | **Flag: dimensional purity (Major).** Measures solitary *work style* (introversion), not low interest in helping. A therapist writing case notes alone, or an autistic respondent with strong helping interests, agrees and is wrongly scored down on S. Construct contamination + neurodivergence DIF risk (pre-flag Stage 5). |
| 27 | Prefer workplaces where people cooperate closely | 3.6 | OK. |
| 34 | Listening carefully when someone shares a personal difficulty | 3.8 | **OK — exemplary.** Specific, observable, the least fakeable S item in the set. |
| 40 | Conversations with people give me energy | 3.5 | **Flag: dimensional purity (Major).** This is a textbook Big Five Extraversion marker with no helping/serving/developing content. Vocational S ≠ trait E. Will cross-load on PIO and drag the S scale toward sociability. |
| 47 | Roles where my main task is supporting other people's growth | 3.4 | OK. Strong, role-anchored. |
| 54− | Full day of helping people with personal problems would exhaust me | 3.1 | OK as antonym reversal (emotional-labor drain is legitimate S-negative content); hypothetical "would" is a minor temporal-frame deviation. |
| 61 | Explaining difficult things so others understand | 3.9 | OK; third member of the teaching cluster (1, 41, 61) — S-scale content leans heavily on instruction vs. care. Monitor redundancy (predicted r Q1–Q61 ≈ .65–.75). |

**Reverse scoring:** 2 (−). Both reversals are sociability/energy items rather than helping-interest antonyms — the scale's negative pole is "introversion," which is the wrong negative pole for Social interests.

### The Pioneer (PIO / Enterprising) — Q5, Q12, Q18, Q24−, Q30, Q37, Q44−, Q51, Q58−, Q64

| Q | Text (abbrev.) | Est. M | Audit |
|---|---|---|---|
| 5 | Convincing others to support an idea | 3.4 | OK. |
| 12 | Taking the lead when a group needs direction | 3.5 | OK; mild desirability tilt (leadership is flattering), tolerable. |
| 18 | Competition brings out my best effort | 3.3 | OK. Crisp, discriminating. |
| 24− | Prefer to follow a leader rather than be the leader | 2.9 | OK antonym reversal; small desirability asymmetry (admitting followership) slightly compresses the low end. |
| 30 | Enjoy work environments where things move quickly | 3.6 | **Flag: specificity (Minor).** Pace-generic; fast environments include ERs and kitchens (S/R). Weakly E-specific; expect diffuse cross-loadings. |
| 37 | Being the person who starts a new project | 3.5 | **OK — exemplary.** Initiation captured concretely without status language. |
| 44− | Trying to persuade people drains my energy | 2.9 | OK. Well-chosen antonym (persuasion-drain is genuinely E-negative). |
| 51 | Winning an important agreement gives me a strong feeling of excitement | 3.3 | **Flag: clarity (Minor).** "Winning an agreement" is unidiomatic translation-ese; "a strong feeling of excitement" is padded. Say "Winning an important negotiation excites me." Also presumes deal-making exposure (student population may lack referent). |
| 58− | Prefer a calm, predictable role over a competitive one | 3.2 | **Flag: purity (Minor–Major).** "Calm, predictable" is affirmative GRD content; agreement scores the respondent down on E *and* is substantively C. Manufactures artifactual E–C negative correlation (same mechanism as Q45/Q16). |
| 64 | Would enjoy being responsible for the success of a business or a team | 3.4 | **Flag: clarity (Minor).** "A business or a team" spans very different aspiration levels (entrepreneurship vs. line supervision); mild double-barrel. "Would enjoy" hypothetical frame. |

**Reverse scoring:** 3 (−), adequate balance.

### The Guardian (GRD / Conventional) — Q3, Q10, Q16, Q22, Q29−, Q36, Q43−, Q50, Q57, Q63−

| Q | Text (abbrev.) | Est. M | Audit |
|---|---|---|---|
| 3 | Organizing information into clear systems | 3.6 | OK. |
| 10 | Checking details to make sure everything is correct | 3.7 | OK; desirability tilt (conscientiousness halo) — acceptable. Consistency anchor (pairs Q56). |
| 16 | Work best with a clear plan and a fixed schedule | 3.6 | OK alone; "clear plan **and** fixed schedule" is a soft compound (usually co-occurring, tolerable). Cross-scale twin of VIS Q45− (see above). Sibling of Q57 (predicted r ≈ .7). |
| 22 | Completing a task exactly as planned gives me satisfaction | 3.7 | OK. |
| 29− | Enjoy jobs where every day is different and unplanned | 3.4 | OK reversal; agreement carries A/E variety-seeking content — inherent to C's negative pole, acceptable. |
| 36 | Keeping records accurate and up to date | 3.3 | OK. |
| 43− | Would rather improvise than follow a step-by-step plan | 3.0 | OK reversal; watch positive cross-loading on VIS ("improvise"). |
| 50 | Prefer a stable job with clear duties over one that changes all the time | 3.7 | OK; evaluatively neutralized comparative. In economically insecure populations expect elevated means (stability preference is partly situational, not vocational) — norm carefully. |
| 57 | Clear rules and procedures help me feel confident at work | 3.6 | OK; monitor redundancy with Q16. |
| 63− | Careful, detailed paperwork quickly drains my energy | 3.3 | **Flag: clarity (Minor).** "Paperwork" is mildly dated/culture-bound for digital-native respondents; "detailed administrative work" translates and ages better. |

**Reverse scoring:** 3 (−), adequate.

### Quality-control items (audited against numeric-only display per the known defect)

| Q | Type | Text / instruction | Robust to numeric-only display? | Audit |
|---|---|---|---|---|
| 17 | Attention (correct = 4) | "…please choose 'Agree' for this one." | **NO — Critical.** Instructs a verbal label absent from the visible controls. Attentive respondents on touch devices must recall the top-of-page key from ~14 items earlier. Measures label–number mapping memory, not attention. |
| 33 | Attention (correct = 1) | "…please select 'Strongly disagree.'" | **NO — Critical.** Same failure. Endpoint position gives partial rescue (respondents may guess "strongly disagree = 1"), but guessing direction is exactly what an attention check must not require. |
| 49 | Attention (correct = 3) | "This is a quality check. Please choose 'Neutral'…" | **NO — Critical.** Same failure, worst case: midpoint label is least guessable from a bare "3". Secondary defect independent of display: a straight-liner mashing "3" passes Q49 by accident (and one mashing "4" passes Q17), so each check is blind to the straight-lining pattern that matches its own key; only the long-string screen (§6.7-C) catches those. |
| 41 | Consistency (pairs Q1) | "I like showing another person how to do something new." | **YES.** Content-based; display-independent. Semantic equivalence with Q1 is genuine. Good separation (40 items). |
| 56 | Consistency (pairs Q10) | "I enjoy reviewing work carefully to find small errors." | **YES.** Content-based; equivalence with Q10 is genuine ("checking details / everything correct" ≈ "reviewing carefully / find small errors"). Good separation (46 items). |

**Consistency-pair calibration note (Minor):** the flagging rule (§6.7-B: invalid if either pair diff ≥ 3, or both pairs ≥ 2) is aggressive for only two pairs. Single-item retest agreement for attentive respondents on 5-point Likert is imperfect (adjacent-category shifts of 1–2 are common, especially when the numeric-only display forces private anchor mapping — the same respondent may map "like/enjoy" onto 4 at Q10 and 5 at Q56). The construction standard's benchmark (|diff| ≥ 3 on **more than 2 pairs**) presumes more pairs. Recommendation: add 1–2 more pairs (one reverse-paraphrased) and require two independent signals before invalidating; and note the numeric-only display *itself* inflates pair differences, so current consistency flags are also contaminated by the UI defect.

**Label-independent rewordings (attention checks)** — dual-code number + label so the item works under any rendering, and remains correct after the UI is fixed:

- **Q17 →** "To show that you are reading each statement, select answer **4** ('Agree') for this one."
- **Q33 →** "For this statement, select answer **1** ('Strongly disagree')."
- **Q49 →** "This is a quality check. Select the middle answer, **3** ('Neutral'), for this statement."

Alternative (display-proof, content-based) replacements if instructed-response items must be avoided entirely — infrequency format: "I have visited every country in the world." (correct: 1/2); this also removes the mapping burden completely. Recommended package: keep three instructed items with dual coding **and** fix the UI (label every button with number + anchor text, e.g. stacked "4 / Agree"; make `.scale-key` `position: sticky`; add per-option `aria-label` with the full anchor).

---

## B. Problematic Item Inventory (18 of 65 = 27.7%; minimum 20% satisfied)

Ordered by severity, then by structural impact.

| Item # | Dimension | Primary Issue | Severity | Action | Suggested Revision |
|---|---|---|---|---|---|
| Q17 | Validity (ACHK-1) | Instructs verbal label invisible in numeric-only UI; false invalidations of attentive respondents | **Critical** | Revise (+ fix UI) | "To show that you are reading each statement, select answer 4 ('Agree') for this one." |
| Q33 | Validity (ACHK-2) | Same display mismatch | **Critical** | Revise (+ fix UI) | "For this statement, select answer 1 ('Strongly disagree')." |
| Q49 | Validity (ACHK-3) | Same display mismatch; midpoint least guessable from bare "3"; also blind to 3-straight-liners | **Critical** | Revise (+ fix UI) | "This is a quality check. Select the middle answer, 3 ('Neutral'), for this statement." |
| Q21 | MEN | Measures introversion/solitary work style, not low helping interest; neurodivergence DIF risk | Major | Replace | "Work that involves guiding or supporting people does not appeal to me." (true S-antonym) |
| Q40 | MEN | Pure trait-Extraversion marker; no helping content; cross-loads on PIO | Major | Revise | "Conversations where I help someone work through a question give me energy." |
| Q39 | MAK | Comparative antonym imports I/A content ("ideas"); contaminated reversal | Major | Revise | "I have little interest in working with tools or physical materials." |
| Q53 | MAK | Confounds R interest with stamina/health/age/disability; DIF risk | Major | Revise | "Hands-on practical tasks feel like a chore to me." |
| Q65 | VIS | Direct antonym of Q59 in same scale/facet (predicted \|r\| > .85); "from nothing" borderline idiom | Major | Replace | "I am not interested in work that asks for new ideas or original designs." (or replace with an aesthetic-facet reversal) |
| Q45 | VIS | Near-duplicate of GRD Q16 keyed opposite on another scale; manufactures artifactual A–C negative r | Major | Revise | "Detailed instructions for how to do my work make it less enjoyable for me." |
| Q58 | PIO | "Calm, predictable" is affirmative GRD content; artifactual E–C bipolarity | Major | Revise | "I avoid roles where I have to compete with others." |
| Q35 | EXP | Ceiling ("truly works," "deep satisfaction" near-universally endorsed); weak discrimination | Minor | Revise | "I will spend hours working out exactly why something behaves the way it does." (raises intensity) |
| Q46 | MAK | Ceiling (pride in fixing is near-universal) | Minor | Revise | "I look for chances to fix things even when no one has asked me to." |
| Q51 | PIO | "Winning an important agreement" unidiomatic; padded phrasing; assumes deal-making exposure | Minor | Revise | "Winning an important negotiation excites me." |
| Q20 | MAK | Heterogeneous setting list (workshop / work site / outdoors) — endorsable via non-R content | Minor | Revise | "I feel at home in places where people work with tools and materials." |
| Q64 | PIO | "A business or a team" spans different constructs; hypothetical frame | Minor | Revise | "I would enjoy being the person responsible for a team's results." |
| Q31 | VIS | Ambiguity-tolerance content; cross-loads C/I | Minor | Revise (or monitor in pilot) | "I prefer tasks where the goal is fixed and clear over tasks I can shape myself." |
| Q9 | EXP | "Deep thinking" evaluative + flattering; ceiling pressure | Minor | Revise | "I enjoy problems that take a long time to think through." |
| Q63 | GRD | "Paperwork" dated/culture-bound | Minor | Revise | "Careful, detailed administrative work quickly drains my energy." |

Severity counts: 3 Critical, 7 Major, 8 Minor.

---

## C. Dimension-Level Item Set Evaluation

| Scale | Predicted α | Content breadth | Item count (≥5 benchmark) | Construct representation | Notes |
|---|---|---|---|---|---|
| MAK (R) | .82–.88 (as-written); subtract ~.03–.05 as-rendered (unlabeled scale noise, all scales) | Good: repair, tools, building, materials, sites, disassembly | 10 — adequate | Good; mechanical/outdoor R covered, but no data on physical-computational R boundary | Q39/Q53 likely to load a method/contamination factor; α may be honest but structure impure |
| EXP (I) | .80–.86 | Good: causal curiosity, reading, analysis pace, persistence, depth | 10 — adequate | Good; scientific + analytic facets both present | Ceilings on Q9/Q35 compress top-end discrimination where career decisions actually happen |
| VIS (A) | .80–.86 (inflated) | **Narrower than blueprint suggests**: novelty-invention facet over-sampled (Q6, 11, 38, 59, 65); aesthetics 2 items; autonomy 2 items; performing/expressive-verbal facets absent | 10 nominal; ~8 effective after redundancy | Partial — "Artistic" reduced mostly to ideational originality | High α here would be redundancy, not breadth (attenuation paradox) |
| MEN (S) | .78–.84 | Teaching/explaining over-sampled (Q1, 61 + Q41 exposure); care (34, 8), cooperation (27), development (15, 47) present | 10 — adequate | Compromised by 2 sociability items (Q21, Q40) that measure Extraversion, not Social interest | Purity, not reliability, is the S-scale problem; α will look fine while construct drifts |
| PIO (E) | .76–.83 | Good: persuasion, leadership, competition, initiation, negotiation, ownership | 10 — adequate | Good coverage of E's facets | Lowest predicted α: heterogeneous facets + two comparative reversals (Q24, Q58) |
| GRD (C) | .82–.88 | Good: organizing, checking, records, planning, rules, stability | 10 — adequate | Good | Strongest scale overall; watch Q16/Q57 redundancy and situational contamination of Q50 |

Cross-scale structural note (hand-off to Stage 3): three reversal items (Q39, Q45, Q58) implement their antonym by borrowing a *neighboring scale's* positive content (I/A, C, C respectively). This will (a) inflate negative inter-scale correlations beyond what the RIASEC hexagon predicts, and (b) risk a method factor among reversed items — the exact failure mode the construction standard warns validation must check.

---

## D. Response Scale Assessment

1. **Scale type:** 5-point agreement Likert is appropriate for preference/interest constructs in a general population at 8th-grade reading level; consistent with the format decision tree (preferences → Likert 5). No change needed *in principle*.
2. **Anchor labels:** Symmetric and conventional. "Neutral" is a mild deviation from the recommended "Neither agree nor disagree" — "Neutral" invites "no opinion/doesn't apply" readings on NRG items ("X gives me energy" — a respondent who has never done X parks on Neutral for the wrong reason). Minor; recommend the longer label at least in the printed key.
3. **As rendered, the anchors do not exist.** The delivery UI's numbered-only buttons violate the standard's *"always fully label every point"* rule for every one of the 65 items. This is the single largest measurement threat in the instrument as fielded — bigger than any item-text issue — because it (a) reduces reliability on all scales, (b) invalidates the attention-check subsystem (Section 0), (c) inflates consistency-pair differences, and (d) breaks accessibility. **Fix:** label each option (number + anchor, stacked), make the scale key sticky, add full `aria-label` per option.
4. **Midpoint:** Appropriate for these bipolar preference constructs. Two dimension-specific cautions: (i) GRD Q50 and MEN Q15-type items with high means push midpoint use into disagreement territory asymmetrically; (ii) Q49's correct answer *is* the midpoint, so midpoint-heavy responders (a known style, elevated in some cultures) pass it non-diagnostically.
5. **Alternative formats:** No change recommended for v1.x. For a future v2: NRG items would arguably sit more naturally on an intensity scale ("drains me a lot … energizes me a lot"), and a forced-choice section would help if the instrument ever drifts toward higher stakes; both are out of scope while §1.1 restricts use to guidance.
6. **Consistency of format:** Uniform across all 65 items — a strength; the two special item types (instructed response, duplicate) correctly reuse the same response widget.

---

## E. Special Format Items

Covered in detail in Section A (quality-control table). Summary:

- **Instructed-response attention checks (3):** psychometrically standard technique, correctly spaced (25/50/75%), correct keys spread across the range (4, 1, 3). **As deployed, all three fail** due to label-dependence in a label-free UI; they currently *add* error to the validity verdict rather than removing it. Data from these items cannot be combined into the §6.7 validity verdict until the display or wording is fixed; any pilot data collected through the current UI should have attention-check failures quarantined from the invalidity rule (use completion-time and long-string screens only).
- **Consistency duplicates (2):** well-constructed, display-robust, properly separated, correctly excluded from scale scores. Information cost: 2 administered items yield a coarse 2-observation consistency estimate; flagging thresholds are aggressive for so few observations (recommend 3–4 pairs or softer combination rule).
- **Combinability:** both special formats are on the same 5-point widget, so no scoring-algorithm incompatibility exists; neither contaminates scale scores (verified against §6.2: Q17, Q33, Q41, Q49, Q56 excluded — and verified in the scoring tool's item table, which types them ATT/CON).

---

## F. Overall Item Quality Summary

- **High quality, no significant issues:** 47/65 = **72%**
- **Minor revision needed:** 8/65 = **12%**
- **Major revision or replacement:** 7/65 = **11%**
- **Critical (validity subsystem as deployed):** 3/65 = **5%**

**Five strongest items**

1. **Q2** (MAK) "I enjoy repairing broken objects with my hands." — concrete, behavioral, translation-proof, high discrimination across the full R range.
2. **Q23** (EXP) "I like work settings where careful analysis matters more than speed." — evaluatively neutralized comparative; both poles respectable, so it measures preference rather than self-flattery.
3. **Q34** (MEN) "I enjoy listening carefully when someone shares a personal difficulty." — specific and observable; the least desirability-contaminated Social item.
4. **Q62** (EXP) "I like work that lets me spend a long time investigating a single question." — discriminates high-I from casually curious; distinctive content no other scale claims.
5. **Q37** (PIO) "I like being the person who starts a new project." — captures initiation crisply without status/leadership desirability language.

**Five weakest items**

1. **Q17/Q33/Q49** (attention checks, taken as a set) — as deployed they instruct labels the interface never shows; they invert into a memory test and systematically false-flag attentive respondents.
2. **Q21** (MEN) — scores introverted helpers down on Social interest; construct contamination with DIF exposure.
3. **Q39** (MAK) — reversal via a neighboring construct ("ideas"); pollutes both the R scale and the inter-scale structure.
4. **Q40** (MEN) — a Big Five Extraversion item wearing a Social-scale badge.
5. **Q65** (VIS) — near-perfect antonym of Q59 in the same scale and facet; buys keying balance at the price of an item slot, plus a mild idiom.

### Overall Item Quality Grade

- **Item bank as written:** **B+** — disciplined, behaviorally anchored, translation-conscious writing with correct keying architecture; held back by two Extraversion-contaminated Social items, three neighbor-construct reversals, one redundant antonym pair, and a handful of ceiling items.
- **Instrument as currently administered (the unit that matters):** **C+** — the numeric-only rendering strips the anchors from all 65 items in violation of the instrument's own §3.2 and the construction standard's full-labeling rule, and it converts the entire attention-check subsystem from a validity asset into a false-invalidation engine.

**Path to A−:** (1) fix the delivery UI (labeled buttons, sticky key, aria-labels) and dual-code the three attention checks; (2) replace/revise the 7 Major items per Section B; (3) intensify the 4 ceiling items; (4) add 1–2 consistency pairs and soften the invalidity rule. All are cheap, pre-pilot fixes; none require new construct work.

*Hand-offs: cross-loading reversals and the VIS–GRD / PIO–GRD artifactual bipolarity → Stage 3 (structure); Q53 age/disability and Q21 neurodivergence concerns → Stage 5 (DIF); pilot data collected through the current UI should be treated as a separate administration condition.*
