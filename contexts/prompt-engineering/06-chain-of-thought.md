---
id: "chain-of-thought"
title: "Chain of Thought (CoT) Prompting"
description: "Step-by-step reasoning technique for complex problems including math, analysis, and multi-step decision making"
reference_url: "https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/chain-of-thought"
category: "reasoning"
tags: ["chain-of-thought", "reasoning", "step-by-step", "analysis", "problem-solving"]

contextual_header: |
  This context module provides reasoning techniques for implementing systematic 
  step-by-step analysis in the domain of complex problem solving and logical 
  deduction. It specifically addresses multi-step reasoning, mathematical problem 
  solving, and transparent decision-making by implementing Chain of Thought (CoT) 
  methodology with explicit intermediate steps. This technique is most effective when 
  dealing with problems requiring logical progression and works best in combination 
  with structured formatting and concrete examples. It helps solve reasoning opacity, 
  logical errors, and verification difficulties, producing transparent, auditable, 
  and reliable thought processes.

embedding_metadata:
  domain: "prompt-engineering"
  technique_type: "reasoning"
  complexity_level: "intermediate"
  primary_use_cases:
    - "Complex mathematical problems"
    - "Multi-step analysis tasks"
    - "Logical reasoning and deduction"
    - "Research and investigation processes"
    - "Complex decision making"
  solves_problems:
    - "Opaque or unexplained reasoning processes"
    - "Logical errors and invalid conclusions"
    - "Difficulty verifying AI reasoning steps"
    - "Inconsistent problem-solving approaches"
    - "Premature conclusions without sufficient analysis"
  works_well_with: ["xml-tags-structure", "multishot-examples", "extended-thinking"]
  requires_techniques: ["prompt-engineering-best-practices"]
---

# Chain of Thought (CoT) Prompting

## Overview

Chain of thought prompting encourages Claude to break down complex problems step-by-step,
dramatically improving performance on tasks like research, analysis, and problem-solving.

## Benefits and Tradeoffs

### Why Use CoT?

- **Accuracy**: Step-by-step reasoning reduces errors in math, logic, and complex analysis
- **Coherence**: Structured thinking produces well-organized responses
- **Debugging**: Visible thought process helps identify unclear prompts

### When to Avoid CoT

- Increased output length impacts latency
- Simple tasks don't require in-depth thinking
- Use judiciously to balance performance and speed

**Rule of thumb**: Use CoT for tasks a human would need to think through (complex math, multi-step
analysis, writing complex documents, multi-factor decisions).

## Implementation Methods (Least to Most Complex)

### 1. Basic Prompt

Add "Think step-by-step" to your prompt.

- **Limitation**: Lacks guidance on how to think
- **Example**: "Draft personalized emails... Think step-by-step before you write the email."

### 2. Guided Prompt

Outline specific thinking steps.

- **Limitation**: No structure to separate thinking from answer
- **Example**: "Think before you write. First, think through what messaging might appeal... Then,
  think through what aspects would appeal... Finally, write the email using your analysis."

### 3. Structured Prompt

Use XML tags like `<thinking>` and `<answer>` to separate reasoning from output.

- **Best practice**: Most effective for complex tasks
- **Example**: "Think before you write in `<thinking>` tags... Finally, write the email in `<email>`
  tags."

## Critical Rule

**Always have Claude output its thinking.** Without outputting the thought process, no thinking
occurs!

## Example Impact

### Without CoT (Financial Analysis)

- Surface-level recommendation
- Lacks quantification
- Misses historical context
- Result: Basic advice without depth

### With CoT (Financial Analysis)

- Calculates exact figures for both scenarios
- Considers historical market volatility
- Analyzes client's risk tolerance
- Result: Thorough, justifiable recommendation with \$13,382 vs \$17,623 comparison

## Best Practices

1. Match CoT complexity to task complexity
2. Use structured tags for easier parsing
3. Guide thinking steps for domain-specific tasks
4. Balance thoroughness with latency requirements
