# Codex Skills

Skills and prompts specifically designed for OpenAI Codex.

## About Codex

Codex is OpenAI's AI system that translates natural language to code. It powers:
- GitHub Copilot
- OpenAI API code completions
- Various code generation tools

Codex excels at:
- Quick code completions
- Generating boilerplate code
- Translating between languages
- Writing concise implementations

## Available Skills

### Code Generation
- `generate-function.md` - Create standalone functions
- `generate-class.md` - Create class definitions
- `generate-boilerplate.md` - Generate project scaffolding

### Code Translation
- `translate-language.md` - Convert code between languages
- `modernize-syntax.md` - Update to newer language versions

### Quick Tasks
- `add-error-handling.md` - Add try-catch blocks and validation
- `add-logging.md` - Insert logging statements
- `add-types.md` - Add type annotations

## Usage Tips

1. **Keep Prompts Concise**: Codex works well with shorter, focused prompts
2. **Provide Examples**: Show input/output examples when possible
3. **Use Comments**: In-code comments guide Codex effectively
4. **Specify Language**: Always specify the programming language

## Example Usage

```
Use the skill: generate-function.md
Language: Python
Task: Create a function to validate email addresses using regex
```

## Contributing

Add your own Codex-specific skills following the template in `/templates/`.
