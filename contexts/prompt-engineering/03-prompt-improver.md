---
id: "prompt-improver-tool"
title: "Prompt Improver Tool"
description: "Automated prompt enhancement through 4-step process for complex tasks requiring high accuracy"
reference_url: "https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/prompt-improver"
category: "prompt-engineering"
tags:
  ["prompt-improver", "automation", "chain-of-thought", "xml-tags", "examples"]
use_cases:
  - "Complex tasks requiring detailed reasoning"
  - "Accuracy-critical applications"
  - "Improving existing prompts"
  - "Adding chain-of-thought to prompts"
complexity: "intermediate"
dependencies: ["xml-tags", "chain-of-thought", "examples"]
related_techniques: ["chain-of-thought", "xml-tags", "examples"]
---

# Prompt Improver Tool

## Overview

The prompt improver automatically analyzes and enhances prompts through a 4-step process, making
them more robust for complex tasks requiring high accuracy.

## How It Works

### 4-Step Enhancement Process

1. **Example identification**: Locates and extracts examples from your template
2. **Initial draft**: Creates structured template with clear sections and XML tags
3. **Chain of thought refinement**: Adds detailed reasoning instructions
4. **Example enhancement**: Updates examples to demonstrate new reasoning process

## What You Get

- **Detailed chain-of-thought instructions** guiding Claude's reasoning
- **Clear XML organization** separating different components
- **Standardized example formatting** with step-by-step reasoning
- **Strategic prefills** guiding initial responses

## When to Use

### Best For

- Complex tasks requiring detailed reasoning
- Accuracy-critical applications
- Significant output improvement needs

### Not Ideal For

- Latency-sensitive applications
- Cost-sensitive use cases
- Simple, straightforward tasks

## Example Transformation

### Original Prompt

```text
From the following list of Wikipedia article titles, identify which article this sentence came from.
Respond with just the article title and nothing else.

Article titles: {{titles}}
Sentence to classify: {{sentence}}
```

### Improved Prompt

```text
You are an intelligent text classification system specialized in matching sentences to Wikipedia article titles.

First, review the following list of Wikipedia article titles:
<article_titles>
{{titles}}
</article_titles>

Now, consider this sentence that needs to be classified:
<sentence_to_classify>
{{sentence}}
</sentence_to_classify>

Follow these steps:
1. List the key concepts from the sentence
2. Compare each key concept with the article titles
3. Rank the top 3 most relevant titles and explain why
4. Select the most appropriate article title

Wrap your analysis in <analysis> tags. Include:
- List of key concepts
- Comparison with article titles
- Ranking of top 3 titles with explanations
- Final choice and reasoning

After your analysis, output only the chosen article title.
```

## Key Improvements Applied

- **Adds reasoning steps**: Clear methodology for decision-making
- **Uses XML tags**: Organized content structure
- **Explicit formatting**: Clear output requirements
- **Guided analysis**: Step-by-step thinking process

## Usage Tips

### Prerequisites

- Prompt template to improve
- Feedback on current issues (recommended)
- Example inputs/outputs (recommended)

### No Examples? Use Test Case Generator

1. Generate sample inputs
2. Get Claude's responses
3. Edit to match ideal outputs
4. Add polished examples to prompt

## Troubleshooting

### Common Issues

- **Missing examples**: Ensure proper XML formatting at start of first user message
- **Verbose reasoning**: Add specific length/detail instructions
- **Mismatched steps**: Modify reasoning steps for your use case

## Important Notes

- Examples appear separately in Workbench UI but are included in first user message for API calls
- View raw format via "Get Code" button
- Creates longer, thorough responses (consider for latency-sensitive apps)
