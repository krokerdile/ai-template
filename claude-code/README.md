# Claude Code Skills

Skills and prompts specifically designed for Claude Code (Anthropic's AI assistant).

## About Claude Code

Claude Code is Anthropic's AI coding assistant that excels at:
- Understanding complex codebases
- Writing well-structured, maintainable code
- Following instructions precisely
- Providing detailed explanations
- Multi-step reasoning and planning

## Available Skills

### Code Generation
- `generate-api-endpoint.md` - Create RESTful API endpoints
- `generate-test-suite.md` - Generate comprehensive test cases
- `generate-component.md` - Create React/Vue/Angular components

### Code Review
- `security-review.md` - Review code for security vulnerabilities
- `performance-review.md` - Analyze code performance
- `best-practices-review.md` - Check adherence to best practices

### Refactoring
- `extract-function.md` - Extract repeated code into functions
- `modernize-code.md` - Update legacy code to modern standards
- `improve-readability.md` - Enhance code clarity and structure

### Documentation
- `generate-docstrings.md` - Create function/class documentation
- `generate-readme.md` - Create comprehensive README files
- `generate-api-docs.md` - Document API endpoints

## Usage Tips

1. **Be Specific**: Claude works best with detailed, specific instructions
2. **Provide Context**: Share relevant code context and requirements
3. **Iterate**: Use follow-up prompts to refine results
4. **Request Explanations**: Ask Claude to explain its reasoning

## Example Usage

```
Use the skill: generate-test-suite.md
Context: Python Flask API with user authentication
Requirements: Unit tests with pytest, >80% coverage
```

## Contributing

Add your own Claude-specific skills following the template in `/templates/`.
