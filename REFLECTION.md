# Reflection: Challenges Faced in Balancing Stakeholder Needs
## RPL Online Application System — CPUT
**Document Type:** Reflection  
**Version:** 1.0  
**Date:** March 2026  
**Project:** Recognition of Prior Learning (RPL) Online Application System  
**Author:** [Zola Matebese] | [213133369]

---

## Overview

Requirements engineering is rarely a process of simply cataloguing what each stakeholder wants and combining the lists. In practice, it involves navigating genuine tensions where one stakeholder's ideal outcome actively conflicts with another's. This reflection documents the most significant challenges encountered during the stakeholder analysis and requirements definition phases of the RPL Online Application System, and how those conflicts were approached and resolved.

---

## Challenge 1: Applicant Simplicity vs. SAQA Compliance Complexity

The most persistent tension in this project was between the RPL applicant's need for a simple, fast, accessible application experience and the regulatory depth required by SAQA's RPL Policy and Criteria (2016).

An RPL applicant — often a working adult accessing higher education for the first time in years — needs the system to feel approachable and non-intimidating. Every additional field, every mandatory document, and every conditional section adds friction that could cause an applicant to abandon the process. Research by Harris (2000) and Wheelahan et al. (2012) consistently identifies the administrative burden of RPL as a primary deterrent, and the design of the system must actively counteract this.

SAQA's requirements, however, are substantive. The policy mandates that applications contain structured evidence mapped against specific learning outcomes; that assessors record formal, justified decisions; that appeals procedures are documented and accessible; and that all records are retained for regulatory audit purposes. These are non-negotiable institutional obligations that the system must enforce, not optional add-ons.

**How this was resolved:** The resolution was to make complexity progressive rather than simultaneous. The guided multi-step form (FR-02) presents requirements one section at a time, with contextual help text explaining why each piece of information is needed in plain language. SAQA-mandated fields are marked as required, but their purpose is explained inline rather than assumed. The system enforces completeness at submission (rather than at each step), so applicants can fill in sections out of order as they gather documents. This approach respects both the applicant's experience and the regulator's requirements without compromising either.

---

## Challenge 2: IT Department Security Requirements vs. Applicant Accessibility

The IT Department's security requirements — AES-256 encryption, TLS 1.3, POPIA-compliant data handling, virus scanning on uploads, session locking after failed logins — are legitimate and non-negotiable from a legal and institutional risk perspective. However, several of these controls introduced friction in the applicant experience.

The account lockout policy (FR-01: lock after 5 failed attempts) was the most directly contentious. Applicants who submit RPL applications may access the system infrequently — perhaps once per application cycle — making password forgetting likely. A strict lockout with only email-based recovery could strand applicants who have changed email addresses or have limited internet access outside the application period.

Similarly, the POPIA consent and cookie mechanisms (NFR-10) added steps to the onboarding flow that testing suggested some users would find confusing or off-putting.

**How this was resolved:** The account recovery mechanism was designed to support both email OTP and an alternative identity verification path using the applicant's South African ID number plus date of birth — reducing dependence on a single communication channel without weakening identity assurance. The POPIA consent flow was simplified to a single, plain-language modal at first login rather than a layered series of prompts. The security properties remained intact; only the presentation was adjusted to minimise unnecessary friction.

---

## Challenge 3: Co-ordinator Control vs. Assessor Autonomy

The RPL Co-ordinator requires full visibility and control over the entire application pipeline. Their role depends on knowing the status of every application at all times, and they need the ability to override decisions, reassign applications, and escalate stalled cases.

Subject assessors, however, have limited time and deep subject expertise. They resist systems that feel like bureaucratic surveillance — where every action is logged, every decision is scrutinised, and they cannot exercise professional judgment without a formal justification trail. Initial feedback from similar institutional systems suggests that over-prescriptive assessor interfaces contribute to non-adoption.

**How this was resolved:** The assessor dashboard (FR-06) was designed to feel like a professional workspace rather than a monitoring tool. The assessor sees only their assigned applications — not the full pipeline — and the justification field is framed as a "professional record" (for SAQA audit purposes) rather than a supervisory compliance requirement. The co-ordinator's override capability is functional but not surfaced in the assessor view, preserving the sense of assessor autonomy while maintaining institutional accountability. The audit trail exists at the database level without being a visible feature of the assessor experience.

---

## Challenge 4: Real-Time Notifications vs. IT Bandwidth and Infrastructure

The RPL applicant stakeholder strongly prioritised real-time notifications — knowing immediately when their application status changed, when an assessor had reviewed their evidence, or when a decision had been made. From a user experience perspective, this is a highly valued feature that directly addresses one of the most-cited pain points of the current Microsoft Forms process (where applicants receive no automated communication at all).

The IT department, however, raised concerns about the infrastructure cost and complexity of implementing real-time push notifications at scale — particularly WebSocket connections maintaining open channels for potentially hundreds of concurrent applicants. During peak intake periods, this could place meaningful load on network and server resources, and the ongoing maintenance of a real-time notification service adds operational complexity.

**How this was resolved:** A pragmatic middle ground was agreed: the system implements near-real-time email notifications (triggered within 5 minutes of any status change) rather than WebSocket-based push notifications. Email is universally accessible, requires no persistent connection, and is consistent with applicants' existing communication channels with the institution. The dashboard status display (FR-07) is refreshed on page load rather than via a live WebSocket feed, with a manual "Refresh status" button for applicants who want an immediate check. This approach met the applicant's core need — "I know what's happening with my application without having to phone anyone" — without the infrastructure overhead of persistent real-time connections.

---

## Challenge 5: CPUT Management Reporting vs. SAQA Regulatory Standardisation

CPUT senior management required a flexible, filterable reporting dashboard (FR-10) that could generate ad hoc reports tailored to internal governance needs — by faculty, by department, by intake period, with custom date ranges. This is a reasonable institutional requirement and essential for evidence-based resource planning.

SAQA's reporting requirements, however, are structured and standardised. The regulator expects data in specific fields, categories, and formats to enable national-level aggregation. A flexible ad hoc reporting tool that serves management well may not produce the precisely structured outputs that SAQA's audit templates require.

**How this was resolved:** The reporting module was designed with two distinct layers. A flexible dashboard layer (for internal management use) allows free filtering, custom visualisations, and Excel/PDF export. A separate "Compliance Reports" section provides pre-configured, locked report templates that output data in SAQA's prescribed format. These templates are maintained by the system administrator and updated when SAQA modifies its reporting requirements. The two layers share the same underlying data, but serve different audiences with different output structures — avoiding the compromise of designing a single report that is adequate for neither purpose.

---

## Key Learning

The most important lesson from this requirements engineering process is that many apparent stakeholder conflicts are not genuine value conflicts but rather presentation and design problems. Security does not have to feel punitive; compliance does not have to feel bureaucratic; oversight does not have to feel surveilling. In many cases, the requirement itself is non-negotiable but the way it is implemented and communicated to users is fully within the designer's control. The requirements engineer's role is to hold both the functional specification and the user experience perspective simultaneously — and to find design choices that honour both rather than trading one off against the other.

---

## References

- Harris, J. 2000. *RPL: power, pedagogy and possibility.* Pretoria: Human Sciences Research Council Press.
- South African Qualifications Authority (SAQA). 2016. *Policy and criteria for the recognition of prior learning.* Pretoria: SAQA.
- Wheelahan, L. et al. 2012. *Recognition of prior learning: policy and practice in Australia.* Adelaide: NCVER.
