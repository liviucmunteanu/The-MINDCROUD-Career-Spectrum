# Item Construction Rules

This reference contains the authoritative rules for writing assessment items across all
formats. Every item the skill generates must pass all applicable rules.

## Table of Contents
1. Universal Item Rules (all formats)
2. Likert Scale Items
3. Forced-Choice Items
4. Semantic Differential Items
5. Situational Judgment Test Items
6. Multiple-Choice (Cognitive/Aptitude) Items
7. Behavioral Frequency Rating Items (360/Competency)
8. Bias Control Strategies
9. Item Keying and Reverse Scoring
10. Response Format Decision Tree

---

## 1. Universal Item Rules

Apply these to EVERY item regardless of format:

### Clarity Rules
- **One idea per item.** Never combine two concepts. "I feel anxious and dizzy" is
  double-barreled — split into two items.
- **8th grade reading level** for general populations, 6th grade for broad/diverse populations.
  Use short sentences (≤20 words), common vocabulary, active voice.
- **No jargon or technical terms** unless the target population is specifically technical
  AND the construct requires domain language.
- **No idioms, metaphors, or culturally specific references** that don't translate across
  cultures (e.g., "I hit it out of the park" — meaningless outside baseball cultures).
- **No double negatives.** "I never feel unhappy" is cognitively confusing.
- **No absolutes** unless measuring extremity is intentional. Avoid "always," "never,"
  "completely," "totally" — these produce skewed distributions.

### Content Rules
- **Behavioral and observable language** over evaluative abstractions.
  Good: "I start conversations with people I don't know"
  Bad: "I am an extroverted person"
- **Present tense, first person** for self-report items.
- **Specific time frames** when measuring states (not traits): "In the past two weeks..."
- **Avoid presuppositions.** "How much do you enjoy your job?" presupposes enjoyment.
  Better: "I find satisfaction in my daily work tasks."

### Structural Rules
- **Consistent grammatical structure** within each dimension's items.
- **Vary sentence length naturally** — not all items should be the same length.
- **No item stems that cue the "correct" answer** through social desirability.
- **Each item must be independently interpretable** — no items that reference other items.

---

## 2. Likert Scale Items

### Response Point Selection
- **5-point scale**: Sufficient for most purposes. Use for: shorter instruments, lower
  literacy populations, mobile-first administration.
  Labels: Strongly Disagree / Disagree / Neither Agree nor Disagree / Agree / Strongly Agree
- **7-point scale**: Captures more variance, slightly better reliability. Use for:
  research contexts, nuanced measurement, populations comfortable with finer distinctions.
  Labels: Strongly Disagree / Disagree / Somewhat Disagree / Neither / Somewhat Agree / Agree / Strongly Agree
- **Always fully label every point** — numbered-only or endpoint-only labels reduce reliability.
- **Include midpoint** for bipolar constructs (attitudes, opinions). Omit for unipolar
  constructs where zero is meaningful (frequency: Never to Always).

### Anchor Alternatives
| Construct Type | Anchors |
|---|---|
| Agreement | Strongly Disagree → Strongly Agree |
| Frequency | Never → Always (or: Never / Rarely / Sometimes / Often / Always) |
| Intensity | Not at All → Extremely |
| Satisfaction | Very Dissatisfied → Very Satisfied |
| Importance | Not at All Important → Extremely Important |
| Likelihood | Very Unlikely → Very Likely |

### Likert Item Writing Rules
- Write the statement so that agreement = higher score on the target construct (for
  positively keyed items).
- Avoid "agree/disagree" in the item text itself — that's what the scale does.
- Make items discriminating: they should differentiate high from low scorers.
  "I breathe air regularly" doesn't discriminate.
- Target items at different intensity levels across the construct continuum — some easy
  to endorse, some moderate, some extreme.

---

## 3. Forced-Choice Items

### Block Construction
- **Pair format (2 statements)**: Choose which describes you more. Simplest, but limited.
- **Triplet format (3 statements)**: Rank or pick most/least. Better discrimination.
- **Quad format (4 statements)**: Pick most and least like you. Best psychometric properties
  but highest cognitive load.

### Critical Rules
- **Match social desirability within blocks.** Each statement in a block must be equally
  attractive/unattractive. If one statement is obviously more socially desirable, respondents
  will choose it regardless of accuracy, destroying validity.
- **Each statement in a block must come from a different dimension.** Never pair items
  from the same construct — that makes the forced choice meaningless.
- **Use Thurstonian IRT for scoring** — classical scoring of forced-choice produces ipsative
  data (constant sum across traits), which cannot be used for between-person comparisons,
  correlational analysis, or factor analysis. Thurstonian IRT recovers normative scores.
- **Include both positively and negatively keyed items** across blocks for Thurstonian IRT
  to work optimally (especially with <30 traits).

### Example Block (Quad, Big Five)
```
Which statement is MOST like you, and which is LEAST like you?
A. I enjoy trying new and unusual experiences. [Openness+]
B. I keep my workspace tidy and organized. [Conscientiousness+]
C. I feel energized after spending time with a large group. [Extraversion+]
D. I tend to go along with others' wishes to avoid conflict. [Agreeableness+]
```
All four are moderately socially desirable. Each taps a different dimension.

---

## 4. Semantic Differential Items

- Use **7-point bipolar adjective pairs** (Osgood, 1957).
- Three universal dimensions: Evaluation (good–bad), Potency (strong–weak), Activity (fast–slow).
- Include **3–4 adjective pairs per dimension**, 10–15 pairs per concept evaluated.
- **Randomize polarity direction** — don't put all positive anchors on the same side.
- Pairs must be true antonyms, not merely different concepts.

### Example (Brand Perception)
```
Please rate [Brand X] on each pair of words:

Modern  ○ ○ ○ ○ ○ ○ ○  Traditional
Weak    ○ ○ ○ ○ ○ ○ ○  Powerful      ← polarity flipped
Boring  ○ ○ ○ ○ ○ ○ ○  Exciting      ← polarity flipped
Reliable ○ ○ ○ ○ ○ ○ ○  Unreliable
```

---

## 5. Situational Judgment Test (SJT) Items

### Scenario Construction
- Build scenarios from **critical incidents** — realistic situations the target population
  actually faces. If possible, have the user provide 5–10 real workplace scenarios.
- Each scenario should be 50–100 words, specific enough to constrain interpretation but
  general enough to apply broadly.
- Include contextual details: who is involved, what the stakes are, what constraints exist.

### Response Options
- Provide **4–6 response options** varying in effectiveness from highly effective to
  counterproductive.
- Use **"should do" instructions** ("What SHOULD you do?") for maximum criterion-related
  validity. Use "would do" only when measuring typical behavior is more important than
  maximum performance.
- Establish scoring keys through **SME consensus** — describe a process for 10–12
  subject matter experts to independently rate each response option's effectiveness,
  then average ratings.

### Scoring Methods
- **Most/Least effective**: Respondent picks best and worst option. Score: +1 for correct
  most, +1 for correct least, 0 otherwise. Simple, reliable.
- **Likert rating of each option**: Respondent rates each option's effectiveness 1–5.
  Score: distance from expert consensus. More informative but longer.
- **Ranking**: Respondent ranks all options. Score: correlation with expert ranking. Most
  informative but highest cognitive load.

### SJT Reliability Note
Cronbach's alpha is inappropriate for multidimensional SJTs because scenarios intentionally
tap different competencies. Use split-half with Spearman-Brown correction instead, or
report reliability per competency cluster.

---

## 6. Multiple-Choice (Cognitive/Aptitude) Items

### Item Structure
- **Stem**: Clear question or incomplete statement. Must be meaningful on its own without
  reading options.
- **Key**: One correct answer.
- **Distractors**: 3 plausible wrong answers. Each should represent a common misconception
  or error pattern, not random nonsense.

### Rules
- **All options similar in length and grammatical structure.** The correct answer must not
  stand out visually.
- **Avoid "all of the above" and "none of the above"** — they create guessing artifacts.
- **Avoid negative stems** ("Which is NOT...") unless testing crucial safety knowledge.
- **Arrange items in progressive difficulty** (easy → hard) for power tests.
- **Time limits**: Include for speed tests; exclude for power tests measuring maximum
  performance.

### Difficulty Targeting
- Target item difficulty (p-values) to follow a roughly normal distribution centered at
  p = .50, ranging from .20 to .80.
- In IRT terms: difficulty parameters (b) should span −2.0 to +2.0 on the θ scale.
- Discrimination (point-biserial) should reach ≥ .30 (good), minimum ≥ .20 (acceptable).
- In IRT: discrimination parameters (a) should exceed 0.80.

---

## 7. Behavioral Frequency Rating Items (360/Competency)

- Use **behavioral frequency anchors**: Never / Rarely / Sometimes / Often / Consistently
  (preferred over agree/disagree for observable behaviors).
- Always include **"No Opportunity to Observe"** option — don't force raters to guess.
- Items must describe **specific, observable behaviors**, not traits or intentions.
  Good: "Acknowledges team members' contributions in meetings"
  Bad: "Is a supportive leader"
- For **360-degree instruments**: write items that are observable from all rater perspectives
  (self, manager, peer, direct report). Some behaviors may only be visible from certain
  angles — tag items with applicable rater groups.
- Target **3–5 items per competency**, 8–10 competencies, totaling 30–50 items.
- Require **minimum 3 raters per category** for anonymity and stability.

---

## 8. Bias Control Strategies

### Acquiescence Bias (Tendency to Agree)
- **Primary defense**: Use behavioral language and direct questions rather than
  agree/disagree format when possible.
- **Secondary defense**: Include ~25% antonym-reversed items (NOT negation-reversed).
  Good reversal: "I am talkative" → "I am quiet"
  Bad reversal: "I am talkative" → "I am NOT talkative" (confusing, creates artifacts)
- **Tertiary defense**: Forced-choice format eliminates acquiescence entirely.

### Social Desirability Bias (Tendency to Present Favorably)
- Use **concrete behavioral language** instead of evaluative statements.
  Good: "I have taken office supplies home for personal use" (specific, behavioral)
  Bad: "I am an honest person" (abstract, evaluative — everyone agrees)
- For **high-stakes contexts**: use forced-choice blocks matched on desirability level.
- Include a **validity scale** (6–10 items) measuring socially desirable responding.
  Example items: "I have never told a lie" / "I have never been late to an appointment"
  Flag scores above the 95th percentile.
- **Evaluative neutralization**: frame items to make both endpoints equally acceptable.
  "I prefer working with others" vs "I prefer working independently" — neither is
  inherently more desirable.

### Extreme Response Style (Tendency to Use Scale Endpoints)
- More prevalent in some cultural contexts (Latin American, Middle Eastern cultures).
- **Mitigation**: Use forced-choice formats, or use 6-point scales (no midpoint) when
  midpoint avoidance is the concern.
- **Statistical mitigation**: Model response style as a covariate in analyses.

### Careless/Inattentive Responding
- Include **infrequency items** (extreme statements no attentive person would endorse):
  "I have traveled to every country on Earth" / "I can see into the future"
- Include **consistency pairs**: semantically equivalent items placed far apart in the
  instrument. Flag respondents with large discrepancies (|diff| ≥ 3 on 5-point scale
  for more than 2 pairs).
- Include **instructed response items**: "Please select 'Agree' for this item."
- Monitor **completion time**: flag responses completed in <2 seconds per item average.

---

## 9. Item Keying and Reverse Scoring

### Current Best Practice
The field is moving away from heavy reliance on reverse-scored items because they:
- Often cluster into artifactual method factors in factor analysis
- Reduce scale reliability, especially in diverse or lower-literacy populations
- Create confusion in cross-cultural adaptation

### Recommended Approach
- **Default ratio: ~75% positively keyed, ~25% negatively keyed** (antonym-based reversal only)
- Place reverse-scored items at natural points in the instrument, not clustered together
- When using reverse items, ALWAYS verify they load on the intended factor (not a method factor)
  during validation
- For cognitive items: difficulty variation serves the same purpose as keying balance —
  some items are "easy to get right" and some "easy to get wrong"

### Scoring Reverse Items
- 5-point scale: reverse = (6 − response). So 1→5, 2→4, 3→3, 4→2, 5→1.
- 7-point scale: reverse = (8 − response). So 1→7, 2→6, etc.
- General formula: reverse = (max + 1) − response.
- Always clearly mark reverse-scored items in the scoring key with an (R) designation.

---

## 10. Response Format Decision Tree

Use this tree to recommend format when the user is unsure:

```
Is the construct a cognitive ABILITY (right/wrong answers)?
├── YES → Multiple-Choice or Performance Task
│   ├── Speed matters? → Timed MC (power + speed)
│   └── Reasoning/judgment? → SJT or constructed response
└── NO → Self-report
    ├── Is FAKING a serious concern (high-stakes selection)?
    │   ├── YES → Forced-Choice with Thurstonian IRT
    │   └── NO ↓
    ├── Measuring ATTITUDES/OPINIONS?
    │   ├── Toward a concept/brand? → Semantic Differential
    │   └── General attitude? → Likert (5 or 7 point)
    ├── Measuring BEHAVIORAL FREQUENCY?
    │   └── → Frequency scale (Never → Always) or BARS
    ├── Measuring PREFERENCES/VALUES?
    │   ├── Comparing multiple options? → MaxDiff or Conjoint
    │   └── Rating importance? → Likert Importance scale
    └── Default → Likert 5-point (agreement or frequency anchors)
```
