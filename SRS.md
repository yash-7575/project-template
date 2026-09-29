# SRS Template — CS Engineering Projects

Fill-in-ready SRS for AI/ML, web, cloud, security, and hackathon projects. Bracketed text is a placeholder; delete example lines when done.

---

## Project Info

| Field | Value |
| --- | --- |
| Project Name | [Enter project name] |
| Version | v0.1 |
| Owner | [Name / Team] |
| Date | [YYYY-MM-DD] |
| Related PRD | [Link] |
| Status | Draft / Review / Approved |

---

## 1. System Overview

**Purpose:** [Core technical objective in 1–2 sentences.]

**Actors:** [Guest, Authenticated User, Admin, API Client, Webhook, Scheduler, AI Agent.]

**Main workflow:** [Input] → [Validation] → [Processing] → [Storage] → [Output]

**Assumptions & constraints:** [Tech stack limits, budget, deadline, free-tier APIs, hardware.]

---

## 2. Functional Requirements

Each requirement must be testable (pass/fail).

| ID | Requirement | Priority | PRD feature |
| --- | --- | --- | --- |
| FR-001 | The system shall [testable action]. | Must | [Feature 1] |
| FR-002 | The system shall [testable action]. | Must | [Feature 2] |
| FR-003 | The system shall [testable action]. | Should | [Feature 3] |

Priority: **Must** / **Should** / **Could** / **Won't** (MoSCoW).

---

## 3. Non-Functional Requirements

| Category | Specification |
| --- | --- |
| Performance | [API p95 < 200 ms; inference < 2 s; page load < 3 s] |
| Security | [JWT auth, TLS, bcrypt/argon2, env-var secrets, input sanitization, LLM prompt-injection defense] |
| Reliability | [99.9% uptime; retries; graceful degradation; backups] |
| Scalability | [1k concurrent users; horizontal scaling; job queue] |
| Usability | [WCAG 2.1 AA; responsive; dark/light mode] |
| Maintainability | [README, unit test coverage ≥ 70%, linting, CI] |
| Portability | [Docker; Linux/macOS/Windows] |
| Observability | [Structured logs, /health endpoint, error alerts] |
| Cost | [≤ ₹X/month; free-tier respected] |

---

## 4. User Roles & Permissions

| Role | Access | Restrictions |
| --- | --- | --- |
| Admin | Full read/write/delete; user management | Audit-logged |
| Member | Read/write own content | Cannot see others' data |
| Guest | Read-only public pages | No authenticated endpoints |
| API Client | Scoped token access | Rate-limited |

---

## 5. Inputs & Outputs

| Input | Format | Validation | Output |
| --- | --- | --- | --- |
| [Uploaded file] | [JPG/PNG ≤ 5 MB] | [Type + size check] | [JSON result] |
| [Text query] | [UTF-8 ≤ 2000 chars] | [Non-empty, sanitized] | [Answer + sources] |

**Pipelines:**
- [Input source] → [Processing] → [Output destination]

---

## 6. Business Rules

- **BR-001:** [A user must be verified before accessing protected data.]
- **BR-002:** [Free-tier users are capped at N requests/day.]
- **BR-003:** [Only the resource owner or an admin can delete a resource.]

---

## 7. Integrations

| Service | Purpose | Auth | Limits / Fallback |
| --- | --- | --- | --- |
| [OpenAI / Gemini / Groq] | LLM inference | API key (env) | Rate limit; fallback model |
| [Firebase / Supabase] | Auth + DB | OAuth 2.0 / JWT | Free-tier quota |
| [SendGrid] | Email | API key | Retry 3× |
| [AWS S3] | File storage | IAM role | Lifecycle policy |

---

## 8. Data Requirements

**Entities & relationships:** [User 1─N Project; Project 1─N Task; Task N─N Tag.]

| Entity | Key fields | Notes |
| --- | --- | --- |
| User | id, email, role, created_at | email unique |
| [Entity 2] | [fields] | [notes] |

**Retention & deletion**
- Logs retained: [X days].
- Soft-deleted accounts purged after [X days] via scheduled job.
- Backups: [frequency, location, tested restore].
- Privacy: [PII handling, consent, encryption at rest].

---

## 9. Errors & Edge Cases

| Case | Trigger | Behavior |
| --- | --- | --- |
| Invalid input | Wrong type/size/format | 422 with field-level message |
| Network failure | Third-party down/timeout | Retry w/ backoff × 3, then friendly error |
| Unauthorized | Guest hits protected endpoint | 401 (or redirect to login) |
| Forbidden | User accesses another's data | 403 |
| Missing data | Required field empty | Block flow, highlight field |
| Rate limit | Too many requests | 429 with `Retry-After` |
| Not found | Bad ID | 404 |
| Server error | Unhandled exception | 500, log stack, no internals leaked |
| Model failure | Low confidence / empty output | Fallback message, flag for review |

---

## 10. Acceptance Criteria (Gherkin)

**Successful login**
- Given a registered user with valid credentials
- When they submit the login form
- Then the system returns a valid token and redirects to the dashboard

**Invalid input rejected**
- Given an authenticated user on the upload page
- When they upload a file over the size limit
- Then the system returns 422 with a clear message

**Third-party outage**
- Given the external API is down
- When the user submits a request
- Then the system retries 3× with backoff, then shows fallback

**Unauthorized access**
- Given a guest with no session
- When they hit a protected endpoint
- Then the system returns 401 and exposes no data

---

## 11. Traceability Matrix

| PRD feature | FR ID | Scenario | Status |
| --- | --- | --- | --- |
| [Feature 1] | FR-001 | Scenario 1 | ☐ |
| [Feature 2] | FR-002 | Scenario 2 | ☐ |

---

## 12. Sign-off Checklist

- [ ] Every FR is testable and has an ID
- [ ] Every FR maps to a PRD feature
- [ ] NFRs have measurable numbers
- [ ] Roles/permissions cover every endpoint
- [ ] Edge cases and errors defined
- [ ] Acceptance scenarios cover main flow + failure paths
