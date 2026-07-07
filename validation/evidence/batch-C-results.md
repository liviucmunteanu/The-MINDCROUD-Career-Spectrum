# Batch C Validation Results — Personas 21–30 (Industry & Function Diversity)

Instrument: The MINDCROUD Career Spectrum v1.0. Scoring per `data/scoring.json` +
Section 6 of the manual. Scorer: `score_batch_c.py` (reverse = 6−raw for the 15
listed items; spectrum = floor(((raw−10)/40×100)+0.5), i.e. explicit half-up because
Python's `round()` is banker's rounding; dominant = top 2, +3rd if score2−score3 ≤ 10;
DI = max−min, flat if <15; attention Q17=4/Q33=1/Q49=3; consistency |Q1−Q41|, |Q10−Q56|).

Classification counting uses the **primary combination** (the top-2 pairing that selects
the 15 combination profiles) as the pass/fail criterion, with dominant-set membership
noted separately.

---

## Per-persona records

### Persona 21 — Wayne Dudek (master plumber, trades skeptic)
- **Responses Q1–65:** 4,5,3,3,2,1,5,3,3,4,1,4,2,5,3,4,[4],3,2,5, 4,4,3,1,2,5,3,4,4,4,4,5,[1],2,4,4,4,1,1,3, [4],3,3,3,3,5,2,3,[3],4, 3,1,1,3,5,4,4,3,2,4, 3,2,4,5,4
- **Key rationale:** MAK maxed (q2/q7/q14/q20/q26/q32/q46/q60 all 4–5; reverse q53 "physical work drains" answered 1 → energizes). VIS floored (q6/q11/q38/q52 = 1). GRD high on code/invoicing (q10,q16,q22,q36,q50,q57 = 4). Business-ownership items (q64=5 owns business, q37=4, q12=4) pull PIO up, but pure-salesmanship items low (q5=2, q44 persuade-drains answered 3). Attention all correct; consistency pairs exact (A=0, B=0). Minor authentic inconsistencies: q1/q41 teaching = 4 (trains apprentices), q28 reverse.
- **Raw:** MAK 49, EXP 26, VIS 17, MEN 28, PIO 36, GRD 34
- **Spectrum:** MAK 98, PIO 65, GRD 60, MEN 45, EXP 40, VIS 18
- **Dominant:** MAK + **PIO** + GRD (PIO 65 > GRD 60; gap PIO−GRD = 5 → GRD included as 3rd)
- **DI:** 80 — well-differentiated. **Verdict: Valid.**
- **Expected vs computed:** Expected MAK+GRD primary (Steady Hand, RC) with PIO tertiary.
  Computed **MAK+PIO primary (The Groundbreaker, RE)**, GRD tertiary. **MISMATCH on primary
  combination** — the dominant *set* {MAK, PIO, GRD} is correct, but PIO (65) edged GRD (60)
  into the second slot.
- **What it reveals:** The PIO scale conflates *business ownership / initiative* (q37, q64,
  q12) with *enterprising temperament / persuasion drive* (q5, q18, q44, q51). A craftsman
  who owns a business but dislikes selling still scores PIO in Strong Resonance. The
  instrument cannot separate "runs a business by necessity" from "loves the enterprising
  game," flipping his RIASEC code from RC (Steady Hand) to RE (Groundbreaker).

### Persona 22 — Dr. Sunita Raghavan (vaccine scientist, EXP+order)
- **Responses:** 3,2,5,5,2,2,4,3,5,5,3,2,5,2,3,4,[4],2,2,2, 4,5,5,3,3,2,3,1,2,2,2,2,[1],3,5,5,3,3,4,2, [3],5,1,4,4,3,3,5,[3],4, 2,2,3,4,1,5,5,4,4,3, 4,5,2,3,2
- **Key rationale:** EXP maxed to raw 50 (all 10 items endorsed incl. reverse q28=1, q55=1). GRD near-max (q3=5,q10=5,q22=5,q36=5,q57=5,q16=4). MEN/PIO low. Consistency A=0, B=0 (q10=5/q56=5). Attention all correct.
- **Raw:** MAK 25, EXP 50, VIS 29, MEN 28, PIO 23, GRD 46
- **Spectrum:** EXP 100, GRD 90, VIS 48, MEN 45, MAK 38, PIO 33
- **Dominant:** EXP + GRD (gap GRD−VIS = 42 → no 3rd). **DI 67**, well-differentiated. **Valid.**
- **Expected vs computed:** Expected EXP+GRD (The Analyst, IC). **MATCH.**
- **Reveals:** Clean convergent anchor. The instrument correctly recovers the "scientist
  under strict protocol" as Investigative+Conventional. Note EXP hit the ceiling (100) —
  no headroom to distinguish her from an even-more-extreme investigative respondent.

### Persona 23 — Lars Eikeland (Arctic field ecologist, EXP+MAK)
- **Responses:** 3,4,3,5,2,2,4,3,5,3,3,2,5,4,3,2,[4],2,4,5, 4,3,5,4,3,4,3,1,4,2,2,4,[1],3,5,4,3,3,3,2, [3],5,3,4,2,4,2,4,[3],2, 2,2,2,4,1,4,3,5,3,4, 4,5,4,2,3
- **Key rationale:** Outdoors q20=5 and EXP items q4/q13/q35/q42/q62=5 both high — the critical test that q20 is not read as trades-only. MAK physical items (gear/boats q7,q14,q26,q32,q46,q60 = 4) endorsed. Solo-field-day authenticity: q21 reverse answered 4 (agrees he works best alone) → deliberate MEN penalty. PIO floored. Consistency A=0, B=1.
- **Raw:** MAK 40, EXP 49, VIS 31, MEN 27, PIO 20, GRD 27
- **Spectrum:** EXP 98, MAK 75, VIS 53, MEN 43, GRD 43, PIO 25
- **Dominant:** EXP + MAK (gap MAK−VIS = 22 → no 3rd). **DI 73.** **Valid.**
- **Expected vs computed:** Expected EXP+MAK (The Diagnostician, RI). **MATCH.**
- **Reveals:** Realistic correctly captured *outdoor-physical* work, not only tools — a key
  discriminant success. Note MEN and GRD tied exactly at 43 (rank 4/5), harmless here but
  illustrates how frequently near-ties arise on the compressed 0–100 scale.

### Persona 24 — Daniela Fuentes (data scientist, EXP low-Social)
- **Responses:** 2,2,5,5,1,3,2,2,5,4,3,2,5,1,2,3,[4],3,4,1, 5,4,5,3,3,2,2,1,2,3,3,1,[1],2,5,4,3,3,5,1, [2],5,2,5,3,4,1,5,[3],3, 1,2,4,5,1,5,3,4,4,3, 3,5,3,2,2
- **Key rationale:** Digital-analytical work must land in EXP without a MAK hands-on signal. EXP raw 50. MAK physical items floored (q2=2,q7=2,q14=1,q20=1,q32=1) and q39 reverse "prefer ideas to objects" = 5 → MAK Low Resonance (23). Best-alone q21 reverse = 5 → MEN floored (18). GRD 68 (data-checking q10/q36/q56). Consistency A=0, B=1.
- **Raw:** MAK 19, EXP 50, VIS 32, MEN 17, PIO 21, GRD 37
- **Spectrum:** EXP 100, GRD 68, VIS 55, PIO 28, MAK 23, MEN 18
- **Dominant:** EXP + GRD (gap GRD−VIS = 13 → no 3rd). **DI 82.** **Valid.**
- **Expected vs computed:** Expected EXP+GRD, MAK low (The Analyst, IC). **MATCH — discriminant
  validity confirmed:** a "technical" job with no hands-on component correctly produced low MAK (23).
- **Reveals:** Strong discriminant-validity success. The MAK scale is driven by physical/tactile
  content, not by the colloquial sense of "technical," so knowledge-work analytics does not leak
  into Realistic.

### Persona 25 — Thandiwe Mokoena (freelance brand designer, VIS+PIO)
- **Responses:** 3,3,3,4,3,5,3,3,4,3,5,3,4,2,3,2,[4],3,4,2, 3,3,3,2,5,3,3,3,4,4,1,2,[1],3,4,2,4,5,4,4, [4],4,4,3,1,3,3,3,[3],2, 4,5,3,4,3,3,2,3,5,2, 3,3,5,4,1
- **Key rationale:** VIS maxed (q6=5,q11=5,q25=5,q52=5,q59=5; reverse q31/q45/q65 correctly disagreed). Enterprise is necessity-driven: q37=4 (starts projects), q5=3 (convinces because she must), q51=4, q64=4 — PIO moderate. EXP moderate from creative problem-solving. Consistency A=1, B=0.
- **Raw:** MAK 25, EXP 35, VIS 49, MEN 30, PIO 35, GRD 22
- **Spectrum:** VIS 98, **EXP 63 = PIO 63** (exact tie), MEN 50, MAK 38, GRD 30
- **Dominant:** VIS + EXP + PIO (score2−score3 = 0 → 3rd included). **DI 68.** **Valid.**
- **Expected vs computed:** Expected VIS+PIO primary (The Creative Director, AE) with EXP tertiary.
  **My naive stable sort broke the EXP=PIO=63 tie by dict insertion order (EXP before PIO), producing
  VIS+EXP primary (The Idea Architect, IA).** **MISMATCH on primary combination** — but the dominant
  *set* {VIS, EXP, PIO} is exactly the expected three.
- **Ambiguity noted:** Section 6.5 tie-breaking only covers a *rank-3* tie ("shared third strand").
  It gives **no rule for a tie between the rank-2 and rank-3 scales** when both are dominant anyway.
  The combination profile (which of 15 named archetypes the client is told they are) therefore depends
  on an unspecified, arbitrary ordering. My implementation output IA; a different sort would output AE.

### Persona 26 — Gianluca Moretti (session violinist, pure Artistic)
- **Responses:** 4,3,1,3,2,5,2,4,3,1,4,2,2,2,4,1,[4],2,5,2, 3,2,3,4,5,2,4,4,5,3,1,3,[1],4,3,1,3,5,3,4, [4],3,5,4,1,3,4,3,[3],1, 2,5,4,3,3,2,1,4,5,2, 4,3,5,1,1
- **Key rationale:** VIS maxed (q6=5,q19=5,q25=5,q52=5,q59=5). GRD reverse items capture *aversion*: q29 "loves unplanned days" = 5, q63 "paperwork drains" = 5, q43 "improvise" = 5, plus q3=1,q10=1,q16=1,q36=1,q50=1,q57=1 → GRD raw 11, spectrum **3** (near floor). MEN 70 (teaches students, q8=4,q34=4,q47=4). Consistency A=0, B=1.
- **Raw:** MAK 24, EXP 28, VIS 49, MEN 38, PIO 21, GRD 11
- **Spectrum:** VIS 98, MEN 70, EXP 45, MAK 35, PIO 28, GRD 3
- **Dominant:** VIS + MEN (gap MEN−EXP = 25 → no 3rd). **DI 95** (widest in batch). **Valid.**
- **Expected vs computed:** Expected VIS+MEN, GRD floor near 0–15 (The Inspirer, AS). **MATCH.**
- **Reveals:** Confirms the reverse-scored GRD items measure genuine *aversion* to Conventional
  work, not mere absence — GRD reached spectrum 3, exercising the bottom of the 0–100 scale.
  Also shows the scale *can* produce a very wide DI (95) when a respondent uses the extremes.

### Persona 27 — Farid Benali (chef-owner, 3-avatar blend) — KEY 2-vs-3 TEST
- **Responses:** 3,4,3,3,4,5,5,2,3,4,5,5,3,5,3,4,[4],4,4,5, 2,4,2,1,5,5,3,4,3,5,2,5,[1],2,4,3,5,4,1,4, [3],3,3,2,2,4,2,3,[3],2, 4,5,2,5,4,4,3,1,5,3, 3,2,4,5,1
- **Key rationale:** Deliberate spread across three scales — MAK hands (q7=5,q14=5,q20=5,q26=5,q32=5), VIS creation (q6=5,q11=5,q25=5,q52=5,q59=5), PIO ownership/command (q12=5,q37=5,q64=5,q30=5,q18=4). GRD only food-safety (q16=4,q22=4); MEN low. Consistency A=0, B=0.
- **Raw:** MAK 45, EXP 27, VIS 46, MEN 27, PIO 46, GRD 31
- **Spectrum:** **VIS 90 = PIO 90** (tie), MAK 88, GRD 53, EXP 43, MEN 43
- **Dominant:** VIS + PIO + MAK — score2−score3 = 90−88 = 2 ≤ 10 → **3rd (MAK) included → 3 dominant.**
  **DI 47.** **Valid.**
- **Expected vs computed:** Expected 3-way MAK+VIS+PIO. **MATCH — the 2-vs-3 dominant logic worked:**
  the tight 90/90/88 cluster correctly yielded three dominant avatars.
  **BUT the naming layer breaks:** the top-2 tie (VIS=PIO=90) forces a single combination label
  (The Creative Director, AE), and MAK — despite being effectively co-primary at 88 — is relegated to
  "flavor." The 15-combination scheme has no vocabulary for a true three-way (RAE) profile.
- **Reveals:** The dominant-count rule is sound, but the **combination-profile system is only 2D** —
  it cannot represent a genuine three-avatar person, exactly the case the persona was built to stress.
  A near-tie at the top (VIS vs PIO) also silently decides the archetype.

### Persona 28 — Grace Adhiambo (ICU nurse, MEN+GRD)
- **Responses:** 5,3,4,4,2,2,4,5,4,5,2,3,4,2,5,5,[4],2,1,2, 1,5,4,3,2,3,5,2,2,4,4,3,[1],5,4,5,2,2,2,4, [5],4,1,4,4,4,5,4,[3],4, 2,1,2,1,3,5,5,4,2,3, 5,2,2,3,4
- **Key rationale:** MEN maxed incl. q54 reverse "helping exhausts me" = 1 → energizes; raw 49. GRD accuracy (medication checks q10=5,q22=5,q36=5,q57=5,q16=5). MAK equipment items (q7=4,q46=4) moderate. EXP moderate from clinical reasoning (q4,q9,q13,q35,q48 = 4). q27 cooperation = 5. Consistency A=0, B=0.
- **Raw:** MAK 32, EXP 37, VIS 18, MEN 49, PIO 25, GRD 46
- **Spectrum:** MEN 98, GRD 90, EXP 68, MAK 55, PIO 38, VIS 20
- **Dominant:** MEN + GRD (score2−score3 = 90−68 = 22 > 10 → no 3rd). **DI 78.** **Valid.**
- **Expected vs computed:** Expected MEN+GRD primary (The Anchor, SC) with **MAK tertiary**.
  Primary **MATCH**, but **MAK did not become tertiary** — clinical-reasoning content pushed EXP (68)
  above MAK (55), and the 22-point gap barred any third avatar. Minor secondary discrepancy.
- **Reveals:** For nursing, the EXP scale absorbs "diagnostic/clinical reasoning," so the expected
  hands-on MAK tertiary is outranked by Investigative. Authentic, but shows tertiary predictions are
  fragile — small content-overlap effects reorder ranks 3–4.

### Persona 29 — Björn Sigurdsson (child-protection social worker, near-pure Social)
- **Responses:** 4,2,3,3,3,2,2,5,3,4,2,3,2,2,5,3,[4],1,2,2, 2,3,3,4,2,2,5,3,3,2,3,2,[1],5,3,4,2,3,4,4, [5],4,2,3,3,3,5,2,[3],4, 2,2,4,4,4,4,4,5,2,1, 4,3,4,2,3
- **Key rationale:** MEN peaks (q8=5,q15=5,q34=5,q47=5); disagrees q21 reverse (=2). GRD split: record accuracy matters (q10=4,q22=3,q36=4,q50=4,q57=4) but q63 "paperwork drains" agreed = 4 (documentation is "the job's tax"). PIO/MAK floored. Consistency A=1, B=0.
- **Raw:** MAK 20, EXP 28, VIS 24, MEN 43, PIO 21, GRD 34
- **Spectrum:** MEN 83, GRD 60, EXP 45, VIS 35, PIO 28, MAK 25
- **Dominant:** MEN + GRD (gap GRD−EXP = 15 > 10 → no 3rd). **DI 58.** **Valid.**
- **Expected vs computed:** Expected MEN+GRD, weak second, single-peak Social (The Anchor, SC). **MATCH.**
- **Reveals:** Single-peak Social emerges cleanly (MEN 83 with a 23-point gap to GRD). Shows the
  reverse/positive GRD split can coexist — documentation-heavy caseload does NOT collapse a
  genuine Social dominance.

### Persona 30 — Mele Tupou (Pasifika primary teacher, MEN+VIS)
- **Responses:** 5,2,3,3,3,4,2,5,3,3,5,4,3,3,5,3,[4],2,4,3, 1,3,2,3,4,3,5,4,4,4,2,3,[1],5,3,3,4,4,3,5, [5],3,4,2,2,3,5,3,[3],3, 2,4,3,2,4,4,3,4,5,2, 5,2,4,3,2
- **Key rationale:** MEN teaching items maxed (q1=5, q41=5 consistent, q61=5, q8=5, q34=5, q47=5). VIS expressive items 4–5 (q11=5,q59=5,q25=4). PIO competition suppressed by collectivist framing: q18=2 ("we succeed together"), q5=3, q64=3. Consistency A=0, B=1.
- **Raw:** MAK 27, EXP 26, VIS 42, MEN 49, PIO 31, GRD 27
- **Spectrum:** MEN 98, VIS 80, PIO 53, MAK 43, GRD 43, EXP 40
- **Dominant:** MEN + VIS (gap VIS−PIO = 27 > 10 → no 3rd). **DI 58.** **Valid.**
- **Expected vs computed:** Expected MEN+VIS (The Inspirer, AS), low PIO. **MATCH.**
- **Reveals:** Cultural check passes at the classification level — collectivist suppression of the
  PIO *competition* item (q18) kept PIO to Moderate (53). But this is a **content-validity caveat,
  not a fix:** the low PIO reflects a culturally-framed reading of "competition brings out my best,"
  which the instrument scores identically to genuine low enterprising interest. Same score, different
  meaning — invisible to the automated report.

---

## Cross-batch observations

- **All 10 profiles: Valid verdict.** Every persona passed all three attention checks (authored
  correct: Q17=4, Q33=1, Q49=3) and both consistency pairs (max pair difference observed = 1).
  Batch C contained no adversarial responders, so validity machinery had nothing to catch here.
- **Ceiling saturation:** EXP hit spectrum 100 for both P22 and P24; VIS hit 98 for three personas;
  MEN hit 98 twice. Any respondent endorsing ~9–10 of a scale's items maxes out, erasing distinctions
  among strong-but-different respondents.
- **Frequent exact ties** on the compressed 0–100 grid (P23 MEN=GRD=43; P25 EXP=PIO=63; P27 VIS=PIO=90;
  P28 nothing but tight; P30 MAK=GRD=43). Ties at rank 1–3 boundaries directly change the reported
  archetype yet are largely unaddressed by the documented tie-breaking rules.
