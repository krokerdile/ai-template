# Security Review

## Purpose

Perform a comprehensive security review of code to identify vulnerabilities, security anti-patterns, and potential exploits.

## Category

- [ ] Code Generation
- [x] Code Review
- [ ] Refactoring
- [ ] Testing
- [ ] Documentation
- [x] Debugging
- [ ] Architecture

## AI Assistant Compatibility

- [x] Claude Code
- [ ] Codex
- [x] Cursor

## Prompt Template

```
Perform a security review of the following code, checking for:

1. Common vulnerabilities (OWASP Top 10)
2. Input validation issues
3. Authentication/authorization flaws
4. Data exposure risks
5. Injection vulnerabilities (SQL, XSS, etc.)
6. Insecure dependencies
7. Cryptographic weaknesses
8. Error handling that leaks information

For each issue found, provide:
- Severity: Critical/High/Medium/Low
- Description: What the issue is
- Impact: What could happen
- Recommendation: How to fix it
- Example: Fixed code snippet

Code to review:
[PASTE CODE HERE]

Context:
- Language/Framework: [SPECIFY]
- Environment: [Production/Development]
- Exposure: [Public-facing/Internal]
```

## Example Usage

### Input

```javascript
const express = require('express');
const app = express();

app.get('/user/:id', (req, res) => {
  const userId = req.params.id;
  const query = `SELECT * FROM users WHERE id = ${userId}`;
  
  db.query(query, (err, results) => {
    if (err) {
      res.status(500).send(err.message);
    } else {
      res.json(results[0]);
    }
  });
});

app.post('/login', (req, res) => {
  const { username, password } = req.body;
  
  const user = users.find(u => u.username === username && u.password === password);
  
  if (user) {
    res.json({ token: user.id });
  } else {
    res.status(401).send('Invalid credentials');
  }
});
```

### Expected Output

```markdown
## Security Review Results

### Issue 1: SQL Injection Vulnerability
**Severity**: Critical
**Location**: Line 5
**Description**: User input is directly interpolated into SQL query without sanitization.
**Impact**: Attacker could execute arbitrary SQL commands, access/modify/delete data.
**Recommendation**: Use parameterized queries or prepared statements.

Fixed code:
```javascript
const query = 'SELECT * FROM users WHERE id = ?';
db.query(query, [userId], (err, results) => {
  // ...
});
```

### Issue 2: Information Disclosure
**Severity**: Medium
**Location**: Line 9
**Description**: Error messages expose internal system details.
**Impact**: Attackers gain information about database structure and errors.
**Recommendation**: Return generic error messages to users, log details internally.

Fixed code:
```javascript
if (err) {
  console.error('Database error:', err);
  res.status(500).json({ error: 'Internal server error' });
}
```

### Issue 3: Plaintext Password Comparison
**Severity**: Critical
**Location**: Line 18
**Description**: Passwords are stored and compared in plaintext.
**Impact**: If database is compromised, all user passwords are exposed.
**Recommendation**: Hash passwords using bcrypt or argon2.

Fixed code:
```javascript
const bcrypt = require('bcrypt');

// During registration
const hashedPassword = await bcrypt.hash(password, 10);

// During login
const user = users.find(u => u.username === username);
if (user && await bcrypt.compare(password, user.passwordHash)) {
  // Generate proper JWT token
}
```

### Issue 4: Weak Token Generation
**Severity**: High
**Location**: Line 21
**Description**: User ID used directly as authentication token.
**Impact**: Easily guessable tokens, session hijacking, privilege escalation.
**Recommendation**: Use JWT or cryptographically secure random tokens.

### Issue 5: No Rate Limiting
**Severity**: Medium
**Description**: No protection against brute force attacks on login endpoint.
**Impact**: Attackers can attempt unlimited login attempts.
**Recommendation**: Implement rate limiting using express-rate-limit or similar.

## Summary
- Critical: 2
- High: 1
- Medium: 2
- Low: 0

Immediate action required for SQL injection and password security issues.
```

## Tips

- Tip 1: Provide full code context including dependencies for thorough review
- Tip 2: Specify the deployment environment (public-facing vs internal) for risk assessment
- Tip 3: Ask for prioritized list when there are many issues
- Tip 4: Request specific code examples for fixes, not just descriptions

## Variations

### Variation 1: Quick Security Scan
Focus only on Critical/High severity issues for faster review.

### Variation 2: Compliance Review
Add specific compliance requirements (PCI-DSS, HIPAA, GDPR) to the prompt.

### Variation 3: Dependency Security
Focus on third-party library vulnerabilities and outdated dependencies.

## Related Skills

- `generate-test-suite.md` - Generate security-focused test cases
- `refactor-security.md` - Automatically fix common security issues
- `generate-api-docs.md` - Document security requirements

## Metadata

- **Created**: 2026-01-16
- **Last Updated**: 2026-01-16
- **Author**: AI Template
- **Tags**: #security #review #vulnerability #owasp #audit
