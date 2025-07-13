---
id: "reduce-hallucinations"
title: "Reducing Hallucinations"
description: "Techniques to minimize factually incorrect or inconsistent outputs and ensure trustworthy responses"
reference_url: "https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/reduce-hallucinations"
category: "prompt-engineering"
tags:
  ["hallucinations", "accuracy", "verification", "citations", "trustworthiness"]
use_cases:
  - "Factual accuracy requirements"
  - "High-stakes decision support"
  - "Document-based analysis"
  - "Research and fact-checking"
complexity: "intermediate"
dependencies: []
related_techniques: ["chain-of-thought", "long-context", "clear-direct"]
---

# Reducing Hallucinations

## Overview

Even advanced models like Claude can generate factually incorrect or inconsistent text. These
techniques minimize hallucinations to ensure accurate, trustworthy outputs.

## Basic Strategies

### 1. Allow Uncertainty

Explicitly permit Claude to say "I don't know" to drastically reduce false information.

**Example prompt**:

```text
Focus on financial projections, integration risks, and regulatory hurdles.
If you're unsure about any aspect or if the report lacks necessary information,
say "I don't have enough information to confidently assess this."
```

### 2. Use Direct Quotes

For long documents (>20K tokens), require word-for-word quotes before analysis.

**Example structure**:

```text
1. Extract exact quotes from the policy that are most relevant to GDPR and CCPA compliance.
   If you can't find relevant quotes, state "No relevant quotes found."
2. Use the quotes to analyze compliance, referencing quotes by number.
   Only base your analysis on the extracted quotes.
```

### 3. Verify with Citations

Make responses auditable by requiring citations for all claims.

**Example approach**:

```text
After drafting, review each claim in your press release.
For each claim, find a direct quote from the documents that supports it.
If you can't find a supporting quote for a claim, remove that claim
and mark where it was removed with empty [] brackets.
```

## Advanced Techniques

### Chain-of-Thought Verification

Request step-by-step reasoning before final answers to reveal faulty logic.

### Best-of-N Verification

Run the same prompt multiple times and compare outputs. Inconsistencies may indicate hallucinations.

### Iterative Refinement

Use outputs as inputs for follow-up prompts, asking Claude to verify or expand previous statements.

### External Knowledge Restriction

Explicitly instruct Claude to only use provided documents, not general knowledge.

## Best Practices

- Always validate critical information for high-stakes decisions
- Combine multiple techniques for maximum reliability
- Ground responses in provided text whenever possible
- Make uncertainty explicit rather than generating plausible-sounding fiction

**Remember**: These techniques significantly reduce but don't eliminate hallucinations entirely.
