# Cursor Skills

Skills and prompts specifically designed for Cursor IDE.

## About Cursor

Cursor is an AI-first code editor built on VSCode that integrates AI assistance directly into the development workflow.

Features:
- Natural language to code generation
- Inline code editing and suggestions
- Codebase-aware AI assistance
- Chat interface for coding questions
- Multi-file code understanding

## Available Skills

### Editor Commands
- `edit-in-place.md` - Modify existing code inline
- `generate-with-context.md` - Generate code using surrounding context
- `refactor-selection.md` - Refactor highlighted code

### Codebase Operations
- `explain-codebase.md` - Get high-level codebase explanations
- `find-similar-code.md` - Locate similar patterns in codebase
- `trace-dependencies.md` - Understand dependency relationships

### Productivity
- `fix-error.md` - Automatically fix compilation/runtime errors
- `implement-todo.md` - Implement TODO comments
- `add-tests.md` - Generate tests for selected functions

## Usage Tips

1. **Use Codebase Context**: Cursor understands your entire project
2. **Highlight Code**: Select specific code sections for focused help
3. **Use Chat Mode**: Ask questions about your codebase
4. **Iterate Inline**: Make quick edits directly in the editor

## Example Usage

```
Use the skill: edit-in-place.md
Selection: Function calculateTotal()
Task: Add input validation and error handling
```

## Cursor-Specific Features

- **Cmd+K**: Generate/edit code inline
- **Cmd+L**: Open AI chat
- **@ mentions**: Reference specific files or symbols
- **Multi-file edits**: Make changes across multiple files

## Contributing

Add your own Cursor-specific skills following the template in `/templates/`.
