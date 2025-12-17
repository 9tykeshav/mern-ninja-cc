# MERN Ninja

> MERN stack mastery tools for [Claude Code](https://claude.ai/claude-code)

A plugin that supercharges Claude Code with specialized skills for MongoDB, Express, React, and Node.js development.

## Installation

```bash
/plugin install 9tykeshav/mern-ninja-cc
```

## Skills

### `mern-ninja:backend-test-writer`

Generates comprehensive backend tests with smart defaults and zero config.

**Just ask:**
```
Generate tests for my user routes
Write tests for the auth service
Create tests for my User model
```

**What it does:**

| File Type | Test Type | Approach |
|-----------|-----------|----------|
| Routes/Controllers | Integration | Supertest + mongodb-memory-server |
| Services | Unit | Mocked dependencies |
| Models | Unit | Validation, methods, toJSON |
| Middleware | Unit | Mock req/res/next |
| Utilities | Unit | Pure function tests |

**Features:**
- Auto-detects test framework (Jest/Vitest/Mocha)
- Gap analysis on existing tests before generating new ones
- Priority levels (P0/P1/P2) for each test case
- Domain-specific edge cases (dates → DST/timezone, money → precision)
- Setup/teardown boilerplate included

---

### `mern-ninja:code-reviewer`

Reviews MERN stack code for security, performance, and best practices.

**Just ask:**
```
Review my authentication code
Check this Express API for security issues
Audit this MongoDB schema
```

**Review priorities:**

| Priority | Focus |
|----------|-------|
| 1. Security | Injection, XSS, auth flaws, secrets, CORS |
| 2. Performance | N+1 queries, re-renders, blocking ops |
| 3. Best Practices | Error handling, async patterns, cleanup |
| 4. Architecture | API design, state sync, type safety |

**Sample output:**

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
```

## Reference Guides

The plugin includes ~1,500 lines of curated best practices:

| Guide | Coverage |
|-------|----------|
| `security.md` | OWASP Top 10, MERN-specific vulnerabilities |
| `react.md` | Hooks, re-renders, security, testing |
| `nodejs.md` | Async patterns, event loop, memory |
| `express.md` | Middleware, auth, error handling |
| `mongodb.md` | Schema design, indexing, queries |
| `fullstack.md` | API design, auth flows, state sync |
| `test-patterns.md` | Complete test examples by file type |
| `test-setup.md` | Jest config, fixtures, mocking |

## Roadmap

- [ ] `mern-ninja:scaffolder` – Generate MERN boilerplate
- [ ] `mern-ninja:migrator` – Database migration helper
- [ ] `mern-ninja:frontend-test-writer` – React component tests

## License

MIT
