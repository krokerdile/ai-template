# Documentation Guide

This directory contains guides and references for working with AI coding assistants.

## Contents

- [Getting Started](#getting-started)
- [Choosing the Right Assistant](#choosing-the-right-assistant)
- [Writing Effective Prompts](#writing-effective-prompts)
- [Organizing Your Skills](#organizing-your-skills)
- [Best Practices](#best-practices)
- [Troubleshooting](#troubleshooting)

## Getting Started

### What are Agent Skills?

Agent skills are reusable prompts, instructions, and workflows that help you get consistent, high-quality results from AI coding assistants. Think of them as templates or recipes for common coding tasks.

### Why Organize Skills?

- **Consistency**: Get predictable results for common tasks
- **Efficiency**: Avoid rewriting prompts from scratch
- **Sharing**: Help teammates leverage proven approaches
- **Learning**: Build a knowledge base of what works
- **Evolution**: Continuously improve your prompts

### Quick Setup

1. Clone or fork this repository
2. Browse the skills in each assistant directory
3. Try some example skills with your preferred AI assistant
4. Create your own skills in the `custom/` directory
5. Share skills that work well with your team

## Choosing the Right Assistant

### Claude Code (Anthropic)

**Best for:**
- Complex, multi-step tasks
- Detailed code reviews
- Understanding large codebases
- Writing comprehensive documentation
- Security analysis
- Refactoring legacy code

**Strengths:**
- Excellent at following detailed instructions
- Strong reasoning and planning capabilities
- Good at explaining its decisions
- Handles context well

**When to use:**
- New features requiring multiple files
- Architecture decisions
- Thorough code reviews
- Learning about unfamiliar code

### Codex (OpenAI)

**Best for:**
- Quick code completions
- Generating boilerplate
- Translating between languages
- Simple function generation
- Code snippets

**Strengths:**
- Fast responses
- Good at pattern matching
- Wide language support
- Concise implementations

**When to use:**
- Rapid prototyping
- Autocomplete in IDE
- Quick utility functions
- Standard implementations

### Cursor IDE

**Best for:**
- Inline code editing
- Codebase-aware suggestions
- Interactive development
- Multi-file changes
- Context-rich assistance

**Strengths:**
- Deep IDE integration
- Understands your entire project
- Fast iteration with Cmd+K
- Natural conversation flow
- File references with @mentions

**When to use:**
- Daily development work
- Exploring unfamiliar codebases
- Making targeted edits
- Asking questions about code
- Iterative refinement

## Writing Effective Prompts

### The Prompt Structure

A good prompt has these components:

1. **Context**: What's the situation?
2. **Goal**: What do you want to achieve?
3. **Requirements**: What must be included?
4. **Constraints**: What to avoid or limitations?
5. **Format**: How should the output look?
6. **Examples**: Show what you expect

### Example of a Good Prompt

```markdown
Context: I'm building a REST API with Express.js for a blog application.

Goal: Create an endpoint to publish a blog post.

Requirements:
- Validate post title (required, max 200 chars)
- Validate post content (required, max 10000 chars)
- Check user authentication (JWT)
- Verify user owns the post
- Update publish date timestamp
- Return 404 if post not found
- Return 403 if not authorized

Constraints:
- Use existing auth middleware
- Follow existing error handling patterns
- No additional dependencies

Format: Complete endpoint with middleware, validation, and error handling

Example:
Similar to the existing /api/posts/create endpoint but for publishing drafts
```

### Example of a Poor Prompt

```markdown
Make a publish endpoint
```

**Why it's poor:**
- No context about the project
- Unclear requirements
- No specifications
- Missing constraints
- No expected format

### Prompt Writing Tips

1. **Be Specific**: "Add input validation" → "Add email validation using regex, check for max length 254 chars"

2. **Provide Context**: Include relevant code, frameworks, patterns already used

3. **Show Examples**: Reference existing code or show expected output

4. **State Constraints**: Mention what not to do, dependencies to avoid

5. **Request Explanations**: Ask "explain your approach" for learning

6. **Iterate**: Refine prompts based on results

7. **Use Clear Language**: Avoid ambiguity, define technical terms

## Organizing Your Skills

### By Project Phase

```
├── planning/
│   ├── architecture-design.md
│   └── tech-stack-selection.md
├── development/
│   ├── feature-implementation.md
│   └── bug-fixing.md
└── maintenance/
    ├── refactoring.md
    └── optimization.md
```

### By Task Type

```
├── generation/
├── review/
├── documentation/
├── testing/
└── debugging/
```

### By Language/Framework

```
├── python/
├── javascript/
├── rust/
└── go/
```

### By Domain

```
├── web-development/
├── data-science/
├── devops/
└── mobile/
```

Choose what works for your workflow!

## Best Practices

### 1. Version Your Skills

Track changes to understand what works:
```markdown
## Changelog
- 2026-01-16: Added error handling examples
- 2026-01-10: Initial version
```

### 2. Tag Your Skills

Use tags for easy discovery:
```markdown
Tags: #api #testing #python #backend
```

### 3. Document Results

Note what works and what doesn't:
```markdown
## Notes
- Works best with Claude Code
- May need iteration for complex edge cases
- Good starting point, always review generated code
```

### 4. Include Anti-Patterns

Show what to avoid:
```markdown
## Anti-Patterns
- Don't use this for real-time data processing
- Not suitable for code that needs optimization
```

### 5. Maintain Examples

Keep examples up-to-date with current frameworks and practices.

### 6. Test Your Skills

Try skills with different:
- AI assistants
- Code contexts
- Edge cases
- Team members

### 7. Share and Collaborate

- Get feedback from teammates
- Contribute successful skills to shared repos
- Learn from others' approaches

## Troubleshooting

### Problem: Inconsistent Results

**Solutions:**
- Add more specific requirements
- Include more examples
- Specify exact format/structure
- Try different assistant (Claude vs Codex)

### Problem: Code Doesn't Work

**Solutions:**
- Verify you provided correct context
- Check for outdated library versions in prompt
- Review and test generated code
- Iterate with error messages

### Problem: Output Too Generic

**Solutions:**
- Add project-specific context
- Include existing code patterns
- Reference specific files/functions
- Be more explicit about style

### Problem: Takes Too Long

**Solutions:**
- Break into smaller tasks
- Use faster assistant (Codex) for simple tasks
- Create more focused prompts
- Use templates for common patterns

### Problem: Misunderstands Requirements

**Solutions:**
- Simplify language
- Add examples of expected output
- Break down complex requirements
- Provide visual diagrams if applicable

## Additional Resources

### Learning

- Experiment with different prompt styles
- Study successful prompts from others
- Keep a journal of what works
- Join AI coding communities

### Tools

- Use version control for your skills
- Create snippets in your IDE
- Build prompt libraries
- Automate common workflows

### Community

- Share your best skills
- Learn from others
- Contribute to open source skill repos
- Give feedback on skills you try

## Getting Help

- Check existing skills in this repo
- Search for similar prompts online
- Ask in AI coding communities
- Experiment and iterate

Remember: Prompt engineering is a skill that improves with practice!
