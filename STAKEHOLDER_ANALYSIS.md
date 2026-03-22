# Stakeholder Analysis
## RPL Online Application System — CPUT
**Document Type:** Stakeholder Analysis  
**Version:** 1.0  
**Date:** March 2026  
**Project:** Recognition of Prior Learning (RPL) Online Application System  
**Author:** [Zola Matebese] | [213133369]

---

## 1. Overview

This document identifies and analyses the key stakeholders of the RPL Online Application System being developed to replace the current Microsoft Forms-based process at the Cape Peninsula University of Technology (CPUT). Stakeholder analysis was conducted through domain research, policy review (SAQA, CHE), and knowledge of higher education administrative workflows.

---

## 2. Stakeholder Analysis Table

### Stakeholder 1 — RPL Applicant (Prospective Student)

| Field | Detail |
|---|---|
| **Role** | External user submitting an RPL application to gain academic credit or admission based on prior learning and work experience. The applicant is the primary end-user of the system's front-facing portal. |
| **Key Concerns** | Clear, guided application process; transparent status tracking; ability to upload supporting evidence (certificates, portfolios, employer letters); timely feedback on application outcome; mobile-friendly access. |
| **Pain Points** | The current Microsoft Forms process provides no application tracking; applicants receive no automated acknowledgement or status updates; the form does not enforce which documents must be uploaded; applicants must follow up manually via email or phone; the form is lost if the session times out. |
| **Success Metrics** | Application submission time reduced to under 20 minutes; 90%+ of applicants report understanding the process via post-submission survey; zero applications lost due to system failure; status update delivered within 24 hours of any assessor action. |

---

### Stakeholder 2 — RPL Co-ordinator

| Field | Detail |
|---|---|
| **Role** | Internal CPUT staff member responsible for managing the end-to-end RPL process: receiving applications, routing them to the correct assessors, following up on outstanding documentation, and communicating outcomes to applicants. |
| **Key Concerns** | Centralised dashboard showing all active applications and their current stage; automated routing of applications to appropriate subject assessors; ability to request additional documents from applicants; management reports for institutional reporting to CHE/SAQA. |
| **Pain Points** | Microsoft Forms exports data as flat Excel spreadsheets with no workflow tracking; the co-ordinator manually emails every application to the relevant assessor; there is no audit trail of decisions; generating a status report requires manually counting rows in a spreadsheet. |
| **Success Metrics** | Administrative processing time per application reduced by 40%; zero applications misrouted to incorrect assessors; end-of-term institutional reports generated in under 5 minutes; 100% of active applications have a visible, current status at all times. |

---

### Stakeholder 3 — Subject Assessor (Academic Staff)

| Field | Detail |
|---|---|
| **Role** | An academic staff member with subject expertise who evaluates the RPL applicant's evidence against the required learning outcomes of a specific module or qualification. Assessors provide a formal recommendation (approve / conditional / decline) which the RPL Co-ordinator acts on. |
| **Key Concerns** | Receiving only applications relevant to their subject area; access to all uploaded evidence documents in a single view; ability to record a structured assessment decision with justification; clarity on SAQA-mandated assessment criteria embedded in the interface. |
| **Pain Points** | Currently receives applications as email attachments in no standard format; has no formal system to record the assessment decision — decisions are communicated informally back to the co-ordinator; there is no record of the assessor's reasoning for future audits. |
| **Success Metrics** | 100% of assessment decisions recorded in-system with mandatory justification field; assessors receive only applications assigned to their subject area (zero misdirected applications); average assessment turnaround time reduced from 15 days to 7 days. |

---

### Stakeholder 4 — Faculty / Departmental Administrator

| Field | Detail |
|---|---|
| **Role** | The departmental or faculty-level administrator who provides oversight of RPL applications within their faculty, monitors approval rates, escalates issues, and ensures faculty compliance with institutional RPL policy. |
| **Key Concerns** | Faculty-level reporting on application volumes, approval rates, and turnaround times; ability to escalate stalled applications; visibility of applications awaiting assessor action; alignment with departmental capacity for RPL processing. |
| **Pain Points** | Currently has no real-time visibility of RPL activity within their faculty; only receives information when the RPL co-ordinator manually compiles a report; cannot identify bottlenecks or track whether assessors are meeting expected turnaround times. |
| **Success Metrics** | Faculty dashboard showing live RPL pipeline data; automated alert when any application exceeds a defined SLA (e.g., 10 working days without action); monthly faculty RPL report exportable in PDF or Excel within 2 clicks. |

---

### Stakeholder 5 — IT Department / System Administrator

| Field | Detail |
|---|---|
| **Role** | Responsible for deploying, hosting, maintaining, securing, and monitoring the RPL Online Application System on CPUT's infrastructure. Also manages user account provisioning, integration with existing student information systems (e.g., PeopleSoft), and system upgrades. |
| **Key Concerns** | System stability and uptime (especially during peak RPL intake periods); secure storage and transmission of personal and academic data; ease of deployment and patching; audit logging of all system activity; compatibility with CPUT's existing enterprise architecture. |
| **Pain Points** | Microsoft Forms has no institutional-level audit logging; data is stored in Microsoft's cloud with limited institutional control; there is no integration with PeopleSoft, requiring manual data rekeying when RPL outcomes are applied to student records; IT has no visibility of system usage or errors. |
| **Success Metrics** | System uptime of 99.5% or above; all personal data stored on CPUT-controlled infrastructure or POPIA-compliant cloud; zero data breaches in first 12 months; integration with PeopleSoft eliminating all manual data transfer; full audit log accessible to IT within 60 seconds of request. |

---

### Stakeholder 6 — CPUT Executive / Senior Management

| Field | Detail |
|---|---|
| **Role** | Senior institutional leaders (e.g., Deputy Vice-Chancellor: Teaching and Learning, Registrar) responsible for RPL policy, regulatory compliance with SAQA and CHE, institutional reporting obligations, and the broader digital transformation strategy of CPUT. |
| **Key Concerns** | Institutional compliance with SAQA's RPL Policy and CHE audit requirements; RPL uptake as a measure of widening access; evidence of digital transformation progress; return on investment of the system development; risk management (data protection under POPIA). |
| **Pain Points** | Currently cannot produce SAQA-compliant RPL reports without significant manual effort; RPL uptake data is unreliable due to fragmented records; POPIA compliance of the Microsoft Forms process is unclear; there is no institutional dashboard demonstrating RPL system performance to external auditors. |
| **Success Metrics** | Full SAQA-compliant RPL report generated automatically per intake cycle; RPL application uptake increase of 25% within 18 months of system launch; POPIA compliance certification achieved within 6 months; positive audit outcome from CHE within first external review post-implementation. |

---

### Stakeholder 7 — SAQA / CHE (Regulatory Bodies)

| Field | Detail |
|---|---|
| **Role** | External regulatory bodies that set the policy and criteria governing how RPL must be conducted at South African HEIs. SAQA's RPL Policy (2016) defines the procedural and evidentiary requirements; the CHE conducts institutional quality audits that include RPL processes. |
| **Key Concerns** | Adherence to SAQA's RPL Policy and Criteria; evidence that assessment decisions are made against formally defined learning outcomes; documentation of the appeals process; equitable access to RPL for all eligible applicants; accurate national RPL statistics. |
| **Pain Points** | Existing processes at many institutions (including those relying on Microsoft Forms) cannot produce the structured evidence trail required by SAQA audits; inconsistent data formats across institutions make national-level RPL statistics unreliable. |
| **Success Metrics** | 100% of system-generated RPL records meet SAQA documentation standards; system produces a structured, exportable audit trail for every application; compliance report generated in SAQA's prescribed format without manual intervention. |

---

## 3. Stakeholder Priority Matrix

| Stakeholder | Influence | Interest | Priority | Engagement Strategy |
|---|---|---|---|---|
| RPL Applicant | Low | High | **High** | Design participatory UX testing; gather feedback via pilot survey |
| RPL Co-ordinator | High | High | **Critical** | Key subject matter expert; involved in requirements workshops |
| Subject Assessor | Medium | Medium | **High** | Prototype review sessions; usability testing of assessor dashboard |
| Faculty Administrator | Medium | Medium | **Medium** | Reporting requirements workshop; sign-off on dashboard mockups |
| IT Department | High | Medium | **Critical** | Architecture review; security and deployment specification sign-off |
| CPUT Senior Management | High | Low | **High** | Steering committee updates; compliance demonstration |
| SAQA / CHE | Low | High | **High** | Policy alignment review; compliance checklist embedded in design |

---

*Document version controlled. All changes must be logged and approved by the RPL System Project Lead.*
