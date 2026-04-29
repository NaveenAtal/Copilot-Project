# Copilot Custom Agent Instructions

These instructions guide the Copilot coding agent when performing code reviews and enforcing naming conventions across this repository.

---

## Code Review Guidelines

When reviewing code, always check for the following:

### General Principles
- Code should be readable, maintainable, and self-documenting.
- Avoid code duplication — apply the DRY (Don't Repeat Yourself) principle.
- Functions and methods should have a single responsibility (SRP).
- Prefer explicit over implicit behavior.
- Remove unused imports, variables, and dead code.

### Security
- Never commit secrets, API keys, tokens, or passwords.
- Validate and sanitize all external inputs.
- Avoid SQL injection, XSS, and other common vulnerabilities.
- Use parameterized queries for database operations.

### Error Handling
- Always handle errors explicitly; never silently swallow exceptions.
- Log errors with sufficient context for debugging.
- Return meaningful error messages to callers.

### Performance
- Avoid N+1 query patterns in database access code.
- Prefer lazy evaluation and streaming over loading large datasets into memory.
- Cache expensive operations where appropriate.

### Testing
- New features must be accompanied by unit tests.
- Test edge cases and failure scenarios, not just the happy path.
- Mocks and stubs should be used sparingly and documented.

---

## Naming Convention Guidelines

Enforce the following naming conventions based on the language in use.

### General Rules (All Languages)
- Names must be descriptive and convey intent.
- Avoid single-letter variable names except for well-understood loop counters (`i`, `j`, `k`).
- Avoid abbreviations unless they are universally understood (e.g., `id`, `url`, `api`).
- Boolean variables should read as a question or statement: `isActive`, `hasPermission`, `canEdit`.

### JavaScript / TypeScript
| Construct        | Convention         | Example                        |
|------------------|--------------------|--------------------------------|
| Variables        | `camelCase`        | `userName`, `totalCount`       |
| Constants        | `UPPER_SNAKE_CASE` | `MAX_RETRIES`, `API_BASE_URL`  |
| Functions        | `camelCase`        | `getUserById`, `formatDate`    |
| Classes          | `PascalCase`       | `UserService`, `OrderManager`  |
| Interfaces       | `PascalCase`       | `UserProfile`, `ApiResponse`   |
| Enums            | `PascalCase`       | `OrderStatus`, `UserRole`      |
| Enum members     | `UPPER_SNAKE_CASE` | `ORDER_PENDING`, `ROLE_ADMIN`  |
| Files (modules)  | `kebab-case`       | `user-service.ts`, `api-client.ts` |

### Python
| Construct        | Convention         | Example                        |
|------------------|--------------------|--------------------------------|
| Variables        | `snake_case`       | `user_name`, `total_count`     |
| Constants        | `UPPER_SNAKE_CASE` | `MAX_RETRIES`, `API_BASE_URL`  |
| Functions        | `snake_case`       | `get_user_by_id`, `format_date`|
| Classes          | `PascalCase`       | `UserService`, `OrderManager`  |
| Modules/Files    | `snake_case`       | `user_service.py`, `api_client.py` |
| Private members  | `_leading_underscore` | `_internal_cache`           |

### Java / Kotlin
| Construct        | Convention         | Example                        |
|------------------|--------------------|--------------------------------|
| Variables        | `camelCase`        | `userName`, `totalCount`       |
| Constants        | `UPPER_SNAKE_CASE` | `MAX_RETRIES`, `API_BASE_URL`  |
| Methods          | `camelCase`        | `getUserById`, `formatDate`    |
| Classes          | `PascalCase`       | `UserService`, `OrderManager`  |
| Packages         | `lowercase`        | `com.example.userservice`      |

### C#
| Construct        | Convention         | Example                        |
|------------------|--------------------|--------------------------------|
| Variables (local)| `camelCase`        | `userName`, `totalCount`       |
| Properties       | `PascalCase`       | `UserName`, `TotalCount`       |
| Constants        | `PascalCase`       | `MaxRetries`, `ApiBaseUrl`     |
| Methods          | `PascalCase`       | `GetUserById`, `FormatDate`    |
| Classes          | `PascalCase`       | `UserService`, `OrderManager`  |
| Interfaces       | `IPascalCase`      | `IUserService`, `IOrderManager`|
| Private fields   | `_camelCase`       | `_userName`, `_totalCount`     |

---

## Pull Request Review Checklist

When reviewing a pull request, verify the following:

- [ ] All naming conventions above are followed.
- [ ] No hardcoded secrets or credentials are present.
- [ ] Error handling is implemented for all failure paths.
- [ ] New or changed logic is covered by tests.
- [ ] No unnecessary dependencies were added.
- [ ] Documentation (inline comments, README) is updated where relevant.
- [ ] The change is backward compatible, or breaking changes are clearly documented.
