---
id: "clear-direct-prompting"
title: "Be Clear, Direct, and Detailed"
description: "Techniques for writing clear, specific instructions that eliminate ambiguity and improve response quality"
reference_url: "https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/be-clear-and-direct"
category: "prompt-engineering"
tags: ["clarity", "specificity", "instructions", "context", "sequential-steps"]
use_cases:
  - "Eliminating ambiguous responses"
  - "Getting specific format requirements"
  - "Complex multi-step tasks"
  - "Domain-specific instructions"
complexity: "beginner"
dependencies: []
related_techniques: ["templates-variables", "examples", "xml-tags"]
---

# Be Clear, Direct, and Detailed

## Overview

Think of Claude as a brilliant but new employee with no context about your norms, styles, or
preferences. The more precisely you explain what you want, the better Claude's response will be.

## Golden Rule

**Show your prompt to a colleague with minimal context and ask them to follow the instructions. If
they're confused, Claude will likely be too.**

## How to Be Clear

### 1. Give Claude Contextual Information

Provide background that helps Claude understand:

- What the task results will be used for
- Target audience for the output
- Where this task fits in the broader workflow
- End goal and success criteria

### 2. Be Specific About Requirements

- If you want only code output, say so explicitly
- Define exact format and structure needed
- Specify what to include or exclude

### 3. Use Sequential Instructions

- Number your steps or use bullet points
- Break complex tasks into clear stages
- Ensure logical flow from start to finish

## Examples Comparison

### Anonymizing Customer Feedback

**Unclear Prompt:**

```text
Please remove all personally identifiable information from these customer feedback messages: {{FEEDBACK_DATA}}
```

Result: Inconsistent anonymization, some names remain

**Clear Prompt:**

```text
Your task is to anonymize customer feedback for our quarterly review.

Instructions:
1. Replace all customer names with "CUSTOMER_[ID]" (e.g., "Jane Doe" → "CUSTOMER_001")
2. Replace email addresses with "EMAIL_[ID]@example.com"
3. Redact phone numbers as "PHONE_[ID]"
4. If a message mentions a specific product (e.g., "AcmeCloud"), leave it intact
5. If no PII is found, copy the message verbatim
6. Output only the processed messages, separated by "---"

Data to process: {{FEEDBACK_DATA}}
```

Result: Consistent, thorough anonymization

### Marketing Email Campaign

**Vague Prompt:**

```text
Write a marketing email for our new AcmeCloud features.
```

Result: Generic email with made-up details

**Specific Prompt:**

```text
Your task is to craft a targeted marketing email for our Q3 AcmeCloud feature release.

Instructions:
1. Target audience: Mid-size tech companies (100-500 employees) upgrading from on-prem to cloud
2. Highlight 3 key features: advanced data encryption, cross-platform sync, real-time collaboration
3. Tone: Professional yet approachable, emphasize security, efficiency, teamwork
4. Include CTA: Free 30-day trial with priority onboarding
5. Subject line: Under 50 chars, mention "security" and "collaboration"
6. Use {{COMPANY_NAME}} and {{CONTACT_NAME}} variables

Structure:
1. Subject line
2. Email body (150-200 words)
3. CTA button text
```

Result: Targeted, professional email matching all requirements

### Incident Response

**Vague Prompt:**

```text
Analyze this AcmeCloud outage report and summarize the key points.
{{REPORT}}
```

Result: Verbose summary with unnecessary detail

**Detailed Prompt:**

```text
Analyze this AcmeCloud outage report. Skip the preamble. Keep your response terse and write only the bare bones necessary information. List only:
1) Cause
2) Duration
3) Impacted services
4) Number of affected users
5) Estimated revenue loss

Here's the report: {{REPORT}}
```

Result: Concise, structured output with only requested information

## Key Takeaways

- **Context matters**: Explain the why, not just the what
- **Be explicit**: Don't assume Claude knows your preferences
- **Structure helps**: Use numbered lists and clear formatting
- **Test your prompts**: Have someone else review for clarity
