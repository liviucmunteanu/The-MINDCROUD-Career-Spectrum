# Batch I Validation Results — Personas 81–90 (Category E: Demographic Diversity)

Instrument: The MINDCROUD Career Spectrum v1.0. Scored with a from-scratch Python
implementation of `data/scoring.json` (`score_batch_I.py`, in this folder), cross-checked
against Section 6 of the manual for rules the JSON omits.

## Naive-implementation decisions where documentation is ambiguous
- **Ranking ties:** Python stable sort over scales in scoring.json order
  (MAK, EXP, VIS, MEN, PIO, GRD). Ties break by that listing order. No documented
  tiebreak exists in scoring.json; Section 6.5 only addresses a rank-3 tie qualitatively.
- **Third-dominant rule:** implemented inclusive, `score2 − score3 ≤ 10`, per both
  scoring.json and Section 6.5.
- **Flat-profile flag (DI < 15):** reported as an interpretive profile flag, NOT folded
  into the validity verdict. Section 6.6 frames it as an interpretation signal, not a
  validity failure; scoring.json's `verdicts` block never lists it. So "VALID-WITH-FLAG"
  in the persona expectations = engine verdict VALID + a separate flat-profile flag.
- **Mild consistency (diff = 2 on one pair):** counted as one caution-level signal by
  analogy to the attention 1-fail caution. Docs never state this explicitly.
- Spectrum = round-half-up((raw − 10)/40 × 100). Reverse = 6 − raw for the 15 listed items.

All 10 personas in this batch pass every attention check (4/1/3), are consistent on both
pairs, and have no long-string run ≥ 12, so **every engine verdict is VALID**. The
demographic-diversity personas are honest, careful responders by design — the batch tests
item *fairness/DIF*, not validity detection.

---

## Persona 81 — Dana Kowalczyk — Female Master Electrician
**Purpose:** gender-neutrality of Maker/Realistic items.
**Response strategy:** MAK positives 5 (Q2,7,14,20,26,32,46,60), MAK reverses low
(Q39=1 "rather ideas than objects" disagree, Q53=1 "physical work drains"→coded 5);
GRD 4s for code compliance (Q3,10,16,22,36,50,57); MEN/VIS/PIO 2–3. Minor inconsistencies:
Q11=3 (some creative wiring layout), Q35=4 (likes understanding why circuits fail),
Q55=4 reverse (pragmatic "quick practical answer").
- Raw: MAK 49, EXP 31, VIS 26, MEN 24, PIO 25, GRD 37
- Spectrum: **MAK 98, GRD 68**, EXP 53, VIS 40, PIO 38, MEN 35
- Dominant: **MAK+GRD** (gap score2−score3 = 15 → EXP excluded). DI 63 (well-diff). Verdict **VALID**.
- Expected MAK+GRD (~95/70) → **MATCH**.
- **DIF evidence:** No MAK item references gender or physique. A male persona giving these
  exact 65 answers scores identically (scoring is answer-only). Confirms Realistic items are
  gender-neutral at the scoring layer. Combination = "The Steady Hand" (RC).

## Persona 82 — Mateo Fernández — Male Early-Childhood Educator
**Purpose:** gender-neutrality of Mentor/Social items (mirror of 81).
**Strategy:** MEN positives 5 (Q1,8,15,27,34,40,47,61), MEN reverses low (Q21=1 alone-all-day,
Q54=2 "helping exhausts"→coded 4); VIS 4s for classroom creativity (Q6,11,19,25,38,52,59);
PIO 2. Inconsistencies: Q24=4 reverse "follow a leader" (he's fine following his director),
Q43=3, Q39=3.
- Spectrum: **MEN 98, VIS 78**, EXP 48, GRD 48, MAK 40, PIO 28
- Dominant: **MEN+VIS** (gap 30 → EXP excluded). DI 70. Verdict **VALID**.
- Expected MEN+VIS (~95/75) → **MATCH**.
- **DIF evidence:** Social items score full for a male respondent; no item is female-coded.
  Combination = "The Inspirer" (AS). Companion mirror-audit to 81 confirms both historically
  gender-coded domains are neutral at item and scoring level.

## Persona 83 — Efua Mensah-Quartey — Market Entrepreneur (Informal Economy)
**Purpose:** whether Enterprising items assume corporate/Western contexts.
**Strategy:** PIO positives 5 (Q5,12,18,30,37,51,64 "success of a business"—her stall),
PIO reverses 1 (Q24 follow-a-leader, Q44 persuading drains, Q58 calm/predictable); GRD 4
(mental ledgers, stock records Q10,22,36); EXP 2 (Q4,13,62 low — no lab framing in her world).
Inconsistencies: Q29=4 reverse "every day different" (market is unpredictable, she likes it),
Q3=4.
- Spectrum: **PIO 95, GRD 65**, VIS 53, MEN 53, MAK 48, EXP 30
- Dominant: **PIO+GRD** (gap 12 → VIS excluded). DI 65. Verdict **VALID**.
- Expected PIO+GRD (~92/68) → **MATCH**.
- **Fairness evidence:** Q5, Q37, Q51, Q64 all endorse cleanly without an employer or org
  chart. Q64 "responsible for the success of a business or a team" maps directly to her stall.
  No PIO item presumes formal employment. Combination = "The Executive" (EC). One watch-item:
  Q18 "competition brings out my best" and Q51 "winning an important agreement" are
  Western-negotiation-flavored but she endorsed them (market haggling). No DIF observed.

## Persona 84 — Kenji Morimoto — Modesty-Norm Responder
**Purpose:** cultural response-style compression (true 5s expressed as 4s).
**Strategy:** MAK/EXP items 4 (never 5 — 5 feels boastful): Q2,7,14,20,26,32,46,60 all 4;
Q4,9,13,23,35,42,48,62 all 4; others 2–3. Obeys attention checks incl. the "immodest" 4 on
Q17 because instructed. Inconsistencies: Q59=3, Q52=3.
- Spectrum: **MAK 73, EXP 70**, VIS 53, GRD 53, MEN 53, PIO 50
- Dominant: **MAK+EXP** (gap 17 → VIS excluded). DI **23** (moderately differentiated).
  Verdict **VALID**.
- Expected MAK+EXP (~72/70), DI ~16–20 → **MATCH** on dominant + verdict; DI landed at 23,
  slightly above the predicted 16–20 band but well above the flat threshold.
- **DIF / cross-cultural evidence (KEY FINDING):** Compression is real and asymmetric. His
  top scores cap at ~73 where a US respondent with *identical interests* would hit ~98
  (compare Persona 81's MAK 98). Because modesty compresses the *ceiling* but not the floor,
  DI is mechanically smaller (23 vs 63 for an equally-interested extreme responder). The
  Dominant-Avatar pair still recovers correctly, so the ranking is robust to modesty
  compression — but Spectrum Score *bands* are not: his "Strong Resonance" MAK 73 understates
  a Core-Resonance-level interest. **Norming/threshold review flagged for cross-cultural use.**

## Persona 85 — Aarav Deshmukh — Duty-Bound Aspirant
**Purpose:** measuring interest independent of obligation (collectivist career context).
**Strategy:** answers *interest* honestly despite UPSC/family duty path: VIS positives 5
(Q6,11,19,25,38,52,59 — nightly poetry), EXP 4, GRD positives 3–4 (respects order, doesn't
love it: Q3=4,Q16=4,Q50=4,Q57=4 but Q36=3), PIO 2. Reverse VIS low (Q31,45,65).
Inconsistencies: Q39=4 reverse (drawn to ideas), Q22=4.
- Spectrum: **VIS 90, EXP 73**, GRD 60, MEN 53, MAK 35, PIO 33
- Dominant: **VIS+EXP** (gap 13 → GRD excluded). DI 57. Verdict **VALID**.
- Expected VIS+EXP (~88/72), GRD ~60 not dominant → **MATCH**.
- **Fairness evidence:** Instrument successfully separates the private artistic identity (VIS
  90) from the duty-driven Conventional path (GRD 60, correctly non-dominant). It measures
  attraction, not obligation. Report-language audit point: recommendations must be framed as
  decision-support, not a prescription that his duty-path is "wrong."

## Persona 86 — Noor Haddad — Deaf Data Analyst
**Purpose:** hearing assumptions in social/communication items (Q40 "conversations", Q34 "listening").
**Strategy:** interprets conversation/listening through signed communication and answers
meaningfully (Q34=4, Q40=4); EXP positives 5 (Q4,9,13,23,35,48,62), GRD 4; MEN moderate.
Reverse EXP low (Q28=1, Q55=2). Inconsistencies: Q42=4, Q46=4.
- Spectrum: **EXP 93, GRD 73, MEN 65**, VIS 53, MAK 45, PIO 45
- Dominant: **EXP+GRD+MEN** — gap score2(GRD 73)−score3(MEN 65) = **8 ≤ 10 → MEN included
  as third dominant**. DI 48. Verdict **VALID**.
- Expected EXP+GRD (~90/75), "MEN ~65" (implied non-dominant) → **MISMATCH on dominant count**.
  The persona-expectation named only 2 dominants, but MEN at 65 falls within 10 of GRD 73, so
  the documented inclusive rule (≤10) **correctly yields 3 dominants (EXP+GRD+MEN)**. This is an
  expectation-writing miss, not an engine error — the naive implementation follows the rule as
  written. Flagged as ambiguity: the expected outcome under-specified the third-strand rule.
- **DIF evidence:** Q40/Q34 did NOT floor for a Deaf respondent because she reinterpreted
  "conversations"/"listening" in a signed modality. But this depends on respondent
  goodwill/reinterpretation. **Item audit: "listening carefully" (Q34) and "conversations"
  (Q40) are auditory-coded; recommend modality-neutral wording** ("giving someone full
  attention", "exchanges with people"). The wording is a latent DIF risk even though this
  attentive respondent routed around it.

## Persona 87 — Callie Brennan — Wheelchair-Using Field Geologist
**Purpose:** whether physical-environment items measure interest or presumed physical capability.
**Strategy:** answers by *interest*, not current access: Q20 "workshop/site/outdoors"=5,
Q32 "physical materials give energy"=4, MAK positives 4–5, EXP positives 5. Reverse MAK/EXP
low. Inconsistencies: Q54=4 reverse, Q26=5.
- Spectrum: **EXP 95, MAK 83**, GRD 60, VIS 55, MEN 50, PIO 48
- Dominant: **EXP+MAK** (gap 23 → GRD excluded). DI 47. Verdict **VALID**.
- Expected EXP+MAK (~92/85) → **MATCH**.
- **Fairness evidence (KEY):** Because she answered by interest, Q20/Q26/Q32 correctly loaded
  MAK — the instrument measured *interest*, not *access*. The risk is entirely in report
  interpretation, not scoring: **recommendations must not equate Realistic interest with
  physical prerequisites** (e.g., don't route MAK-high toward roles gated on unaided mobility).
  Combination = "The Diagnostician" (RI), which fits adapted fieldwork + lab lead well.

## Persona 88 — Charlotte Mercier — Chronic-Illness Professional (ME/CFS)
**Purpose:** the NRG facet's illness confound — for her, literally everything "drains energy."
**Strategy:** all "drains my energy" reverse items endorsed 5 (true, but about illness not
interest): Q44=5, Q53=5, Q54=5, Q63=5, Q65=5 → these reverse-code to 1, deflating PIO, MAK,
MEN, GRD, VIS respectively. All "gives me energy" items ≤2: Q25=2, Q32=1, Q40=1, Q48=1, Q59=1.
ACT/ENV items show real profile: GRD positives 5 (Q3=5,Q10=5,Q16=5,Q36=4,Q50=4), EXP 4.
- Raw: MAK 23, EXP 33, VIS 24, MEN 23, PIO 24, GRD 38
- Spectrum: **GRD 70, EXP 57**, VIS 35, PIO 35, MAK 33, MEN 33
- Dominant: **GRD+EXP** (gap 22 → VIS excluded). DI **37 → well-differentiated, NO flat flag**.
  Verdict **VALID** (no flat flag emitted).
- Expected: GRD dominant/suppressed (~68), DI borderline ~15, **VALID-WITH-FLAG** →
  **MISMATCH**. GRD dominant is correct (~70 vs ~68), but the flat-profile flag **did not fire**:
  DI came out 37, not ~15. Reason: her NRG-driven deflation dragged five scales DOWN (33–35)
  while GRD's strong ACT/ENV items held it at 70, which *widens* DI rather than flattening it.
  The expected "borderline flat" assumed uniform NRG suppression across all six scales, but
  GRD and EXP have enough non-NRG positive items to escape the drag. **The NRG confound here
  produces a spuriously WELL-differentiated profile, not a flat one** — arguably a worse
  outcome, because a confident dominant (GRD) is built partly on an illness artifact.
- **KEY FINDING:** The NRG facet is not illness-neutral. Every "drains energy" reverse item
  she answered honestly-about-illness pulled its scale's coded value to the floor. **Recommend
  facet-level reporting (ACT/ENV separated from NRG)** so illness-loaded NRG can be set aside
  and ACT/ENV can carry interpretation. The instrument gives no signal that GRD's dominance is
  partly a drain-artifact — the profile reads as clean and confident, which is the danger.

## Persona 89 — João Batista — Multi-Job Low-SES Worker
**Purpose:** exposure bias — items about labs, original design, leading projects reference
activities he has never accessed.
**Strategy:** MAK positives 5 (lived: courier/mechanic Q2,7,14,20,26,32,46,60); EXP/VIS
items mostly 3 ("never really done that" → unfamiliarity read as neutral): Q4=3,Q6=3,Q11=3,
Q13=3,Q38=3,Q62=2; GRD 4 (stability need Q3,10,16,50,57). Reverse MAK low (Q39=1,Q53=2).
- Spectrum: **MAK 95, GRD 68**, MEN 50, EXP 48, VIS 48, PIO 48
- Dominant: **MAK+GRD** (gap 18 → MEN excluded). DI 47. Verdict **VALID**.
- Expected MAK+GRD (~90/70) → **MATCH**.
- **Fairness evidence (KEY):** His EXP/VIS scales sit at ~48 — the *midpoint*, not the floor —
  because unfamiliarity was answered as "Neutral," not "Disagree." **Neutral-from-unfamiliarity
  is scored identically to neutral-from-disinterest**, but they mean opposite things (untested
  potential vs genuine indifference). The instrument cannot distinguish them. Manual should note
  an *exposure ceiling* in low-opportunity contexts: mid-range secondary scales may hide latent
  interests that never had a chance to be discovered. Combination = "The Steady Hand" (RC).

## Persona 90 — Yesenia Morales — First-Generation Nursing Student
**Purpose:** reading level / cultural-capital assumptions for young first-gen respondents.
**Strategy:** MEN positives 5 (Q1,8,15,27,34,40,47,61 — caregiving), GRD 4 (protocols comfort
her Q3,10,16,22,36,50,57), PIO 2. Reverse MEN low (Q21=1 alone, Q54=2 helping-exhausts→4).
Inconsistencies: Q24=4 reverse (fine following), Q45=2.
- Spectrum: **MEN 93, GRD 73**, EXP 50, MAK 45, VIS 45, PIO 28
- Dominant: **MEN+GRD** (gap 23 → EXP excluded). DI 65. Verdict **VALID**.
- Expected MEN+GRD (~90/72) → **MATCH**.
- **Fairness evidence:** No jargon trip-ups — items are plain B1-level English and parsed
  cleanly for a bilingual young adult. Confirms readability floor. Combination = "The Anchor"
  (SC), a good fit for nursing. No DIF observed.

---

## Batch summary table
| P | Expected dominant | Computed dominant | DI | Verdict | Match? |
|---|---|---|---|---|---|
| 81 | MAK+GRD | MAK+GRD | 63 | VALID | ✓ |
| 82 | MEN+VIS | MEN+VIS | 70 | VALID | ✓ |
| 83 | PIO+GRD | PIO+GRD | 65 | VALID | ✓ |
| 84 | MAK+EXP | MAK+EXP | 23 | VALID | ✓ |
| 85 | VIS+EXP | VIS+EXP | 57 | VALID | ✓ |
| 86 | EXP+GRD (2) | EXP+GRD+MEN (3) | 48 | VALID | ✗ (rule adds valid 3rd) |
| 87 | EXP+MAK | EXP+MAK | 47 | VALID | ✓ |
| 88 | GRD dom, flat flag, VALID-WITH-FLAG | GRD+EXP, DI 37, NO flat flag, VALID | 37 | VALID | ✗ (flat flag didn't fire) |
| 89 | MAK+GRD | MAK+GRD | 47 | VALID | ✓ |
| 90 | MEN+GRD | MEN+GRD | 65 | VALID | ✓ |

**Classification accuracy: 8/10.**
