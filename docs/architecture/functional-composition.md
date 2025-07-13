# Context Relationship Patterns

This document explains how contexts relate to each other through the metadata schema and demonstrates logical composition patterns.

## Core Principles

### 1. Single Responsibility
Each context file focuses on one technique or pattern:
- **One technique per file**: Each context addresses a specific prompting technique
- **Atomic functionality**: Contexts can be used independently
- **Clear boundaries**: No overlap in technique coverage

### 2. Composability
Contexts combine like functions:
- **Explicit dependencies**: `requires_techniques` field specifies prerequisites
- **Synergy mapping**: `works_well_with` field identifies complementary techniques
- **Conflict detection**: `conflicts_with` field prevents incompatible combinations

### 3. Immutability
Context definitions remain stable:
- **Consistent behavior**: Same inputs produce same outputs
- **No side effects**: Applying a context doesn't change other contexts
- **Predictable combinations**: Composition results are deterministic

## Composition Patterns

### Sequential Composition
```yaml
# Foundation → Enhancement → Specialization
[prompt-engineering-best-practices] → [clear-direct-prompting] → [multishot-examples]
```

### Parallel Composition
```yaml
# Multiple independent enhancements
[xml-tags-structure] + [prefilling-responses] + [output-consistency]
```

### Conditional Composition
```yaml
# Based on requirements
IF accuracy_critical THEN
    [reduce-hallucinations] + [chain-of-thought]
ELIF creativity_needed THEN
    [system-prompts-roles] + [character-consistency]
```

## Relationship Types

### Dependencies (`requires_techniques`)
Hard requirements that must be included:
```yaml
chain-of-thought:
  requires_techniques: ["prompt-engineering-best-practices"]
```

### Synergies (`works_well_with`)
Techniques that enhance each other:
```yaml
chain-of-thought:
  works_well_with: ["xml-tags-structure", "multishot-examples"]
```

### Conflicts (`conflicts_with`)
Incompatible techniques:
```yaml
rapid-response-optimization:
  conflicts_with: ["extended-thinking", "chain-of-thought"]
```

## Composition Rules

### 1. Dependency Resolution
- Always include required techniques automatically
- Resolve dependencies recursively
- Check for circular dependencies

### 2. Conflict Prevention
- Validate compatibility before combination
- Provide alternative suggestions for conflicts
- Ensure mutual conflict symmetry

### 3. Optimization
- Remove redundant techniques
- Prefer foundational techniques as base
- Consider complexity progression

## Implementation Example

```python
def compose_contexts(primary_contexts, requirements):
    """Functional composition of contexts"""
    
    # 1. Resolve dependencies
    all_contexts = resolve_dependencies(primary_contexts)
    
    # 2. Check for conflicts
    validate_compatibility(all_contexts)
    
    # 3. Optimize combination
    optimized = optimize_combination(all_contexts, requirements)
    
    return optimized

def resolve_dependencies(contexts):
    """Recursively resolve all dependencies"""
    resolved = set(contexts)
    
    for context in contexts:
        metadata = get_metadata(context)
        dependencies = metadata.get('requires_techniques', [])
        resolved.update(resolve_dependencies(dependencies))
    
    return list(resolved)
```

This functional approach ensures predictable, maintainable context composition that scales across domains.