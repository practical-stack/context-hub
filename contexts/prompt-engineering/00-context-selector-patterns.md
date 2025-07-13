---
id: "prompt-engineering-pattern-library"
title: "Prompt Engineering Pattern Library"
description: "Common selection patterns, real-world scenarios, and context combinations demonstrating the schema in action"
category: "meta"
tags: ["patterns", "scenarios", "combinations", "selection", "examples"]
---

# Prompt Engineering Pattern Library

This document demonstrates common context selection patterns and real-world scenarios showing how to apply the metadata schema for intelligent context combination.

> **📚 Related Files:**
>
> - [00-context-selector.md](00-context-selector.md) - Core selection logic and diagnostic framework

## 🎯 Common Selection Patterns

### **⚡ Speed-First Pattern**

```
Minimal config: prompt-engineering-best-practices + clear-direct-prompting
Purpose: Fast response, basic quality guarantee
Use: Real-time chatbots, quick prototypes
```

**Example Implementation:**

```
Task: Generate product descriptions
Context: prompt-engineering-best-practices, clear-direct-prompting
Prompt: "Write a clear, concise product description for [product]. Include key features and benefits."
```

### **🔒 Accuracy-First Pattern**

```
Accuracy config: reduce-hallucinations + chain-of-thought + multishot-examples
Purpose: Maximum accuracy, reliability guarantee
Use: Medical/legal/financial domains, critical decisions
```

**Example Implementation:**

```
Task: Medical diagnosis assistance
Context: reduce-hallucinations, chain-of-thought, multishot-examples
Prompt: "Analyze symptoms step-by-step. Only use verified medical knowledge. Provide differential diagnosis with evidence."
```

### **🏭 Production-First Pattern**

```
Stability config: template-based-prompting + output-consistency + prefilling-responses
Purpose: Consistency, scalability, maintainability
Use: API services, large-scale applications
```

**Example Implementation:**

```
Task: Customer service responses
Context: template-based-prompting, output-consistency, prefilling-responses
Prompt: Template-based with variable slots and forced JSON output format
```

### **🎨 Creative-First Pattern**

```
Creativity config: system-prompts-roles + clear-direct-prompting + character-consistency
Purpose: Originality, brand consistency, engagement
Use: Marketing, content creation, creative work
```

**Example Implementation:**

```
Task: Brand storytelling
Context: system-prompts-roles, clear-direct-prompting, character-consistency
Prompt: "You are a brand storyteller. Create engaging narratives that reflect our brand values..."
```

## 🎪 Real-world Scenarios

### **Scenario A: Customer Feedback Analysis Tool**

```
Diagnosis: Data analysis + Structured output + Repeated use
Recommendation: template-based-prompting → xml-tags-structure → output-consistency
Optional: + reduce-hallucinations (if accuracy critical)
```

**Implementation:**

```yaml
Primary: template-based-prompting
- Create reusable template for different feedback types
- Variable slots for product, sentiment, category

Secondary: xml-tags-structure
- Structure analysis with <feedback>, <sentiment>, <category> tags
- Organize complex feedback data hierarchically

Tertiary: output-consistency
- Ensure consistent JSON output format
- Standardize sentiment scale (1-5)
- Maintain category naming conventions
```

### **Scenario B: Creative Marketing Copy Generation**

```
Diagnosis: Content generation + Creativity + Expert perspective
Recommendation: 08-system-prompts → 04-clear-direct → 05-examples
Optional: + 15-character-consistency (for brand tone)
```

**Implementation:**

```yaml
Primary: 08-system-prompts
- "You are a senior marketing copywriter with 10+ years experience"
- Define brand voice and target audience
- Set creative constraints and objectives

Secondary: 04-clear-direct
- Clear instructions for copy length, format, call-to-action
- Specific requirements for tone and style
- Direct guidance on what to avoid

Tertiary: 05-examples
- 2-3 examples of successful brand copy
- Show desired format and style
- Demonstrate brand voice consistency
```

### **Scenario C: Technical Document Summarization**

```
Diagnosis: Document processing + Complex reasoning + Accuracy
Recommendation: 11-long-context → 06-chain-of-thought → 13-reduce-hallucinations
Optional: + 07-xml-tags (for structured summary)
```

**Implementation:**

```yaml
Primary: 11-long-context
- Handle large technical documents (20K+ tokens)
- Process multiple sections and cross-references
- Maintain context across document sections

Secondary: 06-chain-of-thought
- Break down complex technical concepts step-by-step
- Show logical flow of arguments
- Connect related technical points

Tertiary: 13-reduce-hallucinations
- Verify technical accuracy
- Reference only document content
- Flag uncertain interpretations
```

### **Scenario D: Multi-language Code Documentation**

```
Diagnosis: System building + Technical accuracy + Consistency
Recommendation: 02-templates-variables → 13-reduce-hallucinations → 07-xml-tags
Optional: + 06-chain-of-thought (for complex logic explanation)
```

**Implementation:**

```yaml
Primary: 02-templates-variables
- Template for different programming languages
- Variable slots for function names, parameters, return types
- Consistent documentation format

Secondary: 13-reduce-hallucinations
- Only document actual code functionality
- Avoid speculation about code behavior
- Reference actual parameter names and types

Tertiary: 07-xml-tags
- Structure with <function>, <parameters>, <returns>, <example>
- Organize complex API documentation
- Enable easy parsing and formatting
```

## 🔗 Dependency Matrix

| Technique                  | Required Dependencies                     | Recommended Combinations                   |
| -------------------------- | ----------------------------------------- | ------------------------------------------ |
| **prompt-improver-tool**   | xml-tags, chain-of-thought, examples      | -                                          |
| **prompt-chaining**        | xml-tags                                  | chain-of-thought, clear-direct             |
| **long-context-prompting** | xml-tags                                  | reduce-hallucinations, templates-variables |
| **extended-thinking**      | chain-of-thought                          | examples, clear-direct                     |
| **output-consistency**     | prefilling, examples, templates-variables | xml-tags                                   |
| **character-consistency**  | system-prompts, prefilling                | examples                                   |

### **Dependency Resolution Examples**

#### **Using prompt-chaining (requires xml-tags)**

```
Step 1: Apply 07-xml-tags first
- Structure complex task with <task>, <step>, <output> tags
- Define clear boundaries between steps

Step 2: Apply 10-prompt-chaining
- Break down multi-step process
- Chain individual prompts with structured handoffs
```

#### **Using output-consistency (requires prefilling, examples, templates-variables)**

```
Step 1: Apply 02-templates-variables
- Create consistent template structure
- Define variable slots for dynamic content

Step 2: Apply 05-examples
- Show 2-3 examples of desired output format
- Demonstrate consistency across variations

Step 3: Apply 09-prefilling
- Force specific output format (JSON/XML)
- Ensure structural consistency

Step 4: Apply 14-output-consistency
- Combine all previous techniques for maximum consistency
```

## 🚀 Problem-Solving Flow

### **1. Low Response Quality**

```
04-be-clear-and-direct.md → 05-multishot-with-example.md → 06-chain-of-thought.md
```

**Escalation Path:**

- Start with clearer instructions
- Add specific examples if still unclear
- Add reasoning process for complex tasks

### **2. Lack of Consistency**

```
02-use-template-and-variable.md → 09-prefilling-llm-response.md → 14-increasing-output-consistency.md
```

**Escalation Path:**

- Implement template structure
- Force output format
- Apply comprehensive consistency techniques

### **3. Hallucination Issues**

```
13-reduce-hallucinations.md → 06-chain-of-thought.md → 05-multishot-with-example.md
```

**Escalation Path:**

- Apply hallucination reduction techniques
- Add step-by-step reasoning
- Provide concrete examples to guide responses

### **4. Missing Steps in Complex Tasks**

```
10-prompt-chaining-for-complex-task.md → 07-xml-tag-for-structured-prompt.md
```

**Escalation Path:**

- Break down into smaller, chained tasks
- Add structured organization with XML tags

## 🎯 Situation-Specific Optimizations

### **By Token Budget**

#### **Light Budget (< 500 tokens)**

```yaml
Patterns: [Speed-First]
Techniques: [01-best-practice, 04-clear-direct]
Trade-offs: Speed over accuracy
Use cases: Quick prototypes, simple tasks
```

#### **Medium Budget (500-1500 tokens)**

```yaml
Patterns: [Production-First, Creative-First]
Techniques: [01-best-practice, 04-clear-direct, 05-examples, 07-xml-tags]
Trade-offs: Balanced performance
Use cases: Most business applications
```

#### **High Budget (1500+ tokens)**

```yaml
Patterns: [Accuracy-First, Complex reasoning]
Techniques: [All techniques available]
Trade-offs: Maximum quality
Use cases: Critical decisions, complex analysis
```

### **By Use Case Type**

#### **API Integration**

```yaml
Priority: Consistency and reliability
Patterns: [Production-First]
Core techniques: [02-templates-variables, 14-output-consistency, 09-prefilling]
Key considerations: Structured output, error handling
```

#### **Content Creation**

```yaml
Priority: Creativity and brand alignment
Patterns: [Creative-First]
Core techniques: [08-system-prompts, 15-character-consistency, 05-examples]
Key considerations: Brand voice, audience engagement
```

#### **Data Analysis**

```yaml
Priority: Accuracy and insight
Patterns: [Accuracy-First]
Core techniques: [13-reduce-hallucinations, 06-chain-of-thought, 07-xml-tags]
Key considerations: Data integrity, logical reasoning
```

#### **Customer Support**

```yaml
Priority: Consistency and helpfulness
Patterns: [Production-First + Creative elements]
Core techniques:
  [02-templates-variables, 08-system-prompts, 14-output-consistency]
Key considerations: Brand voice, solution accuracy
```

## 🧪 Advanced Combinations

### **Hybrid Patterns**

#### **Accurate + Creative**

```yaml
Use case: Creative content that must be factually accurate
Combination: 08-system-prompts + 13-reduce-hallucinations + 05-examples
Token cost: ~700-1000 tokens
Example: Historical fiction writing, educational content
```

#### **Fast + Consistent**

```yaml
Use case: High-volume, consistent output with speed priority
Combination: 02-templates-variables + 09-prefilling + 04-clear-direct
Token cost: ~400-600 tokens
Example: Email templates, standard reports
```

#### **Complex + Reliable**

```yaml
Use case: Complex analysis with high reliability requirements
Combination: 10-prompt-chaining + 13-reduce-hallucinations + 06-chain-of-thought
Token cost: ~1000-1500 tokens
Example: Legal document analysis, medical case studies
```

### **Technique Synergies**

#### **xml-tags + chain-of-thought**

```
Synergy: Structured reasoning
Benefit: Clear, organized thinking process
Use: Complex problem-solving, step-by-step analysis
```

#### **system-prompts + character-consistency**

```
Synergy: Maintained expertise
Benefit: Consistent expert persona throughout conversation
Use: Advisory roles, specialized consultations
```

#### **templates-variables + output-consistency**

```
Synergy: Scalable standardization
Benefit: Consistent format across varied content
Use: Business processes, automated reporting
```

---

## 📊 Performance Metrics by Pattern

### **Speed-First Pattern**

- **Response Time**: ⭐⭐⭐⭐⭐ (Excellent)
- **Token Efficiency**: ⭐⭐⭐⭐⭐ (Excellent)
- **Accuracy**: ⭐⭐⭐ (Good)
- **Consistency**: ⭐⭐⭐ (Good)

### **Accuracy-First Pattern**

- **Response Time**: ⭐⭐ (Fair)
- **Token Efficiency**: ⭐⭐ (Fair)
- **Accuracy**: ⭐⭐⭐⭐⭐ (Excellent)
- **Consistency**: ⭐⭐⭐⭐ (Very Good)

### **Production-First Pattern**

- **Response Time**: ⭐⭐⭐⭐ (Very Good)
- **Token Efficiency**: ⭐⭐⭐⭐ (Very Good)
- **Accuracy**: ⭐⭐⭐⭐ (Very Good)
- **Consistency**: ⭐⭐⭐⭐⭐ (Excellent)

### **Creative-First Pattern**

- **Response Time**: ⭐⭐⭐⭐ (Very Good)
- **Token Efficiency**: ⭐⭐⭐⭐ (Very Good)
- **Accuracy**: ⭐⭐⭐ (Good)
- **Consistency**: ⭐⭐⭐⭐ (Very Good)

---

**🎯 Pattern Selection Goal**: Choose the optimal pattern based on your specific requirements for speed, accuracy, consistency, and token efficiency. Combine patterns for hybrid approaches when needed.
