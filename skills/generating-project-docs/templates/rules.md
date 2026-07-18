# Rules — {Project Name}

> Conventions every contributor (human or AI) must follow. Architecture context: [Architecture.md](Architecture.md)

## 1. Code Standards

- Language/framework versions: {pin versions from Architecture.md}
- Style: {linter/formatter and config, e.g., ESLint + Prettier defaults, PSR-12}
- Naming: {classes PascalCase, functions camelCase, DB tables snake_case, …}

## 2. Project Structure

```
{folder tree with one-line purpose per folder}
```

## 3. Git Workflow

- Branch naming: {e.g., feature/FR-1-short-name}
- Commit style: {e.g., conventional commits}
- Merge policy: {PR review requirements, who approves}

## 4. Testing Requirements

- {what must be tested, coverage expectations, test naming/location}

## 5. Do

- {practices required in this project}

## 6. Don't

- {forbidden practices — e.g., no raw SQL outside repositories, no secrets in code}

## 7. Definitions

| Term | Meaning in this project |
|------|-------------------------|
| {domain term} | {definition from source} |
