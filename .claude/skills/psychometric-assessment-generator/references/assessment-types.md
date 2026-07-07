# Assessment Type Specifications

This reference provides domain-specific design parameters for each assessment family.
Consult the section matching the user's assessment type.

## Table of Contents
1. Personality & Psychographic Profiling
2. Cognitive & Aptitude Testing
3. Attitudes, Preferences & Values (Market Research)
4. Behavioral & Competency-Based Assessments
5. Hybrid and Specialized Formats

---

## 1. Personality & Psychographic Profiling

### Available Frameworks

#### Big Five (OCEAN) — Gold Standard for Personality
- **Dimensions**: Openness, Conscientiousness, Extraversion, Agreeableness, Neuroticism
- **Facets**: 6 per dimension (30 total in the NEO-PI-R model)
- **Item counts**: 20 items (Mini-IPIP) → 60 (NEO-FFI) → 120 (IPIP-NEO) → 240 (NEO-PI-R, 8/facet)
- **Format**: 5-point Likert (agreement), balanced positive/negative keying
- **Reliability targets**: Domain α = .86–.92 for full-length, α ≥ .70 for short forms
- **When to use**: General personality assessment, career counseling, team building,
  research — the most validated personality model in psychology

##### Big Five Facets for Item Writing
| Domain | Facets |
|--------|--------|
| Openness | Fantasy, Aesthetics, Feelings, Actions, Ideas, Values |
| Conscientiousness | Competence, Order, Dutifulness, Achievement Striving, Self-Discipline, Deliberation |
| Extraversion | Warmth, Gregariousness, Assertiveness, Activity, Excitement-Seeking, Positive Emotions |
| Agreeableness | Trust, Straightforwardness, Altruism, Compliance, Modesty, Tender-Mindedness |
| Neuroticism | Anxiety, Angry Hostility, Depression, Self-Consciousness, Impulsiveness, Vulnerability |

#### HEXACO — When Ethics and Integrity Matter
- **Dimensions**: Honesty-Humility, Emotionality, Extraversion, Agreeableness, Conscientiousness, Openness
- **Key addition**: Honesty-Humility (sincerity, fairness, greed avoidance, modesty)
- **Item counts**: 60, 100, or 200 items
- **When to use**: Predicting counterproductive workplace behavior, ethics-sensitive roles,
  integrity assessment. Research shows H-H predicts unethical behavior better than Big Five

#### Dark Triad — Subclinical Personality Risk
- **Dimensions**: Machiavellianism, Narcissism, Psychopathy
- **Format**: Short Dark Triad (SD3) = 27 items (9 per trait), 5-point Likert
- **When to use**: Leadership derailment assessment, risk profiling. REQUIRES informed
  consent and careful framing — never label results as diagnoses
- **Ethical requirement**: Frame as "interpersonal style patterns," not pathology.
  Include explicit disclaimer that these are subclinical measures, not diagnostic tools.

#### VIA Character Strengths — Positive Psychology Focus
- **Dimensions**: 24 strengths under 6 virtues (Wisdom, Courage, Humanity, Justice,
  Temperance, Transcendence)
- **Format**: 96 items (4 per strength), all positively keyed
- **Scoring**: Rank-order yields top 5 "signature strengths"
- **When to use**: Coaching, development, team strengths mapping, positive psychology
  interventions. No negative outcomes — all results are framed as strengths.

#### Psychographic Segmentation (Market Research)
- **Dimensions**: Activities, Interests, Opinions (AIO framework), or custom segments
  based on values, lifestyle, media consumption, purchase motivations
- **Format**: Likert agreement + behavioral frequency + demographic filters
- **Item counts**: 30–60 items covering 5–8 lifestyle/value dimensions
- **When to use**: Consumer segmentation, persona development, media planning
- **Key difference from clinical personality**: Optimize for marketing actionability,
  not psychological precision. Face validity and interpretability matter more than
  maximum α.

### MBTI Warning
If the user requests an MBTI-style assessment, explain the scientific concerns:
- 39–76% of people receive different types on retest after 5 weeks
- Score distributions are unimodal, not bimodal as type theory requires
- The National Academy of Sciences found weak validity evidence
- Recommend Big Five or HEXACO as scientifically superior alternatives
- If the user still wants a type-based format, build it on Big Five dimensions with
  type-like interpretive labels (this gives them the UX they want with better measurement)

---

## 2. Cognitive & Aptitude Testing

### Verbal Reasoning
- **Formats**: True/False/Cannot Say (passage-based), analogies, sentence completion,
  reading comprehension, vocabulary
- **Items**: 20–40
- **Time**: 15–30 minutes (timed)
- **Difficulty**: Progressive, centered around p = .50
- **Design**: Present a short passage (100–200 words) followed by statements. Respondent
  decides True (follows from passage), False (contradicts passage), or Cannot Say
  (not determinable from passage alone). Passages must be neutral, factual, non-controversial.

### Numerical Reasoning
- **Formats**: Data interpretation (tables, charts, graphs), arithmetic reasoning,
  number series, estimation
- **Items**: 15–25
- **Time**: 20–35 minutes
- **Design**: Present data in realistic business formats (sales tables, financial charts).
  Questions require calculation, comparison, trend identification, and estimation.
  Allow calculators for higher-level tests (focus on reasoning, not arithmetic).

### Abstract/Non-Verbal Reasoning
- **Formats**: Matrix completion (Raven's-style), figure series, pattern recognition,
  spatial rotation
- **Items**: 20–36 (grouped in progressive difficulty sets)
- **Time**: 20–45 minutes
- **Design**: Each item shows a matrix with a missing cell; respondent selects the
  pattern that completes the matrix from 6–8 options. Progressive difficulty within
  sets and across sets. These are among the most culture-fair cognitive measures
  because they minimize verbal and cultural content.
- **g-loading**: .75–.85 — among the purest measures of fluid intelligence

### Critical Thinking
- **Subtests** (Watson-Glaser RED model):
  1. **Recognize Assumptions** — distinguish stated assumptions from inferences
  2. **Evaluate Arguments** — assess argument strength and relevance
  3. **Draw Conclusions** — determine what logically follows from evidence
- **Items**: 40 across subtests
- **Time**: 30–40 minutes
- **Design**: Present scenarios or arguments, ask respondent to evaluate logical validity,
  identify hidden assumptions, or determine whether conclusions are warranted.
  Use real-world topics but avoid politically charged content.

### General Cognitive Design Principles
- Use **item-level time limits** or **total section time limits** — never unlimited time
  for ability tests (unless specifically measuring power vs speed)
- Include **practice items** with correct answers shown before the timed section
- **No trick questions** — items should reward ability, not catch respondents off guard
- Ensure **distractors represent common error patterns**, not random options
- **Difficulty spiraling**: Within each section, progress from easy to hard. This builds
  confidence and reduces anxiety effects on performance.

---

## 3. Attitudes, Preferences & Values (Market Research)

### Likert Attitude Scales
- Standard format for measuring attitudes toward concepts, brands, policies
- 5-point or 7-point agreement scale
- Write items tapping cognitive (beliefs), affective (feelings), and behavioral (intentions)
  components of the attitude
- Include both favorability directions for balance

### Brand Perception Surveys
Follow the **measurement hierarchy** — questions must flow in this order:
1. **Unaided awareness**: "What brands come to mind when you think of [category]?"
   (open-ended, MUST precede aided)
2. **Aided awareness**: "Have you heard of [Brand X]?" (yes/no per brand)
3. **Consideration**: "Would you consider purchasing from [Brand X]?" (yes/maybe/no)
4. **Preference**: "Which brand would you choose first?" (ranking or forced-choice)
5. **Image/attribute association**: Semantic differential or Likert ratings per attribute
6. **Loyalty**: NPS, repeat purchase intent, recommendation likelihood

Key design rules:
- Unaided questions ALWAYS precede aided questions (avoid priming effects)
- Keep total survey to 5–10 minutes (15 min max for ≥80% completion)
- Mobile-first design (53%+ start on mobile)
- Randomize brand order in aided/rating sections

### Net Promoter Score (NPS)
- Single question: "How likely are you to recommend [X] to a friend or colleague?" (0–10)
- Scoring: Promoters (9–10) − Detractors (0–6) = NPS (−100 to +100)
- **Known limitations**: Arbitrary cutoffs discard information; different distributions
  can produce identical scores; predictive validity claims are disputed
- **Recommended supplements**: Customer Effort Score ("How easy was it to...?" 1–7),
  Customer Satisfaction Score (CSAT, "How satisfied were you?" 1–5), and open-ended
  follow-up ("What is the primary reason for your score?")

### Conjoint Analysis (Choice-Based)
- Present 2–5 product profiles per choice set, across 6–15 sets
- Use 4–8 attributes with 2–5 levels each
- Minimum sample: 300 respondents (Sawtooth heuristic: n ≥ 500c/qa)
- Produces part-worth utilities showing relative importance of each attribute level
- Best for: pricing decisions, feature prioritization, product configuration optimization

### MaxDiff (Best-Worst Scaling)
- Present subsets of 3–6 items, ask respondent to pick "most important" and "least important"
- Use 8–16 sets with balanced design (each item appears equal number of times)
- Eliminates "everything is important" bias inherent in rating scales
- Produces ratio-scale importance scores (true zero)
- Best for: feature prioritization, benefit ranking, value proposition testing

---

## 4. Behavioral & Competency-Based Assessments

### 360-Degree Feedback Instruments
- **Items**: 30–50 behavioral items across 8–10 competencies (3–5 items per competency)
- **Rater groups**: Self, Manager, Peers (min 3), Direct Reports (min 3), Others
- **Response format**: Behavioral frequency (Never → Consistently) + "No Opportunity to Observe"
- **Anonymity**: Minimum 3 raters per category to protect anonymity
- **Design principles**:
  - Write items observable from multiple perspectives
  - Tag items by applicable rater groups when some behaviors are role-specific
  - Include importance ratings alongside frequency for gap analysis
  - Frame results as development feedback, never as performance evaluation inputs

### Competency Framework Design
If the user doesn't have an existing competency model, help build one:
1. Start with an established framework (Korn Ferry 38 competencies, SHL UCF, Lominger)
2. Select 8–12 competencies most relevant to the target role/organization
3. Define each competency with: name, definition, behavioral indicators at 3–5 proficiency
   levels (novice → expert)
4. Write 3–5 behavioral frequency items per competency

### Behaviorally Anchored Rating Scales (BARS)
Full construction process:
1. **Job analysis** → identify key performance dimensions
2. **Critical incident collection** → gather 50+ behavioral examples from 10+ SMEs
3. **Dimension grouping** → sort incidents into dimensions (5–8 dimensions)
4. **Retranslation** → independent SMEs re-sort incidents (keep ≥60% agreement)
5. **Effectiveness rating** → SMEs rate each incident on the scale (1–9)
6. **Anchor selection** → retain incidents with SD < 1.50 (high agreement)
7. **Scale construction** → place anchors at appropriate scale points (5–9 points)
8. **Pilot** → test with 20–30 raters for inter-rater reliability

### Situational Judgment Tests for Competency Assessment
See item-construction.md § 5 for item writing rules. Additional competency-specific guidance:
- Map each scenario to 1–2 target competencies
- Include 6–10 scenarios per competency cluster
- Total: 15–25 scenarios for a comprehensive SJT
- Scoring: expert consensus (10–12 SMEs per scenario)
- Report scores by competency cluster, not total score

---

## 5. Hybrid and Specialized Formats

### Career Interest Inventories
- Based on Holland's RIASEC model (Realistic, Investigative, Artistic, Social,
  Enterprising, Conventional)
- Format: Forced-choice pairs across types, or Likert interest ratings for activities
- Items describe activities, not self-concepts: "Building a bookshelf" not "I am handy"
- Output: Three-letter Holland code (e.g., RIA) showing primary, secondary, tertiary types

### Emotional Intelligence (EI)
- **Ability-based** (Mayer-Salovey): Uses performance items with correct answers determined
  by expert consensus. Four branches: perceiving, facilitating, understanding, managing emotions.
  More valid but harder to construct.
- **Trait-based** (self-report): Uses Likert items measuring self-perceived EI.
  Easier to construct but more susceptible to faking. Maps onto Big Five (especially
  Neuroticism, Extraversion, Agreeableness).
- Recommendation: Use ability-based for selection, trait-based for development/coaching.

### Employee Engagement Surveys
- Typically 12–25 items measuring: pride, advocacy, discretionary effort, intent to stay
- Format: 5-point Likert (agreement) + 1–2 open-ended questions
- Include **eNPS**: "How likely are you to recommend this organization as a place to work?"
- Key dimensions: Immediate manager, senior leadership, growth opportunities, recognition,
  workload, purpose/meaning, team collaboration, resources/tools
- Frequency: Pulse surveys (5–10 items, monthly/quarterly) vs comprehensive (full, annual)

### Values Inventories
- Schwartz's 10 basic values: Self-Direction, Stimulation, Hedonism, Achievement, Power,
  Security, Conformity, Tradition, Benevolence, Universalism
- Format: Rate importance of each value as a guiding principle (−1 to 7)
  or rank-order (most to least important)
- Use: Career counseling (values-job fit), organizational culture assessment, cross-cultural
  research
- Cultural note: Value hierarchies differ significantly across cultures — interpretation
  must be culture-referenced

### Well-Being & Life Satisfaction
- Validated instruments exist (PERMA Profiler, SWLS, WHO-5) — reference their structure
  but write original items
- Dimensions: Positive emotions, Engagement, Relationships, Meaning, Accomplishment (PERMA)
- Format: 11-point scale (0–10) for life satisfaction; 5-point Likert for PERMA dimensions
- Sensitivity: Include resource information at the end for respondents experiencing distress
