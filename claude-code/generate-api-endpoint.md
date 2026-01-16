# Generate API Endpoint

## Purpose

Generate a complete RESTful API endpoint with request validation, error handling, and proper HTTP status codes.

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
Generate a RESTful API endpoint with the following specifications:

Resource: [RESOURCE_NAME]
Method: [GET/POST/PUT/DELETE/PATCH]
Path: [/api/path]
Framework: [Express/Flask/FastAPI/Spring/etc.]

Request Body/Parameters:
- [field1]: [type] - [description]
- [field2]: [type] - [description]

Response:
- Success: [status code] - [response structure]
- Errors: [error cases and status codes]

Requirements:
- Input validation
- Error handling with appropriate status codes
- Proper logging
- [Any other specific requirements]
```

## Example Usage

### Input

```
Resource: User
Method: POST
Path: /api/users
Framework: Express.js (Node.js)

Request Body:
- email: string - User's email address
- name: string - User's full name
- age: number - User's age (must be 18+)

Response:
- Success: 201 - Returns created user object
- Errors: 400 for validation errors, 409 for duplicate email

Requirements:
- Email validation
- Age must be 18 or older
- Check for duplicate emails
- Return proper error messages
```

### Expected Output

```javascript
const express = require('express');
const router = express.Router();

// POST /api/users - Create a new user
router.post('/users', async (req, res) => {
  try {
    const { email, name, age } = req.body;

    // Input validation
    if (!email || !name || !age) {
      return res.status(400).json({
        error: 'Missing required fields',
        required: ['email', 'name', 'age']
      });
    }

    // Email validation
    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    if (!emailRegex.test(email)) {
      return res.status(400).json({
        error: 'Invalid email format'
      });
    }

    // Age validation
    if (typeof age !== 'number' || age < 18) {
      return res.status(400).json({
        error: 'Age must be 18 or older'
      });
    }

    // Check for duplicate email
    const existingUser = await User.findOne({ email });
    if (existingUser) {
      return res.status(409).json({
        error: 'User with this email already exists'
      });
    }

    // Create user
    const user = new User({ email, name, age });
    await user.save();

    console.log(`User created: ${user.id}`);

    return res.status(201).json({
      message: 'User created successfully',
      user: {
        id: user.id,
        email: user.email,
        name: user.name,
        age: user.age
      }
    });

  } catch (error) {
    console.error('Error creating user:', error);
    return res.status(500).json({
      error: 'Internal server error'
    });
  }
});

module.exports = router;
```

## Tips

- Tip 1: Always specify the framework and language version for consistent results
- Tip 2: List all validation rules explicitly to ensure they're implemented
- Tip 3: Include example error cases to get proper error handling code
- Tip 4: Request logging statements for production-ready code

## Variations

### Variation 1: With Authentication
Add "Requires: JWT authentication" to include auth middleware in the generated code.

### Variation 2: With Database Transaction
Add "Use database transaction" for endpoints that need atomicity.

### Variation 3: With Pagination
For GET endpoints, add "Include pagination (limit, offset)" to the requirements.

## Related Skills

- `generate-test-suite.md` - Generate tests for the API endpoint
- `security-review.md` - Review the generated code for security issues
- `generate-api-docs.md` - Create documentation for the endpoint

## Metadata

- **Created**: 2026-01-16
- **Last Updated**: 2026-01-16
- **Author**: AI Template
- **Tags**: #api #backend #rest #endpoint #validation
