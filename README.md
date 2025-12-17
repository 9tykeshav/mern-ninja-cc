# MERN Ninja

MERN stack mastery tools for Claude Code. Currently includes a comprehensive code reviewer for MongoDB, Express, React, and Node.js projects.

## Installation

### Claude Code

```bash
/plugin install mern-ninja
```

## Available Skills

### `mern-ninja:code-reviewer`

Reviews MERN stack code for security vulnerabilities, performance issues, best practice violations, and architectural concerns.

### `mern-ninja:backend-test-writer`

Generates comprehensive backend tests for Express routes, MongoDB models, Node services, and utilities.

**Usage:**

```
Generate tests for my user routes
Write tests for the auth service
Create tests for my User model
```

**What it generates:**

| File Type | Test Type | Coverage |
|-----------|-----------|----------|
| Routes/Controllers | Integration | Supertest + mongodb-memory-server |
| Services | Unit | Mocked dependencies |
| Models | Unit | Validation, methods |
| Middleware | Unit | Request/response mocking |
| Utilities | Unit | Pure function tests |

**Features:**
- Auto-detects test framework (Jest/Vitest/Mocha)
- Matches project's test file convention
- Generates comprehensive coverage (success + errors + edge cases)
- Includes setup/teardown boilerplate

**Usage:**

```
Review my authentication code
Check this Express API for security issues
Review my React components for performance
Audit this MongoDB schema
```

**What it checks:**

| Priority | Focus |
|----------|-------|
| 1. Security | Injection, XSS, auth flaws, secrets, CORS |
| 2. Performance | N+1 queries, re-renders, blocking ops, indexes |
| 3. Best Practices | Error handling, async patterns, cleanup |
| 4. Architecture | API design, state sync, type alignment |

**Output format:**

```markdown
# MERN Code Review

## Summary
- Files reviewed: 5
- Issues: 2 Critical, 3 Important, 5 Suggestions

## Critical (Must Fix)
### [C1] Security: NoSQL injection in login
**File:** `api/auth/login.js:24`
**Why:** User input passed directly to query
**Fix:** Use explicit field matching

## What's Good
- Proper JWT refresh flow
- Consistent error responses

---
**Ready to fix these?** I'll start with Critical issues.
```

## Reference Files

The code-reviewer skill includes detailed reference guides (~1,180 lines total):

| File | Coverage |
|------|----------|
| react.md | Hooks, re-renders, security, testing |
| security.md | OWASP Top 10, MERN-specific vulnerabilities |
| nodejs.md | Async patterns, event loop, memory |
| express.md | Middleware, auth, error handling |
| mongodb.md | Schema design, indexing, queries |
| fullstack.md | API design, auth flows, state sync |

## Roadmap

Future skills planned:
- `mern-ninja:scaffolder` - Generate MERN boilerplate
- `mern-ninja:migrator` - Database migration helper
- `mern-ninja:frontend-test-writer` - React component test generation

## License

MIT License - see LICENSE file
