---
id: "extended-thinking"
title: "Extended Thinking Tips"
description: "Maximizing Claude's extended thinking capabilities for complex problems with step-by-step reasoning"
reference_url: "https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/extended-thinking"
category: "prompt-engineering"
tags:
  [
    "extended-thinking",
    "complex-problems",
    "reasoning",
    "STEM",
    "constraint-optimization",
  ]
use_cases:
  - "Complex STEM problems"
  - "Constraint optimization"
  - "Structured thinking frameworks"
  - "Multi-step verification"
complexity: "advanced"
dependencies: ["chain-of-thought"]
related_techniques: ["chain-of-thought", "examples", "clear-direct"]
---

# Extended Thinking Tips

## Overview

Extended thinking allows Claude to work through complex problems step-by-step, improving performance
on difficult tasks. These tips help maximize the effectiveness of extended thinking features.

## Technical Considerations

- **Minimum budget**: 1024 tokens (start here and increase as needed)
- **Large budgets**: Use batch processing for >32K tokens to avoid timeouts
- **Language**: Performs best in English (outputs can be any supported language)
- **Alternative**: For <1024 tokens, use standard mode with chain-of-thought prompting

## Prompting Strategies

### 1. Use General Instructions First

Start with high-level guidance rather than prescriptive steps. Claude's creativity often exceeds
human-prescribed processes.

**Instead of**:

```text
Think through this math problem step by step:
1. First, identify the variables
2. Then, set up the equation
3. Next, solve for x
```

**Try**:

```text
Please think about this math problem thoroughly and in great detail.
Consider multiple approaches and show your complete reasoning.
Try different methods if your first approach doesn't work.
```

### 2. Multishot Prompting

Include examples with `<thinking>` or `<scratchpad>` tags to show reasoning patterns:

```text
Problem 1: What is 15% of 80?
<thinking>
To find 15% of 80:
1. Convert 15% to decimal: 15% = 0.15
2. Multiply: 0.15 × 80 = 12
</thinking>
The answer is 12.

Now solve: What is 35% of 240?
```

### 3. Maximize Instruction Following

- Be clear and specific about desired outcomes
- Break complex instructions into numbered steps
- Allow sufficient budget for processing instructions

### 4. Reflection and Verification

Ask Claude to verify work before completing tasks:

```text
Write a factorial function.
Before finishing, verify with test cases:
- n=0, n=1, n=5, n=10
Fix any issues found.
```

## Optimal Use Cases

### Complex STEM Problems

Tasks requiring mental models, specialized knowledge, and sequential logic benefit most from
extended thinking.

### Constraint Optimization

Multiple competing requirements (budget, time, preferences) are better balanced with extended
thinking.

### Structured Thinking Frameworks

Applying analytical frameworks (Porter's Five Forces, Blue Ocean Strategy) benefits from methodical
extended thinking.

## Best Practices

### Debugging and Steering

- Use thinking output to understand Claude's logic
- Don't pass thinking back as user input (degrades performance)
- Prefilling extended thinking is not allowed

### Long Outputs

- Increase both thinking budget AND request detailed outputs
- For 20K+ word outputs, request detailed outlines with word counts
- Ask Claude to index paragraphs to maintain structure

### Clean Responses

If Claude repeats thinking in output, instruct: "Don't repeat your extended thinking, only output
the final answer."

## Key Reminders

- Start with minimum budget (1024 tokens) and increase incrementally
- Extended thinking excels at complex, multi-step problems
- Allow Claude flexibility in approach rather than over-prescribing
- Use verification steps for consistency and error reduction
