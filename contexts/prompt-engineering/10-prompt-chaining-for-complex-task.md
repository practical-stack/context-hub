---
id: "prompt-chaining"
title: "Prompt Chaining for Complex Tasks"
description: "Breaking complex multi-step tasks into smaller, manageable subtasks with clear handoffs between prompts"
reference_url: "https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/chain-prompts"
category: "prompt-engineering"
tags: ["prompt-chaining", "multi-step", "complex-tasks", "subtasks", "workflow"]
use_cases:
  - "Multi-step analysis workflows"
  - "Complex document processing"
  - "Iterative content creation"
  - "Self-correction workflows"
complexity: "advanced"
dependencies: ["xml-tags"]
related_techniques: ["xml-tags", "chain-of-thought", "clear-direct"]
---

# Prompt Chaining for Complex Tasks

## Overview

When handling complex, multi-step tasks, breaking them into smaller, manageable subtasks through
prompt chaining improves accuracy and reliability. Each subtask gets Claude's full attention,
preventing dropped steps or mishandled instructions.

## Key Benefits

- **Accuracy**: Each subtask receives focused attention, reducing errors
- **Clarity**: Simpler subtasks mean clearer instructions and outputs
- **Traceability**: Easy to pinpoint and fix issues in specific steps

## When to Use Prompt Chaining

- Multi-step tasks (research synthesis, document analysis, iterative content creation)
- Tasks with multiple transformations, citations, or complex instructions
- When Claude drops or mishandles steps in a single prompt

## Implementation Steps

1. **Identify subtasks**: Break task into distinct, sequential steps
2. **Structure with XML**: Use XML tags for clear handoffs between prompts
3. **Single-task goal**: Each subtask should have one clear objective
4. **Iterate**: Refine based on performance

## Common Chained Workflows

- **Multi-step analysis**: Legal review → Risk assessment → Email drafting
- **Content pipelines**: Research → Outline → Draft → Edit → Format
- **Data processing**: Extract → Transform → Analyze → Visualize
- **Decision-making**: Gather info → List options → Analyze → Recommend
- **Self-correction**: Generate → Review → Refine → Re-review

## Advanced Technique: Self-Correction Chains

Have Claude review its own work to catch errors and refine outputs:

1. Initial task completion
2. Self-review for accuracy/completeness
3. Refinement based on feedback

## Example Workflows

### Legal Contract Analysis (3-step chain)

1. **Analyze risks** → Output in `<risks>` tags
2. **Draft vendor email** using risks → Output in `<email>` tags
3. **Review email** for tone/clarity → Provide feedback

### Research Summary Self-Correction

1. **Summarize paper** → Focus on methodology, findings, implications
2. **Grade summary** → Evaluate accuracy, clarity, completeness (A-F scale)
3. **Improve summary** → Incorporate feedback for final version

### Strategy Review Pipeline

1. **Analyze strategy** → Focus on scalability, security, cost
2. **Create review document** → Executive summary, analysis, recommendations
3. **Grade document** → Evaluate clarity, actionability, alignment

## Pro Tips

- **Debugging**: Isolate problematic steps in their own prompts
- **Parallel execution**: Run independent subtasks simultaneously for speed
- **XML handoffs**: Use consistent tags for passing data between prompts
- **Optimization**: Keep each prompt focused on a single, clear objective
