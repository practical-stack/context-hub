---
id: "xml-tags-structure"
title: "XML Tags for Structured Prompts"
description: "Using XML tags to organize prompt components for better parsing, clarity, and response quality"
reference_url: "https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/use-xml-tags"
category: "structure"
tags: ["xml-tags", "structure", "organization", "parsing", "clarity"]

contextual_header: |
  This context module provides structured formatting techniques for organizing 
  complex prompts in the domain of prompt engineering and API development. It 
  specifically addresses prompt clarity, component separation, and parsing accuracy 
  by implementing XML tag-based organization patterns. This technique is most 
  effective when dealing with multi-component prompts and works best in combination 
  with templates, examples, and chain-of-thought reasoning. It helps solve prompt 
  confusion, mixed contexts, and parsing errors, producing well-organized, clearly 
  delineated prompt components that improve both human readability and AI comprehension.

embedding_metadata:
  domain: "prompt-engineering"
  technique_type: "structured"
  complexity_level: "beginner"
  primary_use_cases:
    - "Complex prompts with multiple components"
    - "Separating instructions from data"
    - "Structured output requirements"
    - "Programmatic response parsing"
    - "API integration and automation"
  solves_problems:
    - "Ambiguous prompt component boundaries"
    - "Mixed instructions and data causing confusion"
    - "Difficulty parsing complex prompt structures"
    - "Poor prompt organization and readability"
    - "Inconsistent response format interpretation"
  works_well_with: ["template-based-prompting", "multishot-examples", "chain-of-thought"]
---

# XML Tags for Structured Prompts

## Overview

XML tags help Claude parse prompts more accurately when dealing with multiple components like
context, instructions, and examples. This leads to higher-quality outputs and better prompt
organization.

## Key Benefits

- **Clarity**: Separate different prompt parts with clear structure
- **Accuracy**: Reduce misinterpretation errors
- **Flexibility**: Easy modification without rewriting
- **Parseability**: Extract specific response parts via post-processing

## Best Practices

### 1. Be Consistent

Use same tag names throughout prompts and reference them explicitly:

```xml
Using the contract in <contract> tags...
```

### 2. Nest Tags for Hierarchy

```xml
<outer>
  <inner>content</inner>
</outer>
```

### 3. Combine with Other Techniques

- Multishot prompting: `<examples>`
- Chain of thought: `<thinking>`, `<answer>`

## Common Tag Applications

### Financial Report Example

```xml
<data>{{SPREADSHEET_DATA}}</data>

<instructions>
1. Include sections: Revenue Growth, Profit Margins, Cash Flow
2. Highlight strengths and areas for improvement
</instructions>

<formatting_example>{{Q1_REPORT}}</formatting_example>
```

### Legal Analysis Example

```xml
<agreement>{{CONTRACT}}</agreement>
<standard_contract>{{STANDARD_CONTRACT}}</standard_contract>

<instructions>
1. Analyze these clauses:
   - Indemnification
   - Limitation of liability
   - IP ownership
2. Compare to standard contract
3. Summarize findings in <findings> tags
4. List recommendations in <recommendations> tags
</instructions>
```

## Impact Comparison

### Without XML Tags

- Disorganized analysis
- Mixed instructions with content
- Missed key requirements
- Unclear structure

### With XML Tags

- Structured, thorough analysis
- Clear separation of components
- Complete coverage of requirements
- Actionable, organized output

## Pro Tips

- No "canonical" tags exist - use descriptive names
- XML tags + examples + CoT = high-performance prompts
- Makes Claude's output easier to parse programmatically
