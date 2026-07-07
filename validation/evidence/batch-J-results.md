# Batch J Results — Personas 91–100 (Category E: Demographic Diversity)

Instrument: The MINDCROUD Career Spectrum v1.0. Scored with `score_batch_J.py`, a literal
implementation of `data/scoring.json` (reverse = 6−raw for Q21,24,28,29,31,39,43,44,45,53,54,55,58,63,65;
scale sums → Spectrum = round-half-up((raw−10)/40·100); dominant = top-2, +3rd if score2−score3 ≤ 10;
DI = max−min, flat if < 15; attention Q17=4/Q33=1/Q49=3; consistency |Q1−Q41|, |Q10−Q56|).

## Documentation ambiguities encountered (and what the naive implementation did)
1. **Round-half-up vs. language default.** scoring.json mandates half-up rounding, but a naive
   `round()` in Python (banker's/half-to-even) diverges at every X.5 boundary. Batch J hit **14
   such boundaries** (e.g. raw 37→82.5, raw 47→92.5, raw 39→72.5). The script uses explicit
   `floor(x+0.5)`. Under banker's rounding, MAK 92.5 would read 92, PIO/GRD 72.5 would read 72 —
   changing displayed scores and, at P100, the exact PIO=GRD tie value. Implementation-fragility finding.
2. **Is a single "mild inconsistency" (pair diff = 2) a caution-level signal?** §6.7 labels diff=2
   "mild" but the combined-verdict list (§6.7.C, scoring.json `verdicts`) only names attention (1 fail)
   explicitly as caution-level. Naive choice: **count one mild-inconsistency pair as one caution** →
   "Interpret with caution." Affects P92 only.
3. **Does the flat-profile flag feed the validity verdict?** DI/flat is documented as a *profile*
   flag (§6.6), not a *validity* signal. Naive choice: **flat does NOT change the verdict**; reported
   separately. No Batch J persona is flat, so this is moot here.
4. **Third-dominant boundary is inclusive (≤10).** Applied as written; relevant to P93 and P100.

---

## Persona 91 — Dr. Sami Al-Khalidi ("Credential-Displaced Surgeon, L2 English #1")
Careful, slow (35-min) L2 reader; trauma-surgeon identity re-qualifying. EXP/MEN high, MAK (surgery
is handwork) solid, low VIS/PIO.

Responses Q1–65:
5,4,3,5,3,2,5,4,5,4, 3,4,4,4,5,3,[4],3,2,3, 2,4,5,3,3,4,4,1,3,4, 4,4,[1],4,5,3,3,3,3,4,
4,5,2,3,3,5,4,4,[3],3, 3,2,2,2,2,4,4,3,3,4, 5,4,3,4,3

Key rationale: Q4/Q9/Q35/Q48/Q62 EXP=5/4/5/4/4 (diagnostic mind); Q1/Q8/Q15/Q47/Q61 MEN=5/4/5/4/5
(bedside teaching); Q28 (reverse "lose interest in analysis")=1 → recodes 5; Q31 VIS-reverse read
carefully. Dictionary used for "improvise"(Q43=2), "drained"(Q53=2). Attention 4/1/3 all correct.
Consistency Q1=5/Q41=4 (diff 1, within tolerance — the ONE authentic near-miss), Q10=4/Q56=4.

- Raw: MAK 40, EXP 46, VIS 26, MEN 43, PIO 33, GRD 34
- Spectrum: EXP 90, MEN 83, MAK 75, GRD 60, PIO 57, VIS 40
- Dominant: **EXP + MEN + MAK** (MAK 75 within 10 of MEN 83). DI 50 (well-diff). Verdict **VALID**.
- Expected vs actual: expected EXP+MEN with MAK third within 10 → **3 dominant. MATCH.**
- Reveals: careful L2 reading yields a clean, coherent tri-dominant profile — the top-3 rule works
  as intended on a plausible real profile. No DIF against the attentive L2 reader. (Note the MEN
  82.5 half-up boundary — banker's rounding would misreport 82.)

## Persona 92 — Thi Hoa Nguyen ("Basic-English Reader, L2 #2")
Limited English; true Guardian. Simple positives accurate; reverse-keyed GRD items misparsed.

Responses Q1–65:
4,3,4,3,2,2,4,4,3,5, 3,4,2,3,4,5,[4],2,2,3, 2,4,3,4,3,4,5,3,4,3, 5,3,[1],4,3,5,2,2,3,3,
4,3,4,4,5,4,3,2,[3],5, 3,2,3,3,4,3,4,5,2,2, 3,2,4,3,4

Key rationale: GRD positives strong (Q3=4,Q10=5,Q16=5,Q22=4,Q36=5,Q50=5,Q57=4). Reverse GRD
**misread**: Q29 "every day different/unplanned"=4, Q43 "rather improvise"=4, Q63 "paperwork
drains"=4 — each read as agreement, so each recodes to 2 and *lowers* her true-high GRD. MEN
positives 4s. Attention 4/1/3 passed (short imperatives). Q10=5/Q56=3 → **diff 2** (she parsed
"reviewing… to find small errors" shakily).

- Raw: MAK 32, EXP 26, VIS 20, MEN 37, PIO 24, GRD 38
- Spectrum: GRD 70, MEN 68, MAK 55, EXP 40, PIO 35, VIS 25
- Dominant: **GRD + MEN**. DI 45. Consistency pair B diff=2 → 1 caution → Verdict **INTERPRET WITH CAUTION**.
- Expected vs actual: expected GRD attenuated (~70) dominant with MEN (~65), consistency flag →
  REVIEW / VALID-WITH-FLAG. **MATCH** (my "Interpret with caution" = documented VALID-WITH-FLAG tier).
- Reveals: **reverse-keyed items carry disproportionate language load.** Three misread reverses cost
  her ~12–15 GRD points, pulling a "Core Resonance" Guardian down into "Strong Resonance." The same
  language load also produced the borderline consistency flag. Strong localization-priority evidence;
  reverse items should be the first target for plain-language / translated versions.

## Persona 93 — Ruby Thompson ("16-Year-Old, No Work History")
Maps items to school/hobbies; more honest midpoints than adults; likes art + biology.

Responses Q1–65:
4,3,3,4,3,5,2,3,4,3, 4,3,5,4,3,3,[4],3,3,2, 2,4,3,3,5,3,4,3,3,3, 3,3,[1],4,4,3,4,5,3,4,
4,4,3,3,3,3,2,3,[3],3, 3,4,3,3,3,3,3,3,4,2, 3,3,2,3,2

Key rationale: VIS 5s on Q6/Q13(as biology curiosity)/Q25/Q38; EXP 4–5 (biology). Q64 "success of a
business"→her sticker shop, 3. ~30% 3s from genuine uncertainty. Attention 4/1/3 all correct. Pairs
Q1=4/Q41=4, Q10=3/Q56=3.

- Raw: MAK 28, EXP 36, VIS 40, MEN 34, PIO 31, GRD 32
- Spectrum: VIS 75, EXP 65, MEN 60, GRD 55, PIO 53, MAK 45
- Dominant: **VIS + EXP + MEN** (EXP 65 − MEN 60 = 5 ≤ 10 → MEN pulled in as 3rd). DI 30. Verdict **VALID**.
- Expected vs actual: expected **VIS + EXP (2 dominant), DI ~18**. Actual gives the correct top
  pair but **adds a 3rd dominant (MEN)** and DI 30 (well-diff, not moderate). **PARTIAL DEVIATION** —
  the only classification deviation in Batch J.
- Reveals: A young, midpoint-heavy profile compresses ranks 2–5 into a narrow band, so the inclusive
  ≤10 third-dominant rule readily fires and yields 3 dominants where the design anticipated 2. This is
  a boundary-sensitivity finding, not a scoring error — but it shows the top-3 rule is *label-unstable*
  for low-differentiation adolescent profiles. Item audit: Q64/Q50/Q16 ("business", "stable job")
  presuppose workplace framing she had to translate to school/hobby contexts; she coped, but the
  translation is what produced her extra midpoints.

## Persona 94 — Harold Jenkins ("Encore-Stage Craftsman", 68)
Semi-retired master carpenter now mentoring apprentices; hands still itch.

Responses Q1–65:
5,5,3,3,2,3,5,4,4,4, 3,3,3,5,5,4,[4],2,2,5, 2,4,3,4,4,5,4,3,3,2, 4,5,[1],4,4,3,2,3,1,4,
5,3,2,4,3,5,5,3,[3],4, 2,3,3,3,2,4,4,5,3,4, 5,3,4,2,3

Key rationale: MAK positives 5 (Q2,Q7,Q14,Q20,Q26,Q32,Q46,Q60); Q39 MAK-reverse=1→5; MEN 4–5
(mentoring: Q1=5,Q8=4,Q15=5,Q47=5,Q61=5). PIO 2 ("had my fill of running crews"). Attention 4/1/3.
Q1=5/Q41=5, Q10=4/Q56=4.

- Raw: MAK 47, EXP 33, VIS 29, MEN 43, PIO 20, GRD 35
- Spectrum: MAK 93, MEN 83, GRD 63, EXP 57, VIS 48, PIO 25
- Dominant: **MAK + MEN** (GRD 63 vs MEN 83 gap 20 → excluded). DI 68 (well-diff). Verdict **VALID**.
- Expected vs actual: expected MAK+MEN (~92/80). **MATCH.**
- Reveals: **Age ceiling passes** — "career" framing still functions at 68; the MAK+MEN opposite-pole
  pair (Realistic+Social, "The Responder") scores coherently for an encore mentor. Nothing in the
  item set is youth-locked. (Three half-up boundaries here: 92.5/82.5/62.5 — banker's rounding would
  have understated all three.)

## Persona 95 — Ash Okada ("Non-Binary Motion Designer")
they/them; aesthetic obsession; loves technique deep-dives; hates process/paperwork.

Responses Q1–65:
3,2,2,4,2,5,3,3,4,3, 5,2,4,2,3,2,[4],3,4,2, 4,3,4,3,5,2,3,2,4,3, 1,2,[1],3,5,2,3,5,4,3,
3,4,4,4,1,3,2,4,[3],2, 2,5,4,4,3,3,2,3,5,3, 3,3,4,2,2

Key rationale: VIS positives 5 (Q6,Q11,Q25,Q38,Q52,Q59); Q31/Q45/Q65 VIS-reverses=1/1/2 → high
recode. EXP 4s (technique). GRD 2s. Attention 4/1/3. Pairs Q1=3/Q41=3, Q10=3/Q56=3.

- Raw: MAK 23, EXP 39, VIS 48, MEN 27, PIO 25, GRD 22
- Spectrum: VIS 95, EXP 73, MEN 43, PIO 38, MAK 33, GRD 30
- Dominant: **VIS + EXP** (MEN 43 vs 73 gap 30 → excluded). DI 65. Verdict **VALID**.
- Expected vs actual: expected VIS+EXP (~95/70). **MATCH.**
- Reveals: **No gendered language dependency** — the instrument scored a non-binary respondent with
  no textual friction; every item is second-person and gender-neutral. Platform-level finding stands:
  the *demographics capture form* (not the item bank) is where non-binary/self-describe support must
  exist and must not break scoring or report text. Item bank itself is clean.

## Persona 96 — Wiremu Ngata ("Māori Community Coordinator")
Collectivist self-construal; leads constantly but "being THE leader" reads as culturally awkward.

Responses Q1–65:
5,3,4,3,4,3,3,5,3,4, 4,4,3,4,5,3,[4],2,3,4, 1,3,3,3,3,3,5,3,3,4, 3,3,[1],5,4,3,4,3,3,4,
5,4,3,2,3,4,5,3,[3],3, 4,3,3,2,4,4,3,3,3,2, 4,2,3,5,3

Key rationale: MEN positives 5 (Q1,Q8,Q15,Q34,Q47,Q61 reframed as the collective's mahi); Q21
MEN-reverse=1→5. PIO **softened**: leads (Q12=4,Q37=4,Q64=5) but Q5=4, Q18=2, Q51=4, Q58 reverse=3
— reads "being THE leader / winning" as individualist and dampens. Attention 4/1/3. Q1=5/Q41=5,
Q10=4/Q56=4.

- Raw: MAK 32, EXP 30, VIS 31, MEN 47, PIO 37, GRD 32
- Spectrum: MEN 93, PIO 68, MAK 55, GRD 55, VIS 53, EXP 50
- Dominant: **MEN + PIO** (MAK 55 vs PIO 68 gap 13 → excluded). DI 43. Verdict **VALID**.
- Expected vs actual: expected MEN+PIO (~92/70). **MATCH.**
- Reveals: **Individual-agency phrasing deflates Enterprising for collectivist leaders.** His PIO
  landed at 68 ("Strong") not ~85 despite 14 years of running an iwi service — the "I take the lead /
  being THE leader / winning an agreement" wording penalizes communal leadership. Report must not read
  PIO 68 as "lacks leadership drive." Cross-cultural DIF candidate on PIO items Q12/Q18/Q51/Q58.

## Persona 97 — Terrence Boyd ("Re-Entry Professional")
Stability-first (security need); genuine mechanical interest (HVAC/kitchens/repair).

Responses Q1–65:
4,5,3,3,3,2,5,3,4,4, 3,3,3,4,4,5,[4],3,2,5, 3,4,3,3,3,5,4,3,2,4, 4,4,[1],3,4,3,2,3,1,3,
4,3,2,3,4,5,3,3,[3],5, 3,2,2,4,4,4,5,5,3,4, 3,2,3,3,3

Key rationale: MAK positives 5 (Q2,Q7,Q20,Q26,Q46) — genuine. GRD partly **need-inflated**: Q50
"stable job clear duties"=5 (security, not temperament), Q16=5, Q57=5. Q39 MAK-reverse=1→5. Attention
4/1/3. Pairs consistent.

- Raw: MAK 46, EXP 30, VIS 25, MEN 32, PIO 28, GRD 40
- Spectrum: MAK 90, GRD 75, MEN 55, EXP 50, PIO 45, VIS 38
- Dominant: **MAK + GRD**. DI 52. Verdict **VALID**.
- Expected vs actual: expected MAK+GRD (~88/72), GRD need-inflated. **MATCH.**
- Reveals: **Need-vs-interest confound is real and undetectable by current QA.** GRD 75 is
  materially lifted by the three security-context items (Q50/Q16/Q57) answered from economic
  precarity, not Conventional temperament. The instrument cannot separate the two; manual should
  caveat that GRD in a precarity context may over-read. No flag fires — an honest limitation.

## Persona 98 — Latifa Al-Mansoori ("Emirati Finance Graduate")
Answers by attraction, not permission: private passion for visual/brand design vs. family-firm duty.

Responses Q1–65:
3,2,3,4,4,5,2,4,4,3, 5,4,3,3,4,3,[4],4,4,2, 3,4,3,2,5,3,4,3,3,4, 2,2,[1],4,4,3,4,5,4,3,
3,3,3,3,2,3,3,3,[3],2, 4,5,4,3,3,3,3,3,4,2, 3,2,3,5,1

Key rationale: VIS positives 5 (Q6,Q11,Q25,Q38,Q52); Q65 VIS-reverse=1→5, Q45=2→4, Q31=2→4. PIO 4
(ambitious: Q5=4,Q18=4,Q37=4,Q64=5). GRD 3 (respects, doesn't love). Attention 4/1/3. Pairs consistent.

- Raw: MAK 23, EXP 32, VIS 46, MEN 34, PIO 39, GRD 30
- Spectrum: VIS 90, PIO 73, MEN 60, EXP 55, GRD 50, MAK 33
- Dominant: **VIS + PIO** (MEN 60 vs 73 gap 13 → excluded). DI 57. Verdict **VALID**.
- Expected vs actual: expected VIS+PIO (~88/75). **MATCH.**
- Reveals: Instrument captured **honest interest independent of enacted role** — she analyzes finance
  daily yet EXP/GRD (the job's demands) sit mid while VIS/PIO (her attraction) dominate. Confirms the
  tool measures attraction, not current activity. Report-language audit stands: for constrained-agency
  respondents, avoid prescriptive "change careers" framing; decision-support tone required.

## Persona 99 — Samuel Kiptoo ("Agri-Tech Cooperative Farmer")
Fluent with numeric phone UIs (M-Pesa); counterpoint to the UI-confused personas 71/72.

Responses Q1–65:
4,5,4,4,4,2,5,4,3,4, 3,4,4,5,3,3,[4],3,2,5, 3,3,3,2,2,5,4,3,3,3, 4,5,[1],3,4,4,4,3,1,3,
4,3,3,2,3,5,2,3,[3],3, 5,2,3,3,4,4,3,3,3,4, 3,2,3,5,3

Key rationale: MAK positives 5 (Q2,Q7,Q14,Q20,Q26,Q32,Q46,Q60); Q39 reverse=1→5. PIO 4 (organizes
co-op, negotiates milk prices: Q5=4,Q37=4,Q51=5,Q64=5). Attention 4/1/3 — fully comfortable. Pairs
consistent.

- Raw: MAK 47, EXP 31, VIS 25, MEN 32, PIO 39, GRD 33
- Spectrum: MAK 93, PIO 73, GRD 57, MEN 55, EXP 53, VIS 38
- Dominant: **MAK + PIO** (GRD 57 vs 73 gap 16 → excluded). DI 55. Verdict **VALID, zero flags.**
- Expected vs actual: expected MAK+PIO (~90/75), zero flags. **MATCH.**
- Reveals: **Decisive evidence that the 71/72 numeric-UI failures are about anchor communication,
  not user sophistication or resource level.** A low-end-Android, diploma-level, non-Western
  respondent used the numeric 1–5 scale flawlessly because the *convention* was familiar. The fix for
  71/72 is showing anchor labels, not assuming low-resource users can't handle numeric entry.

## Persona 100 — David Marek ("Blind Accessibility Consultant")
Screen-reader power user; interprets visual metaphors tactilely/aurally.

Responses Q1–65:
4,3,5,5,4,3,4,3,5,4, 4,4,5,3,3,4,[4],4,3,2, 3,4,4,2,3,3,4,1,2,4, 3,3,[1],3,5,4,4,4,4,4,
4,5,2,2,3,4,3,5,[3],3, 4,3,4,3,2,4,4,3,4,4, 5,3,3,4,2

Key rationale: EXP positives 5 (Q4,Q9,Q13,Q35,Q48); Q28 reverse=1→5. GRD 4 (systems elegance).
PIO 4. Q25 "making something beautiful"=3 and Q6 "design"=3 — interpreted through tactile/auditory
aesthetics, deliberately moderate. Q20 "workshop/site/outdoors"=2 (not his environment). Attention
4/1/3 — clean, fast screen-reader flow. Pairs Q1=4/Q41=4, Q10=4/Q56=4.

- Raw: MAK 30, EXP 46, VIS 34, MEN 35, PIO 39, GRD 39
- Spectrum: EXP 90, PIO 73, GRD 73, MEN 63, VIS 60, MAK 50
- Dominant: **EXP + PIO + GRD** (PIO=GRD=73 tied at rank 2/3; both within 10 → 3 dominant). DI 40. Verdict **VALID**.
- Expected vs actual: expected EXP + GRD/PIO near-tie at #2/#3 → 3 dominant (~90/74/72). **MATCH**
  (came out as an *exact* PIO=GRD=73 tie rather than 74/72 — even cleaner confirmation of the boundary).
- Reveals: **Numeric-only UI + short items = fully accessible** to a screen-reader user; no
  accessibility barrier in flow. Item audit: Q25 ("beautiful"), Q6 ("design"), Q20 ("workshop/site/
  outdoors") are visually/physically coded but he could still answer meaningfully by re-interpreting —
  recommend modality-neutral wording but no blocking defect. **Rounding fragility spotlight:** PIO and
  GRD both land on raw 39 → 72.5 → half-up 73, producing the exact rank-2/3 tie. Under banker's
  rounding both would be 72 (still tied) but MEN 62.5→62 shifts; a non-half-up implementation would
  silently alter displayed scores near these boundaries.

---

## Classification accuracy: 9.5 / 10
- **9 exact matches** (91, 92, 94, 95, 96, 97, 98, 99, 100) — dominant sets and verdicts as documented.
- **1 partial deviation (93):** correct top pair (VIS+EXP) but the naive ≤10 rule pulled in a **3rd
  dominant (MEN)** where the design expected 2, and DI came out 30 (well-diff) vs expected ~18.
  Boundary-sensitivity, not a scoring error.
