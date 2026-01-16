# Edit Code Inline

## Purpose

Modify existing code directly in place using Cursor's inline editing capability (Cmd+K).

## Category

- [ ] Code Generation
- [ ] Code Review
- [x] Refactoring
- [ ] Testing
- [ ] Documentation
- [ ] Debugging
- [ ] Architecture

## AI Assistant Compatibility

- [ ] Claude Code
- [ ] Codex
- [x] Cursor

## Prompt Template

```
[MODIFICATION_DESCRIPTION]

Keep:
- Existing code structure
- Variable naming conventions
- Comment style

Change:
- [SPECIFIC_CHANGE_1]
- [SPECIFIC_CHANGE_2]
```

## Example Usage

### Input (Highlight this code in Cursor and press Cmd+K)

```javascript
function getUserData(userId) {
  const user = database.users.find(u => u.id === userId);
  return user;
}
```

### Prompt

```
Add error handling and validation:
- Check if userId is valid (not null/undefined)
- Handle case when user is not found
- Add try-catch for database errors
- Return proper error messages
```

### Expected Output

```javascript
function getUserData(userId) {
  try {
    // Validate input
    if (!userId) {
      throw new Error('User ID is required');
    }

    const user = database.users.find(u => u.id === userId);
    
    if (!user) {
      throw new Error(`User with ID ${userId} not found`);
    }
    
    return user;
  } catch (error) {
    console.error('Error fetching user data:', error.message);
    throw error;
  }
}
```

## Tips

- Tip 1: Highlight the exact code section you want to modify for precise edits
- Tip 2: Be specific about what to keep vs. what to change
- Tip 3: Use Cursor's context awareness - it understands surrounding code
- Tip 4: For large changes, break into multiple smaller inline edits

## Variations

### Variation 1: Add Feature
"Add [FEATURE] to this function while keeping existing functionality"

### Variation 2: Refactor
"Refactor this code to use [PATTERN] instead of [CURRENT_APPROACH]"

### Variation 3: Performance
"Optimize this code for performance, specifically [BOTTLENECK]"

### Variation 4: Style
"Reformat to match [STYLE_GUIDE] conventions"

## Cursor-Specific Tips

- Use **Cmd+K** to open inline edit mode
- Use **@filename** to reference other files for context
- Use **Accept** (Tab) or **Reject** (Esc) for suggestions
- Chain multiple edits by accepting and immediately pressing Cmd+K again

## Common Use Cases

### Add Logging
```
Add console.log statements to track execution flow
```

### Add Types
```
Add TypeScript type annotations to parameters and return type
```

### Extract Function
```
Extract the validation logic into a separate validateInput() function
```

### Handle Edge Cases
```
Add handling for empty arrays, null values, and undefined
```

### Modernize Syntax
```
Convert to async/await instead of .then() promises
```

## Related Skills

- `fix-error.md` - Fix compilation or runtime errors
- `refactor-selection.md` - Larger refactoring operations
- `add-tests.md` - Generate tests for modified code

## Metadata

- **Created**: 2026-01-16
- **Last Updated**: 2026-01-16
- **Author**: AI Template
- **Tags**: #cursor #inline #edit #refactor #quick
