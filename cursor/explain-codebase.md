# Explain Codebase

## Purpose

Get high-level understanding of your codebase structure, architecture, and key components using Cursor's codebase awareness.

## Category

- [ ] Code Generation
- [ ] Code Review
- [ ] Refactoring
- [ ] Testing
- [x] Documentation
- [ ] Debugging
- [x] Architecture

## AI Assistant Compatibility

- [ ] Claude Code
- [ ] Codex
- [x] Cursor

## Prompt Template

```
Explain [ASPECT] of this codebase:

Focus on:
- [FOCUS_AREA_1]
- [FOCUS_AREA_2]

Level of detail: [High-level/Detailed/Summary]

Format: [Bullet points/Paragraphs/Diagram]
```

## Example Usage

### Prompt in Cursor Chat (Cmd+L)

```
Explain the authentication system in this codebase:

Focus on:
- How users log in and get tokens
- Where authentication is validated
- How permissions are checked
- Key files and functions involved

Level of detail: Detailed
Format: Bullet points with code references
```

### Expected Output

```markdown
# Authentication System Overview

## Login Flow
- **Entry point**: `src/auth/login.ts` - `loginUser()` function
- Users submit credentials to `/api/auth/login` endpoint
- Credentials validated against database in `src/models/User.ts`
- On success, JWT token generated using `jsonwebtoken` library
- Token includes: user ID, role, expiration (24h)
- Token returned to client and stored in localStorage

## Token Validation
- **Middleware**: `src/middleware/auth.ts` - `authenticateToken()`
- Runs on all protected routes (marked with `requireAuth`)
- Extracts token from `Authorization: Bearer <token>` header
- Verifies token signature and expiration
- Attaches decoded user info to `req.user`
- Returns 401 if token missing/invalid

## Permission Checking
- **Permission system**: `src/middleware/permissions.ts`
- Role-based access control (RBAC)
- Roles: 'admin', 'user', 'guest'
- `requireRole()` middleware checks `req.user.role`
- Admin routes: `/api/admin/*` require 'admin' role
- User routes: `/api/user/*` require 'user' or 'admin'

## Key Files
1. `src/auth/login.ts` - Login logic and token generation
2. `src/auth/register.ts` - User registration
3. `src/middleware/auth.ts` - Token validation middleware
4. `src/middleware/permissions.ts` - Role checking
5. `src/models/User.ts` - User model with password hashing
6. `src/config/jwt.ts` - JWT configuration

## Security Features
- Passwords hashed with bcrypt (10 rounds)
- JWT tokens expire after 24 hours
- Refresh token support in `src/auth/refresh.ts`
- Rate limiting on login endpoint (5 attempts/15 min)
- CORS configured for specific origins only

## Usage Example
```typescript
// Protected route example
router.get('/profile', 
  authenticateToken,
  requireRole('user'),
  getUserProfile
);
```
```

## Tips

- Tip 1: Start with high-level overview, then drill into specifics
- Tip 2: Use @filename mentions to focus on specific files
- Tip 3: Ask follow-up questions to deepen understanding
- Tip 4: Request diagrams for complex flows (Cursor can describe structure)

## Variations

### Variation 1: Architecture Overview
```
Explain the overall architecture of this codebase:
- Main components and their responsibilities
- How components interact
- Key design patterns used
- Technology stack
```

### Variation 2: Data Flow
```
Explain how data flows from [START] to [END]:
- Step-by-step process
- Functions/classes involved
- Database operations
- API calls
```

### Variation 3: Feature Exploration
```
Explain how the [FEATURE_NAME] feature works:
- User-facing functionality
- Implementation details
- Related files and functions
```

### Variation 4: Dependencies
```
Explain the dependencies and relationships:
- What depends on [MODULE]?
- What does [MODULE] depend on?
- External libraries used
```

## Cursor-Specific Features

### Use @ Mentions
- `@filename.ts` - Reference specific files
- `@foldername` - Reference directories
- `@symbol` - Reference functions/classes

### Codebase Search
Cursor automatically searches relevant files when you ask questions about the codebase.

### Follow-up Questions
```
"Show me the code for the token validation"
"Which files handle database connections?"
"Are there any tests for this?"
```

## Common Use Cases

### Onboarding
```
Give me a tour of this codebase. What does it do and how is it organized?
```

### Debugging
```
Where is [FEATURE] implemented? I need to debug an issue with it.
```

### Refactoring
```
Where is [OLD_PATTERN] used? I want to refactor it to [NEW_PATTERN].
```

### Documentation
```
Explain [COMPONENT] so I can document it for the team.
```

## Related Skills

- `find-similar-code.md` - Locate similar patterns in codebase
- `trace-dependencies.md` - Understand dependency relationships
- `generate-api-docs.md` - Document what you've learned

## Metadata

- **Created**: 2026-01-16
- **Last Updated**: 2026-01-16
- **Author**: AI Template
- **Tags**: #cursor #explain #architecture #understanding #codebase
