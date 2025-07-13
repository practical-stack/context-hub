---
id: "prompt-engineering-best-practices"
title: "Claude 4 Prompt Engineering Best Practices"
description: "General principles and specific techniques for effective prompt engineering with Claude 4"
reference_url: "https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview"
category: "prompt-engineering"
tags:
  [
    "best-practices",
    "fundamentals",
    "claude-4",
    "instructions",
    "context",
    "examples",
  ]
use_cases:
  - "Getting started with prompt engineering"
  - "Improving prompt quality and effectiveness"
  - "Transitioning from previous Claude versions"
  - "General purpose prompting guidance"
complexity: "beginner"
dependencies: []
related_techniques: ["clear-direct", "templates-variables", "examples"]

# Contextual embedding fields
contextual_header: |
  This context module provides fundamental prompt engineering best practices 
  in the domain of general-purpose LLM interaction. It specifically addresses 
  core principles for effective communication with Claude 4 by implementing 
  explicit instructions, contextual reasoning, and positive framing techniques. 
  This technique is most effective when starting any prompt engineering task 
  and works best as the foundation for all other techniques. It helps solve 
  ambiguous outputs, instruction misinterpretation, and inconsistent quality, 
  producing clear, reliable, and well-structured AI responses.

embedding_metadata:
  domain: "prompt-engineering"
  technique_type: "foundational"
  complexity_level: "beginner"
  primary_use_cases:
    - "Starting prompt engineering journey"
    - "Establishing baseline prompt quality"
    - "Migrating from previous AI models"
    - "Creating foundation for complex prompts"
  solves_problems:
    - "Vague or ambiguous AI responses"
    - "Inconsistent output quality"
    - "Misunderstood instructions"
    - "Poor format control"
  works_well_with: ["clear-direct-prompting", "prompt-templates-variables", "multishot-examples"]
---

# Claude 4 Prompt Engineering Best Practices

## General Principles

### 1. Be Explicit with Instructions

Claude 4 models require clear, specific instructions for optimal results.

**Less effective:**

```text
Create an analytics dashboard
```

**More effective:**

```text
Create an analytics dashboard. Include as many relevant features and interactions as possible. Go beyond the basics to create a fully-featured implementation.
```

### 2. Add Context to Improve Performance

Explain the reasoning behind instructions for better understanding.

**Less effective:**

```text
NEVER use ellipses
```

**More effective:**

```text
Your response will be read aloud by a text-to-speech engine, so never use ellipses since the text-to-speech engine will not know how to pronounce them.
```

### 3. Be Vigilant with Examples & Details

Ensure examples align with desired behaviors - Claude 4 pays close attention to all details
provided.

## Specific Techniques

### Format Control

1. **Positive framing**: Tell Claude what TO do instead of what NOT to do

   - Try: "Use smoothly flowing prose paragraphs"
   - Avoid: "Don't use markdown"

2. **XML format indicators**: Use tags like `<smoothly_flowing_prose_paragraphs>`

3. **Match prompt style**: Your prompt formatting influences output formatting

### Leverage Thinking Capabilities

Guide reflection and planning:

```text
After receiving tool results, carefully reflect on their quality and determine optimal next steps before proceeding. Use your thinking to plan and iterate based on this new information.
```

### Optimize Parallel Tool Calling

Claude 4 excels at parallel execution:

```text
For maximum efficiency, whenever you need to perform multiple independent operations, invoke all relevant tools simultaneously rather than sequentially.
```

### Agentic Coding

Manage file creation:

```text
If you create any temporary new files, scripts, or helper files for iteration, clean up these files by removing them at the end of the task.
```

### Visual/Frontend Enhancement

Encourage rich implementations:

- "Don't hold back. Give it your all."
- "Include as many relevant features and interactions as possible"
- "Add thoughtful details like hover states, transitions, and micro-interactions"
- "Apply design principles: hierarchy, contrast, balance, and movement"

### General Purpose Solutions

Avoid test-focused implementations:

```text
Please write a high quality, general purpose solution. Implement a solution that works correctly for all valid inputs, not just the test cases. Do not hard-code values or create solutions that only work for specific test inputs.
```

## Migration from Previous Versions

When migrating to Claude 4:

1. **Be more specific** about desired behaviors
2. **Add quality modifiers** to encourage detailed output
3. **Request features explicitly** (animations, interactions, etc.)

## Key Takeaways

- Claude 4 follows instructions precisely - be explicit
- Context and reasoning improve understanding
- Positive instructions work better than negative ones
- Use modifiers to encourage quality and detail
- Frame requests to get "above and beyond" behavior
