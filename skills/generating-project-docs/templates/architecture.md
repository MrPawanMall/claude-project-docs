# Architecture — {Project Name}

> See [Project-Requirement.md](Project-Requirement.md) for the requirements this architecture serves.

## 1. Technology Stack

| Layer | Technology | Reason / Source |
|-------|------------|-----------------|
| Frontend | {framework, version} | {why, or ⚠ GAP if unstated} |
| Backend | {framework, version} | |
| Database | {engine} | |
| Infrastructure / Hosting | {platform} | |

## 2. System Context

{Who and what talks to the system: users, external services, scheduled jobs. A short list or a mermaid diagram.}

```mermaid
graph LR
    User --> App[{Project Name}]
    App --> DB[(Database)]
    App --> Ext[{External service}]
```

## 3. Components

| Component | Responsibility | Delivers requirements |
|-----------|----------------|-----------------------|
| {module/service} | {single-sentence responsibility} | FR-1, FR-3 |

## 4. Data Model (high level)

| Entity | Key fields | Relationships |
|--------|-----------|---------------|
| {entity} | {fields} | {has-many / belongs-to} |

## 5. Integrations & External APIs

| Service | Purpose | Auth method | Failure handling |
|---------|---------|-------------|------------------|
| {API} | {why} | {key/OAuth} | {retry / degrade / alert} |

## 6. Security & Access Control

- Authentication: {method}
- Authorization: {roles/permissions model}
- Data protection: {encryption, PII handling}

## 7. Key Decisions (ADR log)

| # | Decision | Alternatives considered | Rationale |
|---|----------|-------------------------|-----------|
| AD-1 | {decision} | {options} | {why} |
