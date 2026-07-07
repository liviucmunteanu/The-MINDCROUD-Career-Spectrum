# MINDCROUD Career Spectrum — Simulated Validation, Batch A (Personas 01–10)

Scored with `score_batch_A.py` (same directory), a naive literal implementation of `data/scoring.json` + Section 6 of `MINDCROUD-Career-Spectrum.md`.
Reverse items (6−raw): 21, 24, 28, 29, 31, 39, 43, 44, 45, 53, 54, 55, 58, 63, 65. Attention checks Q17=4, Q33=1, Q49=3. Pairs |Q1−Q41|, |Q10−Q56|. Dominants = top 2 (+3rd if score2−score3 ≤ 10). DI = max−min; flat if <15.

**Batch verdict summary: 8/10 exact classification matches, 1 partial (P02), 1 miss (P01). All 10 profiles validity-verdict "Valid" (as designed — QA-stressor personas are 41–60).**

## Global scoring ambiguities observed (naive implementation behavior)

1. **Floating-point half-up rounding bug (real defect class).** `round((raw−10)/40*100)` at raw=33 gives 57.4999…993 in IEEE doubles; naive `floor(x+0.5)` (and Python's banker's `round()`) outputs **57**, but Section 6.4's rule (77.5→78, half-up) demands **58**. Hit twice in this batch: P05 VIS (raw 33) and P09 EXP (raw 33). Raw 35 (62.5) happens to be binary-exact and rounds correctly to 63. Neither instance changed a dominance decision here, but raw 33 vs 34 sits exactly where a 1-point spectrum error could flip the ≤10 third-dominant rule. Docs should specify decimal/rational arithmetic.
2. **Rank-3/4 exact ties below the 10-point window.** P05 (MEN=PIO=63), P07 (MEN=GRD=65), P09 (VIS=GRD=45): the naive stable sort puts whichever avatar appears first in the scales dict (MAK, EXP, VIS, MEN, PIO, GRD order) at rank 3. No dominance impact in these cases (gap23 > 10), but Section 6.5's tie-breaking only covers ties *at* rank boundaries that qualify; it is silent on which tied avatar is "rank 3" for computing score2−score3 (irrelevant numerically, but report ordering is undefined).
3. **Bottom ties** (P03 PIO=GRD=20; P08 EXP=GRD=23): no rule exists or is needed; DI unaffected.
4. **"Caution-level signal" is undefined for a single mild (diff=2) consistency pair.** My naive implementation counts one diff=2 pair as a caution → "Interpret with caution." Never triggered in Batch A (all pair diffs ≤1), but the docs never say whether "mild inconsistency" is caution-level or ignorable.
5. **Flat-profile vs dominant precedence untested in this batch** (no DI<15 profiles among P01–P10); naive impl would still emit 2–3 dominants alongside the flat flag, and the docs do not say to suppress them.

---

## Persona 01 — Noah Whitfield (16, UK, Year 11, undecided)

### Response sheet (Q1–Q65)
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 3 | 14 | 3 | 27 | 3 | 40 | 4 | 53 | 2 |
| 2 | 3 | 15 | 3 | 28 | 4 | 41 | 4 | 54 | 3 |
| 3 | 2 | 16 | 3 | 29 | 4 | 42 | 3 | 55 | 4 |
| 4 | 3 | 17 | **4** | 30 | 4 | 43 | 4 | 56 | 3 |
| 5 | 2 | 18 | 4 | 31 | 3 | 44 | 3 | 57 | 3 |
| 6 | 3 | 19 | 4 | 32 | 3 | 45 | 3 | 58 | 3 |
| 7 | 4 | 20 | 4 | 33 | **1** | 46 | 4 | 59 | 3 |
| 8 | 3 | 21 | 2 | 34 | 2 | 47 | 2 | 60 | 4 |
| 9 | 4 | 22 | 3 | 35 | 4 | 48 | 3 | 61 | 3 |
| 10 | 2 | 23 | 2 | 36 | 1 | 49 | **3** | 62 | 2 |
| 11 | 3 | 24 | 4 | 37 | 2 | 50 | 3 | 63 | 4 |
| 12 | 3→2* | 25 | 3 | 38 | 4 | 51 | 3 | 64 | 2 |
| 13 | 4 | 26 | 3 | 39 | 3 | 52 | 2 | 65 | 3 |

*(Q12 recorded as 2.)* Key rationales: hobby-adjacent ACT items decisive (Q7/Q60=4 gaming PC tinkering; Q13=4 games/tech; Q20/Q32=4 via PE/outdoors; Q18=4 competitive gaming); ENV items about workplaces he's never seen sit at 3 (Q16, Q23, Q26, Q27, Q50); teenage impatience honestly endorses EXP drain reverses Q28=4, Q55=4; Q36=1 ("records accurate" = homework admin, hates it). Intentional minor inconsistencies: Q9=4 (likes puzzle games) vs Q28=4 (loses interest in long analysis); Q1=3 vs Q41=4 (pair diff 1); Q19=4 vs Q45=3.

### Computed
- Raw: MAK 35, EXP 29, VIS 31, MEN 30, PIO 27, GRD 23
- Spectrum: **MAK 63, VIS 53, MEN 50, EXP 48, PIO 43, GRD 33**
- Dominant: **MAK + VIS + MEN** (3-way; gap23 = 3) | DI = 30 → Well-differentiated | Checks 0 fails; pairs 1/1 → **Valid**

### Expected vs computed — **MISS**
Expected weak MAK+EXP lead. MAK led as expected, but EXP fell to rank 4: the two EXP reverse items (Q28, Q55) punished authentic adolescent impatience −4 coded points, while VIS and MEN coasted to 53/50 on midpoint 3s (a stack of "don't know" 3s yields spectrum 50 — enough to enter the dominance window when the real signal is weak).

### What it reveals
- Neutral ≠ absence of interest: midpoint-heavy scales land at ~50 and can become "dominant" by default in low-information respondents. The 3-way rule fired on noise.
- DI=30 labeled this "Well-differentiated" only because GRD was singularly low — DI (max−min) is not a differentiation measure of the top of the profile.
- For adolescents, EXP's NRG/patience-worded reverses measure maturity as much as interest.

---

## Persona 02 — Bianca Petrescu (17, Romania, vocational auto-mechanics)

### Response sheet
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 3 | 14 | 5 | 27 | 3 | 40 | 2 | 53 | 1 |
| 2 | 5 | 15 | 3 | 28 | 2 | 41 | 3 | 54 | 3 |
| 3 | 3 | 16 | 4 | 29 | 2 | 42 | 4 | 55 | 3 |
| 4 | 4 | 17 | **4** | 30 | 3 | 43 | 2 | 56 | 4 |
| 5 | 1 | 18 | 3 | 31 | 4 | 44 | 4 | 57 | 4 |
| 6 | 2 | 19 | 2 | 32 | 5 | 45 | 3 | 58 | 4 |
| 7 | 5 | 20 | 5 | 33 | **1** | 46 | 5 | 59 | 3 |
| 8 | 3 | 21 | 4 | 34 | 2 | 47 | 2 | 60 | 5 |
| 9 | 4 | 22 | 5 | 35 | 5 | 48 | 4 | 61 | 3 |
| 10 | 4 | 23 | 3 | 36 | 2 | 49 | **3** | 62 | 3 |
| 11 | 3 | 24 | 4 | 37 | 2 | 50 | 4 | 63 | 4 |
| 12 | 2 | 25 | 3 | 38 | 2 | 51 | 2 | 64 | 2 |
| 13 | 4 | 26 | 5 | 39 | 1 | 52 | 2 | 65 | 3 |

Key rationales: MAK ceiling with textbook reverse handling (Q39=1, Q53=1 — physical work energizes); diagnostics drive genuine EXP (Q35=5 "understanding how something truly works" is literally her craft; Q4/Q9/Q13/Q42=4); GRD split exactly as designed — workshop procedure high (Q22=5, Q16/Q57=4, Q10/Q56=4/4) but paperwork low (Q36=2, Q63=4 agree-drains); PIO floor (Q5=1, Q24=4 happy to follow the master). Intentional inconsistencies: Q22=5 (exactly-as-planned) vs Q29=2 only mild disagree; Q13=4 vs Q62=3.

### Computed
- Raw: MAK 50, EXP 38, VIS 25, MEN 26, PIO 21, GRD 36
- Spectrum: **MAK 100, EXP 70, GRD 65, MEN 40, VIS 38, PIO 28**
- Dominant: **MAK + EXP + GRD** (3-way; gap23 = 5) | DI = 72 | Checks pass; pairs 0/0 → **Valid**

### Expected vs computed — **PARTIAL**
Expected MAK+GRD with EXP tertiary; computed MAK+EXP+GRD (EXP outranked GRD by 5 points). Same three avatars, ranks 2/3 swapped. Cause: EXP-05 (Q35) and diagnostic ACT items capture mechanic troubleshooting strongly, while GRD-06/GRD-10 subtract for paperwork aversion even in a procedure-loving tradesperson. Combination profile served would be "The Diagnostician" (MAK+EXP, RI) — arguably a *better* fit for a diagnostics-loving mechanic than the expected "Steady Hand" (RC), so the miss is defensible substantively.

### What it reveals
- MAK raw 50 → spectrum 100: ceiling reached by an honest 17-year-old; no headroom to distinguish her from an even stronger Realistic profile.
- GRD scale mixes "procedure/precision" and "paperwork/records" content; trades respondents split them, which pulls GRD below diagnostic EXP.
- The ≤10 third rule worked well here: reporting all three avatars is the honest answer.

---

## Persona 03 — Kaito Mori (18, Japan, gap year, artist under parental pressure)

### Response sheet
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 2 | 14 | 5 | 27 | 2 | 40 | 2 | 53 | 4 |
| 2 | 4 | 15 | 3 | 28 | 3 | 41 | 3 | 54 | 4 |
| 3 | 2 | 16 | 2 | 29 | 4 | 42 | 4 | 55 | 3 |
| 4 | 4 | 17 | **4** | 30 | 2 | 43 | 4 | 56 | 3 |
| 5 | 2 | 18 | 2 | 31 | 1 | 44 | 5 | 57 | 2 |
| 6 | 5 | 19 | 5 | 32 | 4 | 45 | 1 | 58 | 4 |
| 7 | 3 | 20 | 2 | 33 | **1** | 46 | 4 | 59 | 5 |
| 8 | 3 | 21 | 5 | 34 | 3 | 47 | 2 | 60 | 4 |
| 9 | 4 | 22 | 3 | 35 | 4 | 48 | 2 | 61 | 3 |
| 10 | 2 | 23 | 4 | 36 | 1 | 49 | **3** | 62 | 4 |
| 11 | 5 | 24 | 4 | 37 | 3 | 50 | 1 | 63 | 5 |
| 12 | 1 | 25 | 5 | 38 | 5 | 51 | 2 | 64 | 1 |
| 13 | 5 | 26 | 3 | 39 | 3 | 52 | 5 | 65 | 1 |

Key rationales: perfect VIS ceiling incl. reverses (Q31=1, Q45=1, Q65=1); **Q13=5 is the parent-pleasing inflation** (reads sci-tech articles partly to feel like an engineer's son); N-High agrees with drain reverses (Q53=4, Q54=4, Q44=5), which costs MAK/MEN/PIO; model-building keeps MAK real (Q14=5, Q2=4, Q60=4); Q48=2 (complicated problems trigger anxiety, not energy) — an authentic inconsistency against Q9=4. GRD/PIO floors (Q50=1 rejects the stable job his parents want).

### Computed
- Raw: MAK 34, EXP 37, VIS 50, MEN 23, PIO 18, GRD 18
- Spectrum: **VIS 100, EXP 68, MAK 60, MEN 33, PIO 20, GRD 20** (PIO/GRD exact bottom tie)
- Dominant: **VIS + EXP + MAK** (3-way; gap23 = 8) | DI = 80 | Checks pass; pairs 1/1 → **Valid**

### Expected vs computed — **MATCH**
Expected VIS+EXP (pressure-inflated) with true second MAK — computed 3-way contains exactly this structure. The ≤10 window rescued the authentic MAK signal that the inflated EXP would otherwise have hidden.

### What it reveals
- One socially-pressured item (Q13) plus N-driven Q48 suppression produced an 8-point EXP−MAK gap — retest after the pressure lifts would plausibly reorder ranks 2 and 3. The instrument has no way to see this; only the 3-way rule kept both in view.
- Second ceiling case (VIS 100) in three personas; ceiling frequency at the top of honest strong profiles looks high for a 10-item/50-point scale.

---

## Persona 04 — Destiny Carter (19, USA, community college, first-gen, anxious)

### Response sheet
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 4 | 14 | 3 | 27 | 4 | 40 | 3 | 53 | 4 |
| 2 | 2 | 15 | 4 | 28 | 3 | 41 | 4 | 54 | 3 |
| 3 | 3 | 16 | 4 | 29 | 3 | 42 | 3 | 55 | 4 |
| 4 | 3 | 17 | **4** | 30 | 3 | 43 | 2 | 56 | 3 |
| 5 | 2 | 18 | 3 | 31 | 4 | 44 | 4 | 57 | 4 |
| 6 | 3 | 19 | 2 | 32 | 3 | 45 | 2 | 58 | 4 |
| 7 | 2 | 20 | 2 | 33 | **1** | 46 | 4 | 59 | 3 |
| 8 | 4 | 21 | 2 | 34 | 4 | 47 | 3 | 60 | 2 |
| 9 | 3 | 22 | 4 | 35 | 3 | 48 | 2 | 61 | 3 |
| 10 | 4 | 23 | 3 | 36 | 2 | 49 | **3** | 62 | 2 |
| 11 | 3 | 24 | 4 | 37 | 2 | 50 | 4 | 63 | 3 |
| 12 | 2 | 25 | 3 | 38 | 3 | 51 | 3 | 64 | 2 |
| 13 | 2 | 26 | 3 | 39 | 3 | 52 | 3 | 65 | 3 |

Key rationales: 2–4 range as designed; MEN helping items 4 (Q1, Q8, Q34, Q15); stability items 4 (Q50, Q16, Q57 — wants safety); **under-endorses PIO despite organizing shifts** (Q12=2, Q37=2, Q24=4 "follow a leader"); Q48=2 (complicated problems = anxiety); self-doubt inconsistency: Q46=4 (proud fixing things) vs Q2=2, and Q61=3 vs Q1=4 (believes she'd enjoy teaching but doubts she can explain).

### Computed
- Raw: MAK 26, EXP 26, VIS 29, MEN 36, PIO 23, GRD 35
- Spectrum: **MEN 65, GRD 63, VIS 48, MAK 40, EXP 40, PIO 33** (MAK/EXP tie)
- Dominant: **MEN + GRD** (gap23 = 15 → no third) | DI = 32 → "Well-differentiated" | Checks pass; pairs 0/1 → **Valid**

### Expected vs computed — **MATCH**
MEN+GRD exactly; scores compressed to the 33–65 band as intended.

### What it reveals
- The instrument classified her correctly, but labeled a self-doubt-compressed profile "Well-differentiated" (DI=32) purely because anxious PIO under-endorsement (33) stretched the bottom. A confidence-suppressed profile and a robust one produce indistinguishable DI values — DI conflates trait differentiation with response-style depression of single scales.
- Report-language risk confirmed: her top score (65) is only "Strong Resonance," bottom-band adjacent; nothing in the scoring output distinguishes "modest interests" from "modest self-belief."

---

## Persona 05 — Arjun Nair (21, India, mech-eng student, robotics lead)

### Response sheet
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 4 | 14 | 5 | 27 | 4 | 40 | 4 | 53 | 2 |
| 2 | 5 | 15 | 4 | 28 | 1 | 41 | 4 | 54 | 3 |
| 3 | 4 | 16 | 3 | 29 | 3 | 42 | 5 | 55 | 2 |
| 4 | 5 | 17 | **4** | 30 | 4 | 43 | 2 | 56 | 4 |
| 5 | 2 | 18 | 4 | 31 | 3 | 44 | 3 | 57 | 4 |
| 6 | 3 | 19 | 3 | 32 | 4 | 45 | 3 | 58 | 3 |
| 7 | 5 | 20 | 4 | 33 | **1** | 46 | 5 | 59 | 4 |
| 8 | 3 | 21 | 3 | 34 | 3 | 47 | 3 | 60 | 5 |
| 9 | 5 | 22 | 4 | 35 | 5 | 48 | 5 | 61 | 4 |
| 10 | 4 | 23 | 4 | 36 | 3 | 49 | **3** | 62 | 4 |
| 11 | 4 | 24 | 2 | 37 | 4 | 50 | 2 | 63 | 3 |
| 12 | 4 | 25 | 3 | 38 | 4 | 51 | 3 | 64 | 4 |
| 13 | 5 | 26 | 4 | 39 | 2 | 52 | 2 | 65 | 2 |

Key rationales: EXP near-ceiling with clean reverses (Q28=1, Q55=2); MAK 5s on build/tools/tinker; PIO selective — leads the club (Q12=4, Q37=4, Q64=4, Q18=4 exam-culture competition) but hates selling (Q5=2, Q44=3); Q50=2 (would leave a "stable" job for a challenge). Minor inconsistencies: Q16=3 vs Q22=4; Q59=4 (inventing energizes) vs mid VIS elsewhere.

### Computed
- Raw: MAK 45, EXP 47, VIS 33, MEN 35, PIO 35, GRD 34
- Spectrum: **EXP 93, MAK 88, MEN 63, PIO 63, GRD 60, VIS 57*** (MEN/PIO exact tie at rank 3; *VIS 57 is the fp artifact — documented half-up rounding gives 58)
- Dominant: **EXP + MAK** (gap23 = 25) | DI = 36 | Checks pass; pairs 0/0 → **Valid**

### Expected vs computed — **MATCH**
EXP+MAK exactly ("The Diagnostician," RI — the engineering pair). Note: expected "PIO tertiary" — computed has MEN and PIO tied at 63, with naive sort listing MEN third; no dominance consequence (gap 25), but a report that names the "third strand" would print MEN by dict-order accident.

### What it reveals
- Clean strong signal handled well; ranks 1–2 unambiguous.
- Exact mid-table ties are common with 10-item scales (3 of 10 personas in this batch produced at least one); every downstream display decision inherits arbitrary sort order.
- Raw 33 → 57 vs 58: first sighting of the rounding defect (cosmetic here).

---

## Persona 06 — Siobhan Gallagher (23, Ireland, new staff nurse)

### Response sheet
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 5 | 14 | 3 | 27 | 5 | 40 | 4 | 53 | 2 |
| 2 | 3 | 15 | 5 | 28 | 3 | 41 | 5 | 54 | 1 |
| 3 | 3 | 16 | 4 | 29 | 2 | 42 | 4 | 55 | 4 |
| 4 | 4 | 17 | **4** | 30 | 4 | 43 | 2 | 56 | 4 |
| 5 | 2 | 18 | 2 | 31 | 3 | 44 | 4 | 57 | 4 |
| 6 | 2 | 19 | 2 | 32 | 4 | 45 | 2 | 58 | 4 |
| 7 | 4 | 20 | 3 | 33 | **1** | 46 | 4 | 59 | 3 |
| 8 | 5 | 21 | 1 | 34 | 5 | 47 | 5 | 60 | 2 |
| 9 | 3 | 22 | 4 | 35 | 4 | 48 | 3 | 61 | 4 |
| 10 | 4 | 23 | 3 | 36 | 3 | 49 | **3** | 62 | 2 |
| 11 | 3 | 24 | 4 | 37 | 2 | 50 | 4 | 63 | 4 |
| 12 | 3 | 25 | 3 | 38 | 2 | 51 | 2 | 64 | 3 |
| 13 | 4 | 26 | 4 | 39 | 2 | 52 | 2 | 65 | 3 |

Key rationales: MEN ceiling-adjacent with the diagnostic reverse pattern — **Q54=1 (helping does NOT exhaust her)**, Q21=1; the designed valid split: **Q63=4 (paperwork drains) while Q10=4 and Q56=4 (checking details still endorsed)** — non-contradictory and the pair stays coherent; hands-on clinical MAK (Q7, Q26, Q32, Q46 = 4); Q30=4 ward pace (mild inconsistency with low PIO elsewhere); Q55=4 (wants the quick practical answer — nurse pragmatism, dents EXP honestly).

### Computed
- Raw: MAK 35, EXP 32, VIS 27, MEN 48, PIO 24, GRD 36
- Spectrum: **MEN 95, GRD 65, MAK 63, EXP 55, VIS 43, PIO 35**
- Dominant: **MEN + GRD + MAK** (3-way; gap23 = 2) | DI = 60 | Checks pass; pairs 0/0 → **Valid**

### Expected vs computed — **MATCH**
MEN+GRD with GRD at exactly the predicted 55–65 (65), MAK tertiary picked up by the ≤10 rule. The NRG facet architecture worked: Q63 subtraction kept GRD moderate instead of high, without corrupting the consistency pair.

### What it reveals
- Best-case demonstration of the reverse-item design: "helping energizes / charting drains" is representable and scored sensibly.
- "The Anchor" (MEN+GRD, SC) plus Maker third describes ward nursing accurately — a convergent-validity win.

---

## Persona 07 — Mateusz Zieliński (24, Poland, electrician planning a firm)

### Response sheet
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 4 | 14 | 5 | 27 | 4 | 40 | 4 | 53 | 1 |
| 2 | 5 | 15 | 4 | 28 | 3 | 41 | 4 | 54 | 3 |
| 3 | 3 | 16 | 4 | 29 | 3 | 42 | 4 | 55 | 4 |
| 4 | 4 | 17 | **4** | 30 | 4 | 43 | 2 | 56 | 4 |
| 5 | 4 | 18 | 4 | 31 | 4 | 44 | 2 | 57 | 4 |
| 6 | 2 | 19 | 2 | 32 | 5 | 45 | 3 | 58 | 2 |
| 7 | 5 | 20 | 5 | 33 | **1** | 46 | 5 | 59 | 4 |
| 8 | 3 | 21 | 2 | 34 | 3 | 47 | 3 | 60 | 4 |
| 9 | 3 | 22 | 4 | 35 | 4 | 48 | 4 | 61 | 4 |
| 10 | 4 | 23 | 2 | 36 | 4 | 49 | **3** | 62 | 2 |
| 11 | 3 | 24 | 2 | 37 | 5 | 50 | 3 | 63 | 3 |
| 12 | 4 | 25 | 3 | 38 | 3 | 51 | 4 | 64 | 5 |
| 13 | 4 | 26 | 5 | 39 | 1 | 52 | 2 | 65 | 2 |

Key rationales: MAK 49/50 (only Q60=4 — takes things apart for work, not fun); PIO exactly as briefed: Q37=5, Q64=5, Q18=4, Q24=2 (prefers leading), all three reverses correctly rejected (Q44=2, Q58=2); GRD moderate via codes/invoicing (Q36=4, Q57=4) but Q50=3 (leaving stable employment to found a firm — authentic tension); minor inconsistencies: Q59=4 (inventing solutions energizes) vs VIS otherwise low; Q55=4 (practical-answer bias) vs Q35=4.

### Computed
- Raw: MAK 49, EXP 32, VIS 28, MEN 36, PIO 42, GRD 36
- Spectrum: **MAK 98, PIO 80, MEN 65, GRD 65, EXP 55, VIS 45** (MEN/GRD exact tie at rank 3)
- Dominant: **MAK + PIO** (gap23 = 15 → no third) | DI = 53 | Checks pass; pairs 0/0 → **Valid**

### Expected vs computed — **MATCH**
MAK+PIO ("The Groundbreaker," RE — service-business ownership: literally his plan). Expected GRD tertiary; computed has GRD tied with MEN at 65 and neither included (gap 15). The naive sort would report MEN as rank 3 (dict order), so even the near-miss "third strand" narrative would name the wrong avatar relative to expectation — harmless here, undefined behavior in general.

### What it reveals
- Trades+enterprise blend detected without forcing MAK-only: key combination-profile success.
- Second demonstration that rank-3 exact ties are frequent and unhandled below the dominance window.

---

## Persona 08 — Chloe Bennett (26, Australia, SaaS account executive)

### Response sheet
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 4 | 14 | 2 | 27 | 4 | 40 | 5 | 53 | 3 |
| 2 | 2 | 15 | 4 | 28 | 5 | 41 | 5 | 54 | 2 |
| 3 | 2 | 16 | 2 | 29 | 4 | 42 | 2 | 55 | 5 |
| 4 | 2 | 17 | **4** | 30 | 5 | 43 | 4 | 56 | 2 |
| 5 | 5 | 18 | 5 | 31 | 2 | 44 | 1 | 57 | 2 |
| 6 | 3 | 19 | 4 | 32 | 3 | 45 | 4 | 58 | 1 |
| 7 | 2 | 20 | 3 | 33 | **1** | 46 | 3 | 59 | 3 |
| 8 | 4 | 21 | 1 | 34 | 3 | 47 | 3 | 60 | 1 |
| 9 | 2 | 22 | 3 | 35 | 3 | 48 | 3 | 61 | 4 |
| 10 | 2 | 23 | 1 | 36 | 2 | 49 | **3** | 62 | 1 |
| 11 | 4 | 24 | 1 | 37 | 4 | 50 | 1 | 63 | 5 |
| 12 | 5 | 25 | 3 | 38 | 3 | 51 | 5 | 64 | 5 |
| 13 | 3 | 26 | 3 | 39 | 4 | 52 | 4 | 65 | 2 |

Key rationales: PIO 49/50 — Q51=5 (the close), Q30=5, Q18=5, all reverses maximally rejected (Q24=1, Q44=1, Q58=1); **EXP reverses endorsed as designed: Q28=5, Q55=5** plus Q23=1, Q62=1 → EXP floor; people-energy MEN (Q40=5, Q21=1) with only moderate counseling ACT (Q34=3); Q45=4 slightly inconsistent with Q19=4 (likes freedom but wants the playbook — sales-process reality); Q52=4 personal brand.

### Computed
- Raw: MAK 24, EXP 19, VIS 34, MEN 40, PIO 49, GRD 19
- Spectrum: **PIO 98, MEN 75, VIS 60, MAK 35, EXP 23, GRD 23** (EXP/GRD bottom tie)
- Dominant: **PIO + MEN** (gap23 = 15 → no third) | DI = 75 | Checks pass; pairs 1/0 → **Valid**
- Longest identical run: 4 → long-string screen clear.

### Expected vs computed — **MATCH**
PIO+MEN exactly ("The Motivator," SE); EXP and GRD correctly floored at 23. The EXP reverse items did their discriminant job on a low-Investigative extravert.

### What it reveals
- Near-ceiling PIO (raw 49 → 98): 0–100 scaling retains headroom for honest superlatives, but this is the third 95+ score in eight personas — top-band compression is systematic for strong-identity respondents.
- VIS at 60, only 15 from MEN: pitch-deck creativity leaks into VIS; had she rated Q25/Q59 one point higher, a spurious third dominant would have fired.

---

## Persona 09 — Tendai Chikwava (28, Zimbabwe, disillusioned PhD, loves tutoring)

### Response sheet
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 5 | 14 | 2 | 27 | 4 | 40 | 3 | 53 | 4 |
| 2 | 2 | 15 | 5 | 28 | 3 | 41 | 5 | 54 | 2 |
| 3 | 3 | 16 | 3 | 29 | 3 | 42 | 4 | 55 | 3 |
| 4 | 4 | 17 | **4** | 30 | 2 | 43 | 3 | 56 | 3 |
| 5 | 3 | 18 | 2 | 31 | 2 | 44 | 4 | 57 | 3 |
| 6 | 3 | 19 | 3 | 32 | 2 | 45 | 3 | 58 | 4 |
| 7 | 2 | 20 | 2 | 33 | **1** | 46 | 3 | 59 | 2 |
| 8 | 4 | 21 | 3 | 34 | 4 | 47 | 5 | 60 | 2 |
| 9 | 4 | 22 | 3 | 35 | 3 | 48 | 2 | 61 | 5 |
| 10 | 3 | 23 | 4 | 36 | 2 | 49 | **3** | 62 | 2 |
| 11 | 3 | 24 | 4 | 37 | 2 | 50 | 3 | 63 | 4 |
| 12 | 2 | 25 | 2 | 38 | 3 | 51 | 2 | 64 | 2 |
| 13 | 4 | 26 | 3 | 39 | 4 | 52 | 2 | 65 | 3 |

Key rationales: MEN teaching identity — **Q1=5, Q41=5 (pair coherent by design), Q61=5, Q47=5, Q54=2**; EXP state-vs-trait split exactly as briefed: ACT items 4 (Q4, Q9, Q13, Q42, Q23) but NRG/stamina items suppressed (**Q48=2, Q62=2, Q35=3** — four years on one question killed the romance); burnout inconsistency Q23=4 vs Q62=2 is the diagnostic signature; PIO reverses endorsed from depletion (Q44=4, Q58=4).

### Computed
- Raw: MAK 22, EXP 33, VIS 28, MEN 42, PIO 21, GRD 28
- Spectrum: **MEN 80, EXP 57*, VIS 45, GRD 45, MAK 30, PIO 28** (*fp artifact: documented rounding gives 58; VIS/GRD exact tie)
- Dominant: **MEN + EXP** (gap23 = 12 → no third) | DI = 52 | Checks pass; pairs 0/0 → **Valid**

### Expected vs computed — **MATCH**
MEN+EXP in the required order (MEN first, 80 vs 57/58) — the report would correctly lead with Mentor. "The Healer" (IS: teaching/counseling/health education) points him at exactly the pivot he is contemplating.

### What it reveals
- The gap23=12 nearly admitted VIS/GRD as a third dominant (threshold 10); had the rounding bug gone the other way (EXP 58 → gap 13) nothing changes, but at EXP=56 vs 55 this persona would flip between 2 and 3 dominants — the 1-point rounding defect is materially close to a decision boundary here.
- Facet structure encodes his burnout (EXP ACT high, NRG low) but the scoring output discards facet detail — the most clinically useful signal in his protocol is computed away in the scale sum.

---

## Persona 10 — Larissa Fontes (29, Brazil, startup generalist)

### Response sheet
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 4 | 14 | 3 | 27 | 4 | 40 | 5 | 53 | 3 |
| 2 | 2 | 15 | 4 | 28 | 4 | 41 | 4 | 54 | 3 |
| 3 | 3 | 16 | 1 | 29 | 5 | 42 | 4 | 55 | 4 |
| 4 | 4 | 17 | **4** | 30 | 5 | 43 | 5 | 56 | 3 |
| 5 | 4 | 18 | 3 | 31 | 1 | 44 | 2 | 57 | 2 |
| 6 | 4 | 19 | 5 | 32 | 3 | 45 | 1 | 58 | 1 |
| 7 | 3 | 20 | 2 | 33 | **1** | 46 | 3 | 59 | 5 |
| 8 | 4 | 21 | 2 | 34 | 4 | 47 | 4 | 60 | 2 |
| 9 | 3 | 22 | 3 | 35 | 4 | 48 | 3 | 61 | 4 |
| 10 | 2 | 23 | 2 | 36 | 2 | 49 | **3** | 62 | 1 |
| 11 | 5 | 24 | 2 | 37 | 5 | 50 | 1 | 63 | 5 |
| 12 | 4 | 25 | 4 | 38 | 5 | 51 | 4 | 64 | 4 |
| 13 | 4 | 26 | 3 | 39 | 4 | 52 | 4 | 65 | 2 |

Key rationales: designed GRD demolition — **Q29=5 (loves unplanned days), Q43=5 (improvises), Q63=5, Q16=1, Q50=1**; VIS high with Q45=1 as briefed; PIO ownership (Q37=5, Q64=4, Q58=1) but Q18=3 (collaborative, not competitive); MEN people-energy (Q40=5, Q27=4); O-very-high curiosity keeps EXP mid (Q4/Q13/Q42=4) while Q62=1/Q28=4 (variety-seeker cannot sit with one question — authentic inconsistency with Q42=4).

### Computed
- Raw: MAK 26, EXP 29, VIS 46, MEN 40, PIO 42, GRD 17
- Spectrum: **VIS 90, PIO 80, MEN 75, EXP 48, MAK 40, GRD 18**
- Dominant: **VIS + PIO + MEN** (3-way; gap23 = 5) | DI = 72 | Checks pass; pairs 0/1 → **Valid**
- Longest identical run: 3 → clear.

### Expected vs computed — **MATCH**
Expected 3-way PIO+VIS+MEN; computed 3-way with the same set (VIS leading). The 2-vs-3 logic triggered correctly for a genuine generalist. GRD 18 vs VIS 90 confirms the reverse-worded GRD items can drive a true floor without response-style artifacts.

### What it reveals
- The tertiary-avatar threshold behaves as intended on its designed target case.
- The report must now render "Creative Director + Motivator" simultaneously; with a lead-avatar swap (VIS vs PIO first), the primary combination profile chosen ("VIS+PIO" vs "PIO+VIS" — same cell here, but pair naming is order-insensitive only because the JSON has 15 unordered pairs; which pair among the three (VIS+PIO, VIS+MEN, PIO+MEN) is "primary" for a 3-way profile is not specified anywhere.

---

## Batch A scoreboard

| # | Persona | Expected | Computed dominants | Spectrum (MAK/EXP/VIS/MEN/PIO/GRD) | DI | Verdict | Result |
|---|---|---|---|---|---|---|---|
| 01 | Noah | ~MAK+EXP weak | MAK+VIS+MEN | 63/48/53/50/43/33 | 30 | Valid | **MISS** |
| 02 | Bianca | MAK+GRD (EXP 3rd) | MAK+EXP+GRD | 100/70/38/40/28/65 | 72 | Valid | **PARTIAL** |
| 03 | Kaito | VIS+EXP (+MAK) | VIS+EXP+MAK | 60/68/100/33/20/20 | 80 | Valid | MATCH |
| 04 | Destiny | MEN+GRD | MEN+GRD | 40/40/48/65/33/63 | 32 | Valid | MATCH |
| 05 | Arjun | EXP+MAK | EXP+MAK | 88/93/57*/63/63/60 | 36 | Valid | MATCH |
| 06 | Siobhan | MEN+GRD (+MAK) | MEN+GRD+MAK | 63/55/43/95/35/65 | 60 | Valid | MATCH |
| 07 | Mateusz | MAK+PIO | MAK+PIO | 98/55/45/65/80/65 | 53 | Valid | MATCH |
| 08 | Chloe | PIO+MEN | PIO+MEN | 35/23/60/75/98/23 | 75 | Valid | MATCH |
| 09 | Tendai | MEN+EXP | MEN+EXP | 30/57*/45/80/28/45 | 52 | Valid | MATCH |
| 10 | Larissa | 3-way PIO+VIS+MEN | VIS+PIO+MEN | 40/48/90/75/80/18 | 72 | Valid | MATCH |

\* fp rounding artifact: raw 33 → naive 57, documented rule → 58.

**Accuracy: 8/10 exact, 1 partial (set correct, rank 2/3 swapped), 1 miss.**

## Instrument findings from Batch A

1. **Midpoint inflation in low-information respondents (P01).** A stack of "don't know" 3s scores 50/100 per scale; for a 16-year-old the dominance algorithm promoted two midpoint-heavy scales (VIS, MEN) into a 3-way dominant set while the true-but-impatience-penalized EXP fell out. The instrument cannot distinguish "neutral because unknown" from "moderately interested."
2. **DI (max−min) mislabels profile quality (P01, P04).** Both a weakly-formed adolescent profile (DI=30) and a confidence-compressed profile (DI=32) were certified "Well-differentiated" because one scale happened to be low. DI measures range, not top-of-profile separation; a top-3-spread metric would serve the dominance decision better.
3. **Half-up rounding is fp-fragile (P05, P09).** Raw 33 → 57.5 → naive output 57 (should be 58). Cosmetic in this batch but sits 2 points from a third-dominant boundary decision in P09.
4. **Rank-3 exact ties are frequent and behavior is undefined below the dominance window** (P05 MEN=PIO, P07 MEN=GRD, P09 VIS=GRD). Sort-order accidents would name the "nearest third strand" in reports.
5. **Reverse-item architecture largely works as intended:** it correctly floored EXP for Chloe, kept GRD moderate for Siobhan while preserving pair consistency, and floored GRD for Larissa/Kaito — but it double-charges respondents whose *stamina* (adolescence, burnout, neuroticism) rather than *interest* is low (P01 EXP, P09 EXP, P03 MAK/MEN).
6. **Ceiling frequency:** 3 of 10 honest respondents hit ≥98 on a scale (P02 MAK=100, P03 VIS=100, P07 MAK=98, P08 PIO=98). Ten items give little headroom at the top of strong-identity profiles.
7. **GRD scale is bidimensional in trades/clinical respondents (P02, P06):** procedure/precision content scores high while records/paperwork content scores low, systematically pulling GRD below competitors and (P02) demoting the expected MAK+GRD to MAK+EXP+GRD.
8. **The ≤10 third-dominant rule earned its keep** (P03 rescued the pressure-hidden true MAK; P06, P10 correct 3-ways) but also fired on noise (P01). Its value is conditional on profile elevation being meaningful.
9. **Facet information is discarded at scoring time (P09, P06):** ACT-vs-NRG splits encode state (burnout) vs trait (interest), the most interpretively valuable signal in two protocols, yet no facet output survives to the report.
