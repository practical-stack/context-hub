---
id: "multishot-examples"
title: "Multishot Prompting with Examples"
description: "Using few-shot prompting with 3-5 diverse examples to improve accuracy, consistency, and output quality"
reference_url: "https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/use-examples"
category: "prompt-engineering"
tags: ["examples", "few-shot", "multishot", "consistency", "accuracy"]
use_cases:
  - "Structured output formatting"
  - "Consistent response style"
  - "Complex classification tasks"
  - "Specific format requirements"
complexity: "beginner"
dependencies: []
related_techniques: ["xml-tags", "templates-variables", "clear-direct"]
---

# Multishot Prompting with Examples

## Overview

Examples are a powerful technique for improving Claude's accuracy, consistency, and output quality.
Known as few-shot or multishot prompting, this approach is particularly effective for structured
outputs or specific formats.

## Key Benefits

- **Accuracy**: Reduces instruction misinterpretation
- **Consistency**: Enforces uniform structure and style
- **Performance**: Enhances handling of complex tasks

## Best Practices

**Include 3-5 diverse, relevant examples** for optimal performance, especially for complex tasks.

## Crafting Effective Examples

### Requirements

- **Relevant**: Mirror your actual use case
- **Diverse**: Cover edge cases and potential challenges without unintended patterns
- **Clear**: Wrap in `<example>` tags (multiple examples in `<examples>` tags)

### Tip

Ask Claude to evaluate your examples for relevance, diversity, or clarity, or generate additional
examples from your initial set.

## Example Comparison

### Customer Feedback Analysis Task

**Task**: Categorize issues (UI/UX, Performance, Feature Request, Integration, Pricing, Other) and
rate sentiment (Positive/Neutral/Negative) and priority (High/Medium/Low).

**Without Examples**:

- Produces long explanatory text
- Inconsistent formatting
- May miss multiple categories per item

**With Examples**:

```xml
<example>
Input: The new dashboard is a mess! It takes forever to load, and I can't find the export button. Fix this ASAP!
Category: UI/UX, Performance
Sentiment: Negative
Priority: High
</example>
```

**Result**: Structured, consistent output matching the example format exactly, with multiple
categories properly identified per feedback item.

## Implementation Tips

1. Test examples against edge cases
2. Ensure examples demonstrate all possible output variations
3. Keep example formatting consistent with desired output
4. Update examples when requirements change
