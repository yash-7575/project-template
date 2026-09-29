# PRD Template — CS Engineering Projects

A fill-in-ready PRD template for any CS engineering project (AI/ML, web, cloud, security, hackathon). Each section has prompts; delete bracketed examples once filled.

---

## Project Info

| Field | Value |
| --- | --- |
| Project Name | [Enter project name] |
| Version | v0.1 |
| Owner | [Name / Team] |
| Date | [YYYY-MM-DD] |
| Status | Draft / Review / Approved |
| Type | [Web / AI-ML / Cloud / Security / Embedded / Research / Tool] |
| Timeline | [Start → Deadline] |

---

## 1. Problem

**What problem exists?**
[Describe the pain point in plain words.]

**Who experiences it?**
[Persona + frequency + severity.]

**What happens if we do nothing?**
[Wasted time/money/security risk; users stuck with worse alternatives.]

**Existing alternatives:** [What people use today and why it falls short.]

---

## 2. Vision & Goals

**Vision:** [One sentence north star.]

**Goals (max 3):**
1. [Goal 1]
2. [Goal 2]
3. [Goal 3]

**Non-goals:** [Explicitly what this project will NOT achieve.]

**Success looks like:** [Post-launch state for user, project, evaluators.]

---

## 3. Target Users

**Primary**
- Persona: [Student / Developer / Admin / Analyst]
- Core need: [The one main thing]
- Pain today: [What they currently do]

**Secondary**
- Persona: [Reviewer / Prof / Support]
- Core need: [Indirect benefit]

**Context:** [Device, network, technical skill, environment.]

---

## 4. Core Features

| # | Feature | Description & user value | Priority |
| --- | --- | --- | --- |
| 1 | [Name] | [What / why] | P0 |
| 2 | [Name] | [...] | P0 |
| 3 | [Name] | [...] | P1 |

Priority: **P0** = MVP blocker · **P1** = important, cut if needed · **P2** = nice-to-have

---

## 5. User Stories & Acceptance Criteria

- As a [persona], I want to [action], so that [outcome].
  - **Given** [context] **when** [action] **then** [expected result].
- As a [persona], I want to [action], so that [outcome].
  - **Given** [...] **when** [...] **then** [...].

---

## 6. Technical Requirements

**Architecture:** [Monolith / microservices / serverless / pipeline. Link diagram.]

| Layer | Choice | Reason |
| --- | --- | --- |
| Frontend | [React / Streamlit / CLI / Mobile] | |
| Backend | [FastAPI / Node / Flask] | |
| Data / DB | [Postgres / SQLite / Vector DB] | |
| AI / ML | [Model / API / dataset] | |
| Infra | [AWS / Vercel / Docker / local] | |
| Integrations | [Third-party APIs + rate limits] | |

**Non-functional requirements**
- **Performance:** [e.g. p95 < 2s, 50 concurrent users]
- **Security:** [auth, secrets, input validation, prompt-injection defense for LLMs]
- **Reliability:** [uptime target, error handling, fallbacks]
- **Privacy / compliance:** [PII, licensing, dataset terms]
- **Cost:** [budget cap, free-tier limits]
- **Maintainability:** [README, tests, code style, backups]

---

## 7. MVP Scope

- [Core feature that proves the main idea]
- [Minimal UI or API to use it]
- [Basic auth / data handling if needed]
- [Working demo — deployed or reproducible]
- [Basic docs]

---

## 8. Out of Scope

- [V2 feature]
- [Unsupported platform / scale]
- [Advanced ideas — multi-language, admin dashboards, fine-tuning]

---

## 9. Success Metrics

| Category | Target | Outcome |
| --- | --- | --- |
| Product | [90% task completion] | [Core flow works end-to-end] |
| Technical / Model | [accuracy ≥ 85%, latency < 2s, 0 crit vulns] | [Reliable + secure] |
| User | [8/10 testers finish unaided] | [Easy to use] |
| Impact | [hackathon shortlist / 100 users / paper] | [Real-world value] |

---

## 10. Milestones

| Phase | Deliverable | Target |
| --- | --- | --- |
| Research & design | PRD, wireframes, architecture | [date] |
| Build MVP | Core features working | [date] |
| Test & harden | Bugs, security, evaluation | [date] |
| Launch / demo | Deploy, present, report | [date] |

---

## 11. Risks & Mitigations

| Risk | Likelihood | Impact | Mitigation |
| --- | --- | --- | --- |
| API cost / rate limits | Med | High | Cache, fallback model |
| Scope creep | High | Med | Stick to MVP list |
| Data quality | Med | High | Validate inputs, use test set |
| Tight deadline | High | High | Cut P1 early |

---

## 12. Assumptions & Open Questions

**Assumptions**
- Users have [stable internet / modern browser / GPU].
- [Segment] prefers [A] over [B].
- [API / dataset] stays free and available.

**Open Questions**
- Legal / privacy / licensing review needed?
- Strict API or compute limits?
- Who approves final scope?

---

## 13. Definition of Done

- [ ] All MVP items pass acceptance criteria
- [ ] Code in version control with README + setup steps
- [ ] Tests or manual test log completed
- [ ] Secrets removed from repo
- [ ] Demo / video / presentation ready
- [ ] Backup of code + data taken

---

## 14. References

- [Designs, repos, papers, datasets, team @mentions]
