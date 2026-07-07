# MINDCROUD Career Spectrum — Validation Batch B (Personas 11–20)

Simulated administration and scoring per `data/scoring.json` and Section 6 of `MINDCROUD-Career-Spectrum.md`.
Scoring script: `score_batch_B.py` (same directory). All 10 profiles passed all attention checks (by persona design — none of the 11–20 personas is a careless-responding case), so validity mechanisms in this batch exercise consistency pairs, ceiling/floor behavior, tie-breaking, third-dominant thresholds, and rounding.

**Batch classification accuracy: 8/10** (misses: Persona 12, Persona 14 — both caused by the third-dominant ≤10-point rule sweeping in an avatar the persona design did not intend as dominant).

**Implementation notes discovered while scoring (apply to every persona below):**

1. **Half-up rounding is silently broken for raw = 33.** `(33-10)/40*100` evaluates in IEEE-754 float as `57.49999999999999`, so both a naive `round()` and even an explicit `floor(x+0.5)` half-up produce **57**, while the documented rule (57.5 → 58) requires **58**. Raw values 27, 29, 31, 35, 37, … happen to produce exact `.5` floats and round correctly; raw 33 does not. Affected in this batch: P11 (PIO), P13 (GRD), P14 (GRD), P19 (EXP), P20 (EXP) — each reported 57 where the spec demands 58. No dominant sets changed here, but a 1-point error at a 10-point threshold boundary is a live risk.
2. **Banker's rounding vs documented half-up.** Python's builtin `round()` (used by any truly naive implementation) rounds half-to-even: e.g., raw 27 → 42.5 → `round()` gives 42, spec says 43; raw 47 → 92.5 → 92 vs 93. Nine of ten personas in this batch had at least one scale where `round()` disagrees with the documented rule. The spec text is clear ("round half up") but `scoring.json`'s bare `"formula": "round(...)"` invites the wrong builtin.
3. **Verdict-rule ambiguity.** The docs define caution ("1 attention failure", pair diff of 2 = "mild inconsistency") and invalid conditions, but never state whether a mild pair inconsistency or a flat-profile flag counts as a "caution-level signal" for the combined verdict. My implementation counted pair-diff==2 as caution and excluded the flat-profile flag from the validity verdict. Not triggered in this batch (all pairs ≤1, no flat profiles), but it is undefined behavior in the spec.
4. **Tie handling is naive sort-order dependent.** For exact ties (P20: PIO=GRD=68 at ranks 2/3), a stable descending sort resolves rank order by scale-dictionary insertion order (MAK, EXP, VIS, MEN, PIO, GRD) — PIO lands at "rank 2" purely because it precedes GRD in the JSON. Here the outcome is the same either way (score₂−score₃ = 0 ≤ 10, so both enter), and Section 6.5's rank-1/2 tie rule agrees ("both are Dominant"). But no output distinguishes "tied" from "ranked" — the report would print an ordered list implying PIO > GRD.

Legend for response sheets: `Q#=raw` ; `(r)` = reverse-scored item; check items marked ✓.

---

## Persona 11: Emeka Obi — maths teacher weighing school administration

**Expected:** MEN + GRD dominant; PIO borderline third.

### Response sheet
```
Q1=5  Q2=3  Q3=4  Q4=4  Q5=4  Q6=2  Q7=3  Q8=5  Q9=3  Q10=4
Q11=3 Q12=4 Q13=3 Q14=3 Q15=5 Q16=4 Q17=4✓ Q18=2 Q19=2 Q20=2
Q21=2(r) Q22=4 Q23=3 Q24=2(r) Q25=3 Q26=3 Q27=4 Q28=2(r) Q29=2(r) Q30=2
Q31=4(r) Q32=2 Q33=1✓ Q34=4 Q35=3 Q36=4 Q37=3 Q38=3 Q39=4(r) Q40=4
Q41=5 Q42=4 Q43=2(r) Q44=2(r) Q45=4(r) Q46=4 Q47=5 Q48=3 Q49=3✓ Q50=4
Q51=4 Q52=2 Q53=3(r) Q54=1(r) Q55=3(r) Q56=4 Q57=4 Q58=4(r) Q59=3 Q60=2
Q61=5 Q62=2 Q63=2(r) Q64=4 Q65=2(r)
```
Key rationales: Q1/Q41 = 5/5 (teaching is his identity); Q54 = 1 (a day of helping students would NOT exhaust him — 10 years prove it); Q12/Q64 = 4 (wants institutional leadership) but Q18/Q30 = 2 (competition and speed are not why — administrative, not entrepreneurial, leadership); GRD steady 4s (marking registers, schemes of work). Intentional minor inconsistencies: Q65=2 (creating doesn't drain him despite low VIS — lesson design), Q46=4 (fixing pride despite low MAK), Q13=3 (a maths teacher neutral on science reading — he reads pedagogy, not tech).

### Scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 27 | 32 | 26 | 46 | 33 | 40 |
| Spectrum | 43 | 55 | 40 | **90** | 57* | **75** |

*PIO 57 is the raw-33 float bug; spec half-up gives 58. Does not change the outcome.

- **Dominant (computed): MEN + GRD** — matches expected. Third-ranked PIO at 57/58 is 17–18 points behind GRD, so the "borderline third" the persona design predicted is in fact clearly excluded; the instrument answered his real counseling question (administrative vs entrepreneurial leadership) correctly by keeping PIO out.
- DI = 50 (Well-differentiated). Attention 3/3, pairs 0/0. **Verdict: Valid.**
- **Expected vs computed:** match. Note the persona file called PIO "borderline"; at these authentic response levels it isn't — the 10-point third-avatar window is narrower than intuition suggests.

**What this reveals:** The PIO scale successfully separates "wants responsibility" (Q12, Q64 high) from "wants competition/pace" (Q18, Q30 low) — good internal facet spread. But the report machinery discards PIO entirely at rank 3 +17, even though PIO 57–58 vs EXP 55 is the interpretively relevant contrast for this client. A 2-dominant report hides the very tension he took the test to resolve.

---

## Persona 12: Anneke Visser — financial controller, single-peak Guardian, skeptical taker

**Expected:** GRD + EXP (distant, weak second ~45); tests whether a forced second dominant overstates a weak avatar.

### Response sheet
```
Q1=3  Q2=2  Q3=5  Q4=3  Q5=2  Q6=1  Q7=2  Q8=3  Q9=3  Q10=5
Q11=2 Q12=2 Q13=2 Q14=2 Q15=3 Q16=5 Q17=4✓ Q18=2 Q19=1 Q20=1
Q21=4(r) Q22=5 Q23=4 Q24=4(r) Q25=2 Q26=3 Q27=3 Q28=2(r) Q29=1(r) Q30=2
Q31=5(r) Q32=2 Q33=1✓ Q34=3 Q35=3 Q36=5 Q37=2 Q38=2 Q39=4(r) Q40=2
Q41=3 Q42=3 Q43=1(r) Q44=4(r) Q45=5(r) Q46=3 Q47=2 Q48=2 Q49=3✓ Q50=5
Q51=3 Q52=2 Q53=4(r) Q54=3(r) Q55=3(r) Q56=5 Q57=5 Q58=5(r) Q59=2 Q60=1
Q61=3 Q62=2 Q63=1(r) Q64=2 Q65=3(r)
```
Key rationales: All GRD at ceiling including all three reverse items correctly rejected (Q29=1, Q43=1, Q63=1); Q45=5 (genuinely wants every step decided in advance → VIS coded 1); Q10/Q56 = 5/5 (pair coherent at ceiling); EXP only lifted by analysis-adjacent items (Q23=4, Q28 disagreed). Intentional minor inconsistencies: Q26=3 (mildly likes visible results), Q51=3 (closing the annual accounts is a small win), Q65=3 (neutral, skeptical shrug).

### Scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 20 | 29 | 17 | 27 | 20 | 50 |
| Spectrum | 25 | 48 | 18 | 43 | 25 | **100** |

- **Dominant (computed): GRD + EXP + MEN** — score₂ − score₃ = 48 − 43 = 5 ≤ 10, so MEN (43, "Moderate Resonance", barely) is promoted to a third **Dominant** avatar.
- DI = 82 (Well-differentiated). Attention 3/3, pairs 0/0. **Verdict: Valid.** Exact tie MAK=PIO=25 at ranks 4/5 (harmless, but sort-order decides printed order).
- **Expected vs computed: MISMATCH.** Expected 2 dominants (GRD + weak EXP); rule produced 3. Why: the ≤10-point window is anchored to score₂, not to any absolute strength floor. When the second avatar is itself weak (48), anything mediocre within 10 points rides in.

**What this reveals:** The core weakness of the dominant-avatar rule for single-peak profiles. Anneke is a 100-vs-everything-else person; the instrument reports *three* "Dominant" avatars, two of which are sub-50 (below "Moderate Resonance" midline). A report telling a contented, precision-driven controller that "The Mentor" is one of her dominant career avatars overstates a 43. The rule needs an absolute floor (e.g., dominant only if ≥ some band) or must label ranks 2–3 as "secondary" when they fall ≥30 points behind rank 1.

---

## Persona 13: Amanda Foster-Reyes — teacher → junior developer (career changer, frame confusion)

**Expected:** MEN + EXP; result should validate the pivot.

### Response sheet
```
Q1=5  Q2=2  Q3=4  Q4=5  Q5=3  Q6=4  Q7=3  Q8=4  Q9=5  Q10=4
Q11=4 Q12=3 Q13=4 Q14=3 Q15=5 Q16=3 Q17=4✓ Q18=2 Q19=3 Q20=2
Q21=3(r) Q22=4 Q23=4 Q24=3(r) Q25=3 Q26=3 Q27=4 Q28=1(r) Q29=3(r) Q30=3
Q31=2(r) Q32=2 Q33=1✓ Q34=4 Q35=5 Q36=3 Q37=4 Q38=4 Q39=4(r) Q40=4
Q41=5 Q42=4 Q43=3(r) Q44=4(r) Q45=3(r) Q46=4 Q47=4 Q48=5 Q49=3✓ Q50=3
Q51=3 Q52=3 Q53=4(r) Q54=3(r) Q55=2(r) Q56=4 Q57=4 Q58=4(r) Q59=3 Q60=2
Q61=5 Q62=3 Q63=4(r) Q64=3 Q65=2(r)
```
Key rationales: Q1/Q41 = 5/5 — teaching identity is stable across the career change, passing QA exactly as the persona design predicted despite mixed temporal frames. Q4/Q9/Q35/Q48 = 5 (the new love: debugging as detective work); Q28=1 (long detailed analysis is the job now and she likes it); Q54=3 honest ambivalence after 12 classroom years. Frame-confusion artifacts kept in deliberately: Q62=3 (answers from teacher frame — "long single question" sounds like grading) vs Q23=4 (developer frame); Q37=4 (she DID start a bootcamp leap) vs otherwise low PIO; Q46=4 despite low MAK (fixing broken code feels like fixing).

### Scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 25 | 44 | 35 | 41 | 28 | 33 |
| Spectrum | 38 | **85** | 63 | **78** | 45 | 57* |

*GRD raw 33 → spec 58, float bug output 57.

- **Dominant (computed): EXP + MEN** — matches expected (order reversed: EXP leads). Third VIS 63 misses by exactly the boundary: 78 − 63 = 15 > 10.
- DI = 47 (Well-differentiated). Attention 3/3, pairs 0/0. **Verdict: Valid.**
- **Expected vs computed:** match. EXP > MEN ordering actually *strengthens* the guidance value — the report leads with the new direction, validating the pivot.

**What this reveals:** The instrument handled the hardest interpretive case in the batch well. The Q1/Q41 consistency pair measures identity-stable content, so a career changer passes QA even while answering other items from two different life frames — which is correct behavior (frame mixing is not carelessness). Her VIS 63 (BA English) sitting 15 points off inclusion shows the third-avatar cliff: at 64+ she'd have been a 3-avatar profile; nothing in the report will mention the near-miss.

---

## Persona 14: Ingrid Bakke — brand manager returning after a 7-year parenting break

**Expected:** PIO + VIS, slightly compressed; "does she still clear the dominance threshold?"

### Response sheet
```
Q1=4  Q2=2  Q3=4  Q4=4  Q5=4  Q6=4  Q7=2  Q8=3  Q9=3  Q10=3
Q11=5 Q12=4 Q13=3 Q14=3 Q15=3 Q16=3 Q17=4✓ Q18=3 Q19=4 Q20=3
Q21=2(r) Q22=4 Q23=3 Q24=2(r) Q25=4 Q26=3 Q27=4 Q28=3(r) Q29=3(r) Q30=4
Q31=2(r) Q32=3 Q33=1✓ Q34=3 Q35=4 Q36=3 Q37=4 Q38=4 Q39=4(r) Q40=4
Q41=4 Q42=4 Q43=3(r) Q44=2(r) Q45=2(r) Q46=3 Q47=3 Q48=3 Q49=3✓ Q50=3
Q51=4 Q52=5 Q53=3(r) Q54=3(r) Q55=3(r) Q56=4 Q57=4 Q58=3(r) Q59=4 Q60=1
Q61=4 Q62=2 Q63=3(r) Q64=3 Q65=2(r)
```
Key rationales: ACT/interest items confident (Q11=5, Q52=5 — brand craft survived the break); ENV items pulled to 3 as designed (Q16, Q23, Q50 — "I don't know what offices are like now"); PIO dented where pre-break she'd have said 5: Q64=3 ("responsible for the success of a business" feels big right now), Q18=3, Q58=3. Intentional inconsistencies: Q10=3 but Q56=4 (pair diff 1 — passes); Q22=4 planning satisfaction vs Q29/Q43 neutral.

### Scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 25 | 32 | 42 | 35 | 37 | 33 |
| Spectrum | 38 | 55 | **80** | 63 | **68** | 57* |

*GRD raw 33 → spec 58, float output 57.

- **Dominant (computed): VIS + PIO + MEN** — 68 − 63 = 5 ≤ 10 pulls MEN in as third.
- DI = 42 (Well-differentiated — the flat-profile flag does NOT fire despite compression). Attention 3/3, pairs 0/1. **Verdict: Valid.**
- **Expected vs computed: MISMATCH (partial).** VIS + PIO both dominate as designed — she "clears the threshold" — but confidence-driven compression of the middle band (MEN 63, GRD 57–58, EXP 55 all within 8 points) drags MEN into the dominant set. Her MEN is sociability, not vocational service orientation.

**What this reveals:** Score compression from self-doubt doesn't trip any flag (DI still 42 because MAK floors at 38... actually 80−38), yet it materially changes the *classification*: the third-dominant window is much more likely to trigger in compressed profiles, so returning professionals systematically get noisier 3-avatar reports precisely when their confidence is lowest. The DI (max−min) is blind to mid-band bunching; a top-3 spread statistic would catch this.

---

## Persona 15: Dragan Kovačević — CNC master machinist promoted to supervisor, misses the machines

**Expected:** MAK + GRD, MEN tertiary; PIO must NOT be dominant despite his title.

### Response sheet
```
Q1=4  Q2=5  Q3=4  Q4=3  Q5=2  Q6=2  Q7=5  Q8=3  Q9=4  Q10=5
Q11=2 Q12=3 Q13=2 Q14=5 Q15=4 Q16=5 Q17=4✓ Q18=3 Q19=1 Q20=5
Q21=3(r) Q22=5 Q23=4 Q24=3(r) Q25=3 Q26=5 Q27=4 Q28=2(r) Q29=2(r) Q30=3
Q31=4(r) Q32=5 Q33=1✓ Q34=3 Q35=4 Q36=4 Q37=2 Q38=2 Q39=1(r) Q40=3
Q41=4 Q42=3 Q43=2(r) Q44=4(r) Q45=4(r) Q46=5 Q47=3 Q48=3 Q49=3✓ Q50=5
Q51=3 Q52=2 Q53=2(r) Q54=3(r) Q55=4(r) Q56=5 Q57=5 Q58=4(r) Q59=2 Q60=5
Q61=4 Q62=2 Q63=2(r) Q64=3 Q65=3(r)
```
Key rationales: MAK at near-ceiling incl. Q26=5 ("see the physical results" — the item written for him) and Q39=1 (emphatically prefers objects to ideas); Q24=3 — the designed nuance: he *took* the lead but doesn't prefer it, neutral is the honest answer; Q64=3 (responsible for team success = his current job, ambivalent); mentoring apprentices keeps MEN moderate (Q1=4, Q61=4, Q15=4). Intentional inconsistencies: Q25=3 (a perfectly machined part IS beautiful — mild VIS bleed), Q9=4 vs Q13=2 (loves solving concrete problems, never reads about tech), Q55=4 (wants the quick practical answer — pulls EXP down, consistent with trade pragmatism).

### Scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 49 | 31 | 21 | 34 | 26 | 45 |
| Spectrum | **98** | 53 | 28 | 60 | 40 | **88** |

- **Dominant (computed): MAK + GRD** — matches expected exactly. MEN third-ranked at 60 (88 − 60 = 28, excluded); PIO 40, decisively non-dominant.
- DI = 70 (Well-differentiated). Attention 3/3, pairs 0/0. **Verdict: Valid.**
- **Expected vs computed:** match, including the critical negative prediction: PIO stays out despite two years of a supervisory title.

**What this reveals:** Strong criterion behavior — the instrument sides with the heart, not the org chart. Q24's reverse framing ("prefer to follow rather than lead") lets a reluctant leader answer neutrally without either inflating or crushing PIO; the persuasion/competition items (Q5=2, Q44 agreed) do the discriminating. The MAK+GRD "Steady Hand" combination profile (skilled machine operation, QC) is nearly a literal description of the job he wants back.

---

## Persona 16: Dr. Camille Rousseau — burned-out internist exploring medical writing/teaching exits

**Expected:** EXP + VIS, MEN suppressed to mid-range by state (not trait); flags retest question.

### Response sheet
```
Q1=4  Q2=2  Q3=3  Q4=5  Q5=2  Q6=4  Q7=3  Q8=3  Q9=5  Q10=4
Q11=4 Q12=3 Q13=5 Q14=2 Q15=4 Q16=3 Q17=4✓ Q18=2 Q19=4 Q20=2
Q21=4(r) Q22=4 Q23=4 Q24=3(r) Q25=3 Q26=3 Q27=3 Q28=2(r) Q29=3(r) Q30=2
Q31=2(r) Q32=2 Q33=1✓ Q34=3 Q35=5 Q36=3 Q37=2 Q38=4 Q39=4(r) Q40=2
Q41=4 Q42=4 Q43=2(r) Q44=4(r) Q45=2(r) Q46=3 Q47=3 Q48=3 Q49=3✓ Q50=2
Q51=2 Q52=3 Q53=4(r) Q54=5(r) Q55=2(r) Q56=4 Q57=3 Q58=4(r) Q59=4 Q60=2
Q61=4 Q62=4 Q63=4(r) Q64=2 Q65=2(r)
```
Key rationales: Q54=5 — truthfully, right now, a day of helping people with problems would exhaust her (MEN NRG coded 1); Q40=2 (conversations currently drain); yet MEN ACT holds mid (Q1=4, Q61=4 — teaching/explaining intact, Q15=4 meaning survives). EXP reverent (Q4/Q9/Q13/Q35 = 5, diagnostic love intact) with one state-driven inconsistency: Q48=3 (complicated problems no longer *energize* — burnout leaks into EXP NRG too, a subtle authentic contradiction with Q35=5). VIS writing exit: Q6=4, Q11=4, Q19=4, Q59=4. Q30=2 (hospital pace is what broke her).

### Scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 23 | 43 | 38 | 29 | 22 | 31 |
| Spectrum | 33 | **83** | **70** | 48 | 30 | 53 |

- **Dominant (computed): EXP + VIS** — matches expected. Third GRD 53 (70 − 53 = 17, excluded). MEN lands at 48 — exactly the "suppressed to mid-range" the facet design predicted.
- DI = 53 (Well-differentiated). Attention 3/3, pairs 0/0. **Verdict: Valid.**
- **Expected vs computed:** match.

**What this reveals:** The facet architecture works but is invisible in the output. Her MEN ACT items average ~3.6 while MEN NRG items average ~1.7 — a textbook "still interested, currently drained" signature the item design deliberately enables — yet no scored output (spectrum, dominants, DI, verdict) surfaces facet splits. The scoring spec sums straight across facets, so the interpretively crucial ACT-vs-NRG divergence exists only in the raw data. A facet-discrepancy flag ("MEN energy far below MEN activity — consider current-state effects; recommend retest") would convert an implicit design feature into an actual clinical safeguard.

---

## Persona 17: Bernard Osei-Bonsu — district registrar, 28 years civil service, proud Conventional

**Expected:** GRD + MEN; Guardian must read as a strength.

### Response sheet
```
Q1=4  Q2=3  Q3=5  Q4=3  Q5=2  Q6=1  Q7=2  Q8=4  Q9=3  Q10=5
Q11=2 Q12=3 Q13=2 Q14=2 Q15=4 Q16=5 Q17=4✓ Q18=1 Q19=1 Q20=2
Q21=2(r) Q22=5 Q23=4 Q24=5(r) Q25=2 Q26=3 Q27=4 Q28=2(r) Q29=1(r) Q30=1
Q31=5(r) Q32=2 Q33=1✓ Q34=4 Q35=3 Q36=5 Q37=2 Q38=2 Q39=3(r) Q40=4
Q41=4 Q42=3 Q43=1(r) Q44=4(r) Q45=5(r) Q46=4 Q47=4 Q48=2 Q49=3✓ Q50=5
Q51=2 Q52=2 Q53=3(r) Q54=2(r) Q55=4(r) Q56=5 Q57=5 Q58=5(r) Q59=1 Q60=1
Q61=4 Q62=2 Q63=1(r) Q64=2 Q65=4(r)
```
Key rationales: GRD perfect 50 including emphatic Q29=1/Q43=1 (unplanned days and improvisation are how records get lost) and Q63=1 (paperwork feeds him); Q24=5 — genuinely prefers serving under authority (PIO coded 1); Q18=1, Q30=1 with the suspicion the test wants otherwise; steady MEN 4s from mentoring junior clerks (Q15, Q34, Q61). Deliberate, slow, all checks passed. Intentional inconsistencies: Q12=3 (he does chair the records committee), Q46=4 (pride in fixing a broken filing system — MAK bleed), Q65=4 (creating from nothing does drain him — consistent temperament, inconsistent only with his otherwise polite 2s).

### Scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 25 | 28 | 15 | 40 | 17 | 50 |
| Spectrum | 38 | 45 | 13 | **75** | 18 | **100** |

- **Dominant (computed): GRD + MEN** — matches expected. Clean gap to third (EXP 45, −30).
- DI = 87 (Well-differentiated). Attention 3/3, pairs 0/0. **Verdict: Valid.**
- **Expected vs computed:** match. GRD hits the exact ceiling (100) — the second ceiling case in this batch.

**What this reveals:** The GRD scale reaches 100 for an authentic (non-inflating) respondent, meaning the top of the scale carries no headroom to distinguish "very high" from "the most Conventional person the scale can describe" — two personas in one batch of ten hit exact 100s (also P18 PIO), suggesting ceilings will be common for well-crystallized mid/late-career profiles. His MEN+GRD maps to "The Anchor" (SC) — people-facing coordination — a dignified and accurate frame for a registrar; the combination taxonomy passes the tone test at the data level.

---

## Persona 18: Margarethe Lindgren — divisional managing director eyeing board work

**Expected:** PIO + EXP; near-ceiling PIO tests 0–100 headroom.

### Response sheet
```
Q1=3  Q2=1  Q3=3  Q4=4  Q5=5  Q6=2  Q7=2  Q8=3  Q9=5  Q10=2
Q11=3 Q12=5 Q13=4 Q14=2 Q15=3 Q16=2 Q17=4✓ Q18=5 Q19=3 Q20=1
Q21=2(r) Q22=3 Q23=3 Q24=1(r) Q25=2 Q26=2 Q27=3 Q28=2(r) Q29=4(r) Q30=5
Q31=2(r) Q32=1 Q33=1✓ Q34=2 Q35=4 Q36=1 Q37=5 Q38=4 Q39=4(r) Q40=5
Q41=3 Q42=4 Q43=4(r) Q44=1(r) Q45=2(r) Q46=2 Q47=2 Q48=5 Q49=3✓ Q50=1
Q51=5 Q52=3 Q53=4(r) Q54=4(r) Q55=3(r) Q56=3 Q57=2 Q58=1(r) Q59=3 Q60=1
Q61=4 Q62=2 Q63=4(r) Q64=5 Q65=2(r)
```
Key rationales: All ten PIO items maxed, including strong disagreement with all three reverse items (Q24=1, Q44=1, Q58=1) — a legitimately perfect Enterprising record after 30 years of evidence. GRD gutted by delegation (Q36=1 records, Q50=1 stability, Q63=4 paperwork drains — agreeing with a reverse item as designed). EXP strategic (Q9=5, Q48=5) but impatient with depth (Q62=2, Q23=3 — speed matters; an authentic tension with Q9). Intentional inconsistencies: Q13=4 vs Q62=2 (reads about tech, won't sit with one question); Q61=4/Q40=5 (mentors leaders, loves the room) vs otherwise low-A MEN 2s; Q10=2 vs Q56=3 (pair diff 1 — passes).

### Scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 16 | 38 | 32 | 31 | 50 | 20 |
| Spectrum | 15 | **70** | 55 | 53 | **100** | 25 |

- **Dominant (computed): PIO + EXP** — matches expected. Third VIS 55 (70 − 55 = 15, excluded).
- DI = 85 (Well-differentiated). Attention 3/3, pairs 0/1. **Verdict: Valid.**
- **Expected vs computed:** match. PIO = exactly 100.

**What this reveals:** Ceiling behavior confirmed: a coherent senior executive maxes PIO with zero measurement headroom — the instrument cannot distinguish her from a merely very-Enterprising respondent, and any retest can only regress downward (guaranteed negative retest artifact at ceiling). The EXP+PIO "Strategist" (IE) pairing with management career families is apt for a board trajectory. Note VIS 55 and MEN 53 sitting 2 points apart: which appears as "third strand" in any narrative is decided by 1 response-point noise.

---

## Persona 19: Tomás Herrera — vineyard owner-operator, 40 years farming

**Expected:** MAK + GRD, EXP tertiary; Q20 must carry outdoors as Realistic.

### Response sheet
```
Q1=3  Q2=5  Q3=4  Q4=4  Q5=1  Q6=2  Q7=5  Q8=3  Q9=3  Q10=4
Q11=2 Q12=2 Q13=3 Q14=5 Q15=4 Q16=5 Q17=4✓ Q18=1 Q19=2 Q20=5
Q21=4(r) Q22=5 Q23=4 Q24=4(r) Q25=3 Q26=5 Q27=3 Q28=2(r) Q29=2(r) Q30=1
Q31=4(r) Q32=5 Q33=1✓ Q34=2 Q35=4 Q36=4 Q37=2 Q38=2 Q39=1(r) Q40=2
Q41=3 Q42=3 Q43=2(r) Q44=5(r) Q45=4(r) Q46=5 Q47=2 Q48=3 Q49=3✓ Q50=5
Q51=2 Q52=2 Q53=1(r) Q54=4(r) Q55=4(r) Q56=4 Q57=4 Q58=5(r) Q59=2 Q60=3
Q61=3 Q62=3 Q63=3(r) Q64=3 Q65=4(r)
```
Key rationales: Q20=5 — "workshop, work site, or outdoors" reads him perfectly; Q53=1 (a full day of physical work is life, not drain); Q16=5/Q22=5 (harvest IS a plan); Q44=5 (persuading people absolutely drains him → PIO coded 1), Q18=1, Q30=1. Q6/Q52 = 2 — the design/personal-style items feel alien, answered low as the persona file specifies (a mild accessibility bias data point). EXP tertiary from soil/weather diagnosis (Q4=4, Q23=4, Q35=4). Intentional inconsistencies: Q64=3 (he IS responsible for a business — grudging neutral against his floor-level PIO), Q60=3 (takes pumps apart from necessity, not joy), Q13=3 (reads agronomy bulletins, wouldn't call it "science reading").

### Scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 48 | 33 | 21 | 26 | 16 | 42 |
| Spectrum | **95** | 57* | 28 | 40 | 15 | **80** |

*EXP raw 33 → spec 58, float output 57.

- **Dominant (computed): MAK + GRD** — matches expected; EXP third-ranked at 57/58 (80 − 58 = 22, excluded, correctly "tertiary" not dominant).
- DI = 80 (Well-differentiated). Attention 3/3, pairs 0/0. **Verdict: Valid.**
- **Expected vs computed:** match.

**What this reveals:** Q20's three-way wording (workshop / work site / outdoors) successfully carries an agricultural Realistic signal — MAK 95 with no trades-shop context at all. His PIO 15 despite 40 years running a business confirms the instrument measures interest, not achievement (converging with P15's title-vs-heart result from the opposite direction). The Q6/Q52 alienation cost VIS ~4 raw points — for a low-VIS profile it's harmless, but the same wording bias would distort a rural respondent whose creativity is craft-shaped rather than "design/style"-shaped.

---

## Persona 20: Judith Aronson — retired insurance executive, SCORE volunteer mentor

**Expected:** MEN + PIO, GRD tertiary; items must work in a non-job-seeking, volunteering frame.

### Response sheet
```
Q1=5  Q2=2  Q3=4  Q4=3  Q5=4  Q6=2  Q7=2  Q8=5  Q9=4  Q10=4
Q11=3 Q12=4 Q13=3 Q14=2 Q15=5 Q16=4 Q17=4✓ Q18=3 Q19=2 Q20=2
Q21=1(r) Q22=4 Q23=3 Q24=2(r) Q25=3 Q26=3 Q27=4 Q28=3(r) Q29=3(r) Q30=3
Q31=3(r) Q32=2 Q33=1✓ Q34=4 Q35=4 Q36=4 Q37=4 Q38=3 Q39=4(r) Q40=5
Q41=5 Q42=4 Q43=2(r) Q44=2(r) Q45=3(r) Q46=3 Q47=5 Q48=4 Q49=3✓ Q50=3
Q51=4 Q52=3 Q53=4(r) Q54=2(r) Q55=3(r) Q56=5 Q57=4 Q58=3(r) Q59=3 Q60=1
Q61=5 Q62=2 Q63=3(r) Q64=4 Q65=3(r)
```
Key rationales: Q21=1 (emphatically not a lone worker), Q40=5, Q47=5 ("support other people's growth" is her whole current life), Q1/Q41 = 5/5; PIO in advisory register — Q5=4, Q37=4, Q51=4, Q64=4 (her founders' businesses), but Q18/Q30/Q58 = 3 (competitive fire banked, honestly neutral at 63); GRD 4s from compliance instincts, softened by retirement (Q50=3 — job stability no longer applies, an item-frame gap for post-career takers). Intentional inconsistencies: Q10=4 vs Q56=5 (pair diff 1), Q35=4/Q48=4 curiosity without any other EXP commitment (Q62=2), Q29=3 (volunteering made unplanned days... fine, against her GRD 4s).

### Scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 21 | 33 | 28 | 47 | 37 | 37 |
| Spectrum | 28 | 57* | 45 | **93** | **68** | **68** |

*EXP raw 33 → spec 58, float output 57.

- **Dominant (computed): MEN + PIO + GRD** — **exact tie at 68** for ranks 2/3. The naive implementation's stable sort placed PIO "above" GRD solely because PIO precedes GRD in the scales dictionary; the ≤10 rule (68 − 68 = 0) then admits the other regardless, so the dominant set is the same under any tie order. Section 6.5's tie rules cover rank-1/2 ties and the 4-dominant tie-at-rank-3 case, but are silent on how to *order* a 2/3 tie in the report narrative.
- DI = 65 (Well-differentiated). Attention 3/3, pairs 0/1. **Verdict: Valid.**
- **Expected vs computed:** match (expected MEN + PIO with GRD tertiary; the tie legitimately promotes GRD to co-third — consistent with the persona design's "GRD tertiary").

**What this reveals:** Post-career validity largely holds: MEN+PIO ("The Motivator", SE) with strong GRD is a faithful portrait of a SCORE mentor. Two instrument notes: (1) the report will print an ordered avatar list that implies PIO > GRD when they are identical — tied scores need explicit tie rendering; (2) Q50 ("stable job with clear duties") is unanswerable in-frame for a retiree — she defaulted to neutral, quietly costing GRD 1–2 points, exactly the kind of job-framed item drift the persona was built to expose.

---

## Batch B synthesis

### Classification accuracy: 8/10
| # | Persona | Expected | Computed | Match |
|---|---|---|---|---|
| 11 | Emeka Obi | MEN+GRD (PIO borderline) | MEN+GRD | YES |
| 12 | Anneke Visser | GRD+EXP | GRD+EXP+**MEN** | NO — spurious third |
| 13 | Amanda Foster-Reyes | MEN+EXP | EXP+MEN | YES |
| 14 | Ingrid Bakke | PIO+VIS | VIS+PIO+**MEN** | NO — spurious third |
| 15 | Dragan Kovačević | MAK+GRD, ¬PIO | MAK+GRD | YES |
| 16 | Camille Rousseau | EXP+VIS | EXP+VIS | YES |
| 17 | Bernard Osei-Bonsu | GRD+MEN | GRD+MEN | YES |
| 18 | Margarethe Lindgren | PIO+EXP | PIO+EXP | YES |
| 19 | Tomás Herrera | MAK+GRD | MAK+GRD | YES |
| 20 | Judith Aronson | MEN+PIO (+GRD) | MEN+PIO+GRD (tie 68/68) | YES (with tie note) |

Both failures share one mechanism: **the third-dominant window (score₂ − score₃ ≤ 10) is relative-only.** It fires for a weak second (P12: third at 43 becomes "Dominant") and for compressed mid-bands (P14: sociability-MEN at 63 rides in), while correctly staying shut for well-differentiated profiles. All 10 profiles scored Valid (by design — batch B contains no careless responders), all DIs ≥ 42, so the flat-profile and attention machinery was never the binding constraint; the dominant-selection rule was.

### Instrument weaknesses exposed by this batch
1. Third-dominant rule lacks an absolute strength floor → sub-50 "Dominant Avatars" (P12).
2. Rounding spec is implementation-fragile: float half-up silently emits 57 for raw 33 (spec: 58) in 5/10 personas; Python `round()` deviates from documented half-up on nine of ten personas.
3. Facet splits (ACT vs NRG) are the instrument's best diagnostic idea (P16 burnout signature) but no scored output exposes them.
4. Ceiling saturation: 2/10 authentic personas hit exact 100 (P17 GRD, P18 PIO); crystallized profiles will routinely max scales.
5. DI (max − min) is blind to mid-band compression that drives third-avatar noise (P14).
6. Tied spectrum scores are rendered as ordered ranks by sort accident (P20); item frames still assume employment (Q50 for retirees; Q6/Q52 register for agrarian takers).
7. Conversely, confirmed strengths: interest-over-title discrimination (P15, P19), reverse-item PIO nuance (Q24), Q20's outdoors wording, consistency pairs tolerant of legitimate frame-mixing (P13).
