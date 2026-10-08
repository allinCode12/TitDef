# CrewSync — Mock Title Defense Slide Deck Blueprint
*(Drop-in replacement for Slides 4 to 14 of your AzTech Mock Title Defense presentation)*

---

### Slide 4: Title Slide
* **Title:** CrewSync: An AI-Assisted Web and Mobile-Based System for Event Staffing, Predictive Response Analytics, and Schedule Conflict Prevention for a Party Service Business
* **Subtitle:** Capstone Title Proposal
* **Client Partner:** Kiddie Salon by Nail Brat
* **Specialization:** BSIT — Web and Mobile Application
* **Presenter / Proponent:** [Your Name] (Team AzTech)

---

### Slide 5: Title and Four-Element Breakdown (Module 1)
* **Title Breakdown Table:**
  * **System / Capability:** Event Staffing, Predictive Response Analytics, and Schedule Conflict Prevention
  * **Users / Setting:** Party Service Business (Kiddie Salon by Nail Brat)
  * **Value / Problem Direction:** Fully staffed events with tracked availability; designed to prevent overlapping confirmed assignments; less manual follow-up
  * **Specialization Differentiator:** Web and Mobile (Owner web management dashboard + Talent mobile availability app with push alerts)
* **One-Line Value Pitch:**
  * Bridges the gap between informal chat message chaos and verified, on-time event talent staffing.

---

### Slide 6: Background and Evidence Status (Module 1)
* **Industry & Setting Context:**
  * Party & event-based kiddie services deploy on-call freelancers (face painters, nail artists, hair stylists) across dynamic off-site venues.
  * Rapid party bookings require multi-role talent coordination per event tier.
* **Evidence Status Matrix:**
  * **Partner Verification:** Kiddie Salon by Nail Brat operates active party events across Metro Manila [Verified - Social Channels].
  * **Client Need:** Owner reported verbally that staff scheduling and follow-ups are a critical operational bottleneck [Reported verbally — endorsement letter pending; to be confirmed in interview].
  * **Current Staffing Latency:** Hours/days spent following up in chat groups `[TO VALIDATE - Primary Investigation]`.
  * **Incidents of Double-Booking / Late Declines:** Recorded occurrences `[TO VALIDATE - Historical Chat Review]`.
  * **Talent Smartphone Access & Data Connectivity:** Mobile OS distribution `[TO VALIDATE - Talent Survey]`.

---

### Slide 7: Problem: Symptoms vs. Root Causes + Stakeholders (Module 1)
* **Symptoms `[TO VALIDATE]`:**
  * Staffing inquiries buried in active messaging threads (Messenger/Viber).
  * Prolonged response times and unconfirmed attendance close to event dates.
  * Risk of double-booking talents across overlapping party venues.
  * Owner spends excessive operational hours manually chasing talent availability.
* **Root Cause Hypothesis:**
  * **Absence of a structured, centralized event-to-role assignment workflow** with enforceable response deadlines and automated conflict checking.
* **Stakeholders (Module 3):**
  * **Shop Owner / Event Coordinator:** Process Owner & Admin (High power, High interest).
  * **Talents (Face Painters, Nail Artists, Hair Stylists):** Direct Mobile Users (High interest, Operational).
  * **Party Hosts / Parents:** Indirect beneficiaries (Reliable service delivery; Not system users).
  * **Adviser & Panel:** Project Governance and Evaluation.

---

### Slide 8: General and Specific Objectives (Module 2)
* **General Objective:**
  * To develop a web and mobile talent scheduling and availability confirmation system for Kiddie Salon by Nail Brat to streamline event staffing and verify talent availability.
* **Specific Objectives:**
  1. Develop an **Owner Web Admin Panel** to manage package tiers, schedule events, auto-generate required talent slots, and track real-time staffing status.
  2. Develop a **Talent Mobile App** for on-call artists to receive event requests, view venue/tier details, and accept/decline before an automated deadline.
  3. Implement **automated auto-escalation** for expired/declined requests and **scheduling conflict checks** with buffer time.
  4. Implement role-based access, audit activity logs, and privacy controls complying with **RA 10173 (Data Privacy Act of 2012)**.
  5. Evaluate system usability and performance using selected **ISO/IEC 25010** characteristics, measuring reduction in average time-to-staff against baseline `[TO VALIDATE]`.

---

### Slide 9: Proposed Solution and Flow Diagram (Module 2)
* **Step-by-Step Flow:**
  * **Step 1: Event Creation & Slot Generation:** Owner inputs confirmed booking (Date, Time, Venue, Package Tier). System automatically creates needed skill slots (e.g., 2 Face Painters + 1 Nail Tech).
  * **Step 2: Automated Eligibility and Request Dispatch:** System filters talents by skill, active status, blackout dates, and travel conflicts, then dispatches invitations with a response countdown.
  * **Step 3: Talent Response & Auto-Escalation:** Talents tap Accept or Decline on mobile. If declined or expired, slot auto-escalates to the next eligible talent.
  * **Step 4: Real-Time Monitoring & Roster Lock:** Owner dashboard monitors status (Open, Partially Staffed, Fully Staffed, At Risk) with manual override capabilities.

---

### Slide 10: Related Systems vs. CrewSync (Differentiator)
* **Comparison Matrix:**
  * **Messenger / Viber Groups:** High messaging clutter; no response deadlines; no automated slot tracking; manual confirmation.
  * **Shared Spreadsheets / Calendars:** Static; lacks push notifications; no auto-escalation; no conflict detection.
  * **Standard Shift Scheduling Apps (When I Work, Homebase):** Designed for fixed hourly shifts at fixed storefronts; lacks event package tier logic; expensive recurring per-user SaaS fees.
* **CrewSync Differentiator:**
  * Custom package-tier slot generator + deadline-enforced mobile confirmation + automated re-dispatching + conflict-checking travel buffer, specifically customized for Kiddie Salon by Nail Brat. *[Preliminary comparison based on publicly described features; competitor capabilities and pricing require verification — see Context Pack §3.]*

---

### Slide 11: Scope and Limitations (Module 1)
* **In Scope (✓):**
  * Owner Web Panel (Event creation, tier/role configuration, talent registry, live staffing board, override controls, logs).
  * Talent Mobile App (PWA/Mobile: push notifications, accept/decline actions, personal schedule, blackout dates).
  * Automated business logic (Deadline timers, auto-escalation, conflict/travel-time buffer checks).
* **Out of Scope (✗):**
  * Direct customer/parent booking portal (Client maintains existing Facebook marketing).
  * Online payments, talent compensation/payroll computation, and tips calculation.
  * Inventory/supplies tracking (Nail polish, paint kits).
  * AI-based ranking/profiling algorithms (Rule-based eligibility is used for transparency and ethics).
* **Delimitation Note:**
  * Single-client evaluation restricted to Kiddie Salon by Nail Brat operations.

---

### Slide 12: Key Requirements (Module 3)
* **Functional Requirements (MoSCoW):**
  * **Must:** Role-based authentication; Tier-to-slot generator; Job notification dispatch with deadline; Accept/Decline action; Schedule conflict blocker; Live staffing dashboard; Manual admin override.
  * **Should:** Automated escalation engine; Blackout date management; Event push reminders; Activity audit log.
  * **Could:** SMS fallback gateway for urgent alerts; External map navigation link for venues.
* **Non-Functional & Quality Standards (ISO/IEC 25010):**
  * **Performance Efficiency:** Dispatch alert delivery threshold `[X] seconds — target to be established and measured during performance testing [post-test criterion]`.
  * **Reliability:** System is designed to block overlapping confirmed assignments for any single talent; prevention to be verified through testing [post-test criterion].
  * **Usability:** Talent can review and accept a job request with minimal taps — tap-count target to be validated in usability testing [post-test criterion].
  * **Security & Privacy:** Minimal PII collection, hashed credentials, HTTPS/TLS encryption, RA 10173 data minimization.

---

### Slide 13: Feasibility Snapshot and Lifecycle Choice (Module 2)
* **Six-Dimensional Feasibility Snapshot:**
  * **Technical:** Feasible. Standard web frontend, mobile PWA/push service, and relational database. Push reliability on iOS tested via service worker standards.
  * **Operational:** Likely Feasible. Verbal client commitment (endorsement letter pending); reported high-friction manual follow-up routine [TO VALIDATE].
  * **Economic:** Conditional. Low expected development cost using standard cloud tiers (Firebase/Supabase/Node); free push tiers avoid recurring SMS fees; final PHP cost estimate pending.
  * **Schedule:** Conditional. Feasibility within the academic calendar depends on team skills, remaining term, and client availability for reviews; planned via phased hybrid sprints.
  * **Security:** Conditional. Planned: role-based access control, secure session management, and encrypted storage.
  * **Legal & Ethical:** Conditional. RA 10173-compliant data handling planned; open disclosure of team member client relationship; transparent talent rotation rules proposed.
* **Lifecycle Choice:**
  * **Tailored Hybrid Approach:** Prototyping (for talent mobile interface usability) + Agile Sprints (for core scheduling logic build) wrapped in Predictive Stage-Gates (formal client and academic milestone sign-offs).

---

### Slide 14: Data Gathering Plan and Next Steps (Module 3 & 4)
* **Next Steps for Primary Fact-Finding:**
  * **Phase A — Client Owner In-Depth Interview:** Document exact service package tiers, talent headcount, current booking volume, and historical pain points.
  * **Phase B — Talent User Survey:** Gather device models (Android vs. iOS), data availability, and response habits.
  * **Phase C — Artifact & Log Review:** Inspect de-identified chat communication logs and booking calendars to establish quantitative baselines (time-to-staff).
  * **Phase D — Client Endorsement Letter:** Formally execute the signed partnership agreement.
* **Convergence Goal:**
  * Replace all `[TO VALIDATE]` baseline markers with empirical client data for the final Title Defense and Chapter 1 documentation.
