# Templates

This directory contains templates for creating new agent skills.

## Available Templates

### skill-template.md
The main template for creating any type of agent skill. Includes:
- Purpose and category
- Prompt template structure
- Example usage section
- Tips and variations
- Metadata tracking

## How to Use Templates

1. **Copy the template**:
   ```bash
   cp templates/skill-template.md [destination]/my-skill-name.md
   ```

2. **Fill in the sections**:
   - Write a clear purpose statement
   - Select the appropriate category
   - Craft your prompt template
   - Add concrete examples
   - Document tips and variations

3. **Test your skill**:
   - Try it with different AI assistants
   - Iterate based on results
   - Document what works best

4. **Maintain and update**:
   - Update the "Last Updated" date when you modify it
   - Add new variations as you discover them
   - Refine based on usage experience

## Template Sections Explained

### Purpose
A concise 1-2 sentence description of what the skill accomplishes.

### Category
Select the primary category this skill belongs to. This helps with organization and discovery.

### AI Assistant Compatibility
Mark which assistants this skill works well with. Some prompts work better with specific models.

### Prompt Template
The actual prompt structure. Use placeholders like [PLACEHOLDER] for variable parts.

### Example Usage
Show concrete before/after examples. This is the most important section for others to understand your skill.

### Tips
Practical advice from your experience using this skill.

### Variations
Different ways to use the same basic skill for different purposes.

### Related Skills
Link to complementary or alternative skills.

### Metadata
Track when the skill was created and updated, plus relevant tags for searching.

## Best Practices

1. **Be Specific**: Vague prompts get vague results
2. **Show Examples**: Real examples are worth a thousand words
3. **Document Edge Cases**: Note what works and what doesn't
4. **Keep It Updated**: Revisit and refine skills regularly
5. **Use Clear Language**: Write for your future self and others

## Creating Different Types of Skills

### Quick Command Skills
For simple, one-shot commands (e.g., "Add logging to this function")

### Multi-Step Skills
For complex workflows (e.g., "Generate a feature with tests and docs")

### Review/Analysis Skills
For examining existing code (e.g., "Review for security issues")

### Refactoring Skills
For transforming code structure (e.g., "Extract reusable components")

## Contributing Templates

If you create a new template type that could be useful to others, consider adding it to this directory with clear documentation.
