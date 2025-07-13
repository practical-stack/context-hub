---
id: "system-prompts-roles"
title: "System Prompts and Role Assignment"
description: "Using system parameter to assign specific roles and domain expertise to Claude for enhanced performance"
reference_url: "https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/system-prompts"
category: "prompt-engineering"
tags:
  [
    "system-prompts",
    "role-assignment",
    "domain-expertise",
    "persona",
    "specialization",
  ]
use_cases:
  - "Domain-specific analysis"
  - "Professional persona adoption"
  - "Specialized communication styles"
  - "Expert-level responses"
complexity: "intermediate"
dependencies: []
related_techniques: ["prefilling", "character-consistency", "clear-direct"]
---

# System Prompts and Role Assignment

## Overview

Using the `system` parameter to assign Claude a specific role dramatically improves performance.
This technique, known as role prompting, transforms Claude from a general assistant into a virtual
domain expert.

## Key Benefits

- **Enhanced accuracy**: Significant performance boost in complex scenarios (legal analysis,
  financial modeling)
- **Tailored tone**: Adjusts communication style (CFO's brevity vs copywriter's flair)
- **Improved focus**: Keeps responses within task-specific requirements

## Implementation

Use the `system` parameter in the Messages API:

```python
import anthropic

client = anthropic.Anthropic()

response = client.messages.create(
    model="claude-3-7-sonnet-20250219",
    max_tokens=2048,
    system="You are a seasoned data scientist at a Fortune 500 company.", # <-- role prompt
    messages=[
        {"role": "user", "content": "Analyze this dataset for anomalies: <dataset>{{DATASET}}</dataset>"}
    ]
)
```

## Best Practices

- Put role definition in `system` parameter
- Keep task-specific instructions in `user` turn
- Experiment with different roles for varied perspectives
- Be specific with role descriptions (e.g., "data scientist specializing in customer insight
  analysis")

## Impact Examples

### Legal Contract Analysis

**Without role**: Misses critical issues, provides surface-level analysis

**With role (General Counsel)**:

- Identifies liability cap of $500 as grossly inadequate
- Catches dangerous indemnification clauses
- Recommends rejection with specific negotiation points

### Financial Analysis

**Without role**: Basic summary of numbers

**With role (CFO)**:

- Strategic insights on resource reallocation
- Specific action items (freeze hires, cut CAC by 15%)
- Board-ready analysis with growth/burn trade-offs
- Clear strategic stance with measurable targets

## Pro Tips

- Different roles yield different insights from same data
- Specific role descriptions enhance domain expertise
- Combine with other techniques for maximum effectiveness
