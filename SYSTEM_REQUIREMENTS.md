# System Requirements Document (SRD)
## RPL Online Application System — CPUT
**Document Type:** System Requirements Document  
**Version:** 1.0  
**Date:** March 2026  
**Project:** Recognition of Prior Learning (RPL) Online Application System  
**Author:** [Zola Matebese] | [213133369]  
**Status:** Draft — Under Review

---

## 1. Introduction

### 1.1 Purpose
This System Requirements Document (SRD) defines the functional and non-functional requirements for the Recognition of Prior Learning (RPL) Online Application System at the Cape Peninsula University of Technology (CPUT). It serves as the authoritative specification guiding the design, development, testing, and deployment of the system.

### 1.2 Scope
The RPL Online Application System replaces the current Microsoft Forms-based RPL application process. It will support the full lifecycle of an RPL application — from initial submission by the applicant, through assessment by academic staff, to outcome communication and record-keeping — in a dedicated, integrated web-based platform.

### 1.3 Stakeholder Traceability
All requirements in this document are traceable to the concerns of identified stakeholders (see `STAKEHOLDER_ANALYSIS.md`). Each functional requirement references the stakeholder(s) whose need it addresses.

---

## 2. Functional Requirements

### FR-01 — User Registration and Authentication
**Statement:** The system shall allow RPL applicants to register an account using their South African ID number or passport number, verify their identity via email OTP, and log in securely to access their application portal.  
**Stakeholder(s):** RPL Applicant, IT Department  
**Acceptance Criteria:**  
- Registration is completed in under 3 minutes for a user with all required information.
- Email OTP is delivered within 60 seconds of registration request.
- Accounts are locked after 5 consecutive failed login attempts and require email verification to unlock.
- Registered applicants can log in with email and password on any modern browser without browser extensions.

---

### FR-02 — Guided Multi-Step Application Form
**Statement:** The system shall present RPL applicants with a guided, multi-step application form that dynamically displays only the fields and document requirements relevant to the qualification or module being applied for.  
**Stakeholder(s):** RPL Applicant, RPL Co-ordinator  
**Acceptance Criteria:**  
- Form sections are presented sequentially with a visible progress indicator (e.g., Step 2 of 5).
- Applicants can save their progress at any step and return to complete the application within 30 days before it expires.
- Conditional fields are hidden or shown based on previous answers with no page reload (client-side rendering).
- All mandatory fields are clearly marked and the system prevents submission until all mandatory fields and required file uploads are complete.

---

### FR-03 — Document Upload and Validation
**Statement:** The system shall allow applicants to upload supporting evidence documents (certificates, transcripts, employer letters, portfolio evidence) in PDF, JPG, or PNG format, with server-side validation of file type, file size, and completeness.  
**Stakeholder(s):** RPL Applicant, Subject Assessor, RPL Co-ordinator  
**Acceptance Criteria:**  
- Maximum file size per upload is 10 MB; maximum total application size is 50 MB.
- Accepted file types are .pdf, .jpg, .jpeg, .png only; any other file type is rejected with a clear error message.
- The system verifies that each required document category has at least one file uploaded before allowing form submission.
- Uploaded files are virus-scanned before being stored; any infected file is rejected with notification to the applicant.

---

### FR-04 — Application Submission and Automated Acknowledgement
**Statement:** The system shall generate a unique application reference number upon successful submission and automatically send the applicant an email acknowledgement containing the reference number, a summary of submitted information, and estimated processing timelines.  
**Stakeholder(s):** RPL Applicant, RPL Co-ordinator  
**Acceptance Criteria:**  
- Reference number is generated within 5 seconds of submission.
- Acknowledgement email is delivered within 2 minutes of submission.
- Email contains: reference number, list of uploaded documents, qualification/module applied for, and next steps.
- Submission confirmation is also displayed on-screen immediately after submission.

---

### FR-05 — Application Routing to Subject Assessors
**Statement:** The system shall automatically route each submitted RPL application to the relevant subject assessor(s) based on the qualification or module specified in the application, using a configurable assessor-qualification mapping table maintained by the RPL Co-ordinator.  
**Stakeholder(s):** RPL Co-ordinator, Subject Assessor  
**Acceptance Criteria:**  
- Routing occurs automatically within 1 hour of application submission (or immediately if the co-ordinator manually triggers it).
- The assessor receives an email notification with a link to their assessor dashboard showing the new application.
- If no assessor is mapped for the requested qualification, the application is flagged as "Unassigned" and the RPL Co-ordinator receives an alert.
- The co-ordinator can manually override routing at any time.

---

### FR-06 — Assessor Evaluation Dashboard
**Statement:** The system shall provide authenticated subject assessors with a dashboard listing all applications assigned to them, each displaying the applicant's uploaded evidence, the relevant learning outcomes, and a structured form for recording the assessment decision and justification.  
**Stakeholder(s):** Subject Assessor, RPL Co-ordinator  
**Acceptance Criteria:**  
- Dashboard loads all assigned applications within 3 seconds.
- Assessors can filter applications by status (Pending, In Review, Decided).
- The assessment decision form includes: decision field (Approved / Conditionally Approved / Declined), mandatory justification text field (minimum 50 characters), and optional request for additional documents.
- A submitted decision cannot be altered without a co-ordinator override, ensuring audit integrity.

---

### FR-07 — Real-Time Application Status Tracking
**Statement:** The system shall provide RPL applicants with a real-time status tracking view showing the current stage of their application (e.g., Submitted, Under Review, Awaiting Additional Documents, Decision Made, Outcome Communicated) and the date of the most recent status change.  
**Stakeholder(s):** RPL Applicant, RPL Co-ordinator  
**Acceptance Criteria:**  
- Status is updated within 5 minutes of any action taken by a co-ordinator or assessor.
- The applicant receives an automated email notification whenever their application status changes.
- Status history (full log of all transitions) is visible to the applicant.
- No technical knowledge is required to interpret the status — plain-language descriptions accompany each status code.

---

### FR-08 — Additional Document Request Workflow
**Statement:** The system shall allow assessors or the RPL Co-ordinator to request additional supporting documents from an applicant, automatically notifying the applicant by email and setting the application status to "Awaiting Additional Documents" until the upload is completed.  
**Stakeholder(s):** Subject Assessor, RPL Applicant, RPL Co-ordinator  
**Acceptance Criteria:**  
- Request includes a mandatory description of what document is required and why.
- Applicant receives notification within 5 minutes of the request being submitted.
- Applicant has 10 working days to upload the requested document before the application is escalated to the co-ordinator for a decision.
- The system allows up to 3 additional document requests per application.

---

### FR-09 — Outcome Communication and Record Creation
**Statement:** The system shall automatically generate and deliver a formal outcome letter to the applicant upon finalisation of the assessment decision, and create a structured RPL outcome record in the system database that is exportable to PeopleSoft student information system format.  
**Stakeholder(s):** RPL Applicant, RPL Co-ordinator, CPUT Senior Management  
**Acceptance Criteria:**  
- Outcome letter is generated from a configurable CPUT-branded template and delivered by email within 5 minutes of decision finalisation.
- Letter content includes: applicant details, qualification applied for, decision, justification summary, and appeals information.
- RPL outcome record is exportable in CSV and XML formats compatible with PeopleSoft's data import specification.
- Records are retained in the system for a minimum of 5 years in compliance with POPIA.

---

### FR-10 — Management Reporting Dashboard
**Statement:** The system shall provide the RPL Co-ordinator and Faculty Administrators with a management reporting dashboard displaying key RPL metrics, including application volumes by period, approval/decline rates by faculty and module, average processing time, and SLA compliance rates.  
**Stakeholder(s):** RPL Co-ordinator, Faculty Administrator, CPUT Senior Management, SAQA/CHE  
**Acceptance Criteria:**  
- Dashboard data is refreshed in real time (maximum 15-minute delay from action to dashboard update).
- Reports can be filtered by academic year, intake period, faculty, department, and application status.
- All reports are exportable as PDF and Excel with a single click.
- A SAQA-compliant summary report is available as a named, pre-configured export template.

---

### FR-11 — Appeals Process Management
**Statement:** The system shall provide applicants whose RPL application was declined with a digital appeals submission channel within the system, routing the appeal to the RPL Co-ordinator and generating a formal appeals tracking reference number.  
**Stakeholder(s):** RPL Applicant, RPL Co-ordinator, SAQA/CHE  
**Acceptance Criteria:**  
- Appeals submission option is available only to applicants with a "Declined" outcome, within 20 working days of outcome.
- Appeal form requires: grounds for appeal (free text, minimum 100 characters) and optional additional supporting documents.
- Appeals are acknowledged automatically within 2 minutes.
- Appeals tracking is visible to the applicant in their application status view.

---

### FR-12 — Role-Based Access Control (RBAC)
**Statement:** The system shall enforce role-based access control ensuring that applicants, assessors, co-ordinators, faculty administrators, and system administrators each access only the data and functions appropriate to their role.  
**Stakeholder(s):** IT Department, RPL Co-ordinator, CPUT Senior Management  
**Acceptance Criteria:**  
- Five distinct system roles are defined: Applicant, Assessor, RPL Co-ordinator, Faculty Administrator, System Administrator.
- An applicant can only view and edit their own application data.
- An assessor can only view applications assigned to them.
- Attempts to access unauthorised data return a 403 Forbidden response with no data leakage.
- Role assignments are managed by the System Administrator with a full audit log of all changes.

---

## 3. Non-Functional Requirements

### Category: Usability

#### NFR-01 — Accessibility Compliance
**Statement:** The applicant-facing portal shall comply with the Web Content Accessibility Guidelines (WCAG) 2.1 Level AA standards to ensure accessibility for users with visual, motor, and cognitive impairments.  
**Rationale:** RPL applicants may include adults with disabilities who rely on screen readers or keyboard navigation.  
**Measurable Criterion:** An automated WCAG 2.1 AA audit using an accredited tool (e.g., axe DevTools) returns zero critical violations; manual testing with a screen reader (NVDA or JAWS) confirms all form fields are correctly labelled and navigable.

#### NFR-02 — Learnability
**Statement:** A first-time RPL applicant with no prior experience of the system shall be able to complete and submit an application without requiring external assistance or training materials, guided by in-system instructions and contextual help tooltips alone.  
**Measurable Criterion:** In usability testing with 10 representative first-time users, 80% or more complete a test application submission without requesting help, in a maximum of 25 minutes.

---

### Category: Deployability

#### NFR-03 — Platform Independence
**Statement:** The system shall be deployable on both Linux (Ubuntu 22.04 LTS or later) and Windows Server 2019 or later environments, and shall run in a containerised Docker environment to ensure consistent deployment regardless of underlying OS.  
**Measurable Criterion:** A clean deployment from the Docker Compose configuration file completes successfully in under 15 minutes on a standard server; all automated tests pass after deployment on both Ubuntu 22.04 and Windows Server 2022.

#### NFR-04 — Cloud and On-Premises Flexibility
**Statement:** The system architecture shall support deployment both on CPUT's on-premises infrastructure and on POPIA-compliant South African cloud providers (e.g., Amazon Web Services af-south-1, Microsoft Azure South Africa North) without code changes.  
**Measurable Criterion:** A documented deployment runbook exists for both on-premises and cloud deployment; system passes full functional test suite in both environments.

---

### Category: Maintainability

#### NFR-05 — API Documentation
**Statement:** All system APIs shall be documented using the OpenAPI 3.0 specification, published as an interactive Swagger UI accessible to authorised developers, to facilitate future system integrations (e.g., PeopleSoft, Learning Management Systems).  
**Measurable Criterion:** 100% of public API endpoints are documented in the OpenAPI specification; Swagger UI is accessible at `/api/docs` to authenticated system administrators; documentation is updated automatically by the CI/CD pipeline on each release.

#### NFR-06 — Code Maintainability Standards
**Statement:** All source code shall conform to a defined coding standard (ESLint for JavaScript/TypeScript; PEP 8 for Python), shall achieve a minimum test coverage of 80% on business-logic modules as measured by a code coverage tool, and shall be version-controlled in Git with a documented branching strategy.  
**Measurable Criterion:** CI/CD pipeline enforces linting on every pull request and rejects merges with coverage below 80%; code complexity score (measured by SonarQube) remains below a Cognitive Complexity threshold of 15 for any single function.

---

### Category: Scalability

#### NFR-07 — Concurrent User Capacity
**Statement:** The system shall support a minimum of 500 concurrent authenticated users during peak RPL intake periods without degradation of response time beyond the defined performance thresholds.  
**Measurable Criterion:** Load testing (using Apache JMeter or k6) simulating 500 concurrent users performing mixed application, upload, and status-check operations sustains average API response times below 2 seconds for 95% of requests, with no application errors.

#### NFR-08 — Horizontal Scalability
**Statement:** The application layer shall be stateless and horizontally scalable, enabling additional application server instances to be added behind a load balancer without downtime or re-configuration, to accommodate growth in RPL uptake beyond initial projections.  
**Measurable Criterion:** Adding a second application instance behind the load balancer during a live load test results in a measurable reduction in average response time with no user sessions disrupted; session state is maintained via the shared Redis cache, not in-process memory.

---

### Category: Security

#### NFR-09 — Data Encryption
**Statement:** All personal data (as defined under the South African Protection of Personal Information Act, 2013) stored in the system database shall be encrypted at rest using AES-256 encryption; all data in transit between the client and server shall be encrypted using TLS 1.3 or later.  
**Measurable Criterion:** A third-party penetration test confirms AES-256 encryption at rest and TLS 1.3 in transit; the system achieves an SSL Labs rating of A or above; no personal data fields are stored in plaintext in any database table, log file, or backup.

#### NFR-10 — POPIA Compliance
**Statement:** The system shall implement data minimisation principles, provide applicants with the ability to request deletion of their personal data (subject to retention obligations), maintain a data processing register, and include a cookie consent mechanism on all pages accessible before authentication.  
**Measurable Criterion:** A POPIA compliance checklist (based on the Information Regulator's guidance) is completed and signed off by CPUT's Data Protection Officer before go-live; the data deletion request function is tested and confirmed to anonymise all personal identifiers within 30 working days of request.

---

### Category: Performance

#### NFR-11 — Page Load and API Response Time
**Statement:** All pages in the applicant portal shall achieve a Google Lighthouse performance score of 80 or above under simulated 4G mobile network conditions; all API endpoints shall return responses within 2 seconds for 95% of requests under normal load (up to 200 concurrent users).  
**Measurable Criterion:** Lighthouse performance audit run on production build returns score ≥ 80 for both mobile and desktop; API performance validated by automated load test generating 200 concurrent requests — p95 response time ≤ 2 seconds.

#### NFR-12 — File Upload Performance
**Statement:** Document upload operations shall complete within 10 seconds for files up to 10 MB under normal network conditions (≥10 Mbps upload speed), providing real-time progress feedback to the user throughout the upload.  
**Measurable Criterion:** Upload of a 10 MB PDF file completes in under 10 seconds on a 10 Mbps connection in automated testing; progress bar updates at least once per second during upload; no upload operation times out below the 30-second server-side timeout threshold.

---

## 4. Requirements Traceability Matrix

| Requirement ID | Type | Description (Summary) | Stakeholder(s) | Priority |
|---|---|---|---|---|
| FR-01 | Functional | User Registration & Authentication | Applicant, IT | High |
| FR-02 | Functional | Guided Multi-Step Application Form | Applicant, Co-ordinator | Critical |
| FR-03 | Functional | Document Upload & Validation | Applicant, Assessor, Co-ordinator | Critical |
| FR-04 | Functional | Submission Acknowledgement | Applicant | High |
| FR-05 | Functional | Automatic Application Routing | Co-ordinator, Assessor | Critical |
| FR-06 | Functional | Assessor Evaluation Dashboard | Assessor, Co-ordinator | Critical |
| FR-07 | Functional | Real-Time Status Tracking | Applicant, Co-ordinator | High |
| FR-08 | Functional | Additional Document Request | Assessor, Applicant | High |
| FR-09 | Functional | Outcome Communication & Record | Applicant, Management | Critical |
| FR-10 | Functional | Management Reporting Dashboard | Co-ordinator, Admin, Management | High |
| FR-11 | Functional | Appeals Process Management | Applicant, Co-ordinator, SAQA | Medium |
| FR-12 | Functional | Role-Based Access Control | IT, Co-ordinator, Management | Critical |
| NFR-01 | Non-Functional | WCAG 2.1 AA Accessibility | Applicant | High |
| NFR-02 | Non-Functional | Learnability | Applicant | High |
| NFR-03 | Non-Functional | Platform Independence | IT | High |
| NFR-04 | Non-Functional | Cloud/On-Premises Flexibility | IT, Management | Medium |
| NFR-05 | Non-Functional | API Documentation | IT | Medium |
| NFR-06 | Non-Functional | Code Maintainability | IT | Medium |
| NFR-07 | Non-Functional | 500 Concurrent Users | IT, Management | High |
| NFR-08 | Non-Functional | Horizontal Scalability | IT | Medium |
| NFR-09 | Non-Functional | AES-256 + TLS 1.3 Encryption | IT, Management, SAQA | Critical |
| NFR-10 | Non-Functional | POPIA Compliance | IT, Management, SAQA | Critical |
| NFR-11 | Non-Functional | Page Load Performance | Applicant, IT | High |
| NFR-12 | Non-Functional | File Upload Performance | Applicant | High |

---

*This document is subject to review and sign-off by identified stakeholders before development commences. Requirements may be updated in subsequent sprints following the Agile methodology adopted for this project.*
