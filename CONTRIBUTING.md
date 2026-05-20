# Contributing to awesome-promptcraft-prompts

Thanks for helping improve this prompt engineering library.

## What We Accept

We prioritize contributions that are practical, testable, and reusable.

- new advanced prompts with measurable use cases
- improvements to existing prompts (clarity, constraints, better output schema)
- model-specific tuning notes (ChatGPT, Claude, Gemini)
- prompt benchmarking examples with before/after output quality
- typo fixes and structural improvements

## Prompt Quality Standard

Every prompt must include all six sections:

1. Role
2. Task
3. Context
4. Style
5. Constraints
6. Output Format

Submissions missing one of these sections will be asked to revise.

## Content Rules

- Use realistic scenarios and production-level detail.
- Avoid generic placeholders and vague instructions.
- Include usage instructions and expected AI output characteristics.
- Keep prompts model-agnostic unless file is explicitly model-specific.
- Use clear Markdown headings and readable formatting.

## File Naming Convention

Use lowercase kebab-case:

- good: `saas-architecture-prompts.md`
- good: `debugging-systems-prompts.md`
- avoid: `MyPrompts.md`, `new_file_final_v2.md`

## Pull Request Process

1. Fork the repository.
2. Create a branch: `feat/your-topic` or `fix/your-topic`.
3. Add or update prompt files in the correct category folder.
4. Verify your prompt includes all required sections.
5. Open a pull request with:
   - what changed
   - why it matters
   - sample output improvement summary

## Recommended PR Template

```md
## Summary

## Prompt(s) Added/Updated

## Before vs After Improvement

## Model(s) Tested
- [ ] ChatGPT
- [ ] Claude
- [ ] Gemini

## Checklist
- [ ] Includes Role, Task, Context, Style, Constraints, Output Format
- [ ] Includes usage instructions
- [ ] Includes expected output notes
- [ ] Markdown formatting checked
```

## Community Principles

- Be respectful and constructive.
- Prioritize clarity over complexity.
- Share evidence when proposing changes.

## Need Help?

Open an issue with label: `question` or `prompt-improvement`.
