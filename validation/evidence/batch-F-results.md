# Batch F Results — Personas 51–60 (Psychological Profile Variations)

Instrument: The MINDCROUD Career Spectrum v1.0. Scoring per `data/scoring.json` (authoritative) + Section 6 of the manual. Scorer: `score_batch_F.py` (naive implementation: reverse=6−raw for the 15 listed items; spectrum=round-half-up((raw−10)/40×100); dominant = top-2 + third if score2−score3 ≤ 10 with stable-sort tie handling in scale-declaration order MAK,EXP,VIS,MEN,PIO,GRD; DI=max−min, flat if <15; attention Q17=4/Q33=1/Q49=3; consistency |Q1−Q41|,|Q10−Q56|).

Rounding note: manual says "round half up." 57.5→58, 77.5→78. Python's `round()` is banker's rounding, so the scorer uses `floor(x+0.5)` to honor documented half-up. This matters for raw 33 (57.5→58) and raw 41 (77.5→78) — both appear below.

---

## Persona 51 — Dr. Renata Wolff (meta-aware / psychometrically sophisticated)

Response style: mentally tags each item's scale, self-monitors for social desirability, deliberately avoids 5s on flattering items (compresses the top), answers both consistency pairs identically on purpose, passes all three attention checks knowingly. Intentional minor inconsistencies: Q35 EXP-NRG allowed a 5 (genuine intellectual-honesty item she wouldn't suppress); Q13/Q42/Q62 EXP gets clean 4s.

Key items: Q1=4/Q41=4 (identical on purpose); Q10=4/Q56=4 (identical on purpose); Q17=4, Q33=1, Q49=3 (recognized instantly); flattering VIS/PIO items held to 2–3 to resist desirability.

- Raw: MAK 23, EXP 41, VIS 35, MEN 38, PIO 27, GRD 34
- Spectrum: MAK 33, EXP 78, VIS 63, MEN 70, PIO 43, GRD 60
- Ranked: EXP 78 > MEN 70 > VIS 63 > GRD 60 > PIO 43 > MAK 33
- DI: 45 (well-differentiated). Flat: no.
- Validity: 0 attention fails; pair diffs [0,0]; longest run 4. Verdict: **Valid**.
- Dominant (computed): **EXP + MEN + VIS** (VIS 63 is within 10 of MEN 70 → third strand).

Expected vs computed: Persona spec predicted EXP + MEN. Computed adds VIS as a spurious third. Cause: her self-imposed midpoint compression pulled MEN down to 70 while VIS sat at 63 — a 7-point gap that trips the ≤10 third-dominant rule she was specifically trying to avoid. **The rank order is correct (EXP>MEN, exactly as designed), but compression manufactured an extra dominant.**

Reveals: The ≤10-point third-dominant rule is fragile to overall profile compression. A sophisticated respondent who narrows her own range makes adjacent scales collide, producing *more* dominants, not fewer. Rank-ordering survives; dominant-set does not.

---

## Persona 52 — Charles "Chip" Vandermeer III (impression manager / socially desirable)

Response style: 4–5 on ALL positively-worded items across every avatar ("no wrong answers, only weak ones"); disagrees every "drains me" reverse NRG item; reads carefully so passes attention checks (strategic, not careless). Intentional minor inconsistencies: gave a couple of 4s instead of 5s on less glamorous items (Q14 build-with-hands, Q20 worksite, Q10 detail-check) to look human.

Key items: Q17=4, Q33=1, Q49=3 (deliberately correct); reverse items Q44/Q53/Q54/Q58/Q63/Q65 all answered 1 (nothing drains a winner); Q1=5/Q41=5 and Q10=4/Q56=4 (consistent).

- Raw: MAK 41, EXP 47, VIS 44, MEN 46, PIO 50, GRD 38
- Spectrum: MAK 78, EXP 93, VIS 85, MEN 90, PIO 100, GRD 70
- Ranked: PIO 100 > EXP 93 > MEN 90 > VIS 85 > MAK 78 > GRD 70
- DI: 30 (well-differentiated — *barely*, at the exact ≥30 boundary). Flat: no.
- Validity: 0 attention fails; pair diffs [0,0]; longest run 4. Verdict: **Valid**.
- Dominant (computed): **PIO + EXP + MEN** (MEN 90 within 10 of EXP 93).

Expected vs computed: Spec predicted a flat-high (~80s everywhere) profile that should trigger a low-differentiation warning, with near-arbitrary top-2 selection. **The instrument did NOT flag him.** Two reasons: (1) the 15 reverse-scored "drains me" items, which he uniformly disagreed with, coded *high* and inflated the NRG contribution consistently rather than flattening it; (2) his few strategic 4s on unglamorous Realistic/Conventional items dropped MAK and GRD just enough to push DI to exactly 30 — landing him in "well-differentiated" and defeating the flat-profile safeguard by a single point. He is reported as a Valid, well-differentiated Enterprising-Investigative-Social leader.

Reveals: **This is the instrument's most serious exposed weakness.** There is no social-desirability / infrequency scale, and the only guard against uniform high endorsement is the Differentiation Index — which reverse items and a tiny amount of strategic noise push over the "well-differentiated" line. An impression manager receives a clean, flattering, "valid" profile. DI landing exactly on the 30 boundary shows how close the safeguard came and how easily it is beaten.

---

## Persona 53 — Marites Santos-Dizon (acquiescent / yea-sayer)

Response style: agrees (4–5) with nearly everything as a courtesy norm — including reverse-worded items that contradict her positive answers (Q1 "enjoy teaching"=4 AND Q54 "helping people would exhaust me"=4). Consistency pairs are both positively worded so she passes them. Intentional design point: a 10-long run of 4s (Q41–Q50 region) sits just under the long-string threshold of 12.

Key items: Q17=4 (accidentally correct — she'd agree anyway), Q33=1 (the instruction to "Strongly disagree" overrides her yea-saying — she complies with the instruction), Q49=3 (instruction to pick Neutral — complies); Q1=4/Q41=4; Q10=4/Q56=4.

- Raw: MAK 34, EXP 37, VIS 34, MEN 39, PIO 33, GRD 34
- Spectrum: MAK 60, EXP 68, VIS 60, MEN 73, PIO 57, GRD 60
- Ranked: MEN 73 > EXP 68 > MAK 60 = VIS 60 = GRD 60 > PIO 57
- DI: 16 (moderately differentiated). Flat: no.
- Validity: 0 attention fails; pair diffs [0,0]; longest run 10 (< 12 threshold). Verdict: **Valid**.
- Dominant (computed): **MEN + EXP + MAK** (MAK 60 within 10 of EXP 68; naive tie-break picks MAK over VIS/GRD at 60 because MAK is declared before VIS/GRD).

Expected vs computed: Spec predicted an artificially mid-flat profile that should be FLAGGED via within-avatar contradiction / low internal consistency. **No flag fired.** The reverse-scoring architecture does exactly what it was designed to do — her agree-on-both-sides answers cancel to the mid-30s raw — BUT the instrument has no within-avatar consistency check, no variance/long-string flag below 12, and the consistency pairs are both positively keyed so acquiescence sails through them. She is reported as a Valid Social-Investigative helper. The three-way tie at 60 also exposes the tie-break: MAK is named the third dominant purely because of scale declaration order, not psychology.

Reveals: The 12 reverse items successfully *neutralize* acquiescence in the score but do NOT *detect* it. A yea-sayer's data is silently converted into a plausible-looking flat-mid profile with no warning. The documented rationale ("demonstrates why the reverse items exist") is only half-realized: they launder the bias rather than surface it. Also exposes an undocumented tie-break dependency on scale order.

---

## Persona 54 — Bastian Krüger (high initiative, low structure)

Response style: 5s on initiative/creation (Q37 start projects, Q64 run a business, Q59 inventing, Q38 imagining, Q5 convince, Q19 freedom); strong-agree on GRD reverse items (Q29 unplanned=5, Q43 improvise=5, Q63 paperwork drains=5) and floor on GRD positive items (Q16=1, Q36=1, Q50=1, Q22=2) → GRD floored. MEN and MAK mid-3s (hardware tinkering). Intentional minor inconsistencies: Q2 MAK=3 while Q60 take-apart=4 (curiosity yes, repair meh); Q13 EXP=5 (loves discovery) but Q62 long-investigation=1 (no patience) — a coherent "explores fast, doesn't dig deep" pattern.

Key items: Q17=4, Q33=1, Q49=3 (passes); Q1=4/Q41=4; Q10=2/Q56=3 (diff 1, consistent).

- Raw: MAK 33, EXP 31, VIS 46, MEN 31, PIO 47, GRD 14
- Spectrum: MAK 57, EXP 53, VIS 90, MEN 53, PIO 93, GRD 10
- Ranked: PIO 93 > VIS 90 > MAK 57 > EXP 53 = MEN 53 > GRD 10
- DI: 83 (well-differentiated). Flat: no.
- Validity: 0 attention fails; pair diffs [0,1]; longest run 3. Verdict: **Valid**.
- Dominant (computed): **PIO + VIS** (MAK 57 is 33 points below VIS 90 → no third).

Expected vs computed: **Exact match.** PIO + VIS, GRD floored at 10. Maps to the "Creative Director" (AE) combination.

Reveals: The instrument handles the genuine "founder" pattern cleanly — a very low GRD coexists with very high PIO/VIS and produces a coherent, well-differentiated profile, not a paradox. Floor-vs-dominant contrast renders correctly. Positive case for the reverse-scored GRD items working as intended on an honest respondent.

---

## Persona 55 — Prof. Zhang Liwei (actively devalues VIS/PIO)

Response style: reverent 5s on all EXP items (with correct reverse handling — Q28 "lose interest in analysis"=1, Q55 "prefer quick answer"=1); contemptuous 1s on ALL VIS and PIO items, even ones a neutral low-scorer would rate 2–3; GRD 4s (rigor/records appeal to him). Polarized but internally consistent. Intentional minor inconsistencies: Q60 MAK take-apart=3 and Q7 tools=3 (physics apparatus, mild) rather than pure floor; Q46 fix-something=3.

Note on reverse VIS/PIO items under contemptuous responding: he rates the reverse-worded VIS/PIO items to *express* disdain. Q31 "prefer one correct answer"(VIS reverse)=5→codes 1; Q45 "every step decided in advance"(VIS reverse)=5→codes 1; Q65 "creating from nothing drains me"(VIS reverse)=5→codes 1; Q24 "prefer to follow"(PIO reverse)=5→codes 1; Q44 "persuading drains me"(PIO reverse)=5→codes 1; Q58 "prefer calm predictable"(PIO reverse)=5→codes 1. His disdain is directionally consistent with low VIS/PIO, so reverse coding does not betray him.

Key items: Q17=4, Q33=1, Q49=3 (complies); Q1=3/Q41=3; Q10=4/Q56=4.

- Raw: MAK 21, EXP 50, VIS 10, MEN 20, PIO 10, GRD 40
- Spectrum: MAK 28, EXP 100, VIS 0, MEN 25, PIO 0, GRD 75
- Ranked: EXP 100 > GRD 75 > MAK 28 > MEN 25 > VIS 0 = PIO 0
- DI: 100 (maximally differentiated). Flat: no.
- Validity: 0 attention fails; pair diffs [0,0]; longest run 3. Verdict: **Valid**.
- Dominant (computed): **EXP + GRD** (MAK 28 is 47 below GRD 75 → no third).

Expected vs computed: **Exact match.** EXP + GRD, VIS/PIO floored at 0.

Reveals: Deliberate contemptuous devaluation is statistically indistinguishable from genuine low interest — both produce floors and a clean, unflagged, well-differentiated profile. Because his contempt happens to be *directionally consistent* (he devalues coherently, and handles reverse items in the same disdainful direction), the instrument has no basis to flag it, and arguably shouldn't. Contrast with Persona 60 (extremity as style) below. The 0-floor and 100-ceiling show the spectrum transform saturating at the extremes.

---

## Persona 56 — Astrid Lindholm (effective BECAUSE she avoids a valued behavior)

Response style: authentic solo-effectiveness. Q21 "best alone"(MEN reverse)=5→codes 1 (drives MEN down); Q27 cooperation=1; MEN floored honestly. EXP and GRD 5s. PIO mostly 2 except Q18 competition=5 (markets are competition) — the telling single-item spike. Intentional minor inconsistencies: Q31 VIS reverse=4 (she does prefer one right answer — quant discipline), giving VIS a small lift; Q3 GRD organize=5 but Q16 fixed-schedule=4 (structure in analysis, not in calendar).

Key items: Q17=4, Q33=1, Q49=3 (passes); Q1=2/Q41=2; Q10=5/Q56=5.

- Raw: MAK 20, EXP 49, VIS 27, MEN 16, PIO 26, GRD 44
- Spectrum: MAK 25, EXP 98, VIS 43, MEN 15, PIO 40, GRD 85
- Ranked: EXP 98 > GRD 85 > VIS 43 > PIO 40 > MAK 25 > MEN 15
- DI: 83 (well-differentiated). Flat: no.
- Validity: 0 attention fails; pair diffs [0,0]; longest run 3. Verdict: **Valid**.
- Dominant (computed): **EXP + GRD** (VIS 43 is 42 below GRD 85 → no third).

Expected vs computed: **Exact match.** EXP + GRD, MEN floored at 15.

Reveals: Report-tone test, not a scoring test. The instrument correctly places her as Analyst (EXP+GRD / IC). The open question is whether the *narrative* frames low MEN (15) as a legitimate preference and genuine strength rather than a "social interests to develop" deficiency — the scoring is silent on this, so it depends entirely on report template language downstream of the score. The single-item PIO spike (Q18=5) is invisible at scale level: PIO still reads 40. Facet/single-item signal is lost in aggregation.

---

## Persona 57 — Omar Haddad (genuinely balanced / multipotential)

Response style: thoughtful mid-4 endorsements everywhere with deliberate 2s and 5s scattered (Q18 competition=2; Q46 fixing=5) — rich item-level variance despite flat scale means. Reverse items answered thoughtfully, checks passed, pairs consistent. Intentional minor inconsistencies: Q6 VIS create=4 but Q11 new-ways-to-express=3 and Q65 reverse=2 (create-from-nothing slightly drains) — mild VIS softening; Q28 EXP reverse=2 (some analysis does bore him).

Key items: Q17=4, Q33=1, Q49=3 (passes deliberately); Q1=4/Q41=4; Q10=4/Q56=4; Q46=5 and Q18=2 are the designed variance spikes.

- Raw: MAK 37, EXP 36, VIS 35, MEN 37, PIO 31, GRD 36
- Spectrum: MAK 68, EXP 65, VIS 63, MEN 68, PIO 53, GRD 65
- Ranked: MAK 68 = MEN 68 > EXP 65 = GRD 65 > VIS 63 > PIO 53
- DI: 15 (moderately differentiated — one point above the flat-profile threshold of <15). Flat: no.
- Validity: 0 attention fails; pair diffs [0,0]; longest run 6. Verdict: **Valid**.
- Dominant (computed): **MAK + MEN + EXP** (MAK/MEN tie at rank 1–2; EXP 65 within 10 of MEN 68 → third).

Expected vs computed: Spec predicted a flat-ish ~55–68 "multipotential" profile and asked whether the instrument can (a) distinguish him from disengaged midpoint-clicking (Persona 58) and (b) avoid forcing 2 arbitrary dominants. Result: **(a) YES — cleanly. (b) NO.** On data quality he is decisively separated from Kevin (P58): longest run 6 vs 49, real reverse-item engagement, attention checks actively passed, DI 15 vs 3. But the scoring engine still forces dominants — it names MAK + MEN + EXP as "Dominant Avatars" off a MAK-vs-VIS spread of only 5 points (68 vs 63). There is no "multipotential/undifferentiated" verdict at DI=15; the flat-profile flag requires DI < 15 and he is exactly one point outside it.

Reveals: **The flat-profile flag threshold (<15) is mis-calibrated for genuine balance.** A truly multipotential respondent lands at DI 15 — moderately differentiated — and gets three near-arbitrary dominants drawn from a 5-point band, with a tie at rank 1 silently resolved by scale order. The instrument distinguishes engaged-balanced from disengaged-flat on *validity* signals (good) but has no *interpretive* category for high-quality flatness. It manufactures direction where the honest reading is breadth.

---

## Persona 58 — Kevin O'Rourke (disengaged midpoint responder)

Response style: 3 on essentially every item including reverse items; minimum effort. One deviation: Q50 "prefer stable job with clear duties"=4 (mild genuine agreement he couldn't be bothered to suppress), which is why GRD edges above the others. Fails the attention checks that demand non-neutral answers.

Key items: Q17=3 (FAIL — needs 4); Q33=3 (FAIL — needs 1); Q49=3 (pass, by luck); Q1=3/Q41=3; Q10=3/Q56=3; 49-item long string of 3s.

- Raw: MAK 30, EXP 30, VIS 30, MEN 30, PIO 30, GRD 31
- Spectrum: MAK 50, EXP 50, VIS 50, MEN 50, PIO 50, GRD 53
- Ranked: GRD 53 > MAK = EXP = VIS = MEN = PIO = 50
- DI: 3 (flat profile — flag). Flat: **yes**.
- Validity: **2 attention fails [Q17, Q33]** → potentially-invalid level; pair diffs [0,0]; longest run 49 (≥12 long-string flag). Verdict: **Potentially invalid**.
- Dominant (computed): GRD + MAK + EXP (meaningless — a 3-point artifact of the single Q50=4).

Expected vs computed: **Exact match.** Correctly flagged Potentially Invalid on TWO independent signals (2/3 attention checks failed AND a 49-long string well past the 12 threshold), plus the flat-profile flag. This is the QA baseline and the instrument nails it.

Reveals: The attention checks are well-designed precisely for this respondent — two of the three (Q17=Agree, Q33=Strongly disagree) require leaving the midpoint, so a pure midpoint-clicker cannot pass them. Layered with the long-string screen and flat-profile flag, disengaged central-tendency responding is caught three ways over. **The safeguards work — for careless responders. The contrast with P52 (impression manager, also near-uniform, but NOT flagged) shows the guard rails only catch *lazy* uniformity, not *strategic* uniformity.**

---

## Persona 59 — Priyanka Chandrasekhar (extrinsic/intrinsic motivation split)

Response style: honest 5s on VIS-NRG "energy" items that feel private/safe (Q25 making-beauty=5, Q59 inventing=5) but hedged 2–3s on VIS-ENV items that feel career-disloyal to endorse (Q19 freedom/few-rules=3, Q52 personal-style=3); GRD/PIO 4s from trained banking diligence. The facet split (VIS NRG high, VIS ENV suppressed) is the target signal. Intentional minor inconsistencies: Q6 VIS create=5 leaked through despite self-censorship; Q38 imagine=5; Q31 VIS reverse=2→codes 4 (won't claim she prefers one-right-answer).

Key items: Q17=4, Q33=1, Q49=3 (passes); Q1=3/Q41=3; Q10=4/Q56=4; VIS-NRG (Q25,Q59) vs VIS-ENV (Q19,Q52) is the diagnostic contrast.

- Raw: MAK 24, EXP 32, VIS 43, MEN 30, PIO 36, GRD 37
- Spectrum: MAK 35, EXP 55, VIS 83, MEN 50, PIO 65, GRD 68
- Ranked: VIS 83 > GRD 68 > PIO 65 > EXP 55 > MEN 50 > MAK 35
- DI: 48 (well-differentiated). Flat: no.
- Validity: 0 attention fails; pair diffs [0,0]; longest run 4. Verdict: **Valid**.
- Dominant (computed): **VIS + GRD + PIO** (PIO 65 within 10 of GRD 68 → third).

Expected vs computed: Spec predicted VIS + GRD (or VIS + PIO) — "an uncomfortable, diagnostic pairing." Computed delivers VIS + GRD **and** PIO (all three of the diagnostic candidates, since GRD 68 and PIO 65 are three points apart). **Top-2 exactly as designed; the suppressed VIS signal (83) dominates despite her self-censorship, which is the intended win.** Even with hedged VIS-ENV items, the VIS-NRG endorsements carried the scale to the top.

Reveals: The instrument *does* surface a suppressed interest — VIS wins outright even though she deliberately dampened the environment-facet items. The facet-level story (VIS NRG 5s vs VIS ENV 3s) is the real finding, but it is **invisible in the delivered output**: the score only reports VIS 83. The uncomfortable VIS+GRD banker-artist pairing is exactly the diagnostic value proposition — and it works — but only a consultant reading item-level data (not the scale scores) would see the NRG>ENV split that explains *why* she's conflicted.

---

## Persona 60 — Dumisani Khumalo (extreme responder)

Response style: only 1s and 5s, never 2–4. MAK all 5, GRD all 5, MEN helping 5 (union rep), VIS all 1, EXP all 1, PIO split (leading Q12/Q37... he gave leading 5s but persuasion-drains reverse Q44=1→codes 5, follow-reverse Q24=1→codes 5). Attention check Q49 demands "Neutral"(3) — a genuine conflict with his no-middle style; here he *grudgingly complies* (Q49=3). BUT Q17 demands "Agree"(4), not "Strongly agree" — his extremity makes him answer 5, **failing Q17**.

Key items: Q17=**5** (FAIL — needs exactly 4; his extreme style gives 5); Q33=1 (pass); Q49=3 (grudging compliance — passes); Q1=5/Q41=5; Q10=5/Q56=5.

- Raw: MAK 50, EXP 10, VIS 10, MEN 46, PIO 38, GRD 50
- Spectrum: MAK 100, EXP 0, VIS 0, MEN 90, PIO 70, GRD 100
- Ranked: MAK 100 = GRD 100 > MEN 90 > PIO 70 > EXP 0 = VIS 0
- DI: 100. Flat: no.
- Validity: **1 attention fail [Q17]**; pair diffs [0,0]; longest run 5. Verdict: **Interpret with caution**.
- Dominant (computed): **MAK + GRD + MEN** (MAK/GRD tie rank 1–2; MEN 90 within 10 of GRD 100 → third).

Expected vs computed: Spec predicted MAK + GRD (MEN third), all scores at extremes, and flagged the Q49 conflict. **Dominants: exact match (MAK+GRD+MEN).** The surprise the persona narrative half-anticipated: **the attention-check conflict bites at Q17, not Q49.** Q17 requires the *moderate* response "Agree"(4); an extreme responder who only uses 1 and 5 literally cannot pass it without breaking character. He passed Q49 (grudged to 3) but the extremity tripped Q17 → one caution flag → "Interpret with caution." Consistency pairs survive perfectly (he's decisive and stable), as the spec predicted.

Reveals: **The attention checks have an unintended interaction with extreme response style.** Q17's correct answer is 4 (Agree), a non-extreme value, so a legitimate, engaged, internally-consistent extreme responder gets penalized for *style*, not *inattention* — a false-positive caution. His profile is otherwise textbook-clean (DI 100, pair diffs 0, coherent MAK/GRD trade profile). Extremity alone here does exactly what the spec asked about ("should extremity soft-flag?") — and the answer the instrument gives is an accidental yes, via Q17, for the wrong reason. Also note MAK/GRD tie at 100 resolved by scale order (MAK before GRD).

---

## Batch F cross-persona notes

Tie-break dependence on scale-declaration order (MAK,EXP,VIS,MEN,PIO,GRD) silently determined the third/ordered dominant in P53 (three-way tie at 60), P57 (MAK/MEN tie at rank 1), and P60 (MAK/GRD tie at 100). The manual's tie-breaking guidance (6.5) addresses a *rank-3* tie under the 10-point rule ("shared third strand") but is silent on rank-1/rank-2 ties and on the ordered listing of dominants — the naive implementation just uses stable-sort order, which is arbitrary. Documentation ambiguity; naive output reported above.

Rounding: half-up honored via floor(x+0.5). No batch-F persona sat on a .5 boundary except the standard raw-33→57.5→58 and raw-41→77.5→78, both handled as documented.
