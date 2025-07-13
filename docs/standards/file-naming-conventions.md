# File Naming Conventions

This document defines the standardized naming conventions for Context Hub files.

## Context Files

### Context Modules
```
Format: {id}.md
Examples:
- chain-of-thought.md
- xml-tags-structure.md
- prompt-engineering-best-practices.md
```

**Rules:**
- Use kebab-case (lowercase with hyphens)
- Name should match the `id` field in frontmatter
- Descriptive but concise
- No version numbers or complexity indicators in filename

### Selector Files
```
Format: 00-{purpose}.md
Examples:
- 00-context-selector.md
- 00-context-selector-patterns.md
- 00-context-selector-recovery.md
```

**Rules:**
- Prefix with `00-` to indicate meta-files
- Use kebab-case for the purpose description
- Should be self-explanatory about their function

## Directory Structure

### Domain Directories
```
Format: {domain-name}/
Examples:
- prompt-engineering/
- code-generation/
- data-analysis/
```

**Rules:**
- Use kebab-case
- Single word or hyphenated compound
- Reflect the primary subject domain

### Standard Directories
```
docs/
├── standards/          # Cross-domain standards
├── architecture/       # System design docs
└── contributing/       # Contribution guidelines
```

## ID Conventions

### Context IDs
- Must match filename (without .md extension)
- Use kebab-case
- Be unique across the entire repository
- Be descriptive and self-explanatory

### Examples:
```yaml
# Good IDs
id: "chain-of-thought"
id: "xml-tags-structure"
id: "prompt-engineering-best-practices"

# Avoid
id: "cot"                    # Too abbreviated
id: "chainOfThought"         # Wrong case
id: "01-chain-of-thought"    # No numbers
```

## Migration Notes

When renaming files:
1. Update the `id` field in frontmatter to match new filename
2. Update all references in selector files
3. Update any cross-references in other contexts
4. Maintain backward compatibility notes if needed