# RPL Online Application System
## Cape Peninsula University of Technology

![Version](https://img.shields.io/badge/version-0.2.0-blue)
![Assignment](https://img.shields.io/badge/assignment-4%20of%205-orange)
![Status](https://img.shields.io/badge/status-requirements%20phase-yellow)
![Methodology](https://img.shields.io/badge/methodology-agile-green)
[ Zola Matebese] [213133369]

---

## Project Overview

The **RPL Online Application System** is a purpose-built web-based platform designed to replace the current Microsoft Forms-based Recognition of Prior Learning (RPL) application process at the Cape Peninsula University of Technology (CPUT).

Recognition of Prior Learning (RPL) is a nationally legislated mechanism (SAQA, 2016; CHE, 2016) that enables individuals to earn formal academic credit for knowledge and skills acquired outside of traditional education pathways. The current process relies on Microsoft Forms — a lightweight survey tool that lacks the workflow management, document validation, audit trail, and integration capabilities required for proper RPL administration.

This system addresses that gap by providing a dedicated, integrated digital platform supporting the full RPL application lifecycle: from applicant registration and evidence submission, through multi-stage assessment, to outcome communication and institutional reporting.

---

## Assignment Progress

| Assignment | Focus | Status |
|---|---|---|
| Assignment 3 | Project Initiation — Problem Statement, Scope, Initial Architecture | ✅ Complete |
| **Assignment 4** | **Stakeholder Analysis & System Requirements Documentation** | ✅ **Current** |
| Assignment 5 | System Design — Wireframes, ERD, Architecture Diagrams | 🔜 Upcoming |
| Assignment 6 | Prototype Development | 🔜 Upcoming |
| Assignment 7 | Testing & Evaluation | 🔜 Upcoming |

---

## What's New in Assignment 4

Assignment 4 adds the full **Requirements Engineering** phase to the project, building directly on the problem statement and scope established in Assignment 3. The following documents have been added to the `/docs` directory:

### 📋 [STAKEHOLDER_ANALYSIS.md](./docs/STAKEHOLDER_ANALYSIS.md)
A comprehensive analysis of **7 stakeholders** across the RPL ecosystem:

| # | Stakeholder | Role |
|---|---|---|
| 1 | RPL Applicant | Primary end-user submitting applications |
| 2 | RPL Co-ordinator | Manages end-to-end application pipeline |
| 3 | Subject Assessor | Evaluates evidence against learning outcomes |
| 4 | Faculty/Departmental Administrator | Faculty-level oversight and reporting |
| 5 | IT Department / System Administrator | Infrastructure, security, and integrations |
| 6 | CPUT Senior Management | Governance, compliance, and strategy |
| 7 | SAQA / CHE | Regulatory bodies setting RPL standards |

Each stakeholder is documented with: **Role**, **Key Concerns**, **Pain Points**, and **Success Metrics**.

---

### 📄 [SYSTEM_REQUIREMENTS.md](./docs/SYSTEM_REQUIREMENTS.md)
A complete System Requirements Document covering:

#### Functional Requirements (12 requirements)
| ID | Requirement |
|---|---|
| FR-01 | User Registration and Authentication |
| FR-02 | Guided Multi-Step Application Form |
| FR-03 | Document Upload and Validation |
| FR-04 | Application Submission and Automated Acknowledgement |
| FR-05 | Application Routing to Subject Assessors |
| FR-06 | Assessor Evaluation Dashboard |
| FR-07 | Real-Time Application Status Tracking |
| FR-08 | Additional Document Request Workflow |
| FR-09 | Outcome Communication and Record Creation |
| FR-10 | Management Reporting Dashboard |
| FR-11 | Appeals Process Management |
| FR-12 | Role-Based Access Control (RBAC) |

#### Non-Functional Requirements (12 requirements across 6 categories)
| Category | Requirements |
|---|---|
| **Usability** | WCAG 2.1 AA compliance; Learnability (80% task completion without training) |
| **Deployability** | Linux/Windows Docker deployment; Cloud + on-premises flexibility |
| **Maintainability** | OpenAPI 3.0 documentation; 80% test coverage; SonarQube quality gate |
| **Scalability** | 500 concurrent users; Stateless horizontal scaling via Redis |
| **Security** | AES-256 at rest + TLS 1.3 in transit; Full POPIA compliance |
| **Performance** | Lighthouse score ≥ 80; API p95 ≤ 2s; File upload ≤ 10s for 10 MB |

---

### 🪞 [REFLECTION.md](./docs/REFLECTION.md)
A critical reflection on **5 key stakeholder conflicts** encountered during requirements engineering:
1. Applicant simplicity vs. SAQA compliance complexity
2. IT security controls vs. applicant accessibility
3. Co-ordinator oversight vs. assessor autonomy
4. Real-time notifications vs. IT infrastructure constraints
5. Internal management reporting vs. SAQA regulatory standardisation

---

## Repository Structure

```
rpl-online-application-system/
│
├── README.md                          ← Project overview and progress (this file)
│
├── docs/
│   ├── STAKEHOLDER_ANALYSIS.md        ← Assignment 4: 7 stakeholders fully documented
│   ├── SYSTEM_REQUIREMENTS.md         ← Assignment 4: 12 FR + 12 NFR with acceptance criteria
│   └── REFLECTION.md                  ← Assignment 4: Stakeholder conflict reflection
│
└── [src/ and design/ to be added in Assignments 5–7]
```

---

## System Context Summary

### Problem Being Solved
Microsoft Forms cannot enforce document submission requirements, track multi-stage workflows, generate audit trails, integrate with PeopleSoft, or produce SAQA-compliant reports. These limitations result in:
- Manual data rekeying by RPL Co-ordinators
- Zero transparency for applicants about their application status
- Inability to demonstrate POPIA and SAQA compliance
- Fragmented institutional data that cannot support evidence-based policy

### Proposed Solution
A dedicated web-based RPL Online Application System with:
- Applicant self-service portal with guided form, document upload, and status tracking
- Assessor dashboard with structured decision recording and audit trail
- Co-ordinator workflow management with automated routing and SLA monitoring
- Management reporting with SAQA-compliant export templates
- Full POPIA compliance with AES-256 encryption and role-based access control
- REST API with OpenAPI documentation for integration with PeopleSoft

### Methodology
This project follows an **Agile** development methodology. Requirements are documented here as a baseline but are expected to evolve through sprint retrospectives as stakeholder feedback is incorporated. All changes are version-controlled in this repository.

---

## References

- Council on Higher Education (CHE). 2016. *Recognition of Prior Learning in the context of the South African NQF.* Pretoria: CHE.
- South African Qualifications Authority (SAQA). 2016. *Policy and criteria for the recognition of prior learning.* Pretoria: SAQA.
- Vial, G. 2019. Understanding digital transformation: a review and a research agenda. *The Journal of Strategic Information Systems*, 28(2), pp. 118–144.

---


