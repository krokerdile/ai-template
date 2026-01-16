# AI Agent Skills Template

A comprehensive template for organizing and managing agent skills/prompts for various AI coding assistants.

## Overview

This repository provides a structured way to organize, maintain, and share agent skills (prompts, instructions, and configurations) for different AI coding assistants including Claude Code, Codex, and Cursor.

## Directory Structure

```
.
├── claude-code/     # Skills for Claude Code (Anthropic)
├── codex/           # Skills for OpenAI Codex
├── cursor/          # Skills for Cursor IDE
├── custom/          # Your custom skills and experiments
├── templates/       # Templates for creating new skills
└── docs/            # Documentation and guides
```

## Quick Start

### 1. Choose Your AI Assistant

Navigate to the appropriate directory:
- **Claude Code**: `claude-code/`
- **Codex**: `codex/`
- **Cursor**: `cursor/`
- **Custom Skills**: `custom/`

### 2. Browse Available Skills

Each directory contains:
- README with skill descriptions
- Individual skill files
- Configuration examples

### 3. Use a Template

Copy a template from `templates/` to create your own skill:

```bash
cp templates/skill-template.md custom/my-new-skill.md
```

## Skill Categories

Skills are organized by:
- **Code Generation**: Generate boilerplate, functions, classes
- **Code Review**: Analyze and suggest improvements
- **Refactoring**: Restructure existing code
- **Testing**: Generate tests and test cases
- **Documentation**: Create docs, comments, README files
- **Debugging**: Help identify and fix issues
- **Architecture**: Design patterns and system architecture

## Contributing Your Skills

1. Create your skill in the `custom/` directory
2. Follow the template structure from `templates/`
3. Document your skill with clear examples
4. Test thoroughly before sharing

## Best Practices

- **Be Specific**: Clear, detailed prompts get better results
- **Provide Context**: Include relevant background information
- **Add Examples**: Show expected input/output
- **Iterate**: Refine skills based on results
- **Document**: Explain what the skill does and when to use it

## File Naming Convention

Use descriptive, kebab-case names:
- `generate-react-component.md`
- `review-python-code.md`
- `refactor-legacy-code.md`

## License

MIT License - Feel free to use and modify as needed.

## Resources

- [Claude Documentation](https://docs.anthropic.com/)
- [OpenAI Codex](https://openai.com/blog/openai-codex)
- [Cursor Documentation](https://cursor.sh/docs)