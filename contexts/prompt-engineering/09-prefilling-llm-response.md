---
id: "prefilling-responses"
title: "Prefilling LLM Response"
description: "Guiding Claude's response format by prefilling the assistant message to skip preambles and enforce structure"
reference_url: "https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/prefill-claudes-response"
category: "prompt-engineering"
tags:
  ["prefilling", "response-formatting", "json", "xml", "character-consistency"]
use_cases:
  - "Forcing JSON/XML output format"
  - "Skipping preambles"
  - "Maintaining character consistency"
  - "Structured data extraction"
complexity: "intermediate"
dependencies: []
related_techniques: ["system-prompts", "xml-tags", "character-consistency"]
---

# Prefilling LLM Response

## Overview

Prefilling allows you to guide Claude's responses by starting the `Assistant` message with initial
text. This powerful technique enables you to direct actions, skip preambles, enforce specific
formats (JSON/XML), and maintain character consistency in role-play scenarios.

**Note**: Prefilling is only available for non-extended thinking modes.

## Implementation

Include desired initial text in the `Assistant` message:

```python
import anthropic

client = anthropic.Anthropic()
response = client.messages.create(
    model="claude-opus-4-20250514",
    max_tokens=1024,
    messages=[
        {"role": "user", "content": "What is your favorite color?"},
        {"role": "assistant", "content": "As an AI assistant, I don't have a favorite color, But if I had to pick, it would be green because"}  # Prefill
    ]
)
```

**Warning**: Prefill content cannot end with trailing whitespace.

## Key Applications

### 1. Control Output Formatting

**Technique**: Prefill `{` to force JSON output without preamble

- Cleaner, more concise responses
- Easier programmatic parsing
- No additional processing needed

**Example Impact**:

- Without prefill: Long explanation + JSON in code blocks
- With prefill `{`: Direct JSON output only

### 2. Skip Preambles

Prefilling forces Claude to skip introductory text and get straight to the requested format.

### 3. Maintain Character Consistency

**Technique**: Prefill `[ROLE_NAME]` for roleplay scenarios

- Especially powerful combined with system role prompting
- Helps maintain character over long conversations
- Prevents breaking character

**Example Impact**:

- Without prefill: "As an AI assistant, I would be happy to analyze..."
- With prefill `[Sherlock Holmes]`: Stays in character with appropriate voice and mannerisms

## Best Practices

- Keep prefills minimal - a little goes a long way
- Use for format enforcement (JSON, XML, lists)
- Combine with role prompting for maximum effect
- Test different prefill lengths for optimal results

## Common Use Cases

1. **Data extraction**: Prefill `{` for JSON output
2. **Lists**: Prefill `1.` to start numbered lists
3. **Roleplay**: Prefill `[CHARACTER_NAME]` to maintain persona
4. **Code generation**: Prefill language syntax markers
5. **Structured responses**: Prefill XML tags or headers
