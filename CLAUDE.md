# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

Context Hub is a **schema definition and reference implementation** repository that establishes standardized approaches for storing contextual knowledge across multiple topic domains, with intelligent selection patterns. The goal is to propose a universal metadata schema and demonstrate its application through concrete examples and logical selection systems.

**This is NOT a library or utility project** - it's about defining storage standards, relationship patterns, and intelligent selection logic.

## Core Mission

### Schema-First Approach with Intelligence
1. **Define Universal Standards**: Create metadata schemas that work across any topic domain
2. **Demonstrate Intelligent Selection**: Show logical patterns for choosing and combining contexts
3. **Establish Relationship Patterns**: Create systematic approaches to context connections
4. **Enable Cross-Domain Consistency**: Same structure and selection logic whether it's prompt engineering, React, or data analysis

### Topic-Domain Demonstration
- **Prompt Engineering** (current): Complete proof-of-concept with intelligent selection system
- **React** (planned): Next domain to demonstrate schema universality and selection adaptation
- **Data Analysis** (planned): Further validation of cross-domain applicability
- **Any Topic** (future): Schema and selection patterns should work for any knowledge domain

## Repository Architecture

### Current Structure

```
context-hub/
├── CLAUDE.md                           # Project instructions
├── README.md                           # Public-facing explanation
├── docs/                              # Universal standards and patterns
│   ├── standards/                     # Cross-domain standards
│   │   ├── context-metadata-schema.md # CORE: Universal metadata structure
│   │   └── file-naming-conventions.md # Naming standards
│   └── architecture/                  # Design documentation
│       └── functional-composition.md  # Context relationship patterns
├── contexts/                          # Topic-specific implementations
│   ├── prompt-engineering/            # Domain 1: LLM techniques ✅ COMPLETE
│   │   ├── [15+ context-files].md     # Individual contexts with full schema
│   │   ├── 00-context-selector.md     # Core selection logic ✅
│   │   ├── 00-context-selector-patterns.md  # Selection patterns ✅
│   │   └── 00-context-selector-troubleshooting.md  # Issue resolution ✅
│   ├── react/                         # Domain 2: React development (planned)
│   └── data-analysis/                 # Domain 3: Data analysis (planned)
```

### Design Principles

1. **Universal Schema**: Same metadata structure regardless of topic
2. **Rich Semantics**: Detailed contextual headers for human understanding
3. **Intelligent Relationships**: Explicit connections enabling logical selection
4. **Domain Flexibility**: Schema adapts to any subject area
5. **Maintainable Complexity**: Simple enough to manage manually, smart enough to be useful

## Universal Metadata Schema

### Standard Structure (All Domains)

```yaml
---
id: "unique-identifier"                    # kebab-case, unique across domain
title: "Human-Readable Name"               # Clear, descriptive title
description: "Concise explanation"         # 1-2 sentences explaining purpose
category: "domain-specific-category"       # Categorization within domain
tags: ["tag1", "tag2", "tag3"]            # Searchable keywords

contextual_header: |
  Rich semantic description explaining what this context provides,
  in which domain it applies, what specific problems it addresses,
  when it's most effective, what it works well with, and what
  outcomes it produces. This enables human understanding and
  intelligent selection logic.

embedding_metadata:
  domain: "topic-area"                     # e.g., "prompt-engineering", "react"
  technique_type: "domain-specific-type"  # Categorization within domain
  complexity_level: "beginner|intermediate|advanced"
  primary_use_cases: ["scenario-1", "scenario-2"]
  solves_problems: ["problem-1", "problem-2"]
  works_well_with: ["context-id-1", "context-id-2"]
  requires_techniques: ["prerequisite-id"]     # Optional: hard dependencies
  conflicts_with: ["incompatible-id"]          # Optional: incompatible contexts
---
```

### Intelligent Selection Framework

The schema enables logical context selection through:

**Relationship-Based Logic:**
```yaml
# Automatic dependency resolution
chain-of-thought:
  requires_techniques: ["prompt-engineering-best-practices"]
  works_well_with: ["xml-tags-structure", "multishot-examples"]

# Conflict prevention
rapid-response-optimization:
  conflicts_with: ["chain-of-thought", "extended-thinking"]
```

**Problem-Solution Matching:**
```yaml
# Direct problem targeting
User Problem: "AI responses are inconsistent"
→ Search: contexts with solves_problems containing "inconsistent"
→ Found: output-consistency, template-based-prompting
→ Selection Logic: [output-consistency, prefilling-responses, template-based-prompting]
```

**Pattern-Based Selection:**
```yaml
# Common proven combinations
Speed-First: [prompt-engineering-best-practices, clear-direct-prompting]
Accuracy-First: [reduce-hallucinations, chain-of-thought, multishot-examples]
Production-First: [template-based-prompting, output-consistency, prefilling-responses]
Creative-First: [system-prompts-roles, clear-direct-prompting, character-consistency]
```

## Implementation Status

### ✅ Schema Established
- Universal metadata structure defined and documented
- Cross-domain standards created in `docs/standards/`
- File naming conventions established
- Relationship mapping patterns demonstrated

### ✅ First Domain Complete: Prompt Engineering
- **15+ context modules** with full schema implementation
- **Enhanced metadata applied** to key contexts:
  - `01-best-practice.md` - Basic schema example
  - `06-chain-of-thought.md` - Rich metadata demonstration
  - `07-xml-tag-for-structured-prompt.md` - Relationship mapping example
- **Intelligent selection system** fully implemented:
  - **Core Selector**: Diagnostic questions and selection matrices
  - **Pattern Library**: Common combinations and real-world scenarios
  - **Troubleshooting Guide**: Logical approaches for resolving issues
- **Relationship mapping** demonstrated across contexts

### ✅ Selection Intelligence Features
- **Diagnostic Question System**: Guides users to appropriate contexts based on requirements
- **Pattern Recognition**: Pre-defined combinations for common scenarios (Speed-First, Accuracy-First, etc.)
- **Problem-Solution Matching**: Direct mapping from user problems to relevant contexts
- **Dependency Resolution**: Automatic inclusion of prerequisite contexts
- **Conflict Prevention**: Logic to avoid incompatible technique combinations
- **Troubleshooting Patterns**: Systematic approaches to resolve common issues

### ✅ Repository Architecture
- Cross-domain standards in `docs/standards/`
- Context relationship patterns documented
- Scalable structure for multiple topic domains
- Clean separation between schema definition and domain implementation

### 🔄 Schema Refinement Complete
- Simplified to exclude complex metrics (token costs, effectiveness scores)
- Focused on maintainable metadata that doesn't require domain expertise
- Cleaned up files to focus on schema and selection logic
- Removed unnecessary complexity while preserving intelligent selection

### ⏳ Next Domain Implementation
- **React development** contexts using same schema and selection patterns
- **Data analysis** contexts following same organizational principles
- Validation that schema and selection logic work across diverse topics

## Intelligent Selection Logic

### Core Selection Patterns

**Diagnostic Questions Approach:**
```yaml
Primary Classification:
- Task Type: Content generation vs. Data analysis vs. Problem solving
- Output Format: Free-form vs. Structured vs. Interactive
- Accuracy Requirements: Creative vs. Balanced vs. Critical

Secondary Specification:
- Complexity: Single-step vs. Multi-step vs. Complex reasoning
- Performance: Speed vs. Quality priority
- Context Scale: Short vs. Long document processing
```

**Selection Matrices:**
```yaml
| Requirements | Primary Context | Secondary Context | Tertiary Context |
|--------------|----------------|-------------------|------------------|
| Content + Structure + Accuracy | clear-direct-prompting | xml-tags-structure | multishot-examples |
| Analysis + Complex + Accuracy | chain-of-thought | reduce-hallucinations | xml-tags-structure |
| System + Consistency + Repeated | template-based-prompting | output-consistency | prefilling-responses |
```

**Troubleshooting Logic:**
```yaml
Issue Type → Diagnosis → Solution Path

Inconsistent outputs:
→ Consistency problem
→ Add: output-consistency + template-based-prompting + prefilling-responses

Poor reasoning quality:
→ Reasoning problem  
→ Add: chain-of-thought + xml-tags-structure + multishot-examples

Format violations:
→ Structure problem
→ Add: prefilling-responses + xml-tags-structure + output-consistency
```

## Working with the Schema

### Adding New Domains

1. **Create Domain Directory**: `contexts/{domain-name}/`
2. **Apply Universal Schema**: Use the same metadata structure
3. **Define Domain-Specific Types**: Create `technique_type` categories for the domain
4. **Create Context Modules**: Individual contexts following the schema
5. **Develop Selection Logic**: Adapt diagnostic questions and patterns for the domain
6. **Map Relationships**: Define dependencies, synergies, conflicts

### Schema Compliance for Context Creation

When creating contexts:
- **Follow Standards**: Use `docs/standards/context-metadata-schema.md` exactly
- **Rich Context Headers**: Write detailed semantic descriptions
- **Map Relationships**: Define how contexts connect (`works_well_with`, `requires_techniques`, `conflicts_with`)
- **Domain Consistency**: Use appropriate `technique_type` categories
- **Problem-Solution Clarity**: Clearly define what problems the context solves

### Selection Logic Development

When creating selection systems for new domains:
- **Diagnostic Questions**: Develop domain-specific classification questions
- **Selection Patterns**: Create common combination patterns for typical scenarios
- **Troubleshooting Logic**: Document systematic approaches to resolve issues
- **Relationship Logic**: Use metadata relationships for intelligent suggestions

### Example Domain Expansion

**React Domain** (hypothetical):
```yaml
# react-component-basics.md
domain: "react"
technique_type: "foundational"
works_well_with: ["props-management", "state-basics"]

# state-management-hooks.md  
domain: "react"
technique_type: "state"
requires_techniques: ["react-component-basics"]
conflicts_with: ["class-component-patterns"]

# Selection patterns for React:
Foundation-First: [react-component-basics, props-management]
State-First: [state-management-hooks, component-lifecycle]
Performance-First: [react-memo, virtualization, code-splitting]
```

## Quality Standards

### Current Validation
- Manual schema compliance checking
- Relationship consistency verification (no circular dependencies)
- Cross-reference validation (all referenced IDs exist)
- Selection logic testing with real scenarios

### Scope Limitations
**Intentionally Excluded:**
- Performance metrics and scoring systems
- Automated validation tools
- Complex quality assessments
- Token cost analysis
- Effectiveness rating systems

**Focus**: Simple, maintainable metadata with intelligent selection logic that works across domains

## Development Guidelines

### For Schema Development
- Keep metadata structure universal (works for any topic)
- Avoid domain-specific fields in core schema
- Maintain human readability and manual maintainability
- Enable intelligent selection without requiring complex automation

### For Domain Implementation
- Apply schema consistently within domain
- Create domain-appropriate `technique_type` categories
- Map relationships clearly and test combinations
- Follow established naming conventions
- Develop selection logic adapted to domain needs

### For Context Creation
- Write rich contextual headers with semantic descriptions
- Include concrete use cases and problems solved
- Map relationships to existing contexts accurately
- Follow the universal schema exactly
- Test context combinations for logical coherence

### For Selection Logic Development
- Create diagnostic questions that guide users effectively
- Develop pattern libraries with proven combinations
- Document troubleshooting approaches for common issues
- Use metadata relationships for intelligent suggestions
- Test selection logic with real-world scenarios

## Future Vision

### Schema Evolution
- Refinement based on multi-domain application
- Additional relationship types if patterns emerge
- Enhanced semantic description patterns
- Cross-domain relationship exploration

### Domain Expansion
- React development contexts with selection logic
- Data analysis contexts with domain-specific patterns
- Creative writing contexts with appropriate selection systems
- Any topic area that benefits from structured organization and intelligent selection

### Selection Intelligence Enhancement
- Cross-domain pattern recognition
- Advanced relationship mapping
- Improved diagnostic question systems
- Enhanced troubleshooting logic

## Key Files Reference

### Schema Definition
- `docs/standards/context-metadata-schema.md` - **CORE SCHEMA** (universal structure)
- `docs/standards/file-naming-conventions.md` - Naming standards
- `docs/architecture/functional-composition.md` - Context relationship patterns

### Implementation Examples
- `contexts/prompt-engineering/01-best-practice.md` - Basic schema application
- `contexts/prompt-engineering/06-chain-of-thought.md` - Rich metadata example
- `contexts/prompt-engineering/07-xml-tag-*.md` - Relationship mapping example

### Selection Logic Examples
- `contexts/prompt-engineering/00-context-selector.md` - Core selection logic and diagnostic framework
- `contexts/prompt-engineering/00-context-selector-patterns.md` - Common selection patterns and scenarios
- `contexts/prompt-engineering/00-context-selector-troubleshooting.md` - Issue resolution approaches

## Current Achievements Summary

### ✅ Universal Schema
- Metadata structure works across any domain
- Rich semantic descriptions enable intelligent discovery
- Relationship mapping supports logical selection
- Simple enough for manual maintenance

### ✅ Intelligent Selection System
- Diagnostic questions guide context choice
- Pattern libraries provide proven combinations
- Problem-solution matching connects needs to solutions
- Troubleshooting logic resolves common issues
- Dependency resolution ensures complete context sets

### ✅ Complete Reference Implementation
- 15+ prompt engineering contexts with full metadata
- Working selection logic with real-world scenarios
- Demonstrated relationship mapping and conflict resolution
- Proven cross-domain applicability of schema

### ✅ Clean, Focused Architecture
- Removed complex scoring and metrics
- Maintained intelligent selection logic
- Focused on schema definition and demonstration
- Ready for multi-domain expansion

Remember: This repository is about **defining universal standards** with **intelligent selection logic** and **demonstrating their application**, not building complex management systems. The schema should be simple, universal, and manually maintainable while enabling smart context discovery and combination.

## Claude's Interactions

### Interaction Memories
- Carefully studied repository purpose and core mission
- Committed to maintaining universal schema and intelligent selection principles
- Focused on adding value without unnecessary complexity
- Preserved existing structure and content