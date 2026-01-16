# Contributing to AI Template

Thank you for your interest in contributing! This guide will help you add your skills to the repository.

## How to Contribute

### 1. Adding a New Skill

1. Choose the appropriate directory:
   - `claude-code/` for Claude-specific skills
   - `codex/` for Codex-specific skills
   - `cursor/` for Cursor-specific skills
   - `custom/` for your personal experiments

2. Copy the template:
   ```bash
   cp templates/skill-template.md [directory]/your-skill-name.md
   ```

3. Fill in all sections:
   - Purpose (clear and concise)
   - Category (check applicable boxes)
   - AI Assistant Compatibility
   - Prompt Template (with placeholders)
   - Example Usage (concrete examples)
   - Tips (practical advice)
   - Metadata (dates and tags)

4. Test your skill:
   - Try it with the intended AI assistant
   - Verify it produces expected results
   - Test edge cases
   - Get feedback from others if possible

### 2. Improving Existing Skills

1. Fork the repository
2. Make your improvements:
   - Fix errors or outdated information
   - Add better examples
   - Include additional tips
   - Update for newer frameworks/libraries
3. Update the "Last Updated" date in metadata
4. Submit a pull request with description of changes

### 3. Adding Documentation

- Add guides to `docs/` directory
- Create tutorials for specific workflows
- Share case studies of successful skill usage
- Document best practices you've discovered

## Skill Quality Guidelines

### Required Elements

Every skill should have:
- [ ] Clear purpose statement
- [ ] Category selection
- [ ] Compatible AI assistants marked
- [ ] Complete prompt template
- [ ] At least one concrete example
- [ ] Practical tips based on real use
- [ ] Metadata with tags

### Good Skills Are:

1. **Specific**: Clearly defined scope and purpose
2. **Tested**: Verified to work as described
3. **Documented**: Well-explained with examples
4. **Practical**: Solves real problems
5. **Reusable**: Works in multiple contexts
6. **Updated**: Uses current best practices

### Avoid:

- Overly broad or vague prompts
- Untested or theoretical skills
- Missing examples or context
- Outdated library/framework versions
- Skills without clear use cases

## Naming Conventions

### File Names

Use kebab-case with descriptive names:
- ✅ `generate-react-component.md`
- ✅ `review-security-vulnerabilities.md`
- ❌ `skill1.md`
- ❌ `GenerateComponent.md`

### Tags

Use lowercase with hyphens:
- ✅ `#code-review`
- ✅ `#api-testing`
- ❌ `#Code_Review`
- ❌ `#APITesting`

## Pull Request Process

1. **Fork** the repository
2. **Create a branch** for your contribution:
   ```bash
   git checkout -b add-skill-name
   ```
3. **Add your skill** following the guidelines
4. **Test** your skill thoroughly
5. **Commit** with clear message:
   ```bash
   git commit -m "Add [skill-name] skill for [assistant]"
   ```
6. **Push** to your fork:
   ```bash
   git push origin add-skill-name
   ```
7. **Create Pull Request** with:
   - Clear description of the skill
   - What problem it solves
   - Example of it working
   - Any special notes or requirements

## Code of Conduct

- Be respectful and constructive
- Focus on helping others succeed
- Share knowledge generously
- Give credit to original authors
- Follow licensing requirements

## Questions?

- Open an issue for discussion
- Check existing documentation
- Ask in pull request comments
- Reach out to maintainers

## License

By contributing, you agree that your contributions will be licensed under the same license as this project (MIT License).

Thank you for making this resource better for everyone! 🎉
