# Capstone Project Title Proposal — Title 1 (CrewSync) — Corrected Paste-Ready Fill

**Form:** FEU Institute of Technology · College of Computer Studies · Capstone Project Title Proposal (System Analysis and Design)
**Program:** Bachelor of Science in Information Technology, specialization in Web and Mobile Application
**Group:** AzTech (Group 6) · **Members:** Canido, Felix Jed; Mesina, Patrick Kyle; [3rd member]
**Term:** [x] 1st · Academic Year: 2026–2027
**Proposed Project Title 1:** CrewSync: An AI-Assisted Web and Mobile-Based System for Event Staffing, Predictive Response Analytics, and Schedule Conflict Prevention for a Party Service Business

> **Source of truth (reconciled 2026-10-07):** this file now mirrors the team's actual template fill (`Title-Proposal-Template.docx.pdf`) with the 8 panel-level corrections applied — (1) "micro-service" wording removed, (2) claim verbs neutralized + COI disclosure restored in §2.0, (3) SO3 aligned to title's "Prevention" + SO5 evaluation added, (4) §5.0 claim verb / spacing / beneficiary labels, (5) §6.0 list numbering fixed 1–6, (6) §7.0 appendices limited to evidence that actually exists, (7) three scope guards in §4.0, (8) terminology unified to "talent(s)". Paste each field directly into the form.

---

### 1.0 Area of Investigation

Analysis and design of a system for internal coordination of event staffing in a small event-service business. It includes processes for requesting, confirming, and checking for conflicts in the availability of talent for each booked event, supported by predictive response analytics that help the owner prioritize and follow up. The system will be developed as a web and mobile application, where the owner uses a web-based management application and the talent uses a mobile app with push notifications. This project is relevant to IT0037 Systems Analysis and Design and the BSIT Web and Mobile Application specialization.

---

### 2.0 Background and Rationale of the Project

Kiddie Salon by Nail Brat is a mobile party service company which deploys talents such as face painters, nail artists, and stylists to various children's party venues. The company needs to organize and confirm the right talents for each event based on the type of party package chosen for the occasion.

This project will focus on the staff scheduling process in the company. The process includes sending requests to workers from managers, receiving responses from workers, and making sure that each event is provided with appropriate staff. Project team members will investigate the current situation in the company by conducting interviews, observing, and examining previous documents to identify the major issues.

The proposed system is designed to streamline the scheduling process. It will automatically generate work slots depending on the party package, offer workers a set period to accept or decline, send requests to other workers in case there are no takers, detect schedule conflicts including travel time, rank eligible talents by their likelihood to respond, and provide an updated staffing list to the business owner. Kiddie Salon by Nail Brat is the project's industry partner, and the team openly discloses that the business owner is related to a team member; findings will be cross-checked with the talents' input and available records so they do not rest on a single source.

---

### 3.0 Statement of Objectives

The main objective of the project is to analyze, design, and develop CrewSync, an integrated web and mobile-based event staffing and schedule management system with AI-assisted predictive response analytics. Specifically, the study aims to:

1. Develop a web-based administrative dashboard for business owners or managers to create event bookings, assign roles, and monitor staffing status.
2. Develop a mobile application for event crew or talent to update their availability, receive booking requests, and confirm or decline event assignments.
3. Implement an automated schedule conflict detection and prevention mechanism that blocks overlapping confirmed assignments for a single talent, including a travel-time buffer.
4. Implement AI-assisted response-likelihood scoring for eligible talents — ranking request send-order and flagging at-risk slots early, with visible scoring factors and owner confirmation.
5. Provide an owner analytics dashboard summarizing events per month and per year, package-tier mix, time-to-full-staffing trends, and talent utilization, aggregated from workflow data.
6. Provide real-time push notifications for requests, reminders, and schedule changes.
7. Evaluate the system's usability and quality using selected ISO/IEC 25010 characteristics, and compare the time to fully staff an event before and after adoption using baselines established during the study.

---

### 4.0 Scope and Limitations of the Study

**Scope:** Owner web panel (talent registry and skills, package-tier and role configuration, event creation/edit/cancellation, automatic slot generation, availability-request dispatch, staffing dashboard, manual assignment/override, calendar view, analytics dashboard — monthly/yearly event volume, package mix, staffing-time trends, talent utilization — reports, activity log); talent mobile interface — native Android (primary) plus a responsive web app as the universal channel including iOS users — (request notifications, accept/decline before deadline, personal schedule view, blackout-date setting); business logic (response deadlines, auto-expiry, escalation to next eligible talent, conflict checks with travel-time buffer, reminders, AI-assisted response-likelihood scoring within the eligible set); and evaluation with the owner and participating talents.

**Limitations / out of scope:**
- No customer-facing booking portal — customers continue to book through the business's existing channels.
- No payment, payroll, or talent-fee computation.
- No inventory tracking.
- AI operates only within the eligible set: hard eligibility rules stay transparent and rule-based, scoring factors are visible, the owner confirms recommendations, and a rules-only fallback applies until sufficient response history accumulates.
- Notifications depend on the talent's device and connectivity, with in-app status and owner override as fallbacks.
- Single-client study: evaluation is restricted to Kiddie Salon by Nail Brat; results are not generalized.
- Performance thresholds (response time, tap counts, prevention rates) will be established from baseline measurements and testing rather than assumed in this proposal.

---

### 5.0 Target Beneficiaries

1. Owner / Manager of Kiddie Salon by Nail Brat (the client): reduces manual coordination and is designed to prevent overlapping confirmed assignments.
2. Event crew and freelance talents (face painters, nail artists, stylists): clear visibility of event requests and an easy way to confirm or decline availability.
3. Clients of the business (party hosts and parents): indirect, external beneficiaries — not system users — who benefit from events delivered with properly staffed and confirmed talents.

---

### 6.0 References

- Staffing and scheduling studies
- Related event management studies

> *(Simple/general style for title approval only. Full list kept in reserve below for the final proposal.)*

---

### 7.0 Appendices and Evidence Attachments

- Existing records
- Staffing records
- Interview and evaluation forms

---

<details>
<summary><b>Reserved for final proposal (Chapter 2 / final defense) — not for this form</b></summary>

**References (full):**
1. FEU Diliman. (n.d.). IT0037 Module 1: Systems analysis fundamentals and organizational context [Course material]. Department of Information Technology.
2. FEU Diliman. (n.d.). IT0037 Module 2: Planning systems projects and preliminary investigation [Course material]. Department of Information Technology.
3. Republic of the Philippines. (2012). Data Privacy Act of 2012 (Republic Act No. 10173). Official Gazette.
4. International Organization for Standardization. (2023). ISO/IEC 25010:2023 — Systems and software Quality Requirements and Evaluation (SQuaRE): Product quality model.
5. Shelly, G. B., Cashman, T. J., & Rosenblatt, H. J. (2012). *Systems analysis and design* (9th ed.). Cengage Learning. *(verify edition/year against syllabus copy — no citation found in course materials)*
6. Kiddie Salon by Nail Brat. (n.d.). Home [Facebook page]. Retrieved October 7, 2026, from https://www.facebook.com/kiddiesalonbynailbrat

**Appendices (full):** Client Endorsement & Permission Letter · Client Owner Interview Guide · Conflict-of-Interest Disclosure Statement · Evidence Status Matrix

> System architecture and use-case diagrams belong to analysis/design after title approval — never list them as appendices at title stage (they don't exist yet and would be requested).

</details>
