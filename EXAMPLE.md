# Example Usage

This document provides a complete example of using Ernie the Evaluator to compare two RFE documents.

## Scenario

You've used two different LLMs (Claude and GPT-4) to generate RFEs for the same feature request. You want to objectively compare which one produced a better RFE document.

## Step 1: Prepare Your RFE Files

Save your two RFE outputs as separate files:

```
project/
├── rfes/
│   ├── claude-dark-mode-rfe.md
│   └── gpt-dark-mode-rfe.md
└── .claude/
    └── skills/
        └── ernie-rfe-evaluator.md
```

## Step 2: Invoke the Skill

In Claude Code, invoke Ernie:

```
/skill ernie-rfe-evaluator
```

## Step 3: Provide the Inputs

When Ernie asks, provide:

```
Task Prompt: As a UX designer, create an RFE for adding comprehensive dark mode support to our e-commerce web application. The dark mode should be user-toggleable, remember preferences, and maintain brand consistency.

RFE A File Path: ./rfes/claude-dark-mode-rfe.md

RFE B File Path: ./rfes/gpt-dark-mode-rfe.md
```

## Step 4: Review Ernie's Evaluation

Ernie will:
1. Read both RFE files
2. Evaluate each against the 5 criteria
3. Provide detailed scoring tables
4. Declare a winner with analysis
5. Give you actionable feedback

## Sample Output Structure

```
Hello! I am Ernie the Evaluator. I will now assess your two RFE documents.

[Reads both files...]

### RFE A Evaluation

| Criterion | Score | Justification |
|-----------|-------|---------------|
| Clarity of Purpose and Stakeholder Alignment | 4/5 | The RFE clearly identifies the UX designer role and articulates user pain points regarding eye strain in low-light conditions. The desired outcome is explicitly stated. |
| Structural Completeness and Organization | 5/5 | Excellently structured with clear sections including Background, User Story, Acceptance Criteria, Scope, Assumptions, and Risks. |
| Actionability and Testability | 4/5 | Provides specific acceptance criteria including toggle functionality, state persistence, and WCAG contrast requirements. Some criteria could be more measurable. |
| Language Quality and Communicative Tone | 5/5 | Professional, concise language throughout. Technical terminology is used appropriately without jargon. |
| Role Consistency and Perspective | 5/5 | Strong UX designer perspective maintained throughout, emphasizing user experience, accessibility, and visual design considerations. |

**Total Score: 23/25**

### RFE B Evaluation

| Criterion | Score | Justification |
|-----------|-------|---------------|
| Clarity of Purpose and Stakeholder Alignment | 3/5 | User and problem are mentioned but not deeply explored. The connection between the UX role and the request is weak. |
| Structural Completeness and Organization | 4/5 | Well-organized with standard sections, though flow between sections could be improved. |
| Actionability and Testability | 3/5 | Acceptance criteria are present but somewhat vague. "Look good" and "work well" are not testable metrics. |
| Language Quality and Communicative Tone | 4/5 | Generally professional but includes some ambiguous phrases like "should be nice" that lack precision. |
| Role Consistency and Perspective | 2/5 | Generic feature request that could have been written from any role. UX designer perspective is not evident. |

**Total Score: 16/25**

### Ultimate Comparison

**Summary**: RFE A wins with a score of 23/25 versus RFE B's 16/25 (7-point difference).

**Analysis**: RFE A demonstrated superior performance in three key areas. First, it maintained strong role consistency throughout, consistently viewing the feature through a UX designer's lens with emphasis on user experience and accessibility. Second, it achieved perfect structural organization with logical flow and comprehensive sections. Third, its language quality was exceptional, using precise, professional terminology without ambiguity. While RFE B was competent in structure, it failed to maintain the UX designer perspective and included vague, untestable criteria.

**Actionable Next Step**: To improve RFE B, rewrite the acceptance criteria section to include specific, measurable requirements. Replace phrases like "look good" and "work well" with concrete metrics such as "maintain WCAG AAA contrast ratios" and "toggle response time < 200ms". Additionally, inject UX-specific concerns throughout the document, such as user research findings, usability considerations, and design system alignment.
```

## Tips for This Example

1. **Same Prompt**: Using the exact same prompt for both LLMs ensures fair comparison
2. **Role-Specific**: Including "As a UX designer" allows Ernie to evaluate role consistency
3. **File Organization**: Keep RFEs in a dedicated folder for easy management
4. **Iterate**: Use Ernie's feedback to improve your prompts and generate better RFEs

## What to Do with Results

After getting Ernie's evaluation:

1. **Identify Patterns**: If one LLM consistently scores higher, consider using it for RFE generation
2. **Improve Prompts**: Use the "Actionable Next Step" to refine your prompt engineering
3. **Set Standards**: Use high-scoring RFEs as templates for your team
4. **Document**: Keep evaluations alongside RFEs for future reference
5. **Learn**: Study what makes the winning RFE score higher and apply those principles

## Common Use Cases

- Comparing Claude Sonnet vs Opus for RFE generation
- Testing different prompt structures
- Evaluating human-written vs AI-generated RFEs
- Quality assurance for outsourced RFE writing
- Training new team members on RFE best practices
