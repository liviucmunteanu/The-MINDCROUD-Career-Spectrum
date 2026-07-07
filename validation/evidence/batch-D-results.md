# Batch D Results — Personas 31–40 (The MINDCROUD Career Spectrum v1.0)

Simulated validation run, 2026-07-07. Scoring implemented exactly per `data/scoring.json` (naive implementation: Python stable sort on spectrum scores descending, ties broken by scale insertion order MAK→EXP→VIS→MEN→PIO→GRD; `round((raw-10)/40*100)` half-up; reverse = 6−raw on items 21,24,28,29,31,39,43,44,45,53,54,55,58,63,65). Script: `score_batch_d.py`; machine output: `batch_d_computed.json`.

Response scale: 1=Strongly disagree … 5=Strongly agree. All ten personas were engaged, honest responders per their testing purposes: every persona passes all three attention checks (Q17=4, Q33=1, Q49=3) and both consistency pairs at diff 0–1. No long-string ≥ 12 in any sheet (max run observed: 5).

**Classification accuracy: 10/10** — every persona's computed dominant set matched the expected outcome.

---

## Persona 31: Rick Halvorsen — Enterprising anchor (sales director)

**Testing purpose:** Pure PIO anchor; PIO item-set coherence including correct reverse-item disagreement.

### Response sheet (Q1–Q65)
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 4 | 14 | 2 | 27 | 4 | 40 | 5 | 53 | 3 |
| 2 | 3 | 15 | 4 | 28 | 4 | 41 | 4 | 54 | 2 |
| 3 | 3 | 16 | 2 | 29 | 4 | 42 | 2 | 55 | 4 |
| 4 | 2 | 17 | **4** | 30 | 5 | 43 | 4 | 56 | 3 |
| 5 | 5 | 18 | 5 | 31 | 4 | 44 | 1 | 57 | 3 |
| 6 | 1 | 19 | 2 | 32 | 2 | 45 | 3 | 58 | 1 |
| 7 | 3 | 20 | 3 | 33 | **1** | 46 | 4 | 59 | 2 |
| 8 | 4 | 21 | 2 | 34 | 3 | 47 | 3 | 60 | 2 |
| 9 | 3 | 22 | 4 | 35 | 3 | 48 | 3 | 61 | 4 |
| 10 | 3 | 23 | 2 | 36 | 2 | 49 | **3** | 62 | 1 |
| 11 | 3 | 24 | 1 | 37 | 4 | 50 | 2 | 63 | 4 |
| 12 | 5 | 25 | 2 | 38 | 2 | 51 | 5 | 64 | 5 |
| 13 | 2 | 26 | 3 | 39 | 3 | 52 | 2 | 65 | 3 |

Key-item rationale: Q5/Q12/Q18/Q30/Q51/Q64 = 5 (the close, the leaderboard, team ownership — his identity). Reverse PIO items answered as a leader would: Q24=1, Q44=1 ("persuading drains me" — laughable to him), Q58=1. Q37=4 not 5 (starting projects is fine, closing them is the thrill — deliberate texture). MEN elevated via relationship selling: Q40=5 (conversations energize), Q8/Q1/Q61=4, but Q34=3 (listens to buy-signals, not personal difficulty). EXP suppressed with agree on both reverse items (Q28=4, Q55=4 — quick answers over deep analysis). Minor inconsistencies: Q46=4 (proud fixing things) vs otherwise flat MAK; Q22=4 (satisfaction from plan completion) vs low GRD elsewhere.

### Computed scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 28 | 22 | 22 | 39 | **49** | 25 |
| Spectrum | 45 | 30 | 30 | 73 | **98** | 38 |

- **Dominant: PIO + MEN** (third check: 73−45 = 28 > 10, excluded). Combination: MEN+PIO = "The Motivator" (SE) — though PIO-first ordering suggests ES; the combinations table has no ordering distinction.
- DI = 68, Well-differentiated. Attention 3/3, pairs A=0, B=0. **Verdict: Valid.**
- **Expected vs computed: MATCH** (PIO+MEN).

**What it reveals:** The PIO scale coheres perfectly for a criterion-group Enterprising respondent — all 7 positive items 4–5, all 3 reverse items 1–2, raw 49/50. Reverse items discriminate correctly rather than confusing a genuine high-scorer. Note the ceiling behavior: one honest 4 (Q37) is the only thing separating him from a perfect 100.

---

## Persona 32: Nadia Karimova — Entrepreneur, non-Western context

**Testing purpose:** PIO+VIS "venture as creation"; item framing outside Western corporate culture.

### Response sheet (Q1–Q65)
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 3 | 14 | 3 | 27 | 3 | 40 | 4 | 53 | 3 |
| 2 | 2 | 15 | 3 | 28 | 3 | 41 | 3 | 54 | 3 |
| 3 | 3 | 16 | 2 | 29 | 5 | 42 | 4 | 55 | 4 |
| 4 | 4 | 17 | **4** | 30 | 5 | 43 | 4 | 56 | 2 |
| 5 | 5 | 18 | 4 | 31 | 2 | 44 | 2 | 57 | 2 |
| 6 | 4 | 19 | 4 | 32 | 2 | 45 | 2 | 58 | 1 |
| 7 | 3 | 20 | 3 | 33 | **1** | 46 | 3 | 59 | 5 |
| 8 | 3 | 21 | 3 | 34 | 3 | 47 | 2 | 60 | 1 |
| 9 | 3 | 22 | 3 | 35 | 4 | 48 | 4 | 61 | 3 |
| 10 | 2 | 23 | 2 | 36 | 2 | 49 | **3** | 62 | 2 |
| 11 | 5 | 24 | 1 | 37 | 5 | 50 | 1 | 63 | 4 |
| 12 | 4 | 25 | 3 | 38 | 5 | 51 | 5 | 64 | 5 |
| 13 | 3 | 26 | 4 | 39 | 4 | 52 | 4 | 65 | 1 |

Key-item rationale: Q37=5, Q64=5 (founder identity), Q5/Q51=5 (deal-making with buyers and family networks), Q24=1, Q58=1. VIS as venture-creation: Q38=5 (imagining products that don't exist — her literal history), Q59=5, Q11=5, Q65=1 (creating from nothing is her energy source), but Q25=3 ("beautiful" reads decorative to her — wording gap between aesthetic and generative creativity). GRD floor: Q29=5 raw (loves that every day is different → reverse-coded 1), Q50=1 (a stable, unchanging job is her nightmare). Minor inconsistencies: Q26=4 (seeing warehouses fill is a physical result) against otherwise low MAK; Q4=4 vs Q9=3 on adjacent thinking items.

### Computed scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 26 | 31 | 43 | 30 | **47** | 20 |
| Spectrum | 40 | 53 | **83** | 50 | **93** | 25 |

- **Dominant: PIO + VIS** (third check: 83−53 = 30 > 10, excluded). Combination: VIS+PIO = "The Creative Director" (AE) — career families are ad/brand/media-centric and fit an agri-export founder poorly.
- DI = 68, Well-differentiated. Attention 3/3, pairs A=0, B=0. **Verdict: Valid.**
- **Expected vs computed: MATCH** (PIO+VIS).

**What it reveals:** The instrument correctly registers entrepreneurship-as-creation (PIO+VIS) outside Silicon Valley framing. However, the AE combination's career families ("advertising, marketing, brand," "arts/media direction") mistranslate a founder profile — there is no "Founder" archetype in the 15 combinations, so the closest label misdescribes her actual work. VIS item Q25 ("making something beautiful") under-captures generative, non-aesthetic creativity.

---

## Persona 33: Heinrich Baumgartner — Conventional anchor (audit partner)

**Testing purpose:** Pure GRD anchor; GRD coherence at ceiling; Q10/Q56 pair at ceiling.

### Response sheet (Q1–Q65)
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 2 | 14 | 2 | 27 | 2 | 40 | 2 | 53 | 4 |
| 2 | 3 | 15 | 3 | 28 | 1 | 41 | 2 | 54 | 5 |
| 3 | 5 | 16 | 5 | 29 | 1 | 42 | 4 | 55 | 2 |
| 4 | 4 | 17 | **4** | 30 | 1 | 43 | 1 | 56 | **5** |
| 5 | 2 | 18 | 2 | 31 | 5 | 44 | 4 | 57 | 5 |
| 6 | 1 | 19 | 1 | 32 | 2 | 45 | 5 | 58 | 5 |
| 7 | 2 | 20 | 1 | 33 | **1** | 46 | 3 | 59 | 1 |
| 8 | 2 | 21 | 5 | 34 | 2 | 47 | 2 | 60 | 2 |
| 9 | 4 | 22 | 5 | 35 | 4 | 48 | 4 | 61 | 3 |
| 10 | **5** | 23 | 5 | 36 | 5 | 49 | **3** | 62 | 4 |
| 11 | 1 | 24 | 4 | 37 | 2 | 50 | 5 | 63 | 1 |
| 12 | 2 | 25 | 1 | 38 | 2 | 51 | 3 | 64 | 3 |
| 13 | 3 | 26 | 2 | 39 | 4 | 52 | 1 | 65 | 4 |

Key-item rationale: All ten GRD items at maximum keyed value — positives 5 (Q3, Q10, Q16, Q22, Q36, Q50, Q57), reverses 1 (Q29, Q43, Q63: improvised, unplanned, drained-by-paperwork are all strongly false for him). Q10=5 and Q56=5 — the consistency pair holds at ceiling with diff 0. EXP elevated because audit IS investigation: Q23=5 (analysis over speed — professional creed), Q28=1, Q35=4, Q9=4; but Q13=3 (reads standards, not science). VIS floor: Q31=5 raw (strongly prefers one correct answer → coded 1), Q45=5 raw. Q21=5 (works alone all day, genuinely) crushes MEN via reverse coding. Minor inconsistencies: Q46=3 (mild pride in fixing) amid floor MAK; Q51=3, Q64=3 (partner-level P&L responsibility) amid low PIO; Q61=3 (explains findings to clients) amid low MEN.

### Computed scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 21 | 41 | 12 | 20 | 20 | **50** |
| Spectrum | 28 | **78** | 5 | 25 | 25 | **100** |

- **Dominant: GRD + EXP** (third check: 78−28 = 50 > 10, excluded). Combination: EXP+GRD = "The Analyst" (IC) — quantitative business/financial operations. Excellent fit for an auditor.
- DI = 95, Well-differentiated (near-maximal). Attention 3/3, pairs A=0, B=0 (B at ceiling 5/5). **Verdict: Valid.**
- **Expected vs computed: MATCH** (GRD+EXP).

**What it reveals:** GRD scale reaches a clean, honest ceiling (raw 50) for a criterion Conventional respondent; the Q10/Q56 pair does not break down at scale extremes. MEN/PIO exact tie at 25 for ranks 4–5 was silently ordered MEN-first by sort stability — harmless here but shows rank output is not fully determined by the documented rules.

---

## Persona 34: Rosalind Yeo — Executive assistant

**Testing purpose:** GRD+MEN administrative blend; support-role preference (Q24 agree) must register as authentic profile, not leadership deficit.

### Response sheet (Q1–Q65)
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 4 | 14 | 2 | 27 | 5 | 40 | 4 | 53 | 3 |
| 2 | 3 | 15 | 4 | 28 | 3 | 41 | 4 | 54 | 3 |
| 3 | 5 | 16 | 5 | 29 | 2 | 42 | 4 | 55 | 4 |
| 4 | 3 | 17 | **4** | 30 | 4 | 43 | 2 | 56 | **5** |
| 5 | 2 | 18 | 2 | 31 | 4 | 44 | 4 | 57 | 5 |
| 6 | 2 | 19 | 1 | 32 | 2 | 45 | 4 | 58 | 4 |
| 7 | 3 | 20 | 2 | 33 | **1** | 46 | 4 | 59 | 2 |
| 8 | 4 | 21 | 2 | 34 | 4 | 47 | 5 | 60 | 2 |
| 9 | 3 | 22 | 5 | 35 | 3 | 48 | 3 | 61 | 4 |
| 10 | **5** | 23 | 3 | 36 | 5 | 49 | **3** | 62 | 2 |
| 11 | 3 | 24 | 4 | 37 | 2 | 50 | 4 | 63 | 2 |
| 12 | 2 | 25 | 3 | 38 | 2 | 51 | 3 | 64 | 2 |
| 13 | 3 | 26 | 3 | 39 | 3 | 52 | 3 | 65 | 3 |

Key-item rationale: Q3/Q10/Q16/Q22/Q36/Q57=5 (the control tower). Q24=4 — she *genuinely* prefers enabling a leader to being one; authentic preference, not avoidance. Q47=5 ("support other people's growth" — reads it as her job description), Q27=5 (close cooperation). Q54=3 (helping with schedules yes, all-day personal problems would be a stretch — honest hedge). Minor inconsistencies: Q30=4 (the CEO's office moves fast and she thrives — cuts against her otherwise low PIO); Q29=2 not 1 (some daily variety is fine, softening a ceiling GRD); Q55=4 (quick practical answer — an EA reflex) vs Q42=4 (asks questions until she understands).

### Computed scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 27 | 29 | 23 | **41** | 23 | **46** |
| Spectrum | 43 | 48 | 33 | **78** | 33 | **90** |

- **Dominant: GRD + MEN** (third check: 78−48 = 30 > 10, excluded). Combination: MEN+GRD = "The Anchor" (SC) — "people-facing coordination" is precisely her job. Strong criterion fit.
- DI = 57, Well-differentiated. Attention 3/3, pairs A=0, B=0. **Verdict: Valid.**
- **Expected vs computed: MATCH** (GRD+MEN).

**What it reveals:** Support-role interests register as a *positive, differentiated* profile (GRD 90 / MEN 78), not as absence of leadership. Scoring handles this well; the burden falls on report language — PIO 33 ("Low Resonance") driven by an authentic Q24 preference must not be phrased as deficit. VIS/PIO tie at 33 (ranks 5–6) again silently resolved by sort order.

---

## Persona 35: Diego Salazar — HR generalist (mid-range differentiation test)

**Testing purpose:** Moderate-high MEN/GRD/PIO simultaneously; the 55–70 band where most real users live; tie-margin honesty.

### Response sheet (Q1–Q65)
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 4 | 14 | 3 | 27 | 4 | 40 | 4 | 53 | 3 |
| 2 | 2 | 15 | 4 | 28 | 3 | 41 | 4 | 54 | 3 |
| 3 | 4 | 16 | 4 | 29 | 3 | 42 | 3 | 55 | 3 |
| 4 | 3 | 17 | **4** | 30 | 3 | 43 | 2 | 56 | **4** |
| 5 | 4 | 18 | 3 | 31 | 3 | 44 | 3 | 57 | 4 |
| 6 | 2 | 19 | 2 | 32 | 3 | 45 | 3 | 58 | 3 |
| 7 | 3 | 20 | 3 | 33 | **1** | 46 | 4 | 59 | 3 |
| 8 | 5 | 21 | 2 | 34 | 4 | 47 | 4 | 60 | 2 |
| 9 | 3 | 22 | 4 | 35 | 4 | 48 | 3 | 61 | 4 |
| 10 | **4** | 23 | 3 | 36 | 4 | 49 | **3** | 62 | 2 |
| 11 | 3 | 24 | 3 | 37 | 3 | 50 | 4 | 63 | 3 |
| 12 | 4 | 25 | 3 | 38 | 3 | 51 | 4 | 64 | 4 |
| 13 | 3 | 26 | 3 | 39 | 3 | 52 | 3 | 65 | 3 |

Key-item rationale: The "everything role" — 4s across MEN (Q8=5 the single 5: helping people through problems is why he chose HR) and GRD (payroll, process), 3–4 on PIO (recruits and mediates = mild persuasion comfort: Q5=4, Q51=4 — winning a negotiation does excite him; but Q24=3, Q44=3 neutral). Heavy use of the middle of the scale by design — this is what most real profiles look like. Consistency pairs at exactly 4/4 both (per spec). Minor inconsistencies: Q46=4 (pride in fixing) vs low-mid MAK elsewhere; Q35=4 vs Q62=2 (likes understanding, dislikes long single-question investigation).

### Computed scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 29 | 30 | 28 | **40** | **34** | **38** |
| Spectrum | 48 | 50 | 45 | **75** | **60** | **70** |

- **Dominant: MEN + GRD + PIO.** Third check: score2 − score3 = 70 − 60 = **exactly 10** → included (rule is ≤ 10; my naive implementation includes it). Combination lens ambiguity: primary pair MEN+GRD = "The Anchor" (SC), but MEN+PIO ("Motivator"/SE — HR management) arguably fits his trajectory better; documentation says primary combination = top 2, so PIO's flavor is only Section 8.3 commentary.
- DI = 75 − 45 = **exactly 30** → "Well-differentiated" (band min 30 inclusive). A one-point shift on any item would relabel him "Moderately differentiated" — the persona sits simultaneously on two band boundaries.
- Attention 3/3, pairs A=0, B=0. **Verdict: Valid.**
- **Expected vs computed: MATCH** (MEN+GRD with PIO within 10 → three dominants).

**What it reveals:** The ≤10 third-avatar rule behaves as documented at its exact boundary, and the instrument does report the tie-margin honestly (3 dominants). But this modal, realistic profile lands on *two* knife-edge boundaries at once (third-inclusion = 10, DI = 30); with test-retest noise of ±2 raw points per scale, his report could plausibly flip between 2 and 3 dominants and between differentiation labels — a reliability concern precisely in the band where most users live.

---

## Persona 36: Captain Priya Menon (Ret.) — Military-to-civilian transition

**Testing purpose:** Institutional frame on items; GRD+PIO+MAK spread.

### Response sheet (Q1–Q65)
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 4 | 14 | 3 | 27 | 4 | 40 | 3 | 53 | 2 |
| 2 | 4 | 15 | 3 | 28 | 2 | 41 | 4 | 54 | 3 |
| 3 | 5 | 16 | 5 | 29 | 2 | 42 | 4 | 55 | 4 |
| 4 | 3 | 17 | **4** | 30 | 4 | 43 | 1 | 56 | **4** |
| 5 | 3 | 18 | 4 | 31 | 4 | 44 | 3 | 57 | 5 |
| 6 | 1 | 19 | 1 | 32 | 3 | 45 | 4 | 58 | 3 |
| 7 | 4 | 20 | 4 | 33 | **1** | 46 | 4 | 59 | 2 |
| 8 | 3 | 21 | 3 | 34 | 3 | 47 | 3 | 60 | 3 |
| 9 | 4 | 22 | 5 | 35 | 4 | 48 | 3 | 61 | 4 |
| 10 | **4** | 23 | 2 | 36 | 4 | 49 | **3** | 62 | 2 |
| 11 | 2 | 24 | 2 | 37 | 4 | 50 | 4 | 63 | 2 |
| 12 | 5 | 25 | 2 | 38 | 2 | 51 | 3 | 64 | 5 |
| 13 | 3 | 26 | 4 | 39 | 3 | 52 | 2 | 65 | 3 |

Key-item rationale: Q57=5 ("clear rules help me feel confident" — 18 years of military truth), Q16=5, Q22=5, Q43=1 (improvisation kills soldiers). PIO through command, not commerce: Q12=5 (taking the lead when a group needs direction — literally an officer's duty), Q64=5 (responsible for success of a team), Q24=2, but Q5=3 and Q51=3 ("convincing" and "winning agreements" read as civilian sales language — institutional-frame wording gap suppresses her PIO). MAK via ordnance/equipment: Q2=4, Q7=4, Q20=4 (depot and field), Q26=4, Q53=2 (physical days energize her). Q23=2 (logistics rewards speed, not slow analysis). Minor inconsistencies: Q30=4 (fast-moving ops tempo) beside Q58=3; Q55=4 (quick practical answer — military bias) beside Q42=4.

### Computed scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | **36** | 31 | 19 | 33 | **38** | **45** |
| Spectrum | **65** | 53 | 23 | 57 | **70** | **88** |

- **Dominant: GRD + PIO + MAK.** Third check: 70 − 65 = 5 ≤ 10 → MAK included. Primary combination PIO+GRD = "The Executive" (EC) — management/operations. Good fit for supply-chain leadership.
- DI = 65, Well-differentiated. Attention 3/3, pairs A=0, B=0. **Verdict: Valid.**
- Note: MEN (57) is itself within 10 of MAK (65) at rank 4 but is "never Dominant" per rule 4 — the 4th-rank cliff discards a real secondary signal.
- **Expected vs computed: MATCH** (GRD+PIO, MAK tertiary).

**What it reveals:** The institutional frame works — GRD items written for offices translate cleanly to military logistics. But two PIO items (Q5 "convincing others," Q51 "winning an important agreement") are coded in commercial-persuasion language that an officer who led 200 people answers Neutral to; her PIO (70) is likely an underestimate of her leadership orientation. Commercial framing of Enterprising items penalizes command-style leadership.

---

## Persona 37: Wanjiru Kamau — NGO program coordinator

**Testing purpose:** Persuasion items must capture advocacy, not just commerce; MEN+PIO mission blend; Enterprising ≠ profit-only.

### Response sheet (Q1–Q65)
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 5 | 14 | 2 | 27 | 5 | 40 | 5 | 53 | 4 |
| 2 | 2 | 15 | 5 | 28 | 3 | 41 | 5 | 54 | 2 |
| 3 | 3 | 16 | 3 | 29 | 4 | 42 | 4 | 55 | 4 |
| 4 | 3 | 17 | **4** | 30 | 4 | 43 | 3 | 56 | **3** |
| 5 | 5 | 18 | 3 | 31 | 3 | 44 | 1 | 57 | 3 |
| 6 | 3 | 19 | 3 | 32 | 2 | 45 | 3 | 58 | 2 |
| 7 | 2 | 20 | 3 | 33 | **1** | 46 | 3 | 59 | 3 |
| 8 | 5 | 21 | 2 | 34 | 5 | 47 | 4 | 60 | 1 |
| 9 | 3 | 22 | 3 | 35 | 3 | 48 | 3 | 61 | 4 |
| 10 | **3** | 23 | 2 | 36 | 3 | 49 | **3** | 62 | 2 |
| 11 | 4 | 24 | 2 | 37 | 4 | 50 | 2 | 63 | 4 |
| 12 | 4 | 25 | 3 | 38 | 3 | 51 | 4 | 64 | 4 |
| 13 | 3 | 26 | 2 | 39 | 4 | 52 | 2 | 65 | 2 |

Key-item rationale: Q5=5 — "convincing others to support an idea" is her literal job (chiefs, donors, mothers), and the item wording is mercifully commerce-neutral. Q44=1 (persuading energizes, never drains). Q1/Q8/Q15/Q34/Q40=5 (community mobilization, maternal-health counseling). Q51=4 (a signed donor grant IS winning an important agreement). Q63=4 raw (donor paperwork drains her → GRD reverse-coded 2), Q29=4 (field days are unplanned and she likes it). Q18=3 (competition is not her frame — mission is; slightly suppresses PIO). Q20=3 (comfortable outdoors — fieldwork — against otherwise floor MAK; deliberate texture). Minor inconsistencies: Q11=4 (new ways to express — campaign messaging) vs mid VIS elsewhere; Q55=4 vs Q42=4.

### Computed scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 21 | 28 | 31 | **46** | **41** | 27 |
| Spectrum | 28 | 45 | 53 | **90** | **78** | 43 |

- **Dominant: MEN + PIO** (third check: 78−53 = 25 > 10, excluded). Combination: MEN+PIO = "The Motivator" (SE) — "Community & Social Service (program leadership and advocacy)" is a near-verbatim description of her career. Excellent criterion fit.
- DI = 62, Well-differentiated. Attention 3/3, pairs A=0, B=0. **Verdict: Valid.**
- **Expected vs computed: MATCH** (MEN+PIO).

**What it reveals:** Enterprising ≠ profit-only holds — Q5's neutral wording ("support an idea") lets advocacy score, and PIO reaches 78 for a non-commercial persuader. The one leak: Q18 ("competition brings out my best") assumes competitive rather than mission motivation and costs mission-driven Enterprising types points. The SE combination text is the best-calibrated of any in this batch.

---

## Persona 38: Dr. Alessandro Ferri — Humanities academic

**Testing purpose:** EXP items' STEM wording (Q13) for a non-STEM investigator; EXP+VIS+MEN spread.

### Response sheet (Q1–Q65)
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 4 | 14 | 2 | 27 | 3 | 40 | 3 | 53 | 4 |
| 2 | 2 | 15 | 4 | 28 | 1 | 41 | 4 | 54 | 4 |
| 3 | 3 | 16 | 2 | 29 | 3 | 42 | 5 | 55 | 1 |
| 4 | 5 | 17 | **4** | 30 | 1 | 43 | 3 | 56 | **3** |
| 5 | 3 | 18 | 2 | 31 | 1 | 44 | 4 | 57 | 2 |
| 6 | 5 | 19 | 4 | 32 | 1 | 45 | 2 | 58 | 5 |
| 7 | 2 | 20 | 2 | 33 | **1** | 46 | 3 | 59 | 4 |
| 8 | 3 | 21 | 4 | 34 | 3 | 47 | 4 | 60 | 2 |
| 9 | 5 | 22 | 3 | 35 | 5 | 48 | 4 | 61 | 5 |
| 10 | **3** | 23 | 5 | 36 | 2 | 49 | **3** | 62 | 5 |
| 11 | 5 | 24 | 3 | 37 | 3 | 50 | 4 | 63 | 4 |
| 12 | 2 | 25 | 4 | 38 | 4 | 51 | 2 | 64 | 2 |
| 13 | **3** | 26 | 2 | 39 | 5 | 52 | 4 | 65 | 1 |

Key-item rationale: Q4/Q9/Q42/Q62=5, Q35=5, Q28=1, Q55=1 (deep investigation is the whole point of philosophy). **Q13=3 — the flagged wording-bias data point:** "science, technology, or new discoveries" makes a philosopher hesitate even though he reads *more* than any scientist; a domain-neutral phrasing ("new ideas and discoveries in any field") would have drawn a 5. Q6=5, Q11=5 (essays as original work), Q65=1, Q45=2. Q39=5 raw (strongly prefers ideas over objects → MAK reverse-coded 1), Q32=1. Q21=4 (solitary writer → MEN reverse hit), Q54=4 (all-day pastoral care would exhaust him), yet Q61=5 (explaining difficult things — seminar teaching). Minor inconsistencies: Q50=4 (tenure = stability preference) against otherwise low-mid GRD; Q15=4 vs Q8=3.

### Computed scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 19 | **47** | **44** | 33 | 21 | 27 |
| Spectrum | 23 | **93** | **85** | 57 | 28 | 43 |

- **Dominant: EXP + VIS** (third check: 85−57 = 28 > 10 → MEN third-ranked but NOT dominant). Combination: EXP+VIS = "The Idea Architect" (IA) — "research-driven design/content" stretches to cover a philosopher, barely.
- DI = 70, Well-differentiated. Attention 3/3, pairs A=0, B=0. **Verdict: Valid.**
- **Expected vs computed: MATCH** (EXP+VIS, MEN 3rd-ranked). Note the persona sheet's word "tertiary" is ambiguous — MEN is third in *rank* (57) but at gap 28 it is not a *Dominant* third. Recorded as intended: rank-3, non-dominant.

**What it reveals:** Q13's STEM wording cost a maximal investigator 2 raw EXP points (47 vs potential 49). Here it changed nothing (EXP was rank 1 regardless), but for a humanities respondent with a closer EXP/VIS race the single item could demote EXP from rank 1 or knock a third avatar out. Item-review recommendation confirmed: Q13 measures domain exposure, not investigative disposition.

---

## Persona 39: Nguyen Thi Hoa — Rice cooperative manager (near-tie stress test)

**Testing purpose:** MAK+PIO vs MAK+GRD legitimate near-tie; record which way the algorithm breaks it; non-office item register.

### Response sheet (Q1–Q65)
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 4 | 14 | 4 | 27 | 4 | 40 | 4 | 53 | 2 |
| 2 | 4 | 15 | 3 | 28 | 3 | 41 | 4 | 54 | 3 |
| 3 | 4 | 16 | 4 | 29 | 3 | 42 | 3 | 55 | 4 |
| 4 | 3 | 17 | **4** | 30 | 3 | 43 | 3 | 56 | **4** |
| 5 | 4 | 18 | 3 | 31 | 4 | 44 | 2 | 57 | 4 |
| 6 | 1 | 19 | 2 | 32 | 4 | 45 | 4 | 58 | 3 |
| 7 | 4 | 20 | 5 | 33 | **1** | 46 | 5 | 59 | 2 |
| 8 | 4 | 21 | 3 | 34 | 3 | 47 | 3 | 60 | 3 |
| 9 | 3 | 22 | 4 | 35 | 4 | 48 | 3 | 61 | 3 |
| 10 | **4** | 23 | 3 | 36 | 4 | 49 | **3** | 62 | 2 |
| 11 | 2 | 24 | 3 | 37 | 4 | 50 | 4 | 63 | 4 |
| 12 | 4 | 25 | 2 | 38 | 2 | 51 | 4 | 64 | 4 |
| 13 | 2 | 26 | 5 | 39 | 2 | 52 | 1 | 65 | 3 |

Key-item rationale: Q20=5 (fields ARE her workplace), Q26=5 (harvest is the physical result), Q46=5 (fixing the pump), Q53=2 (physical days energize a farmer). PIO via buyer negotiation: Q5=4, Q51=4 (a good price for 200 families is a strong feeling), Q12=4, Q37=4, Q64=4. GRD via harvest calendars: Q16=4, Q22=4, Q50=4, Q57=4, but Q63=4 raw (cooperative paperwork drains → coded 2). MEN through community standing: Q1/Q8/Q27/Q40=4. VIS floor: Q6=1, Q52=1. Q55=4 raw (quick practical answers — farm pragmatism → EXP reverse hit). Minor inconsistencies: Q13=2 vs Q35=4; Q30=3 beside Q29=3 hedging.

### Computed scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | **42** | 28 | 19 | 34 | **36** | **36** |
| Spectrum | **80** | 45 | 23 | 60 | **65** | **65** |

- **Dominant: MAK + PIO + GRD** — with an **exact PIO/GRD tie at 65 for rank 2**.
  - **Ambiguity + naive behavior recorded:** `scoring.json` says "top 2 ranked" + third if score2−score3 ≤ 10, with no tie rule at all. My naive stable sort broke the tie by scale insertion order (MAK, EXP, VIS, MEN, **PIO**, GRD) → PIO ranked 2nd, GRD 3rd, then score2−score3 = 0 ≤ 10 → GRD included anyway. The MD Section 6.5 tie rule ("tie for rank 2: both are Dominant") reaches the same 3-avatar set by a different route. **But the primary combination label is order-dependent and undefined:** MAK+PIO = "The Groundbreaker" (RE, contracting/ops management) vs MAK+GRD = "The Steady Hand" (RC, machine operation/code-governed trades) are materially different career narratives, and the algorithm chose Groundbreaker purely because PIO precedes GRD in the scales dictionary.
  - Secondary issue: MEN (60) sits within 10 of the tied second-place score (65) at rank 4 and is discarded by the "fourth is never Dominant" rule — for a genuinely broad agrarian-managerial profile, real signal is cut off.
- DI = 57, Well-differentiated. Attention 3/3, pairs A=0, B=0. **Verdict: Valid.**
- **Expected vs computed: MATCH** (MAK dominant + PIO/GRD near-tie; tie recorded as broken toward PIO by implementation accident).

**What it reveals:** The single most consequential undocumented behavior found in this batch: rank-2 ties produce an arbitrary, implementation-defined primary combination. Documentation covers rank-3 ties (Section 6.5) but for a rank-2 tie only says "both are Dominant" — it never says which pair drives the primary combination interpretation in Section 8.3. Items translated adequately to non-office agrarian work (Q20, Q26 register perfectly).

---

## Persona 40: Sam Whitaker — UX researcher (hardest discrimination test)

**Testing purpose:** EXP/MEN/VIS boundary hybrid; third-avatar inclusion rule.

### Response sheet (Q1–Q65)
| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 4 | 14 | 3 | 27 | 4 | 40 | 4 | 53 | 3 |
| 2 | 2 | 15 | 4 | 28 | 2 | 41 | 4 | 54 | 3 |
| 3 | 4 | 16 | 3 | 29 | 3 | 42 | 5 | 55 | 2 |
| 4 | 5 | 17 | **4** | 30 | 3 | 43 | 3 | 56 | **3** |
| 5 | 3 | 18 | 2 | 31 | 2 | 44 | 4 | 57 | 3 |
| 6 | 4 | 19 | 4 | 32 | 2 | 45 | 2 | 58 | 4 |
| 7 | 3 | 20 | 2 | 33 | **1** | 46 | 3 | 59 | 4 |
| 8 | 4 | 21 | 2 | 34 | 5 | 47 | 4 | 60 | 3 |
| 9 | 4 | 22 | 3 | 35 | 5 | 48 | 4 | 61 | 4 |
| 10 | **3** | 23 | 4 | 36 | 3 | 49 | **3** | 62 | 4 |
| 11 | 4 | 24 | 4 | 37 | 3 | 50 | 3 | 63 | 3 |
| 12 | 2 | 25 | 3 | 38 | 4 | 51 | 2 | 64 | 2 |
| 13 | 4 | 26 | 2 | 39 | 4 | 52 | 3 | 65 | 2 |

Key-item rationale: Q4=5, Q42=5 (why users behave as they do — their research question), Q35=5, Q28=2, Q55=2. Q34=5 (research interviews ARE careful listening to difficulties), Q21=2 (mildly disagrees — interviews and workshops fill the day), Q54=3 (honest hedge: research listening energizes, therapy-style all-day would not). VIS concept work: Q6=4, Q11=4, Q19=4, Q38=4, Q59=4, Q45=2, but Q25=3 and Q52=3 (utility over beauty — research-led, not aesthetic-led). Q24=4 (happy contributing, not leading → PIO reverse hit), Q64=2. Q3=4 (organizing research data — GRD bump, deliberate texture against GRD 3 elsewhere). Minor inconsistencies: Q13=4 vs Q60=3 (curious about devices but doesn't dismantle them); Q58=4 vs Q30=3.

### Computed scores
| | MAK | EXP | VIS | MEN | PIO | GRD |
|---|---|---|---|---|---|---|
| Raw | 25 | **43** | **38** | **40** | 23 | 31 |
| Spectrum | 38 | **83** | **70** | **75** | 33 | 53 |

- **Dominant: EXP + MEN + VIS.** Third check: 75 − 70 = 5 ≤ 10 → VIS included. Exactly the intended 3-avatar hybrid; the third-inclusion rule earns its keep on precisely this modern-role profile.
- Combination lens: primary = EXP+MEN = "The Healer" (IS) — clinical/counseling career families that describe a UX researcher in health-tech poorly; the actual best-fit label, EXP+VIS "Idea Architect" (research-driven design), is relegated to flavor. The taxonomy predates hybrid tech roles.
- DI = 50, Well-differentiated. Attention 3/3, pairs A=0, B=0. **Verdict: Valid.**
- **Expected vs computed: MATCH** (EXP+MEN, VIS third within ~8 — actual gap 5).

**What it reveals:** The discrimination machinery works — three genuinely co-elevated avatars are all captured, ranked correctly, and the 10-point window includes the third. The weakness is downstream: the pairwise combinations table forces a "primary pair" reading (IS → Healer → clinical careers) that mismatches the person the profile describes. Three-avatar profiles need three-way interpretation content, which the instrument lacks.

---

## Batch D validity summary table

| # | Persona | Raw (MAK/EXP/VIS/MEN/PIO/GRD) | Spectrum | Dominant | DI | Verdict | Expected | Match |
|---|---|---|---|---|---|---|---|---|
| 31 | Halvorsen | 28/22/22/39/49/25 | 45/30/30/73/98/38 | PIO+MEN | 68 | Valid | PIO+MEN | YES |
| 32 | Karimova | 26/31/43/30/47/20 | 40/53/83/50/93/25 | PIO+VIS | 68 | Valid | PIO+VIS | YES |
| 33 | Baumgartner | 21/41/12/20/20/50 | 28/78/5/25/25/100 | GRD+EXP | 95 | Valid | GRD+EXP | YES |
| 34 | Yeo | 27/29/23/41/23/46 | 43/48/33/78/33/90 | GRD+MEN | 57 | Valid | GRD+MEN | YES |
| 35 | Salazar | 29/30/28/40/34/38 | 48/50/45/75/60/70 | MEN+GRD+PIO | 30 | Valid | MEN+GRD(+PIO) | YES |
| 36 | Menon | 36/31/19/33/38/45 | 65/53/23/57/70/88 | GRD+PIO+MAK | 65 | Valid | GRD+PIO, MAK 3rd | YES |
| 37 | Kamau | 21/28/31/46/41/27 | 28/45/53/90/78/43 | MEN+PIO | 62 | Valid | MEN+PIO | YES |
| 38 | Ferri | 19/47/44/33/21/27 | 23/93/85/57/28/43 | EXP+VIS | 70 | Valid | EXP+VIS, MEN rank-3 | YES |
| 39 | Hoa | 42/28/19/34/36/36 | 80/45/23/60/65/65 | MAK+PIO+GRD (PIO/GRD tie) | 57 | Valid | MAK+(PIO/GRD tie) | YES |
| 40 | Whitaker | 25/43/38/40/23/31 | 38/83/70/75/33/53 | EXP+MEN+VIS | 50 | Valid | EXP+MEN+VIS | YES |

All 10 profiles: attention 3/3 passed, consistency pairs diff ≤ 1, no long-string, verdict Valid.

## Documented ambiguities encountered (and naive-implementation behavior)

1. **Rank-2 exact tie (P39, PIO=GRD=65).** `scoring.json` has no tie rule; MD 6.5 covers rank-1/2 ties ("both Dominant") and rank-3 ties, but neither source defines which tied avatar anchors the *primary combination*. Naive output: PIO ranked 2nd via dict insertion order → "Groundbreaker" (RE) rather than "Steady Hand" (RC). Arbitrary and consequential.
2. **Third-inclusion boundary (P35, gap exactly 10).** "score2 − score3 <= 10" is unambiguous but knife-edged; naive implementation includes the third avatar. One raw point of noise flips the report between 2 and 3 dominants.
3. **DI band boundary (P35, DI exactly 30).** JSON bands `min:30` well-differentiated vs `15–29` moderate — 30 lands in "Well-differentiated" by the inclusive min. Same knife-edge concern.
4. **Rank-4 cliff (P36 MEN=57 vs MAK=65; P39 MEN=60 vs 65).** "Fourth-ranked never Dominant regardless of gaps" discards avatars closer to rank 3 than rank 3 is allowed to be to rank 2. Documented, not ambiguous — but psychometrically arbitrary.
5. **Mild consistency (diff=2) and flat-profile flags** have no explicit caution-level mapping in the verdict rules; naive implementation counts each as one caution signal. Not exercised by this batch (all diffs ≤ 1, no flat profiles).
6. **Ordered vs unordered combinations.** Combination keys are written "MAK+EXP" style with no rule for which avatar is "first" when rank order is reversed (e.g., P31 is PIO-first but the table only has MEN+PIO semantics via SE). Naive lookup treats pairs as unordered.
