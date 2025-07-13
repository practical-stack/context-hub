---
id: "long-context-prompting"
title: "Long Context Prompting"
description: "Techniques for effectively handling large documents and multi-document analysis within Claude's 200K token context window"
reference_url: "https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/long-context-tips"
category: "prompt-engineering"
tags:
  [
    "long-context",
    "large-documents",
    "multi-document",
    "context-window",
    "document-analysis",
  ]
use_cases:
  - "Large document analysis (20K+ tokens)"
  - "Multi-document comparison"
  - "Comprehensive research tasks"
  - "Document-based question answering"
complexity: "advanced"
dependencies: ["xml-tags"]
related_techniques: ["xml-tags", "reduce-hallucinations", "templates-variables"]
---

# Long Context Prompting

## Overview

Claude's extended context window (200K tokens) enables handling complex, data-rich tasks. These
techniques help leverage this capability effectively.

## Essential Techniques

### 1. Put Long Data at the Top

Place long documents (~20K+ tokens) near the beginning of your prompt, above queries, instructions,
and examples.

- **Impact**: Can improve response quality by up to 30% in tests
- **Most effective**: With complex, multi-document inputs

### 2. Structure with XML Tags

For multiple documents, use clear XML structure:

```xml
<documents>
  <document index="1">
    <source>annual_report_2023.pdf</source>
    <document_content>
      {{ANNUAL_REPORT}}
    </document_content>
  </document>
  <document index="2">
    <source>competitor_analysis_q2.xlsx</source>
    <document_content>
      {{COMPETITOR_ANALYSIS}}
    </document_content>
  </document>
</documents>

Analyze the annual report and competitor analysis. Identify strategic advantages and recommend Q3 focus areas.
```

### 3. Ground Responses in Quotes

Ask Claude to quote relevant document parts before completing tasks:

- Helps Claude focus on pertinent information
- Reduces noise from irrelevant content
- Improves accuracy for document-based tasks

**Example structure**:

```xml
Find quotes from the patient records that are relevant to diagnosing symptoms.
Place these in <quotes> tags.
Then, based on these quotes, provide diagnostic information in <info> tags.
```

## Best Practices

- **Document order**: Most important documents first
- **Clear metadata**: Include source, date, type in tags
- **Specific instructions**: Tell Claude exactly how to use the documents
- **Quote-first approach**: For accuracy in long document analysis
