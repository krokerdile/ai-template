# Generate Function

## Purpose

Quickly generate a standalone function with proper documentation, type hints, and error handling.

## Category

- [x] Code Generation
- [ ] Code Review
- [ ] Refactoring
- [ ] Testing
- [ ] Documentation
- [ ] Debugging
- [ ] Architecture

## AI Assistant Compatibility

- [x] Claude Code
- [x] Codex
- [x] Cursor

## Prompt Template

```
Create a function in [LANGUAGE] that [DESCRIPTION].

Function name: [FUNCTION_NAME]
Parameters: [PARAM_LIST]
Returns: [RETURN_TYPE]

Requirements:
- [REQUIREMENT_1]
- [REQUIREMENT_2]

Include:
- Type hints/annotations
- Docstring/comments
- Error handling
- Example usage
```

## Example Usage

### Input

```
Create a function in Python that validates and parses email addresses.

Function name: parse_email
Parameters: email (string)
Returns: dict with 'username' and 'domain' keys, or None if invalid

Requirements:
- Validate email format using regex
- Extract username and domain parts
- Handle edge cases (empty string, None, invalid format)
- Raise ValueError for invalid emails

Include:
- Type hints
- Docstring
- Example usage
```

### Expected Output

```python
import re
from typing import Optional, Dict

def parse_email(email: Optional[str]) -> Dict[str, str]:
    """
    Validate and parse an email address into username and domain components.
    
    Args:
        email: The email address to parse. Can be None or empty string.
        
    Returns:
        A dictionary with 'username' and 'domain' keys if email is valid.
        
    Raises:
        ValueError: If the email format is invalid.
        
    Examples:
        >>> parse_email("user@example.com")
        {'username': 'user', 'domain': 'example.com'}
        
        >>> parse_email("invalid-email")
        Traceback (most recent call last):
        ...
        ValueError: Invalid email format: invalid-email
    """
    # Handle None or empty string
    if not email:
        raise ValueError("Email cannot be empty or None")
    
    # Email validation regex
    email_pattern = r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'
    
    if not re.match(email_pattern, email):
        raise ValueError(f"Invalid email format: {email}")
    
    # Split email into username and domain
    username, domain = email.split('@', 1)
    
    return {
        'username': username,
        'domain': domain
    }


# Example usage
if __name__ == "__main__":
    # Valid email
    result = parse_email("john.doe@example.com")
    print(result)  # {'username': 'john.doe', 'domain': 'example.com'}
    
    # Invalid email
    try:
        parse_email("not-an-email")
    except ValueError as e:
        print(f"Error: {e}")
```

## Tips

- Tip 1: Specify the language version for syntax compatibility (e.g., "Python 3.10+")
- Tip 2: Include edge cases in requirements for robust implementations
- Tip 3: Request example usage to get working demonstration code
- Tip 4: Be specific about error handling (exceptions vs return values)

## Variations

### Variation 1: Quick Snippet
Omit documentation for rapid prototyping: "Create function without docstrings"

### Variation 2: Test-Driven
Add "Also generate unit tests" to get function + tests together

### Variation 3: Performance-Focused
Add "Optimize for performance with O(n) complexity" for efficiency requirements

## Related Skills

- `add-error-handling.md` - Enhance existing functions with error handling
- `add-types.md` - Add type annotations to untyped functions
- `generate-test-suite.md` - Create tests for the generated function

## Metadata

- **Created**: 2026-01-16
- **Last Updated**: 2026-01-16
- **Author**: AI Template
- **Tags**: #codex #function #quick #generation #boilerplate
