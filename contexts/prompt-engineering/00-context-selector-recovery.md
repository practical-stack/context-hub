---
id: "prompt-engineering-troubleshooting"
title: "Prompt Engineering Troubleshooting"
description: "Common issues and logical troubleshooting patterns for context selection"
category: "meta"
tags: ["troubleshooting", "issues", "diagnosis", "patterns", "selection"]
---

# Prompt Engineering Troubleshooting

This document contains common issues and logical troubleshooting patterns to help with context selection when initial approaches don't work as expected.

> **📚 Related Files:**
>
> - [00-context-selector.md](00-context-selector.md) - Core selection logic and diagnostic framework
> - [00-context-selector-patterns.md](00-context-selector-patterns.md) - High-performance patterns and real-world scenarios

## 🚨 Prompt Failure Analysis & Recovery System

### **Failure Type Diagnosis & Recovery Guide**

#### **Type 1: Output Quality Issues**

**🔍 Diagnostic Prompt:**

```
Current prompt: [existing prompt]
Actual output: [LLM response]
Expected result: [desired result]

Analyze the problems in the above prompt and suggest improvements:
1. Lack of clear instructions
2. Missing or inappropriate examples
3. Insufficient context information
4. Missing output format specification
5. Other issues
```

**🛠️ Recovery Strategy:**

```yaml
problem_type_solutions:
  "vague_responses": → strengthen 04-clear-direct + 05-examples
    → add specific instructions

  "inaccurate_information": → 13-reduce-hallucinations + 06-chain-of-thought
    → add verification steps

  "inconsistency": → 02-templates-variables + 14-output-consistency
    → apply structured templates

  "format_errors": → 09-prefilling + 07-xml-tags
    → force output format specification
```

**Example Recovery Process:**

```
Problem: "Response is too vague and generic"
Diagnosis: Lack of specific instructions and examples
Recovery Steps:
1. Apply 04-clear-direct: Add specific, actionable instructions
2. Apply 05-examples: Include 2-3 concrete examples
3. Test and verify improved output quality
```

#### **Type 2: Complexity Overload**

**🔍 Diagnostic Prompt:**

```
Analyze the existing prompt for complexity issues:

<current_prompt>
[entire existing prompt]
</current_prompt>

Analysis criteria:
- Token count: [current token count]
- Number of requirements: [simultaneous requirements]
- Nested instructions: [complex nesting presence]
- Technique combinations: [number of techniques used]

Improvement directions:
1. Priority-based simplification
2. Step-by-step division possibility
3. Core requirement extraction
```

**🛠️ Recovery Strategy:**

```yaml
complexity_reduction_methods:
  "excessive_requirements": → apply 10-prompt-chaining
    → step-by-step execution

  "token_limit_exceeded": → select only 2-3 core techniques
    → apply lightweight patterns

  "nested_instructions": → structure with 07-xml-tags
    → hierarchical information organization
```

**Example Recovery Process:**

```
Problem: "Prompt is too complex and confusing"
Diagnosis: 8 different requirements in single prompt, 1500+ tokens
Recovery Steps:
1. Apply 10-prompt-chaining: Break into 3 sequential prompts
2. Apply 07-xml-tags: Structure each prompt clearly
3. Prioritize top 3 requirements for immediate implementation
```

#### **Type 3: Context Mismatch**

**🔍 Diagnostic Prompt:**

```
Analyze the compatibility between current situation and techniques used:

Purpose: [intended purpose]
Current techniques: [applied techniques]
Actual result: [obtained result]

Mismatch analysis:
1. Purpose vs technique compatibility
2. Prerequisite fulfillment
3. Dependency relationship check
4. Alternative technique recommendations
```

**🛠️ Recovery Strategy:**

```yaml
context_reselection:
  "creative_vs_analytical_mixing": → clarify purpose then reselect techniques
    → clarify role with 08-system-prompts

  "simple_vs_complex_tasks": → reassess complexity
    → select appropriate level techniques

  "one_time_vs_repeated_use": → redesign based on usage pattern
    → consider 02-templates-variables
```

**Example Recovery Process:**

```
Problem: "Using creative techniques for data analysis task"
Diagnosis: Technique mismatch - creative vs analytical requirements
Recovery Steps:
1. Clarify purpose: Data analysis requires accuracy over creativity
2. Reselect techniques: 13-reduce-hallucinations + 06-chain-of-thought
3. Apply 08-system-prompts: "You are a data analyst focusing on accuracy"
```

## 🔄 Conversation Recovery Protocol

### **Phase 1: Context Summarization**

**📋 Context Summary Prompt:**

```
Please summarize the conversation context up to this point:

<conversation_history>
[entire conversation content or key parts]
</conversation_history>

Summary format:
1. **Original Goal**: What the user intended to achieve
2. **Progress**: Methods tried so far
3. **Current Problem**: Where stuck or where things went wrong
4. **Key Issue**: Most important problem to solve
5. **Needed Information**: Additional information required
```

**Usage Example:**

```
When to use: After 3+ failed attempts or when conversation goes off-track
Expected outcome: Clear understanding of current situation
Next step: Apply Phase 2 diagnostic questions
```

### **Phase 2: Diagnostic Information Extraction**

**🔍 Diagnostic Information Collection Prompt:**

```
Please systematically collect the following information for problem solving:

<diagnostic_questions>
Technical constraints:
- Token budget: [any limitations?]
- Response time: [real-time vs batch processing]
- Accuracy requirements: [creativity vs accuracy]

Usage context:
- Usage frequency: [one-time vs repeated use]
- Target users: [experts vs general users]
- Output purpose: [human reading vs machine parsing]

Current state:
- Biggest problem: [specific problem]
- Satisfactory parts: [parts to maintain]
- Priority: [most important improvement]
</diagnostic_questions>

Please describe the current situation specifically for each item.
```

**Usage Example:**

```
When to use: After context summarization, before selecting new approach
Expected outcome: Clear requirements and constraints
Next step: Apply Phase 3 goal redefinition
```

### **Phase 3: Goal Redefinition**

**🎯 Goal Reset Prompt:**

```
Please redefine goals based on collected information:

<goal_refinement>
Original goal: [initial intention]
Current situation: [diagnosis result]
Constraints: [technical/business constraints]

Redefined goals:
1. **Core Goal**: [most important achievement target]
2. **Success Criteria**: [when can we say it's successful]
3. **Priorities**: [1st priority, 2nd priority, 3rd priority]
4. **Compromisable Parts**: [parts that can be sacrificed if needed]
5. **Absolutely Essential Elements**: [parts that must be included]
</goal_refinement>

Please suggest new approaches based on this.
```

**Usage Example:**

```
When to use: After diagnostic information collection
Expected outcome: Clear, achievable goals with success criteria
Next step: Select appropriate techniques using 00-context-selector.md
```

## 🛠️ Meta-Prompting Tools

### **🔧 Situation Analysis Tool**

**Current Situation Analysis Prompt:**

```
Please meta-analyze the prompt engineering attempts so far:

<meta_analysis>
Techniques used: [list of applied techniques]
Token usage: [approximate token count]
Number of attempts: [how many tries]
Changes made: [what was changed each time]

Pattern analysis:
- Recurring problems: [problems that keep appearing]
- Improved parts: [parts that gradually improved]
- Untried approaches: [methods not yet attempted]
</meta_analysis>

Next step recommendation: [specific next action]
```

**Usage Scenarios:**

```yaml
Use when:
  - Multiple failed attempts (3+)
  - Unclear why prompts aren't working
  - Need to identify patterns in failures

Expected insights:
  - Identify recurring issues
  - Spot improvement trends
  - Recommend unexplored approaches
```

### **🎯 Problem Identification Tool**

**Core Problem Identification Prompt:**

```
Please systematically identify the biggest problems in the current prompt:

<problem_identification>
1. **Structural Issues**:
   - Information organization method
   - Instruction sequence
   - Tag and structure usage

2. **Semantic Issues**:
   - Term ambiguity
   - Context deficiency
   - Intent communication failure

3. **Functional Issues**:
   - Output format inconsistency
   - Insufficient exception handling
   - Lack of verification mechanism

4. **Optimization Issues**:
   - Unnecessary complexity
   - Token waste
   - Performance degradation
</problem_identification>

Please select the most serious problem from each category and provide solutions.
```

**Usage Guide:**

```yaml
When to use:
  - Systematic problem diagnosis needed
  - Multiple issues suspected
  - Need comprehensive analysis

Output format:
  - Categorized problem identification
  - Priority ranking
  - Specific solutions for each problem
```

### **🔄 Direction Reset Tool**

**Conversation Direction Reset Prompt:**

```
Let's reset the current conversation and proceed in a new direction:

<conversation_reset>
Previous attempt summary:
- Goal: [original goal]
- Methods tried: [techniques used]
- Result: [obtained result]
- Problems: [discovered problems]

New approach:
1. **Problem Redefinition**: [view problem from different angle]
2. **Method Change**: [try completely different techniques]
3. **Goal Adjustment**: [set more realistic goals]
4. **Step-by-step Approach**: [divide complex problems simply]
</conversation_reset>

What new approach would you like to try?
```

**Reset Strategies:**

```yaml
Problem_Redefinition:
  - Change perspective (user → system view)
  - Simplify complex requirements
  - Focus on core value proposition

Method_Change:
  - Switch from creative to analytical approach
  - Change from single to multi-step process
  - Try different technique combinations

Goal_Adjustment:
  - Lower ambition level temporarily
  - Focus on minimum viable solution
  - Prioritize most critical feature

Step_by_step:
  - Break down into smaller tasks
  - Solve one piece at a time
  - Build complexity gradually
```

## 🔄 Iterative Improvement Approach

### **Simple Improvement Cycle**

```
1. Identify: What specific issue occurred?
2. Diagnose: Which context selection might address it?
3. Adjust: Try different context combinations
4. Observe: Did the issue improve?
5. Standardize: Template successful patterns
```

### **Performance Improvement Strategies**

#### **For Low Effectiveness (< 70%)**

```yaml
Diagnosis: Technique selection mismatch
Actions:
  - Review 00-context-selector.md for better technique matching
- Apply 03-prompt-improver.md for systematic enhancement
- Consider 00-context-selector-patterns.md for proven patterns
```

#### **For Low Efficiency (< 0.5 score/token)**

```yaml
Diagnosis: Token waste or poor technique selection
Actions:
  - Apply token-efficient patterns from 00-context-selector-patterns.md
  - Reduce technique complexity
  - Focus on high-impact, low-cost techniques
```

#### **For Low Consistency (< 80%)**

```yaml
Diagnosis: Lack of structured approach
Actions:
  - Apply 02-templates-variables.md
  - Use 14-output-consistency.md
  - Add 09-prefilling.md for format control
```

#### **For Low Usability (< 3.0)**

```yaml
Diagnosis: User experience issues
Actions:
  - Simplify interface and instructions
  - Add more examples and guidance
  - Improve feedback and error messages
```

## 🎯 Advanced Recovery Techniques

### **Technique Rotation Strategy**

When stuck with current approach, systematically try different technique categories:

```yaml
Rotation_Order:
  1. Clarity_Techniques: [04-clear-direct, 05-examples]
  2. Structure_Techniques: [07-xml-tags, 02-templates]
  3. Quality_Techniques: [13-reduce-hallucinations, 06-chain-of-thought]
  4. Consistency_Techniques: [14-output-consistency, 09-prefilling]
  5. Advanced_Techniques: [10-prompt-chaining, 12-extended-thinking]
```

### **Fallback Hierarchy**

Progressive simplification when complex approaches fail:

```yaml
Level_1_Fallback: "Simplify to core requirements only"
Level_2_Fallback: "Use only 01-best-practice + 04-clear-direct"
Level_3_Fallback: "Manual step-by-step guidance"
Level_4_Fallback: "Break into smallest possible sub-tasks"
```

### **Recovery Success Patterns**

```yaml
Pattern_A_Overshoot_Recovery:
  Problem: "Too complex, overwhelming"
  Solution: "Simplify dramatically, then build up slowly"

Pattern_B_Undershoot_Recovery:
  Problem: "Too simple, lacks depth"
  Solution: "Add structure and examples gradually"

Pattern_C_Mismatch_Recovery:
  Problem: "Wrong technique for task type"
  Solution: "Restart with proper technique selection"
```

---

**🚀 Advanced Recovery Goal**: Provide systematic, senior-level prompt engineering recovery capabilities through comprehensive failure analysis, structured conversation recovery, and continuous performance improvement.
