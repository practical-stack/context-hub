---
id: "prompt-engineering-context-selector"
title: "Prompt Engineering Context Selector"
description: "Meta file for selecting appropriate prompt engineering techniques based on context and requirements"
category: "meta"
tags:
  ["meta", "selector", "context", "prompt-engineering", "reference", "guide"]
---

# Prompt Engineering Context Selector

This document serves as a meta-file for effectively referencing and combining prompt engineering techniques. Each technique can be used functionally to implement optimized prompting for specific situations.

> **📚 Related Files:**
>
> - [00-pattern-library.md](00-pattern-library.md) - High-performance patterns and real-world scenarios
> - [00-failure-recovery.md](00-failure-recovery.md) - Failure analysis and conversation recovery tools

## Prompt Requirements Analysis Framework

### 🔍 Diagnostic Question System

When user requirements are ambiguous, use these questions to select appropriate contexts:

#### **Primary Classification Questions**

```
A. Task Type:
   • Content generation (docs, code, creative)
   • Data analysis (extraction, summary, classification)
   • Problem solving (debugging, optimization, strategy)
   • System building (API, automation, workflow)

B. Output Format:
   • Free-form text vs structured data
   • Single response vs interactive dialogue
   • Human-readable vs machine-parseable

C. Accuracy Requirements:
   • Creativity-focused vs accuracy-focused
   • Experimental vs production use
   • General vs domain-specific
```

#### **Secondary Specification Questions**

```
D. Complexity Indicators:
   • Single-step vs multi-step tasks
   • Simple transformation vs complex reasoning
   • Standard cases vs edge case handling

E. Performance Constraints:
   • Response speed vs quality priority
   • Token cost vs accuracy tradeoff
   • One-time vs repeated use

F. Context Scale:
   • Short instructions vs long document processing
   • Single domain vs multi-domain
   • Existing knowledge vs provided data only
```

### ⚡ Context Selection Engine

#### **Quick Diagnosis Matrix**

| Condition Combination                   | Primary Context                 | Secondary Context               | Tertiary Context                |
| --------------------------------------- | ------------------------------- | ------------------------------- | ------------------------------- |
| **Content + Structure + Accuracy**      | `clear-direct-prompting`        | `xml-tags-structure`            | `multishot-examples`            |
| **Analysis + Complex + Accuracy**       | `chain-of-thought`              | `reduce-hallucinations`         | `xml-tags-structure`            |
| **System + Consistency + Repeated**     | `template-based-prompting`      | `output-consistency`            | `prefilling-responses`          |
| **Problem + Multi-step + Production**   | `prompt-chaining`               | `chain-of-thought`              | `reduce-hallucinations`         |
| **Creative + Role-based + Interactive** | `system-prompts-roles`          | `character-consistency`         | `prefilling-responses`          |

#### **Conditional Logic**

```
IF requirements_are_ambiguous THEN
    question_order: primary_classification → secondary_detail → context_recommendation

ELIF existing_prompt_exists THEN
    start_point: prompt-improver-tool → problem_diagnosis → improvement_direction

ELIF advanced_features_needed THEN
    check_foundation: dependency_check → prerequisite_fulfillment → advanced_technique_application

ELSE
    default_path: prompt-engineering-best-practices → requirement_customization
```

### 🎯 Instant Recommendations by Situation

#### **Common Use Case Shortcuts**

```yaml
"Need JSON output": [prefilling-responses, xml-tags-structure, output-consistency]
"Need accurate analysis":
  [reduce-hallucinations, chain-of-thought, multishot-examples]
"Need expert response": [system-prompts-roles, character-consistency]
"Handle complex tasks": [prompt-chaining, xml-tags-structure, chain-of-thought]
"Need consistent results":
  [template-based-prompting, output-consistency, prefilling-responses]
"Process long documents":
  [long-context-prompting, xml-tags-structure, reduce-hallucinations]
"Improve existing prompt": [prompt-improver-tool, prompt-engineering-best-practices]
```

### 📊 Context Selection by Metadata

#### **By Technique Type**

- **Foundational**: `prompt-engineering-best-practices` - Always include as base
- **Structured**: `xml-tags-structure`, `template-based-prompting` - For organization
- **Reasoning**: `chain-of-thought`, `extended-thinking` - For complex analysis
- **Consistency**: `output-consistency`, `prefilling-responses` - For reliable outputs
- **Accuracy**: `reduce-hallucinations` - For factual correctness
- **Creative**: `system-prompts-roles`, `character-consistency` - For persona-based responses

#### **By Complexity Level**

**Beginner-Friendly Combinations:**
- `prompt-engineering-best-practices` + `clear-direct-prompting` + `multishot-examples`
- `xml-tags-structure` + `template-based-prompting`

**Intermediate Combinations:**
- `chain-of-thought` + `xml-tags-structure` + `reduce-hallucinations`
- `system-prompts-roles` + `character-consistency` + `prefilling-responses`

**Advanced Combinations:**
- `prompt-chaining` + `extended-thinking` + `long-context-prompting`

### 📊 Token-Efficient Selection Guide

#### **Lightweight Priority**

1. **Essential Foundation**: `prompt-engineering-best-practices` + `clear-direct-prompting`
2. **Format Control**: `xml-tags-structure` OR `prefilling-responses`
3. **Quality Boost**: `multishot-examples` OR `chain-of-thought`
4. **Special Requirements**: Add only 1 situational technique

#### **Phased Application Strategy**

```
Phase 1: Basic Structure
- Clear instructions + 1-2 examples
- Token budget: ~200-500 tokens

Phase 2: Quality Enhancement
- Reasoning process + structured tags
- Token budget: ~500-1000 tokens

Phase 3: Advanced Optimization
- Role assignment + consistency control + chaining
- Token budget: ~1000+ tokens
```

### **💡 Smart Recommendation Algorithm**

#### **Conditional Recommendation Matrix**

```python
def recommend_contexts(user_input, constraints):
    # Primary: Essential foundation
    base_contexts = ["01-best-practice"]

    # Secondary: Requirement analysis
    if "accurate" in user_input or "reliable" in user_input:
        base_contexts.append("13-reduce-hallucinations")

    if "structure" in user_input or "json" in user_input:
        base_contexts.extend(["07-xml-tags", "09-prefilling"])

    if "complex" in user_input or "step" in user_input:
        base_contexts.append("06-chain-of-thought")

    # Tertiary: Performance constraints
    if constraints.token_limit < 1000:
        return base_contexts[:2]  # Minimal config
    elif constraints.token_limit < 2000:
        return base_contexts[:3]  # Medium config
    else:
        return base_contexts  # Full config
```

#### **Token Budget Recommendation Strategy**

**🟢 Light (< 500 tokens)**

- Core: `prompt-engineering-best-practices` + `clear-direct-prompting`
- Add only 1: Most critical requirement technique
- Examples: Maximum 1-2

**🟡 Standard (500-1500 tokens)**

- Foundation: `prompt-engineering-best-practices` + `clear-direct-prompting` + `multishot-examples`
- Specialization: 2 additional requirement-specific techniques
- Structure: `xml-tags-structure` recommended

**🟠 Premium (1500+ tokens)**

- Full Stack: Foundation + Specialization + Advanced
- Chain composition: Use `prompt-chaining`
- Optimization: Apply `prompt-improver-tool`

## Metadata-Driven Selection

### Using Context Relationships

The new metadata structure enables intelligent context selection based on relationships:

#### **Dependency Resolution**
When selecting a context, automatically include its `requires_techniques`:
- `chain-of-thought` requires `prompt-engineering-best-practices`
- `xml-tags-structure` works best with foundational prompting

#### **Synergy Detection**
Use `works_well_with` to find complementary combinations:
- `chain-of-thought` + `xml-tags-structure` + `multishot-examples`
- `system-prompts-roles` + `character-consistency` + `prefilling-responses`

#### **Conflict Avoidance**
Check `conflicts_with` to prevent incompatible combinations:
- Avoid mixing creative techniques with rigid consistency controls
- Don't combine rapid-response optimizations with deep reasoning

### Problem-Solution Matching

Use `solves_problems` and `primary_use_cases` for targeted selection:

```yaml
User Problem: "AI responses are inconsistent"
→ Search contexts with solves_problems containing "inconsistent"
→ Found: output-consistency, template-based-prompting
→ Recommend: [output-consistency, prefilling-responses, template-based-prompting]

User Problem: "Need transparent reasoning"
→ Search for "reasoning", "transparency", "verifiable"
→ Found: chain-of-thought
→ Recommend: [chain-of-thought, xml-tags-structure, multishot-examples]
```

## Complexity Classification

### Beginner Level

Fundamental techniques for prompt engineering:

- **[01-best-practice.md](01-best-practice.md)** (`prompt-engineering-best-practices`)
  - Foundation principles for all prompting
  - Must understand before applying other techniques
- **[02-use-template-and-variable.md](02-use-template-and-variable.md)** (`prompt-templates-variables`)
  - Reusable prompt structure design
  - Essential for API-based applications
- **[04-be-clear-and-direct.md](04-be-clear-and-direct.md)** (`clear-direct-prompting`)
  - Clear instruction writing
  - Prevents ambiguous responses
- **[05-multishot-with-example.md](05-multishot-with-example.md)** (`multishot-examples`)
  - Quality improvement through 3-5 examples
  - Ensures consistent output format
- **[07-xml-tag-for-structured-prompt.md](07-xml-tag-for-structured-prompt.md)** (`xml-tags-structure`)
  - Structured prompt composition
  - Basic structure for complex prompts

### Intermediate Level

Techniques combining basic approaches for advanced functionality:

- **[03-prompt-improver.md](03-prompt-improver.md)** (`prompt-improver-tool`)
  - Automatic prompt improvement
  - Dependencies: xml-tags, chain-of-thought, examples
- **[06-chain-of-thought.md](06-chain-of-thought.md)** (`chain-of-thought`)
  - Step-by-step reasoning implementation
  - Core for complex problem solving
- **[08-system-prompt-and-role-assignment.md](08-system-prompt-and-role-assignment.md)** (`system-prompts-roles`)
  - Expert role assignment
  - Domain-specific response generation
- **[09-prefilling-llm-response.md](09-prefilling-llm-response.md)** (`prefilling-responses`)
  - Forced response format specification
  - Guarantees JSON/XML output
- **[13-reduce-hallucinations.md](13-reduce-hallucinations.md)** (`reduce-hallucinations`)
  - Minimize hallucination phenomena
  - Ensures reliable responses
- **[14-increasing-output-consistency.md](14-increasing-output-consistency.md)** (`output-consistency`)
  - Maintain consistent output format
  - Dependencies: prefilling, examples, templates-variables
- **[15-keeping-claude-in-character.md](15-keeping-claude-in-character.md)** (`character-consistency`)
  - Maintain character in long conversations
  - Dependencies: system-prompts, prefilling

### Advanced Level

Advanced techniques for complex workflows and large-scale tasks:

- **[10-prompt-chaining-for-complex-task.md](10-prompt-chaining-for-complex-task.md)** (`prompt-chaining`)
  - Complex multi-step task decomposition
  - Dependencies: xml-tags
- **[11-long-context-prompting.md](11-long-context-prompting.md)** (`long-context-prompting`)
  - Large document processing (20K+ tokens)
  - Dependencies: xml-tags
- **[12-extended-thinking.md](12-extended-thinking.md)** (`extended-thinking`)
  - Complex reasoning process optimization
  - Dependencies: chain-of-thought

## 🎯 LLM Execution Protocol

### **Step-by-Step Execution Guide**

#### **Phase 1: Requirements Diagnosis**

```markdown
1. User input analysis:

   - Extract keywords → Apply keyword matching
   - Classify task type → Apply primary classification questions
   - Check constraints → Token budget, performance requirements

2. Generate questions for ambiguous cases:
   - "What output format do you need? (free-form/structured)"
   - "What's more important: accuracy or speed?"
   - "Is this one-time use or repeated use?"
```

#### **Phase 2: Context Selection**

```markdown
1. Essential base context: Always include `prompt-engineering-best-practices`
2. Add by requirements:
   - Accuracy → `reduce-hallucinations`
   - Structure → `xml-tags-structure` + `prefilling-responses`
   - Complex reasoning → `chain-of-thought`
   - Consistency → `template-based-prompting`
3. Apply priorities considering token budget
```

#### **Phase 3: Prompt Generation**

```markdown
1. Extract core techniques from selected contexts
2. Check dependencies → Apply prerequisite techniques first
3. Optimize combinations → Remove redundancy, consider synergy
4. Compose and verify final prompt
```

### **🚨 Critical Decision Checklist**

#### **Context Selection Verification**

- [ ] Is this the optimal combination within token budget?
- [ ] Are dependency relationships properly reflected?
- [ ] Are user's core requirements covered?
- [ ] Is unnecessary complexity avoided?

#### **Quality Assurance Checkpoints**

- [ ] Basic principles (`prompt-engineering-best-practices`) included
- [ ] Clear instructions (`clear-direct-prompting`) applied
- [ ] Appropriate examples (`multishot-examples`) provided
- [ ] Structured tags (`xml-tags-structure`) used when needed

### **⚡ Quick Reference**

#### **Instant Recipes by Situation**

```yaml
"Simple text generation": [prompt-engineering-best-practices, clear-direct-prompting]
"JSON data extraction": [prompt-engineering-best-practices, prefilling-responses, xml-tags-structure]
"Expert analysis": [prompt-engineering-best-practices, system-prompts-roles, chain-of-thought]
"Consistent reports":
  [prompt-engineering-best-practices, template-based-prompting, output-consistency]
"Complex problem solving":
  [prompt-engineering-best-practices, prompt-chaining, chain-of-thought]
"Creative content": [prompt-engineering-best-practices, system-prompts-roles, multishot-examples]
```

#### **Token Optimization Priority**

```
Priority 1: prompt-engineering-best-practices (essential)
Priority 2: clear-direct-prompting (basic quality)
Priority 3: 1 core requirement (most important function)
Priority 4: 1 support technique (quality improvement)
Priority 5: Advanced techniques (only if budget allows)
```

### **🎓 Senior Prompt Engineer Tips**

#### **Efficiency Maximization**

- Apply 80/20 rule: 80% effect with 20% core techniques
- Progressive improvement: Basic → Quality enhancement → Advanced optimization
- Consider reusability: Design templateable structures

#### **Quality Assurance**

- Examples first: Concrete examples more effective than explanations
- Verifiable: Structure to measure and improve results
- Failure preparedness: Exception scenarios and alternative plans

---

## 🔗 Advanced Features

For advanced functionality, see:

- **[00-context-selector-patterns.md](00-context-selector-patterns.md)** - High-performance patterns, real-world scenarios, dependency matrix
- **[00-context-selector-recovery.md](00-context-selector-recovery.md)** - Failure analysis, conversation recovery, meta-prompting tools

---

**🎯 Primary Goal**: Transform user's ambiguous requirements into concrete, executable prompts while finding the optimal balance between token efficiency and quality
