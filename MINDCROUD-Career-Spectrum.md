# The MINDCROUD Career Spectrum

**A Psychometric Career Assessment Based on Holland's RIASEC Model of Vocational Personality**

| | |
|---|---|
| **Instrument name** | The MINDCROUD Career Spectrum |
| **Version** | 1.1 (English master version) — post-audit revision; see Changelog |
| **Instrument type** | Vocational interest / vocational personality inventory |
| **Stakes** | Medium — career guidance, coaching, and development (not selection or hiring) |
| **Scored items** | 60 (10 per Career Avatar scale) |
| **Administered items** | 65 (60 scored + 3 attention checks + 2 consistency-check duplicates) |
| **Response format** | 5-point Likert agreement scale |
| **Output** | Six Spectrum Scores (0–100), Spectrum Heatmap, 2–3 Dominant Avatars, Differentiation Index, validity flags |
| **Target reliability** | Cronbach's alpha ≥ .80 per scale |
| **Validation status** | Not yet empirically validated (see Section 10). A full simulated psychometric audit (8-stage, 120-persona protocol) was completed 2026-07-07; v1.1 implements its critical fixes. See `validation/mindcroud-career-spectrum-psychometric-audit.md`. |

---

## Section 1. Assessment Overview

### 1.1 Purpose

The MINDCROUD Career Spectrum is a career guidance and coaching instrument. Its purpose is to help working adults and students identify the two or three **Career Avatars** — psychological career profiles — where they have the highest probability of building a fulfilling and rewarding career. It is designed for two use cases:

1. **Consultant-led coaching.** A trained career consultant administers the instrument, reviews the Spectrum Heatmap with the client, and uses the Career Recommendations Engine to structure exploration of concrete career directions.
2. **Self-directed exploration.** A client completes the assessment independently and receives a premium narrative report that describes their Spectrum, their Dominant Avatars, and recommended career families to investigate.

The instrument is explicitly a **development and guidance tool**. It is not designed, normed, or validated for personnel selection, hiring, promotion, or any other high-stakes decision, and it must not be used for those purposes (see Section 11).

### 1.2 Construct

The instrument measures **vocational personality**: stable patterns of preference for work activities, work environments, and the kinds of work that give a person energy or drain it. The theoretical foundation is John Holland's RIASEC model, the most extensively researched and validated framework in career psychology. Holland's central claim — that people and work environments can be described on the same six dimensions, and that congruence between person and environment predicts satisfaction, stability, and performance — has accumulated more than five decades of supporting evidence.

The six RIASEC dimensions are branded as the six **MINDCROUD Career Avatars**:

| Career Avatar | RIASEC dimension | Core pattern |
|---|---|---|
| **The Maker** | Realistic (R) | Practical, hands-on, action-oriented. Energized by tools, machines, physical materials, and tangible results. Drained by ambiguity, office politics, and purely theoretical work. |
| **The Explorer** | Investigative (I) | Analytical, curious, intellectual. Energized by research, data, complex problems, and discovery. Drained by repetitive routine and high-pressure selling. |
| **The Visionary** | Artistic (A) | Imaginative, expressive, original. Energized by creative freedom, aesthetics, and producing something new. Drained by rigid rules and standardization. |
| **The Mentor** | Social (S) | Empathetic, cooperative, service-oriented. Energized by teaching, helping, and developing people. Drained by isolated technical work and impersonal transactional roles. |
| **The Pioneer** | Enterprising (E) | Persuasive, ambitious, energetic. Energized by leading, influencing, competing, and building ventures. Drained by slow bureaucracy and lack of autonomy. |
| **The Guardian** | Conventional (C) | Structured, detail-oriented, dependable. Energized by order, accuracy, systems, and stability. Drained by constant change and unstructured, open-ended demands. |

Two design principles follow from the model:

- **Everyone is a blend.** Respondents carry traits of all six Avatars in different proportions. The instrument therefore reports a full **Spectrum Heatmap** — a 0–100 score on every Avatar — rather than a single type label.
- **Combinations carry the signal.** Following Holland's convention of two- and three-letter codes, interpretation is built on the person's 2–3 **Dominant Avatars** in combination, not on any single scale in isolation.

### 1.3 Target population

- Working adults and students aged 16 and up.
- General population, all education levels.
- All items are written at or below an 8th-grade reading level, in concrete behavioral language, free of idioms, slang, and culturally specific references, so the instrument can be translated into multiple languages without losing meaning.

### 1.4 What the instrument produces

For each respondent:

1. Six **Spectrum Scores** (0–100), one per Career Avatar.
2. The **Spectrum Heatmap**: all six scores visualized as an intensity-coded band display, ordered from highest to lowest.
3. **Dominant Avatars**: the top 2 Avatars, plus the third if it is within 10 points of the second.
4. A **Differentiation Index** and a flat-profile flag where relevant.
5. **Validity indicators** based on attention checks and consistency pairs.
6. A narrative report: band-level descriptors for each Avatar and combination-based career recommendations.

---

## Section 2. Test Blueprint

### 2.1 Dimensions and facets

Each Career Avatar scale samples three facets of the construct, so that a scale score reflects the whole vocational pattern rather than a single behavior:

- **Facet 1 — Activity preferences (ACT):** the work tasks the person enjoys doing.
- **Facet 2 — Environment preferences (ENV):** the settings, structures, and conditions in which the person prefers to work.
- **Facet 3 — Energy and drain (NRG):** what gives the person energy at work and what depletes it.

### 2.2 Blueprint table

| Scale | RIASEC | Items | ACT items | ENV items | NRG items | Positively keyed | Negatively keyed |
|---|---|---|---|---|---|---|---|
| The Maker | R | 10 | 5 | 2 | 3 | 8 | 2 |
| The Explorer | I | 10 | 5 | 2 | 3 | 8 | 2 |
| The Visionary | A | 10 | 4 | 3 | 3 | 7 | 3 |
| The Mentor | S | 10 | 4 | 3 | 3 | 8 | 2 |
| The Pioneer | E | 10 | 4 | 3 | 3 | 7 | 3 |
| The Guardian | C | 10 | 4 | 3 | 3 | 7 | 3 |
| **Total scored** | | **60** | **26** | **16** | **18** | **45 (75%)** | **15 (25%)** |

Keying balance is exactly 75% positive / 25% negative across the instrument, and approximately so within each scale (7–8 positive, 2–3 negative). All negatively keyed items use **antonym-based reversal** — they describe the opposite preference (for example, "I would rather work with ideas than with physical objects") — never simple negation with "not," which is error-prone for respondents and fragile in translation.

### 2.3 Non-scored quality items

| Type | Count | Placement | Purpose |
|---|---|---|---|
| Attention checks | 3 | ~25%, ~50%, ~75% progress points (Q17, Q33, Q49) | Detect inattentive or random responding |
| Consistency-check duplicates | 2 | Far from their paired scored items (Q41 pairs with Q1; Q56 pairs with Q10) | Detect careless or inconsistent responding via semantically equivalent item pairs |

### 2.4 Item-writing standards applied

Every item in the final form satisfies all of the following:

1. **One idea per item.** No double-barreled statements.
2. **Concrete, behavioral, observable language.** Items describe what the person enjoys doing, where they prefer to work, or what energizes or drains them — not abstract self-evaluations ("I am a practical person") or ability claims.
3. **8th-grade reading level or below.** Short sentences, common vocabulary.
4. **Translation robustness.** No idioms, slang, metaphors, or culturally specific references (no country-specific jobs, sports, institutions, or brand names). Every item expresses a meaning that survives literal translation.
5. **Originality.** All 60 items (plus quality items) are 100% original. They were written solely from the conceptual definitions of the six Avatars. No item reproduces or closely paraphrases material from the Strong Interest Inventory, the Self-Directed Search, the O*NET Interest Profiler, the IPIP RIASEC markers, or any other existing instrument.
6. **Pool-based selection.** A candidate pool of 120 items (20 per scale) was generated internally and screened for clarity, distinctiveness (low expected cross-loading on neighboring scales), translation robustness, facet coverage, and keying balance. The strongest 10 items per scale were retained for the final form; the remaining candidates are held in reserve for form revision after pilot item analysis (see Section 10).

### 2.5 Sequencing rules applied

- The form opens with easy, pleasant, non-threatening activity items (teaching a skill, repairing an object, organizing information).
- Items from the six scales are interleaved so no two consecutive items belong to the same scale and the factor structure is not transparent to the respondent.
- No scale labels, Avatar names, or section headers appear during administration.
- All items in the first quarter of the form are positively keyed; negatively keyed items begin after the respondent has settled into the task.
- Attention checks sit at the 25%, 50%, and 75% progress points. Consistency duplicates are separated from their partner items by 40+ positions.

---

## Section 3. Administration Instructions

### 3.1 Standardized respondent instructions

> **Welcome to The MINDCROUD Career Spectrum.**
>
> This questionnaire helps you discover the kinds of work that fit you best — the activities, settings, and challenges where you are most likely to feel engaged, capable, and fulfilled.
>
> You will read 65 short statements. For each one, choose the answer that describes you best:
>
> **1 = Strongly disagree  2 = Disagree  3 = Neutral  4 = Agree  5 = Strongly agree**
>
> A few things to keep in mind:
>
> - **There are no right or wrong answers.** This is not a test of ability or knowledge. It is a picture of your preferences.
> - **Answer for who you are, not who you think you should be.** Ignore what employers, family, or friends might expect. Choose what is true for you.
> - **Do not think about salary, status, or job openings.** Answer only about what you would enjoy.
> - **Go with your first honest reaction.** Most people finish in 10 to 15 minutes.
> - **Answer every statement.** If you are unsure, choose the answer that is closest to how you feel most of the time.
> - **A few statements are quality checks** that ask you to select a specific answer. They simply confirm that the statements are being read — just follow their instruction.
> - **If you are a student or not currently working,** answer about the kinds of work and activities you would enjoy, based on school, projects, hobbies, or any experience you have.
>
> Your answers are confidential and will be used only to prepare your personal Career Spectrum report. When you are ready, begin.

### 3.2 Administration parameters

- **Estimated completion time:** 10–15 minutes for most respondents; allow up to 25 minutes for younger respondents or those completing the form in a second language.
- **Mode:** Online self-report (primary) or supervised paper form. Present items one screen-page at a time or in short blocks; always show the full 5-point scale with its verbal anchors.
- **Environment:** Quiet setting, single sitting, no discussion of answers with others during completion.
- **Administrator conduct:** Administrators may explain the instructions and clarify the meaning of the response scale, but must not explain, rephrase, or interpret individual items. If a respondent asks what an item means, the standard reply is: "Answer based on what the statement means to you."
- **Missing data rule:** The online form should require a response to every item. On paper forms, a scale with more than 2 missing items should not be scored; with 1–2 missing items, substitute the mean of the respondent's completed items on that scale (rounded to the nearest whole number) and flag the scale as estimated.

---

## Section 4. Assessment Items

*Respondent-facing form. Present the response scale once at the top; do not display any Avatar labels, facet labels, or keying information.*

**Response scale (shown once at the top of the form):**

**1 = Strongly disagree  2 = Disagree  3 = Neutral  4 = Agree  5 = Strongly agree**

---

1. I enjoy teaching someone a new skill.
2. I enjoy repairing broken objects with my hands.
3. I enjoy organizing information into clear systems.
4. I enjoy studying information to find out why something happens.
5. I enjoy convincing others to support an idea.
6. I enjoy creating original work, such as a design, a story, or a piece of music.
7. I like using tools or machines to complete a task.
8. I like helping people find a way through their problems.
9. I like solving problems that require deep thinking.
10. I like checking details to make sure everything is correct.
11. I like finding new ways to express an idea.
12. I like taking the lead when a group needs direction.
13. I enjoy exploring new ideas and discoveries in any subject.
14. I enjoy building things I can touch when they are finished.
15. Seeing a person grow because of my support makes my work feel meaningful.
16. I work best when I have a clear plan and a fixed schedule.
17. To show that you are reading each statement, select answer 4 ('Agree') here.
18. Working toward a clear goal against a challenge brings out my best effort.
19. I do my best work in places with freedom and few fixed rules.
20. I feel comfortable in a workshop, on a work site, or outdoors.
21. I prefer work where I am not responsible for anyone else's progress.
22. Completing a task exactly as planned gives me satisfaction.
23. I like work settings where careful analysis matters more than speed.
24. I am more comfortable supporting a plan than deciding it.
25. Making something beautiful gives me energy.
26. I like jobs where I can see the physical results of my work at the end of the day.
27. I prefer workplaces where people cooperate closely.
28. Digging into the details of a problem does not appeal to me.
29. I enjoy jobs where every day is different and unplanned.
30. I enjoy work environments where things move quickly.
31. I prefer tasks with one correct answer over tasks with many possible answers.
32. Working with physical materials gives me energy.
33. For this statement, select answer 1 ('Strongly disagree').
34. I enjoy giving my full attention when someone shares a personal difficulty.
35. Understanding how something truly works gives me deep satisfaction.
36. I enjoy keeping records accurate and up to date.
37. I like being the person who starts a new project.
38. I enjoy imagining things that do not exist yet.
39. Working with physical objects appeals to me less than other kinds of work.
40. Helping another person with a problem gives me energy.
41. I like showing another person how to do something new.
42. I keep asking questions until I fully understand a topic.
43. I would rather improvise than follow a step-by-step plan.
44. Trying to persuade people drains my energy.
45. I prefer work where nothing is left open to my imagination.
46. I feel proud when I fix something that was not working.
47. I like roles where my main task is to support other people's growth.
48. I feel energized when I face a complicated problem.
49. This is a quality check. Select the middle answer, 3 ('Neutral').
50. I prefer a stable job with clear duties over a job that changes all the time.
51. Winning support for my idea after working hard for it excites me.
52. I am drawn to work where personal style and taste matter.
53. Spending the whole day working with my hands would not suit me.
54. A full day of helping people with personal problems would exhaust me.
55. I prefer a quick practical answer over a deep investigation.
56. I enjoy reviewing work carefully to find small errors.
57. Clear rules and procedures help me feel confident at work.
58. I avoid situations where my results are compared with others' results.
59. I feel full of energy when I am inventing something new.
60. I enjoy taking devices apart to learn how they work.
61. I enjoy explaining difficult things in a way others can understand.
62. I like work that lets me spend a long time investigating a single question.
63. Keeping detailed records all day would drain my energy.
64. I would enjoy being responsible for the success of a business or a team.
65. Work that depends on my imagination tires me out.

*End of form. Thank the respondent and confirm submission.*

---

## Section 5. Item Map (Administrator Only)

*This table is confidential test material. Never show it to respondents before or during administration.*

**Legend.** Avatar: MAK = The Maker (Realistic), EXP = The Explorer (Investigative), VIS = The Visionary (Artistic), MEN = The Mentor (Social), PIO = The Pioneer (Enterprising), GRD = The Guardian (Conventional). Facet: ACT = activity preference, ENV = environment preference, NRG = energy/drain. Keying: + = positively keyed, − = negatively keyed (reverse-scored). Item code = internal development ID.

| Q# | Item code | Avatar | Facet | Keying | Notes |
|---|---|---|---|---|---|
| 1 | MEN-01 | MEN | ACT | + | Consistency pair A, first member |
| 2 | MAK-01 | MAK | ACT | + | |
| 3 | GRD-01 | GRD | ACT | + | |
| 4 | EXP-01 | EXP | ACT | + | |
| 5 | PIO-01 | PIO | ACT | + | |
| 6 | VIS-01 | VIS | ACT | + | |
| 7 | MAK-02 | MAK | ACT | + | |
| 8 | MEN-02 | MEN | ACT | + | |
| 9 | EXP-02 | EXP | ACT | + | |
| 10 | GRD-02 | GRD | ACT | + | Consistency pair B, first member |
| 11 | VIS-02 | VIS | ACT | + | |
| 12 | PIO-02 | PIO | ACT | + | |
| 13 | EXP-03 | EXP | ACT | + | |
| 14 | MAK-03 | MAK | ACT | + | |
| 15 | MEN-03 | MEN | NRG | + | |
| 16 | GRD-03 | GRD | ENV | + | |
| 17 | ACHK-1 | — | — | — | Attention check: correct answer = 4 (Agree) |
| 18 | PIO-03 | PIO | NRG | + | |
| 19 | VIS-03 | VIS | ENV | + | |
| 20 | MAK-04 | MAK | ENV | + | |
| 21 | MEN-09 | MEN | ENV | − | Reverse-scored |
| 22 | GRD-04 | GRD | NRG | + | |
| 23 | EXP-04 | EXP | ENV | + | |
| 24 | PIO-08 | PIO | ACT | − | Reverse-scored |
| 25 | VIS-04 | VIS | NRG | + | |
| 26 | MAK-05 | MAK | ENV | + | |
| 27 | MEN-04 | MEN | ENV | + | |
| 28 | EXP-09 | EXP | ACT | − | Reverse-scored |
| 29 | GRD-08 | GRD | ENV | − | Reverse-scored |
| 30 | PIO-04 | PIO | ENV | + | |
| 31 | VIS-08 | VIS | ACT | − | Reverse-scored |
| 32 | MAK-06 | MAK | NRG | + | |
| 33 | ACHK-2 | — | — | — | Attention check: correct answer = 1 (Strongly disagree) |
| 34 | MEN-05 | MEN | ACT | + | |
| 35 | EXP-05 | EXP | NRG | + | |
| 36 | GRD-05 | GRD | ACT | + | |
| 37 | PIO-05 | PIO | ACT | + | |
| 38 | VIS-05 | VIS | ACT | + | |
| 39 | MAK-09 | MAK | ACT | − | Reverse-scored |
| 40 | MEN-06 | MEN | NRG | + | |
| 41 | CCHK-A | — | — | — | Consistency pair A, second member (pairs with Q1); not scored on any scale |
| 42 | EXP-06 | EXP | ACT | + | |
| 43 | GRD-09 | GRD | ACT | − | Reverse-scored |
| 44 | PIO-09 | PIO | NRG | − | Reverse-scored |
| 45 | VIS-09 | VIS | ENV | − | Reverse-scored |
| 46 | MAK-07 | MAK | NRG | + | |
| 47 | MEN-07 | MEN | ENV | + | |
| 48 | EXP-07 | EXP | NRG | + | |
| 49 | ACHK-3 | — | — | — | Attention check: correct answer = 3 (Neutral) |
| 50 | GRD-06 | GRD | ENV | + | |
| 51 | PIO-06 | PIO | NRG | + | |
| 52 | VIS-06 | VIS | ENV | + | |
| 53 | MAK-10 | MAK | NRG | − | Reverse-scored |
| 54 | MEN-10 | MEN | NRG | − | Reverse-scored |
| 55 | EXP-10 | EXP | NRG | − | Reverse-scored |
| 56 | CCHK-B | — | — | — | Consistency pair B, second member (pairs with Q10); not scored on any scale |
| 57 | GRD-07 | GRD | NRG | + | |
| 58 | PIO-10 | PIO | ENV | − | Reverse-scored |
| 59 | VIS-07 | VIS | NRG | + | |
| 60 | MAK-08 | MAK | ACT | + | |
| 61 | MEN-08 | MEN | ACT | + | |
| 62 | EXP-08 | EXP | ENV | + | |
| 63 | GRD-10 | GRD | NRG | − | Reverse-scored |
| 64 | PIO-07 | PIO | ENV | + | |
| 65 | VIS-10 | VIS | NRG | − | Reverse-scored |

**Scale rosters (scored items only):**

- **The Maker (MAK):** Q2, Q7, Q14, Q20, Q26, Q32, Q39ʳ, Q46, Q53ʳ, Q60
- **The Explorer (EXP):** Q4, Q9, Q13, Q23, Q28ʳ, Q35, Q42, Q48, Q55ʳ, Q62
- **The Visionary (VIS):** Q6, Q11, Q19, Q25, Q31ʳ, Q38, Q45ʳ, Q52, Q59, Q65ʳ
- **The Mentor (MEN):** Q1, Q8, Q15, Q21ʳ, Q27, Q34, Q40, Q47, Q54ʳ, Q61
- **The Pioneer (PIO):** Q5, Q12, Q18, Q24ʳ, Q30, Q37, Q44ʳ, Q51, Q58ʳ, Q64
- **The Guardian (GRD):** Q3, Q10, Q16, Q22, Q29ʳ, Q36, Q43ʳ, Q50, Q57, Q63ʳ

(ʳ = reverse-scored.)

---
## Section 6. Scoring Key (Administrator Only)

### 6.1 Response coding

Each scored item is answered on the 5-point scale and coded as follows:

| Response | Positively keyed items | Negatively keyed (reverse-scored) items |
|---|---|---|
| Strongly disagree | 1 | 5 |
| Disagree | 2 | 4 |
| Neutral | 3 | 3 |
| Agree | 4 | 2 |
| Strongly agree | 5 | 1 |

Reverse scoring formula for negatively keyed items: **coded value = 6 − raw response**.

### 6.2 Reverse-scored items (complete list)

The following **15 items** are reverse-scored (5-4-3-2-1):

| Q# | Item code | Avatar scale |
|---|---|---|
| Q21 | MEN-09 | The Mentor |
| Q24 | PIO-08 | The Pioneer |
| Q28 | EXP-09 | The Explorer |
| Q29 | GRD-08 | The Guardian |
| Q31 | VIS-08 | The Visionary |
| Q39 | MAK-09 | The Maker |
| Q43 | GRD-09 | The Guardian |
| Q44 | PIO-09 | The Pioneer |
| Q45 | VIS-09 | The Visionary |
| Q53 | MAK-10 | The Maker |
| Q54 | MEN-10 | The Mentor |
| Q55 | EXP-10 | The Explorer |
| Q58 | PIO-10 | The Pioneer |
| Q63 | GRD-10 | The Guardian |
| Q65 | VIS-10 | The Visionary |

All other scored items are positively keyed (1-2-3-4-5 as answered). Items Q17, Q33, Q41, Q49, and Q56 are **never** included in any scale score.

### 6.3 Raw scale scores

For each Avatar, sum the coded values of its 10 items (after reverse scoring where required):

| Avatar scale | Items summed | Raw score range |
|---|---|---|
| The Maker | Q2 + Q7 + Q14 + Q20 + Q26 + Q32 + Q39ʳ + Q46 + Q53ʳ + Q60 | 10–50 |
| The Explorer | Q4 + Q9 + Q13 + Q23 + Q28ʳ + Q35 + Q42 + Q48 + Q55ʳ + Q62 | 10–50 |
| The Visionary | Q6 + Q11 + Q19 + Q25 + Q31ʳ + Q38 + Q45ʳ + Q52 + Q59 + Q65ʳ | 10–50 |
| The Mentor | Q1 + Q8 + Q15 + Q21ʳ + Q27 + Q34 + Q40 + Q47 + Q54ʳ + Q61 | 10–50 |
| The Pioneer | Q5 + Q12 + Q18 + Q24ʳ + Q30 + Q37 + Q44ʳ + Q51 + Q58ʳ + Q64 | 10–50 |
| The Guardian | Q3 + Q10 + Q16 + Q22 + Q29ʳ + Q36 + Q43ʳ + Q50 + Q57 + Q63ʳ | 10–50 |

(ʳ = use the reversed coding from 6.1.)

### 6.4 Spectrum Score transformation

Convert each raw scale score to a 0–100 **Spectrum Score**:

> **Spectrum Score = ((raw score − 10) / 40) × 100**, rounded half-up to the nearest whole number.

Worked examples: raw 10 → 0; raw 22 → 30; raw 30 → 50; raw 33 → 58 (57.5 rounds up); raw 41 → 78 (77.5 rounds up); raw 50 → 100.

*Implementation rule (mandatory, v1.1):* compute with **exact integer arithmetic** — `spectrum = floor(((raw − 10) × 5 + 1) / 2)`. Floating-point `round()` functions are non-conforming: IEEE doubles represent 57.5 as 57.4999…, and "banker's rounding" rounds .5 values to even — both were shown in the v1.0 audit to produce 1-point errors that sit directly on the dominance boundaries. Report Spectrum Scores as whole numbers only.

*Score lattice note:* attainable Spectrum Scores step in 2.5-point raw equivalents, so a gap of exactly 11 points between two scores is mathematically unreachable; the ≤ 10 rule in 6.5 operationally brackets 10 (include) versus 12 (exclude).

### 6.5 Dominant Avatar rule (revised v1.1)

1. Rank the six Spectrum Scores from highest (rank 1) to lowest (rank 6).
2. The **rank-1** Avatar is always Dominant.
3. The **rank-2** Avatar is Dominant **only if its Spectrum Score is ≥ 40**. If Score₂ < 40, report a **Solo Peak profile**: deliver the rank-1 Avatar narrative alone, present no combination profile, and route the client to exploration-first guidance. (v1.0 defect: pure-single-interest profiles received phantom co-dominant Avatars scored as low as 0, and a blend label whose second half was noise.)
4. The **third-ranked** Avatar is also Dominant if **both** conditions hold: Score₂ − Score₃ ≤ 10 **and** Score₃ ≥ 50. (The elevation gate stops the window from promoting midpoint noise in compressed or adolescent profiles.)
5. This yields **1, 2, or 3 Dominant Avatars** per person. The fourth-ranked Avatar is never Dominant, regardless of gaps.
6. **Solo-peak emphasis flag:** if Score₁ − Score₂ ≥ 25, lead the report with the rank-1 narrative and present the combination as secondary.

**Tie-breaking (deterministic cascade, v1.1).** Whenever two or more Avatars tie at any rank boundary that affects the Dominant set or the primary pair, resolve in this order:
1. Higher **raw scale score** (before transformation).
2. Higher **ACT-facet sum** (activity preferences are the most interest-central facet).
3. If still tied at a pair-defining or third-slot boundary, present **both candidate readings explicitly as "twin readings"** — the report shows both combination profiles and the consultant resolves the emphasis in conversation. Never let implementation sort order silently pick one (v1.0 audit: exact ties occurred in roughly 30% of realistic simulated profiles, and the reported archetype depended on JSON key order).
4. A tie for rank 3 that qualifies under rule 4 is presented as a "shared third strand" exactly as before: top 2 Dominant, both tied thirds named, consultant resolves in conversation.

**Combination lookup rule:** before looking up the pair in Section 8.2 or `scoring.json`, normalize it to canonical Avatar order **MAK, EXP, VIS, MEN, PIO, GRD**. (v1.0 tooling defect: alphabetical ordering broke the lookup for 7 of the 15 pairs.)

**Result precedence (hard rule, v1.1).** Outputs are gated in this order:
1. **Validity:** a *Potentially invalid* verdict suppresses Dominant Avatars, the combination profile, and career families entirely — in the data layer, not merely in report prose.
2. **Flat profile** (Differentiation Index < 15 on a valid protocol): deliver the flat-profile breadth narrative (6.6); do **not** deliver a combination profile.
3. **Low elevation** (Score₁ < 50): deliver the combination as tentative, with exploration-first framing.
4. Otherwise deliver the combination profile normally.

**Classification confidence (report with every profile).** Margin = Score₂ − Score₃ (for the third slot) and Score₁ − Score₂ (for pair order): margin ≥ 15 = High; 8–14 = Moderate; ≤ 7 = Low ("adjacent Avatars are statistically interchangeable — explore both readings").

### 6.6 Differentiation Index

> **Differentiation Index = highest Spectrum Score − lowest Spectrum Score.**

| Differentiation Index | Interpretation |
|---|---|
| ≥ 30 | Well-differentiated profile. Dominant Avatars are a strong basis for direction-setting. |
| 15–29 | Moderately differentiated. Dominant Avatars are meaningful but should be checked against life history and concrete experience. |
| < 15 | **Flat profile — flag.** |

**Flat-profile guidance (report language):** "Your scores are close together across all six Avatars. This usually means one of three things: your interests are still forming, you have genuinely broad interests, or it was hard to choose between the answer options. A flat profile is not a problem — it is a signal that you may benefit from deeper exploration (trying activities, structured experiments, or a guided interview with a consultant) before committing to a single career direction."

Consultants should treat a flat profile as an invitation to use card sorts, work-history interviews, or short real-world experiments rather than leaning on the ranked scores.

**Precedence (v1.1):** on a valid protocol, a flat profile **replaces** the combination profile — the report delivers the breadth narrative above instead of a Dominant-pair archetype (see 6.5, Result precedence). A flat profile is an interpretive gate, **not** a validity signal: it fires identically on disengagement, mood suppression, and genuinely broad interests, so its meaning must be established in debrief, not asserted by the engine.

**DI caveat:** the index measures range, not top-of-profile separation — one low scale can certify an otherwise compressed profile as "well-differentiated." Consultants should also inspect Score₁ − Score₃ before treating a profile as sharply directed.

### 6.7 Validity indicators

**A. Attention checks (Q17, Q33, Q49).**

| Item | Instructed answer | Pass condition |
|---|---|---|
| Q17 | Agree | Response = 4 |
| Q33 | Strongly disagree | Response = 1 |
| Q49 | Neutral | Response = 3 |

Scoring rule:
- **0 failures:** attention criterion passed.
- **1 failure:** caution flag. Score the profile, but note reduced confidence in the report footer and verify engagement in debrief.
- **2 or 3 failures:** **profile flagged as potentially invalid.** Do not deliver an automated report; a consultant should review and, where possible, re-administer.

**B. Consistency pairs.**

| Pair | First member | Second member | Semantic content |
|---|---|---|---|
| A | Q1 ("I enjoy teaching someone a new skill.") | Q41 ("I like showing another person how to do something new.") | Teaching/showing a skill |
| B | Q10 ("I like checking details to make sure everything is correct.") | Q56 ("I enjoy reviewing work carefully to find small errors.") | Detail checking |

Both members of each pair are positively phrased; compute the absolute difference between the two raw responses in each pair (no reversal needed).

Scoring rule:
- Difference of **0–1** on a pair: consistent.
- Difference of **2** on a pair: mild inconsistency. **A single mild pair is a NOTE only — it never counts toward the verdict** (explicit v1.1 ruling; v1.0 left this weight undefined and it alone flipped simulated profiles between "usable" and "discarded").
- Difference of **3–4** on a pair: strong inconsistency (invalid-level signal).
- **Invalid-level if:** either pair shows a difference of 3 or more, **or** both pairs show differences of 2 or more.

**C. Automated screens (required for online administration, v1.1).**

All indices below are computed from the existing 65 responses at zero respondent cost.

| Screen | Rule | Level |
|---|---|---|
| Completion time | total < 180 seconds | Caution |
| Long-string | ≥ 12 identical consecutive responses **or** modal response ≥ 80% of all items | Caution |
| Acquiescence index | mean **raw** response across the 60 scored items ≥ 4.3 | Caution ("agreement style") |
| Elevation index | all six Spectrum Scores ≥ 70 **and** DI < 20 | Caution ("uniformly high") |
| Intra-scale coherence | on ≥ 3 scales, \|mean(positively keyed coded) − mean(reverse-keyed coded)\| ≥ 2 | Caution ("possible misreading of reversed statements") |
| Extreme response style | endpoints (1 or 5) ≥ 85% of responses | Style note only — never a validity signal |
| Interest–energy divergence | any scale with \|mean(NRG coded) − mean(ACT coded)\| ≥ 1.5 | Report note: possible state effect (burnout, illness, mood); advise retest when circumstances change |

- **Combined validity verdict:** *Valid* (no signals) · *Interpret with caution* (exactly one caution-level signal) · *Potentially invalid* (any invalid-level signal, or two or more caution-level signals). Potentially invalid profiles require consultant review or re-administration, and the engine **must suppress** Dominant Avatars, combination, and career families (see 6.5, Result precedence) — v1.0 permitted an every-flag protocol to still receive a named career archetype.
- **Documented limitation (include in the manual and consultant training):** this battery detects **inattention and response-style anomalies, not motivated distortion**. Targeted inflation of a single scale by a determined respondent is undetectable by design — one more reason the instrument is prohibited for selection or hiring.
- **Non-redundancy note:** attention checks and consistency pairs each catch failure classes the other misses (mid-form scale flips pass all attention checks; periodic random patterns pass both consistency pairs). Both mechanisms are mandatory in every administration.

### 6.8 Worked scoring example

A respondent's coded scale sums: Maker 24, Explorer 41, Visionary 38, Mentor 44, Pioneer 33, Guardian 20.

1. Spectrum Scores: Maker 35, Explorer 78, Visionary 70, Mentor 85, Pioneer 58 (57.5 rounds up), Guardian 25.
2. Ranking: Mentor 85 > Explorer 78 > Visionary 70 > Pioneer 58 > Maker 35 > Guardian 25.
3. Dominant Avatars: Mentor and Explorer (top 2). Third rank: Visionary at 70 is within 10 points of 78 → also Dominant. Result: **Mentor + Explorer + Visionary** (three Dominant Avatars).
4. Differentiation Index: 85 − 25 = 60 → well-differentiated.
5. Interpretation lens: Mentor–Explorer combination is primary; Visionary is the flavor (see Section 8.3).

---

## Section 7. The Spectrum Heatmap

### 7.1 Display specification

The report presents all six Spectrum Scores as a **six-band horizontal heatmap**, one band per Avatar:

- **Order:** bands sorted from highest Spectrum Score (top) to lowest (bottom) — the respondent's personal spectrum, not a fixed scale order.
- **Band anatomy:** each band shows the Avatar name and emblem, the Spectrum Score as a number, a horizontal fill proportional to the score (0–100), and the band label (see 7.2).
- **Intensity coding:** color intensity conveys strength. Scores of 81–100 render in the deepest, most saturated tone; intensity fades smoothly through mid-tones (41–80) down to a pale, washed tone for 0–20. Each Avatar may use its own brand hue (e.g., Maker = amber, Explorer = teal, Visionary = violet, Mentor = coral, Pioneer = crimson, Guardian = slate blue), with intensity — not hue — carrying the score information so the display also works in single-color print and for color-blind readers. Always print the numeric score beside each band; color is reinforcement, never the only carrier of information.
- **Dominant markers:** the 2–3 Dominant Avatars carry a "Dominant" badge; if a flat profile is flagged, the heatmap header displays the flat-profile note from Section 6.6 instead of the badges being emphasized.
- **Accessibility:** minimum 4.5:1 text contrast, band label text never rendered in color alone, and a data table equivalent of the heatmap included at the end of the report.

### 7.2 Score bands

| Spectrum Score | Band label |
|---|---|
| 81–100 | **Core Resonance** |
| 61–80 | **Strong Resonance** |
| 41–60 | **Moderate Resonance** |
| 21–40 | **Low Resonance** |
| 0–20 | **Minimal Resonance** |

### 7.3 Band narratives (30 report paragraphs)

*One paragraph per Avatar per band, written for the respondent in warm, aspirational, second-person language. The report engine selects the paragraph matching each Avatar's band.*

#### The Maker

**Core Resonance (81–100).** The Maker is one of the strongest forces in your Spectrum. You come alive when work is physical and real — when you can pick up a tool, shape a material, and stand back at the end of the day to see what you built or repaired. Careers that keep you close to machines, materials, and tangible outcomes are not just options for you; they are where your energy naturally flows. Protect this: choose work where your hands and your practical judgment are the main event, not a side task.

**Strong Resonance (61–80).** The Maker runs strongly through you. You trust what you can touch, test, and fix, and you feel a quiet satisfaction when something broken starts working again because of you. You may not need a fully hands-on career, but you do need real, visible results — roles that stay abstract for months will slowly wear you down. Look for work that lets you build, operate, repair, or improve physical things or systems on a regular basis.

**Moderate Resonance (41–60).** The Maker has a steady, moderate presence in your Spectrum. You can enjoy practical, hands-on tasks, especially when they produce a clear result, but they are not the core of what drives you. In your career, this shows up best as an asset: you are comfortable getting practical when a situation demands it. Let your stronger Avatars set the direction, and treat your Maker side as a dependable skill you can call on.

**Low Resonance (21–40).** The Maker plays a background role for you. Physical, tool-based work is something you can do when needed, but it rarely gives you energy, and a career built mainly around it would likely leave you unsatisfied. This is useful self-knowledge: when comparing career options, be careful with roles where manual or technical hands-on work is the daily core rather than an occasional task.

**Minimal Resonance (0–20).** The Maker sits at the quiet edge of your Spectrum. Work centered on tools, machines, and physical materials simply is not where your motivation lives — and that is perfectly fine. Your energy is drawn elsewhere, and the clearest gift of this score is permission: you do not need to force yourself toward practical, hands-on paths to prove anything. Direct your career-building effort toward the Avatars at the top of your Spectrum.

#### The Explorer

**Core Resonance (81–100).** The Explorer is one of the strongest forces in your Spectrum. Your mind hunts for the "why" behind things — you are drawn to questions, data, and problems that take real thinking to untangle, and understanding something deeply gives you a satisfaction few other experiences can match. Build your career around investigation: research, analysis, diagnosis, and discovery are not just tasks you tolerate, they are the fuel you run on.

**Strong Resonance (61–80).** The Explorer runs strongly through you. You are most engaged when work gives you a puzzle worth solving and the time to solve it properly, and you lose patience with tasks that stay on the surface. Your best-fit careers give you regular, protected space for analysis and learning. Be cautious with roles that are all speed and no depth — you will do them well, but they will not feed you.

**Moderate Resonance (41–60).** The Explorer holds a moderate place in your Spectrum. You enjoy understanding how things work and can dig into a problem when it matters, but endless analysis for its own sake is not your natural home. In practice, this balance serves you well: you can partner with deep specialists without getting lost, and you bring enough curiosity to keep growing. Let your leading Avatars choose the field; your Explorer side will keep you sharp within it.

**Low Resonance (21–40).** The Explorer plays a supporting role for you. Long stretches of research, data work, or theoretical analysis tend to cost you more energy than they return. You can absolutely master the knowledge your career requires — but choose paths where learning serves action, people, or creation, rather than paths where analysis itself is the product.

**Minimal Resonance (0–20).** The Explorer rests at the quiet edge of your Spectrum. Careers built on research, abstract analysis, and long solitary investigation are unlikely to bring out your best, and there is real freedom in knowing that. You learn best by doing, connecting, or creating — so look for environments that keep you moving and engaged, and let others own the deep-analysis work.

#### The Visionary

**Core Resonance (81–100).** The Visionary is one of the strongest forces in your Spectrum. You carry a constant pull toward creating what does not yet exist — new forms, new ideas, new expressions — and you feel most yourself when your work carries your personal signature. Creative freedom is not a luxury for you; it is a working condition. Choose careers that pay you to imagine, design, and originate, and be wary of roles that would standardize you.

**Strong Resonance (61–80).** The Visionary runs strongly through you. Original ideas come naturally, you care about how things look and feel, and rigid procedures make you restless. You do not necessarily need the title of "artist" — but you do need room to shape your own approach and put something new into the world regularly. Seek work where creativity is expected of you, not merely permitted.

**Moderate Resonance (41–60).** The Visionary holds a moderate place in your Spectrum. You appreciate originality and enjoy adding creative touches to your work, yet you do not need constant open-ended invention to feel satisfied. This is a flexible position: you can bring fresh thinking into structured fields, which many teams deeply need. Let your stronger Avatars pick the arena, and use your creative side to stand out within it.

**Low Resonance (21–40).** The Visionary plays a background role for you. Fully open-ended creative work — starting from a blank page with no guide — tends to drain rather than inspire you. You likely do your best work when goals and methods have some definition. When exploring careers, favor roles with clear purpose and structure, and enjoy creativity as an occasional ingredient rather than the main dish.

**Minimal Resonance (0–20).** The Visionary sits at the quiet edge of your Spectrum. Careers that demand constant invention and self-expression are not where your strength or your joy lives, and recognizing this is a genuine advantage. You bring value through other channels — steadiness, analysis, care, action, or leadership — and the world needs those at least as much as it needs new ideas.

#### The Mentor

**Core Resonance (81–100).** The Mentor is one of the strongest forces in your Spectrum. People are your medium: you feel most alive when you are teaching, guiding, supporting, or helping someone move forward, and another person's growth genuinely feels like your success. Build your career around human development — the daily substance of your work should be people, not paper. Roles that isolate you from others will starve the very thing that powers you.

**Strong Resonance (61–80).** The Mentor runs strongly through you. You listen well, you explain well, and you are drawn to workplaces where cooperation is real rather than a slogan. You may not need a purely helping profession, but you do need regular, meaningful human contact and a sense that someone is better off because of you. When comparing options, weigh the human dimension of each role as heavily as the technical one.

**Moderate Resonance (41–60).** The Mentor holds a moderate place in your Spectrum. You care about people and can support, teach, or collaborate effectively, but you also need substance beyond the relationship itself — a craft, a problem, or a goal. This balance is valuable: you can work closely with others without burning out on their needs. Look for roles where helping is woven into the work rather than being the entire work.

**Low Resonance (21–40).** The Mentor plays a supporting role for you. Extended emotional labor — days filled with other people's problems — costs you more energy than it returns. You can be a good colleague and a fair teammate, but careers whose core product is care, teaching, or counseling would likely wear you down. Choose paths where your contribution flows through tasks, ideas, or results, with human interaction in balanced doses.

**Minimal Resonance (0–20).** The Mentor rests at the quiet edge of your Spectrum. Work that consists mainly of nurturing, counseling, or continuous close collaboration does not draw your energy — you contribute best through what you make, solve, organize, or lead. This is not coldness; it is clarity. Honor it by choosing environments that respect focused, independent contribution.

#### The Pioneer

**Core Resonance (81–100).** The Pioneer is one of the strongest forces in your Spectrum. You are built to initiate: to persuade, to lead, to compete, and to turn ambitions into ventures. Influence and momentum give you energy that quieter work never will, and you would rather carry responsibility for results than wait for instructions. Build a career with a scoreboard and a steering wheel — leadership, entrepreneurship, and high-agency roles are your natural territory.

**Strong Resonance (61–80).** The Pioneer runs strongly through you. You step up when a group needs direction, you enjoy winning people over, and slow-moving environments test your patience. You do not need to own the company, but you do need autonomy, visible goals, and room to grow your influence. Favor roles where initiative is rewarded quickly — and be honest with yourself about how much bureaucracy you can tolerate.

**Moderate Resonance (41–60).** The Pioneer holds a moderate place in your Spectrum. You can lead, persuade, and push when the situation calls for it, but constant competition and self-promotion are not what you are seeking from work. This measured drive is an asset: you can take initiative without needing the spotlight. Let your stronger Avatars define the substance of your career, and let your Pioneer side open doors and advance it.

**Low Resonance (21–40).** The Pioneer plays a background role for you. Selling, competing, and jockeying for influence tend to drain you, and careers where advancement depends mainly on constant self-promotion would sit uncomfortably. You do your best work when you can focus on the work itself. Seek cultures that reward contribution and reliability rather than only visibility.

**Minimal Resonance (0–20).** The Pioneer rests at the quiet edge of your Spectrum. High-pressure persuasion, aggressive competition, and the constant hustle of venture-building are not your source of energy — and stepping off that track is a decision, not a defeat. Depth, craft, care, and consistency are equally powerful ways to build a rewarding career. Choose environments that value them.

#### The Guardian

**Core Resonance (81–100).** The Guardian is one of the strongest forces in your Spectrum. You bring order to the world: clear systems, accurate records, dependable processes, and plans that actually hold. Precision is not tedium for you — it is satisfaction, and organizations quite literally run on people with your pattern. Build your career where structure, accuracy, and reliability are mission-critical, and where your care for detail is treated as the professional strength it is.

**Strong Resonance (61–80).** The Guardian runs strongly through you. You work best with a clear plan, defined responsibilities, and standards you can trust, and you take real pride in work that is complete and correct. Constant chaos and shifting goalposts cost you energy that stable, well-run environments give back. Favor organizations with mature processes — or roles where you are the one who builds that maturity.

**Moderate Resonance (41–60).** The Guardian holds a moderate place in your Spectrum. You value order and can happily work within systems, yet you do not need everything planned to feel comfortable. This flexibility is worth money in the real world: you can keep quality high without being rigid. Whatever direction your leading Avatars point, your Guardian side will make your work trustworthy — a reputation that compounds over an entire career.

**Low Resonance (21–40).** The Guardian plays a background role for you. Detailed administration, strict procedures, and highly repetitive structure tend to dull your energy rather than focus it. You can hold the line on quality when it matters, but a career centered on records, compliance, and routine would likely feel confining. Look for roles that offer variety and movement, with structure as a support rather than the substance.

**Minimal Resonance (0–20).** The Guardian sits at the quiet edge of your Spectrum. Highly structured, detail-heavy, routine-driven work is where your motivation runs thinnest, and pretending otherwise helps no one. You thrive on change, ideas, people, or action — so choose settings that move, and where possible, partner with detail-strong colleagues or systems that cover what you would rather not carry alone.

---
## Section 8. Career Recommendations Engine

### 8.1 How the engine works

Recommendations are generated from **Dominant Avatar combinations**, never from a single Avatar. The logic follows Holland's person–environment fit principle: satisfaction, persistence, and performance rise when the pattern of a person's strongest interests matches the pattern of demands and rewards in a work environment. The engine:

1. Takes the respondent's 2–3 Dominant Avatars (Section 6.5).
2. Uses the **top two** as the primary interpretive lens and looks up that pair below.
3. If a third Dominant Avatar exists, applies it as a tiebreaker and flavor (Section 8.3).
4. Outputs the combination profile and its best-fit **career families** — broad occupational groupings aligned with the O*NET job-family structure (SOC major groups), so a consultant can drill from each family into specific O*NET occupations (for example, via O*NET OnLine's browse-by-interests function, which classifies every occupation by its empirical RIASEC code).

Career families are deliberately broad. The instrument identifies the *territory*; the consultant and client choose the *address* using education level, labor-market realities, values, and constraints.

### 8.2 The 15 two-Avatar combinations

*Order within a pair does not matter for the lookup; the higher-scoring Avatar of the pair colors the emphasis in conversation.*

---

**1. The Maker + The Explorer — "The Diagnostician" (R–I)**

You combine a hands-on instinct with an analytical mind: you want to touch the machine *and* understand exactly why it behaves the way it does. You are at your best where physical systems meet hard problems — testing, diagnosing, improving, and making things work measurably better.

Best-fit career families:
- **Architecture & Engineering (including engineering technology):** engineering environments reward exactly this blend — applied analysis performed on real physical systems with testable results.
- **Installation, Maintenance & Repair (diagnostic trades):** advanced repair work (aircraft, industrial machinery, vehicles, building systems) is applied troubleshooting — investigation with tools in hand.
- **Life, Physical & Science Technician roles:** laboratory and field technician work pairs procedures and instruments with genuine scientific questions.

---

**2. The Maker + The Visionary — "The Artisan" (R–A)**

You want to make things — and you want the things you make to carry beauty, originality, and your personal signature. Mass production bores you; your satisfaction comes from skilled hands executing an original idea.

Best-fit career families:
- **Production (craft and precision occupations):** craft trades — woodworking, fabrication, instrument making, tailoring, restoration — reward manual mastery in service of aesthetic quality.
- **Food Preparation & Culinary Arts:** professional cooking is a physical craft judged on creativity and taste, a direct expression of this blend.
- **Arts, Design, Entertainment & Media (technical and fabrication roles):** set building, sound and camera work, exhibit fabrication, and product prototyping put hands-on skill inside creative production.

---

**3. The Maker + The Mentor — "The Responder" (R–S)**

You help people through action, not just words: when someone needs support, your instinct is to show up and physically do something about it. You are energized by service with your sleeves rolled up — practical care with a human face.

Best-fit career families:
- **Protective Service:** emergency response, firefighting, and public safety combine physical capability with direct service to people in need.
- **Healthcare Support:** hands-on patient care — therapy assistance, rehabilitation support, home health — is literally helping with your hands.
- **Personal Care, Fitness & Recreation Services:** coaching, training, and activity instruction let you develop people through physical practice rather than at a desk.

---

**4. The Maker + The Pioneer — "The Groundbreaker" (R–E)**

You want to build real things *and* run the show: practical competence plus the ambition to own outcomes, win work, and lead crews. You respect results you can stand on, and you would rather be responsible for the whole job than a small piece of it.

Best-fit career families:
- **Construction & Extraction (supervisory and contracting roles):** site leadership and contracting reward people who can both do the work and drive the business.
- **Management (construction, agricultural, and operations management):** managing physical operations — farms, fleets, plants, projects — keeps leadership anchored in the tangible world.
- **Installation, Maintenance & Repair (service-business ownership):** trade-based businesses convert hands-on mastery into an enterprise you lead and grow.

---

**5. The Maker + The Guardian — "The Steady Hand" (R–C)**

You are the person who does precise physical work correctly, every time: tools plus standards, skill plus discipline. You take pride in output that passes inspection — and organizations depend on exactly that reliability.

Best-fit career families:
- **Production (skilled machine operation and quality control):** machining, operation, and inspection reward precise hands and respect for specifications in equal measure.
- **Transportation & Material Moving:** professional driving and logistics operations pair physical work with schedules, regulations, and procedures — structure in motion.
- **Construction & Extraction (code-governed trades):** trades such as electrical and plumbing work are hands-on crafts executed inside strict codes and standards, fitting both sides of this blend.

---

**6. The Explorer + The Visionary — "The Idea Architect" (I–A)**

You live where analysis meets imagination: you want to understand deeply *and* express what you find in original form. You are drawn to questions without ready answers and to work that produces new understanding, new designs, or new interpretations.

Best-fit career families:
- **Life, Physical & Social Science (research, especially human and social sciences):** research on people, culture, and behavior rewards rigorous inquiry with interpretive creativity.
- **Architecture & Engineering (architecture and design-led engineering):** architecture is the canonical fusion of analytical constraint and creative form.
- **Arts, Design, Entertainment & Media (research-driven design and content):** user experience research, information design, documentary and science communication turn investigation into crafted expression.

---

**7. The Explorer + The Mentor — "The Healer" (I–S)**

You combine a scientific mind with genuine care for people: you want to understand what is wrong and use that understanding to help someone specific. Diagnosis in service of a human being is your natural work.

Best-fit career families:
- **Healthcare Practitioners & Technical (diagnosing and treating professions):** medicine, nursing, dentistry, and allied clinical fields are built exactly on science applied through a helping relationship.
- **Community & Social Service (clinical and counseling roles):** psychology, counseling, and behavioral health pair investigative depth with one-on-one human development.
- **Educational Instruction (science, health, and postsecondary teaching):** teaching complex subjects rewards deep understanding delivered through patient human connection.

---

**8. The Explorer + The Pioneer — "The Strategist" (I–E)**

You analyze to win: data, markets, and evidence are your raw material, and decisive action is your product. You are most alive when rigorous thinking gives you a competitive edge and the authority to act on it.

Best-fit career families:
- **Business & Financial Operations (analysis and strategy roles):** market research, economics, and management analysis pay for exactly this — investigation that drives commercial decisions.
- **Management (technology, science, and systems management):** leading technical teams and ventures needs someone fluent in the analysis and hungry for the outcome.
- **Legal:** legal work is investigative reasoning deployed in an adversarial, persuasive arena — analysis with a scoreboard.

---

**9. The Explorer + The Guardian — "The Analyst" (I–C)**

You bring deep thinking and impeccable order together: you want problems that require real intelligence *and* solutions that are exact, documented, and verifiable. Precision is not a constraint on your curiosity — it is how your curiosity works.

Best-fit career families:
- **Computer & Mathematical:** software, data science, statistics, and information security reward systematic minds that love structured problem-solving.
- **Business & Financial Operations (quantitative roles):** actuarial, audit, and financial analysis careers pair investigation with standards, controls, and accuracy.
- **Healthcare Practitioners & Technical (laboratory and diagnostic sciences):** laboratory science is rigorous investigation executed through exact protocols — both of your strengths, daily.

---

**10. The Visionary + The Mentor — "The Inspirer" (A–S)**

You create in order to connect: expression, for you, is a way of reaching, teaching, and moving people. You are drawn to work where imagination and empathy amplify each other — where something you made helps someone grow.

Best-fit career families:
- **Educational Instruction & Library (arts, language, and enrichment teaching):** teaching creative and expressive subjects lets you develop people through the work you love.
- **Community & Social Service (expressive and developmental programs):** art, music, and recreational therapy and youth development use creativity as a direct instrument of care.
- **Arts, Design, Entertainment & Media (communication for human impact):** writing, translation, and content creation aimed at educating and inspiring audiences serve both Avatars at once.

---

**11. The Visionary + The Pioneer — "The Creative Director" (A–E)**

You have ideas *and* the drive to sell them: originality plus persuasion, taste plus ambition. You want your creative work to reach the market, win the pitch, and carry your name — and you are willing to lead to make that happen.

Best-fit career families:
- **Arts, Design, Entertainment & Media (direction and production roles):** art direction, producing, and creative leadership reward people who can both generate the vision and drive it to delivery.
- **Management (advertising, marketing, and brand leadership):** marketing and brand management are commercial arenas whose currency is creative ideas.
- **Sales & Related (creative and client-facing services):** selling design, media, and experiences lets persuasion and aesthetic judgment work as one skill.

---

**12. The Visionary + The Guardian — "The Curator" (A–C)**

You pair creative sensibility with a love of order — a rarer blend that makes you the person who gives beautiful things structure and structured things beauty. You polish, refine, organize, and perfect until the work is both correct and elegant.

Best-fit career families:
- **Arts, Design, Entertainment & Media (editing and production-craft roles):** editing, post-production, layout, and publication work reward exacting standards applied to creative material.
- **Educational Instruction & Library (archives, collections, and curation):** archival and collections work preserves creative and cultural material through meticulous systems.
- **Business & Communication Support (technical writing and documentation):** technical writing and documentation design turn complex material into clear, well-crafted, standardized form — precision with a designer's eye.

*Consultant note:* The Visionary and The Guardian sit opposite each other in Holland's hexagon, so this profile is statistically uncommon and may reflect two genuinely competing pulls. Explore which contexts activate each side before narrowing options.

---

**13. The Mentor + The Pioneer — "The Motivator" (S–E)**

People follow you because you genuinely care and visibly lead: warmth with momentum. You are built for roles where developing people and driving results are the same job — rallying, coaching, organizing, and advocating.

Best-fit career families:
- **Management (people-centered management: HR, education, health and community services):** these management tracks are leadership whose product is human growth and well-being.
- **Business & Financial Operations (training, development, and human resources):** learning and talent development professionalize exactly this pairing — influence used to build people.
- **Community & Social Service (program leadership and advocacy):** running programs, fundraising, and advocacy require a persuasive voice in service of others.

---

**14. The Mentor + The Guardian — "The Anchor" (S–C)**

You care for people *through* reliability: being the steady, organized presence others can count on. Your help is practical and consistent — records kept, appointments honored, details handled — and people feel safer because you are there.

Best-fit career families:
- **Healthcare Support (clinical assisting and coordination):** medical and dental assisting and patient coordination combine caring contact with procedures and accurate records.
- **Educational Instruction & Library (instructional support):** teaching assistance and learning support pair daily service to students with structured routines.
- **Office & Administrative Support (people-facing coordination):** front-of-house coordination, client services, and program administration reward warm, dependable, well-organized professionals.

---

**15. The Pioneer + The Guardian — "The Executive" (E–C)**

You drive ambitious goals through disciplined systems: you want to win, and you know that winning at scale requires order, numbers, and follow-through. You are the builder of well-run commercial machines.

Best-fit career families:
- **Management (general, financial, and administrative management):** classic management careers reward exactly this combination of goal-drive and operational control.
- **Sales & Related (structured, high-professionalism sales):** financial services, insurance, real estate, and technical sales pair persuasion with process, licensing, and documentation.
- **Business & Financial Operations (finance, purchasing, and operations):** finance and operations roles convert ambition into systems, budgets, and measurable performance.

---

### 8.3 Handling three-Avatar profiles

When a respondent has three Dominant Avatars (Section 6.5), the engine works as follows:

1. **Primary lens = the top two.** Look up the pair in Section 8.2 exactly as for a two-Avatar profile. The pair defines the career-family territory.
2. **The third Avatar is a tiebreaker and flavor.** It does not add new career families; it *shifts emphasis within* the recommended families and helps choose among specific occupations when the consultant drills down:
   - **As tiebreaker:** when two career families in the pair's list appeal about equally, prefer the one that also feeds the third Avatar. (Example: Explorer + Mentor with third Avatar Guardian → within healthcare, weight structured clinical fields such as nursing, pharmacy, or laboratory-adjacent practice over open-ended counseling.)
   - **As flavor:** within any chosen family, prefer roles whose daily texture matches the third Avatar. (Example: Explorer + Mentor with third Avatar Visionary → within education and clinical fields, weight roles rich in communication, content creation, and creative methods — the Section 6.8 worked example.)
3. **Cross-check with a secondary pair when scores are tight.** If the second and third Spectrum Scores are within 3 points of each other, also read the combination of the first and third Avatars as a secondary profile and look for career families that appear in, or bridge, both lists.
4. **Consultant language:** describe the profile to the client as "your engine, your compass, and your flavor" — the top Avatar is the engine (what powers you), the second is the compass (where you point that power), and the third is the flavor (the daily texture that keeps work enjoyable).

Because the three-letter combination space (120 ordered / 20 unordered combinations) is too large to enumerate usefully, this two-plus-one procedure is the standard interpretive method; it mirrors accepted practice with Holland three-letter codes, where practitioners search occupations across permutations of the top letters when profiles are not sharply differentiated.

---

## Section 9. Psychometric Specifications

### 9.1 Reliability targets

| Property | Target | Benchmark rationale |
|---|---|---|
| Internal consistency (Cronbach's α / McDonald's ω) per scale | **≥ .80** (accept ≥ .78 at pilot; revise items below that) | The O*NET Interest Profiler Short Form — the closest structural analogue (60 items, 10 per RIASEC scale) — reports α = .78–.87 (M ≈ .81) in its psychometric sample and .82–.90 in its stability sample. EFPA review criteria rate .80–.89 as "good." A 10-item interest scale reaching α ≥ .90 is unusual; alphas above .90 are typical only of 30+ item scales (e.g., full O*NET IP: .93–.96; Strong GOTs: .90–.94). |
| Test–retest reliability (2–4 week interval) | **r ≥ .80** per scale | O*NET IP Short Form: r = .78–.86 (M = .82); SDS summary scales: .76–.89. |
| Item quality | Corrected item–total r ≥ .30 within scale; item–total r with own scale > r with any other scale | Standard item-analysis criteria for homogeneous interest scales. |

### 9.2 Planned validity evidence

**Structural validity.** RIASEC data have a known quasi-circumplex structure (hexagonal order R–I–A–S–E–C), so structural evaluation must use circumplex-appropriate methods, not only conventional CFA cutoffs:

- **Randomization test of hypothesized order relations (RTHOR):** target Correspondence Index (CI) ≥ .70, p < .05, on the 15 scale intercorrelations against the 72 circular-order predictions.
- **Multidimensional scaling:** a 2-dimensional solution should recover the R–I–A–S–E–C circular order and Prediger's Things–People / Data–Ideas axes.
- **Six-factor CFA and circular stochastic process model (CIRCUM):** report fit descriptively; note that plain six-factor CFA of RIASEC data routinely shows only marginal fit by conventional cutoffs because adjacent factors correlate by design.
- **Wording-method check:** because the instrument uses 15 reverse-keyed items (75/25 keying per specification), pilot analyses must test for a negative-wording method factor (bifactor or CFA with a wording factor). Psychometric literature documents that reverse-keyed Likert items can create method variance and depress unidimensionality. **Mitigation plan:** all negative items use antonym-based reversal (not negation); the reserve item pool contains positively keyed replacements for every negative item, so any negative item that misbehaves in the pilot (low item–total r, loading on a wording factor, high careless-response sensitivity) is replaced in Form 1.1 without redesigning the blueprint.

**Convergent and discriminant validity.** Correlate the six scales with an established open RIASEC measure (e.g., the public-domain RIASEC markers or the O*NET IP Short Form where licensing permits): target same-named-scale r ≥ .60 (published cross-inventory convergence for same-named RIASEC scales is r ≈ .36–.72, median ≈ .59), with every same-named correlation exceeding all off-diagonal correlations, and the off-diagonal pattern following hexagonal distance (adjacent > alternate > opposite).

**Criterion-related validity (development context).** Longer-term studies should relate congruence between Dominant Avatars and current/subsequent occupation to job satisfaction, engagement, and intention to stay. Meta-analytic benchmarks: interest congruence correlates with performance at ρ ≈ .30 and persistence at ρ ≈ .34–.36 (Nye et al., 2012; congruence-based prediction roughly doubles single-scale prediction, Nye et al., 2017); single interest scales predict performance more modestly (ρ ≈ .14–.26, Van Iddekinge et al., 2011). These effect sizes justify the instrument's positioning: fit meaningfully *raises the probability* of satisfaction and success — it does not guarantee them.

**Fairness.** Examine differential item functioning (DIF) by gender, age group, and (after translation) language version; interest measures show well-documented mean gender differences on Realistic-type content, so norms and report language must avoid presenting such differences as deficits.

### 9.3 Norming recommendations

- **Norm type:** primary reporting uses the criterion-referenced 0–100 Spectrum Score (transparent linear transformation). After norming studies, supplement with percentile norms per scale so consultants can say "compared with other adults."
- **Norm groups:** general working-adult norms first; add student (16–20) norms and, later, language-version norms. Per EFPA review guidance, aim for **≥ 300 per norm group** (200 = adequate, 300 = good, 400+ = excellent).
- **Within-person interpretation remains primary:** because RIASEC interpretation is profile-shaped (rank order within the person), norm-referenced information supports but never replaces the within-person Spectrum ranking.
- **Standards compliance:** development, documentation, and use follow the *Standards for Educational and Psychological Testing* (AERA/APA/NCME, 2014), the EFPA Test Review Model, and — for all future language versions — the ITC *Guidelines for Translating and Adapting Tests* (2nd ed., 2017), including forward-and-back translation, bilingual review, and empirical equivalence checks before operational use of any translation.

---

## Section 10. Validation Roadmap

### 10.1 Honest status statement

**The MINDCROUD Career Spectrum, Version 1.0, is a newly generated instrument. It has not yet been administered to any respondent, and no empirical evidence of its reliability, validity, or fairness exists yet.** Its design follows well-established theory (Holland's RIASEC model) and the psychometric conventions of successful analogous instruments, which makes the targets in Section 9 realistic — but design quality is a hypothesis, not a result. Until the milestones below are met, all reports must carry the provisional-status notice (Section 11.6), and results must be treated as structured conversation starters, not measurements of established precision.

### 10.2 Roadmap

**Phase 0 — Content review and cognitive pretest (before any scoring).**
- Expert review of all 65 items by 2–3 career-assessment professionals against the blueprint (construct match, one-idea rule, reading level, translatability).
- Cognitive interviews with 10–30 respondents spanning the target range (ages 16+, mixed education levels): think-aloud comprehension of every item; revise any item that is misread.

**Phase 1 — Pilot study (N = 100–300).**
- Administer the full form online with response-time capture.
- Item analysis: response distributions, corrected item–total correlations (≥ .30), cross-scale correlations, flag negative-keyed items showing method effects.
- Reliability estimation: Cronbach's α and McDonald's ω per scale (target ≥ .80; investigate any scale < .78).
- Quality-item performance: attention-check failure rates and consistency-pair distributions; recalibrate flagging thresholds if base rates are extreme.
- Replace weak items from the 60-item reserve pool; produce Form 1.1.

**Phase 2 — Structural analysis.**
- Exploratory factor analysis on the pilot/expanded sample (aim for ≥ 5 respondents per item; N ≈ 300–600): confirm six interpretable factors and inspect cross-loadings.
- On an **independent** sample (N = 300+): confirmatory factor analysis, RTHOR randomization test (target CI ≥ .70), multidimensional scaling of the six scales, and a wording-factor check on the reverse-keyed items.

**Phase 3 — Validation study (N = 300+).**
- Convergent/discriminant study against an established RIASEC measure (targets in 9.2).
- Criterion snapshot: current-occupation congruence vs. job satisfaction and engagement measures.
- Test–retest subsample (n ≥ 75, 2–4 week interval; target r ≥ .80).
- DIF and measurement-invariance analyses by gender and age group.

**Phase 4 — Norming and operational release.**
- Norm the instrument on the target client population: ≥ 300 per norm group (working adults; students 16–20 as a second group).
- Publish a technical manual documenting all evidence per AERA/APA/NCME Standards; update report language to reflect actual (not target) reliability and validity.
- Remove the provisional-status notice only when Phases 1–4 are complete.

**Phase 5 — Translation and adaptation (per market).**
- Follow ITC Guidelines: double forward translation, reconciliation, back-translation, bilingual pilot, DIF analysis vs. the English master, and language-specific norms before commercial use in that language.

**Ongoing.** Re-examine norms every 3–5 years; log and review flagged-invalid profile rates; maintain an item bank with versioned forms.

---

## Section 11. Ethical Use Guidelines

### 11.1 Informed consent

Before administration, every respondent must be told, in plain language: what the assessment measures (work-related preferences, not ability, intelligence, or mental health); how long it takes; who will see the results; how data will be stored and for how long; that participation is voluntary; and that they may stop at any time. For respondents under 18, obtain parental/guardian consent where required by local law, and always obtain the young person's own assent.

### 11.2 Data privacy

- Assessment responses and reports are personal data. Process them under applicable data-protection law (e.g., GDPR in the EU): a defined lawful basis, purpose limitation (career guidance only), data minimization, defined retention periods, and the right of access, correction, and deletion.
- Store responses and reports encrypted; restrict access to the respondent, their consultant, and authorized administrators. Never share individual results with employers, schools, or other third parties without the respondent's explicit, specific consent.
- Use aggregated, de-identified data for norming and research only if the consent language covered this.

### 11.3 Appropriate use

- The MINDCROUD Career Spectrum is a **guidance and development tool**. It is appropriate for career exploration, coaching, education planning, and outplacement support.
- It must **not** be used for hiring, selection, promotion, admission, or any decision that grants or denies opportunity. It is neither designed nor validated for those stakes, and such use would be professionally and ethically improper.
- Results describe *preferences and probable fit*, not ability, potential, or worth. No score forbids any career; no score entitles anyone to one.
- Administrators and consultants should be trained in the instrument's model, scoring, and limits; interpretation for clients should be done by, or under the guidance of, a qualified career practitioner, especially for flagged or flat profiles.

### 11.4 Fit raises probability — it does not guarantee outcomes

All report and marketing language must respect the evidence: interest–environment fit meaningfully **raises the probability** of career satisfaction, persistence, and success, but it guarantees nothing. Outcomes also depend on skills, effort, opportunity, economic conditions, and chance. Required report language (verbatim or equivalent):

> "Your Career Spectrum shows where fulfilling work is *most likely* for you — it raises your odds, it does not decide your future. Treat these results as a well-lit starting point for exploration, not as a verdict on what you can or cannot do."

### 11.5 Respondent rights in feedback

Every respondent is entitled to: receive their full results in understandable form; ask questions and receive explanations; disagree with the results and have that disagreement respected as data ("the score suggests X, you experience Y — let's explore the difference"); and know that they can retake the assessment as their interests develop, since interests — especially before the mid-twenties — do change.

### 11.6 Provisional-status notice (mandatory until validation completes)

Until the roadmap in Section 10 is complete, every report must include:

> "This assessment is based on the most extensively researched model in career psychology, but this specific questionnaire is newly developed and still gathering scientific evidence. Please treat your results as a structured, thoughtful starting point for career conversations — and weigh them together with your experience, values, and circumstances."

---

## Appendix. Selected References

- American Educational Research Association, American Psychological Association, & National Council on Measurement in Education. (2014). *Standards for educational and psychological testing.* AERA.
- Armstrong, P. I., Allison, W., & Rounds, J. (2008). Development and initial validation of brief public domain RIASEC marker scales. *Journal of Vocational Behavior, 73*, 287–299.
- European Federation of Psychologists' Associations. (2013/2023). *EFPA review model for the description and evaluation of psychological and educational tests* (v4.2.6).
- Holland, J. L. (1997). *Making vocational choices: A theory of vocational personalities and work environments* (3rd ed.). Psychological Assessment Resources.
- International Test Commission. (2017). *ITC guidelines for translating and adapting tests* (2nd ed.). *International Journal of Testing, 18*(2), 101–134.
- Low, K. S. D., Yoon, M., Roberts, B. W., & Rounds, J. (2005). The stability of vocational interests from early adolescence to middle adulthood. *Psychological Bulletin, 131*, 713–737.
- Meade, A. W., & Craig, S. B. (2012). Identifying careless responses in survey data. *Psychological Methods, 17*, 437–455.
- Nauta, M. M. (2010). The development, evolution, and status of Holland's theory of vocational personalities. *Journal of Counseling Psychology, 57*, 11–22.
- Nye, C. D., Su, R., Rounds, J., & Drasgow, F. (2012). Vocational interests and performance: A quantitative summary. *Perspectives on Psychological Science, 7*, 384–403.
- Nye, C. D., Su, R., Rounds, J., & Drasgow, F. (2017). Interest congruence and performance: Revisiting recent meta-analytic findings. *Journal of Vocational Behavior, 98*, 138–151.
- Rounds, J., Su, R., Lewis, P., & Rivkin, D. (2010). *O\*NET Interest Profiler Short Form psychometric characteristics.* National Center for O\*NET Development.
- Savickas, M. L., Taber, B. J., & Spokane, A. R. (2002). Convergent and discriminant validity of five interest inventories. *Journal of Vocational Behavior, 61*, 139–184.
- Tracey, T. J. G., & Rounds, J. (1993). Evaluating Holland's and Gati's vocational-interest models: A structural meta-analysis. *Psychological Bulletin, 113*, 229–246.
- Van Iddekinge, C. H., Roth, P. L., Putka, D. J., & Lanivich, S. E. (2011). Are you interested? A meta-analysis of relations between vocational interests and employee performance and turnover. *Journal of Applied Psychology, 96*, 1167–1194.

---

## Changelog

### Version 1.1 (2026-07-07) — post-audit revision

Implements the critical fixes from the simulated psychometric audit (8-stage / 120-persona protocol; see `validation/mindcroud-career-spectrum-psychometric-audit.md`, evidence in `validation/evidence/`).

**Items (17 revised, same codes/keying/facets):**
- Attention checks Q17, Q33, Q49 reworded to be dual-coded (number + anchor name) so they work even when a delivery surface under-displays anchors.
- Q21, Q40 (Mentor): replaced introversion/extraversion proxies with helping-domain content.
- Q45 (Visionary), Q58 (Pioneer): de-mirrored from Guardian structure items (engineered A–C bipolarity removed at the worst two points).
- Q28, Q63: attention-/dyslexia-confounded wording replaced with interest-framed wording.
- Q24, Q18: cultural-valence (leader deference, competition) wording neutralized.
- Q53 (stamina confound), Q39 (idea-content import), Q65 (direct antonym of Q59 + borderline idiom), Q13 (STEM/reading channel), Q34 (hearing-assumptive + reading level), Q51 (commercial referent opacity) rewritten.
- Q19, Q29, Q31, Q43, Q50 unchanged but flagged in `items.json` for pilot item analysis (structure-axis / SES confounds).

**Scoring algorithm:**
- Exact integer arithmetic mandated for the Spectrum transformation (float rounding produced 1-point boundary errors).
- Dominance gates added: rank-2 floor (≥ 40, else Solo Peak profile), third-slot elevation gate (≥ 50), solo-peak emphasis flag (gap ≥ 25).
- Deterministic tie-break cascade (raw score → ACT facet → explicit twin readings); canonical pair-key ordering for combination lookup (v1.0 tool silently failed 7/15 pairs).
- Hard result precedence: invalid → suppress everything; flat → breadth narrative, no combination; low elevation → tentative combination.
- Classification confidence bands added (margin-based).

**Validity system:**
- Single mild consistency difference (=2) explicitly ruled a note, not a caution.
- New computed indices: acquiescence, elevation, intra-scale coherence, modal-proportion long-string, extreme-style note, interest–energy divergence (state-confound safeguard).
- Suppression of invalid profiles moved into the data layer.
- Documented limitation added: the battery detects inattention, not motivated distortion.

**Administration:**
- Respondent instructions now announce the quality-check items and include a student-context instruction.
- Delivery rule: every response option must display its number **and** verbal anchor; inputs must be keyboard- and screen-reader-accessible (v1.0 field defect: numeric-only buttons made instructed-response items unanswerable and blocked assistive technology).

### Version 1.0 — initial release.

---

*The MINDCROUD Career Spectrum™ — © MINDCROUD. All items, scales, narratives, and scoring rules in this document are original proprietary content. This document is confidential test material; do not distribute the Item Map or Scoring Key to respondents.*
