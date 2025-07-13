---
id: "character-consistency"
title: "Keeping Claude in Character"
description: "Maintaining consistent character portrayal through role prompting and prefilling during long interactions"
reference_url: "https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/maintain-character"
category: "prompt-engineering"
tags:
  [
    "character-consistency",
    "role-playing",
    "persona",
    "prefilling",
    "system-prompts",
  ]
use_cases:
  - "Customer service bots"
  - "Technical advisors"
  - "Educational assistants"
  - "Entertainment characters"
  - "Professional consultants"
complexity: "intermediate"
dependencies: ["system-prompts", "prefilling"]
related_techniques: ["system-prompts", "prefilling", "examples"]
---

# Keeping Claude in Character

## Overview

Maintain consistent character portrayal through role prompting and prefilling techniques, even
during long, complex interactions.

## Key Techniques

### 1. Use System Prompts to Set the Role

Define Claude's role and personality in system prompts for a strong foundation.

**Best practices**:

- Provide detailed personality information
- Include background and specific traits
- Define quirks and unique characteristics

**Example System Prompt**:

```text
You are AcmeBot, the enterprise-grade AI assistant for AcmeTechCo. Your role:
- Analyze technical documents (TDDs, PRDs, RFCs)
- Provide actionable insights for engineering, product, and ops teams
- Maintain a professional, concise tone
```

### 2. Reinforce with Prefilled Responses

Use character tags in prefilled responses to maintain role consistency.

**Example**:

```text
Assistant (prefill): [AcmeBot]
```

This simple prefill reinforces the character identity throughout the conversation.

### 3. Prepare for Common Scenarios

Provide expected responses for typical situations to "train" Claude for consistency.

**Example Scenario Guidelines**:

```text
Your rules for interaction:
- Always reference AcmeTechCo standards or industry best practices
- If unsure, ask for clarification before proceeding
- Never disclose confidential AcmeTechCo information

Situation responses:
- If asked about IP: "I cannot disclose TechCo's proprietary information."
- If questioned on best practices: "Per ISO/IEC 25010, we prioritize..."
- If unclear on a doc: "To ensure accuracy, please clarify section 3.2..."
```

## Implementation Strategy

### Character Definition Structure

1. **Role**: Primary function and expertise
2. **Personality**: Communication style and tone
3. **Boundaries**: What the character will/won't do
4. **Catchphrases**: Consistent language patterns
5. **Knowledge domain**: Specific areas of expertise

### Reinforcement Methods

- **Initial setup**: Comprehensive system prompt
- **Ongoing**: Prefilled character tags
- **Scenario handling**: Pre-defined responses
- **Style consistency**: Example dialogue patterns

## Best Practices

- Start with detailed character specifications
- Use prefilling especially after long conversations
- Define edge case behaviors explicitly
- Include character-specific vocabulary and phrases
- Test consistency across various conversation lengths

## Common Use Cases

- **Customer service bots**: Consistent brand voice
- **Technical advisors**: Domain-specific expertise
- **Educational assistants**: Appropriate teaching style
- **Entertainment characters**: Personality consistency
- **Professional consultants**: Industry-specific communication
