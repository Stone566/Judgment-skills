---
name: decision-model
description: |
  Helps users build a structured judgment model when they need to make a decision.
  
  Trigger Scenarios:
  - User says "Help me make a decision"
  - User says "Help me decide whether to..."
  - User says "Help me choose..."
  - User says "Help me evaluate..."
  - User says "Help me judge..."
  - User describes a decision-making scenario (e.g., "Should I hire this person?", "Is this project worth investing in?")
  
  This skill is based on the Mechanical Judgment Model from Kahneman's "Noise." It eliminates random noise in human intuition through a standardized linear model, providing more stable and reproducible decision outcomes.
---

# Decision-Judgment Model Skill

## Core Objective

Help users establish a structured decision model by transforming vague judgments into a quantifiable process through the following steps:

1. **Parse Decision Scenario** — Clarify the decision goal (Binary, Ranking, Scoring).
2. **Evaluate Decision Attributes** — Confirm importance and reversibility.
3. **Identify Predictors** — Guide the user to find 6–8 key variables.
4. **Standardize Scoring** — Convert each factor into comparable standardized scores.
5. **Calculate Judgment Score** — Apply a Unit-Weight Model to derive the result.
6. **Provide Decision Recommendation** — Offer clear action advice based on thresholds.

## Workflow

### Step 1: Parse Decision Scenario

When a user presents a decision need, first clarify:

**Decision Goal Type:**
- **Binary**: Yes/No, Pass/Fail, Hire/Don't Hire.
- **Ranking**: Prioritizing multiple options.
- **Scoring**: Evaluating a single option.

**Key Questions:**
- "What kind of decision do you need to make?"
- "How high is the importance of this decision? (High/Medium/Low)"
- "Is the decision reversible if it turns out to be wrong? (Reversible/Irreversible)"

**Importance-Reversibility Matrix:**
| | Reversible | Irreversible |
|---|---|---|
| **High Importance** | Experiment boldly; iterate fast | Proceed with extreme caution; consider worst-case scenarios |
| **Low Importance** | Decide quickly; don't overthink | Not worth significant time investment |

### Step 2: Identify Predictors

Guide the user to identify 6–8 predictive factors (variables) clearly related to the outcome.

**Selection Criteria (Must meet all three):**
1. **Clearly Related**: The factor has a clear logical connection to the decision outcome.
2. **Obtainable Pre-decision**: The information can be obtained before the decision is made.
3. **Relatively Objective**: Can be quantified or has clear evaluation standards.

**Reference for Common Factor Types:**

| Type | Description | Examples |
|------|------|------|
| Historical Performance | Past behavior or outcomes | Sales volume, project completion rate, historical ratings |
| Competency Indicators | Quantifiable data reflecting ability | Test scores, skill levels, years of experience |
| Alignment/Fit | Degree of synergy with needs or standards | Job fit, strategic alignment |
| Risk Indicators | Potential negative factors | Default records, failure count, negative feedback |
| Cost Factors | Resource investment related | Budget, time cost, manpower cost |
| Growth Potential | Future development space | Learning speed, growth trajectory, trainability |

**Guiding Phrases:**
- "What factors do you believe best predict the success of this decision?"
- "If you were making this judgment, what specific areas would you focus on?"
- "Are there any obvious red flags or green lights?"

### Step 3: Design Scoring Standards

Design a 1–5 or 1–10 scale for each factor.

**Scoring Standard Template:**