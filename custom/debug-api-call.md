# Example Custom Skill: Debug API Call

## Purpose

A personalized skill for debugging failed API calls in my projects. Includes specific logging format and error handling patterns I use.

## Category

- [ ] Code Generation
- [ ] Code Review
- [ ] Refactoring
- [ ] Testing
- [ ] Documentation
- [x] Debugging
- [ ] Architecture

## AI Assistant Compatibility

- [x] Claude Code
- [x] Codex
- [x] Cursor

## Prompt Template

```
Debug this API call that's failing:

[PASTE CODE OR ERROR MESSAGE]

Check for:
- Network request configuration
- Request headers (especially Authorization, Content-Type)
- Request body format
- Response status codes and error messages
- CORS issues
- Timeout settings
- Error handling

Provide:
1. Likely root cause
2. How to verify the issue
3. Fixed code with enhanced logging
4. Test cases to prevent regression
```

## Example Usage

### Input

```javascript
async function fetchUserData(userId) {
  const response = await fetch(`https://api.example.com/users/${userId}`);
  const data = await response.json();
  return data;
}

// Error: Getting 401 Unauthorized
```

### Prompt

```
Debug this API call that's failing:

[paste code above]

Currently getting 401 Unauthorized error.
```

### Expected Output

```javascript
// Root cause: Missing Authorization header

async function fetchUserData(userId) {
  try {
    console.log(`[API] Fetching user data for ID: ${userId}`);
    
    const token = localStorage.getItem('authToken');
    if (!token) {
      throw new Error('No authentication token found');
    }
    
    const response = await fetch(
      `https://api.example.com/users/${userId}`,
      {
        headers: {
          'Authorization': `Bearer ${token}`,
          'Content-Type': 'application/json'
        }
      }
    );
    
    console.log(`[API] Response status: ${response.status}`);
    
    if (!response.ok) {
      const errorData = await response.json().catch(() => ({}));
      console.error(`[API] Error response:`, errorData);
      throw new Error(
        `API request failed: ${response.status} ${response.statusText}`
      );
    }
    
    const data = await response.json();
    console.log(`[API] Successfully fetched user:`, data.id);
    return data;
    
  } catch (error) {
    console.error(`[API] Failed to fetch user ${userId}:`, error.message);
    throw error;
  }
}

// Test cases
describe('fetchUserData', () => {
  it('should include Authorization header', async () => {
    localStorage.setItem('authToken', 'test-token');
    // Assert fetch was called with Authorization header
  });
  
  it('should throw error when no token', async () => {
    localStorage.removeItem('authToken');
    await expect(fetchUserData('123')).rejects.toThrow();
  });
});
```

## Tips

- Tip 1: Always include current error message/status code
- Tip 2: Check browser network tab for actual request details
- Tip 3: Verify authentication token is present and valid
- Tip 4: Add console.logs at each step to trace execution

## Variations

### Variation 1: GraphQL Debugging
Focus on GraphQL-specific issues: query syntax, variables, resolver errors

### Variation 2: Timeout Issues
"Debug slow/timeout API calls" - check for performance bottlenecks

### Variation 3: CORS Problems
"Debug CORS errors" - focus on headers and preflight requests

## Related Skills

- `generate-api-endpoint.md` - Generate API endpoints with proper error handling
- `security-review.md` - Review API security
- `generate-test-suite.md` - Create tests for API calls

## Metadata

- **Created**: 2026-01-16
- **Last Updated**: 2026-01-16
- **Author**: Example User
- **Tags**: #debugging #api #custom #http #errors

## Personal Notes

This pattern works well for my Express.js + React projects. Always helps me catch missing headers or malformed requests quickly.
