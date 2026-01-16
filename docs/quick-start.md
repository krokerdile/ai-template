# Quick Start Guide

Get up and running with AI agent skills in 5 minutes!

## Step 1: Choose Your First Skill (1 min)

Pick a skill based on what you're working on right now:

**Writing new code?**
→ Try `claude-code/generate-api-endpoint.md` or `codex/generate-function.md`

**Reviewing code?**
→ Try `claude-code/security-review.md`

**Using Cursor IDE?**
→ Try `cursor/edit-in-place.md` or `cursor/explain-codebase.md`

**Something else?**
→ Browse the READMEs in each directory

## Step 2: Open the Skill File (30 seconds)

```bash
# Example: Open a skill file
cat claude-code/generate-api-endpoint.md
```

Look for the "Prompt Template" section - that's what you'll use.

## Step 3: Customize the Prompt (2 min)

Replace the placeholders with your specifics:

**Before:**
```
Resource: [RESOURCE_NAME]
Method: [GET/POST/PUT/DELETE]
```

**After:**
```
Resource: Product
Method: POST
```

## Step 4: Use with Your AI Assistant (1 min)

### For Claude Code
Copy your customized prompt and paste it into your Claude conversation.

### For Codex/GitHub Copilot
Use as a comment in your code editor:
```javascript
// Create a POST endpoint for Product resource
// Include validation for name (required, max 100 chars)
// Include validation for price (required, positive number)
```

### For Cursor
- Press `Cmd+K` (Mac) or `Ctrl+K` (Windows/Linux)
- Paste your customized prompt
- Or press `Cmd+L` for chat mode

## Step 5: Review and Iterate (30 seconds)

- Check if the output matches your needs
- If not perfect, refine your prompt and try again
- Save successful prompts to your `custom/` directory

## Next Steps

### Learn More
- Read `docs/README.md` for comprehensive guide
- Understand prompt writing in "Writing Effective Prompts" section
- Explore all available skills in each directory

### Create Your Own
1. Copy `templates/skill-template.md`
2. Customize for your needs
3. Save in `custom/` directory
4. Test and iterate

### Share With Team
- Add your best skills to version control
- Create a shared repository
- Document team-specific patterns
- Review and improve together

## Common Mistakes to Avoid

❌ **Using prompts without customization**
✅ Replace ALL placeholders with your specific details

❌ **Being too vague**
✅ Provide specific requirements and examples

❌ **Expecting perfection on first try**
✅ Iterate and refine based on results

❌ **Forgetting to test generated code**
✅ Always review and test AI-generated code

## Quick Tips

💡 **More context = Better results**
Include framework, language version, coding style

💡 **Show examples**
Reference existing code or show expected output

💡 **Break down complex tasks**
Use multiple smaller skills instead of one giant prompt

💡 **Keep what works**
Save successful prompts for future use

## Getting Help

- Check `docs/README.md` for detailed documentation
- Look at example skills for inspiration
- Experiment and learn what works for your use case
- Read `CONTRIBUTING.md` to share your skills

## Examples of Good First Skills

### Generate a Function
**When:** You need a specific function but don't want to write it from scratch
**Use:** `codex/generate-function.md`
**Time saved:** 5-10 minutes per function

### Review Code for Security
**When:** Before committing sensitive code
**Use:** `claude-code/security-review.md`
**Time saved:** 15-30 minutes of manual review

### Explain Unfamiliar Code
**When:** Joining new project or exploring codebase
**Use:** `cursor/explain-codebase.md`
**Time saved:** Hours of code reading

### Edit Code Inline
**When:** Making small improvements to existing code
**Use:** `cursor/edit-in-place.md`
**Time saved:** 2-5 minutes per edit

## Success Story Example

**Before:** Writing an API endpoint from scratch
- Time: 20-30 minutes
- Risk: Forgetting validation, error handling, logging

**After:** Using `generate-api-endpoint.md`
- Time: 5 minutes (customize prompt + review output)
- Result: Complete endpoint with validation, errors, logging
- Bonus: Consistent with best practices

---

**You're ready!** Pick a skill and try it now. Remember: iteration and experimentation are key to mastering AI-assisted coding.
