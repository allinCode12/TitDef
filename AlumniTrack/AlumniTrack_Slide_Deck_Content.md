# AlumniTrack — Mock Title Defense Slide Deck Blueprint
*(Mirror of the CrewSync deck structure — Slides 4 to 14 of the AzTech Mock Title Defense presentation)*

> ⛔ **Gate 0 reminder:** No client is secured yet. Every slide below tagged `[TO VALIDATE]` must stay tagged until the client interview. Do not present hypothesized pain points as findings.

---

### Slide 4: Title Slide
* **Title:** AlumniTrack: An AI-Assisted Web and Mobile-Based System for Graduate Employment Monitoring, Placement Analytics, and Course-to-Career Alignment for a Higher Education Institution
  * *(Base wording submitted by Canido omitted the "…for a Higher Education Institution" element — this version adds Module 1's Users/Setting element; pending team/advisor/panel approval at Gate 1)*
* **Subtitle:** Capstone Title Proposal
* **Client Partner:** ⛔ Gate 0 — being secured *(do not name a client that has not endorsed the project)*
* **Specialization:** BSIT — Web and Mobile Application
* **Presenter / Proponent:** [Your Name] (Team AzTech)

---

### Slide 5: Title and Four-Element Breakdown (Module 1)
* **Title Breakdown Table:**
  * **System / Capability:** Graduate Employment Monitoring, Placement Analytics, and Course-to-Career Alignment (AI-assisted)
  * **Users / Setting:** Graduates/Alumni (web + mobile) and the institution's alumni/registry office (web) — at a Higher Education Institution
  * **Value / Problem Direction:** Continuous, consolidated graduate outcome data instead of periodic manual collection `[TO VALIDATE against current process]`
  * **Specialization Differentiator:** Web and Mobile (alumni self-service submission anywhere + admin analytics dashboard)
* **One-Line Value Pitch:**
  * Graduates report outcomes from their phones; the institution sees placement time and course-to-career alignment on one dashboard.

---

### Slide 6: Background and Evidence Status (Module 1)
* **Industry & Setting Context:**
  * Higher education institutions track graduate employment outcomes for reporting and accreditation `[cite source or drop]`.
  * Alumni are dispersed and phone-first after graduation `[TO VALIDATE with graduate survey]`.
* **Evidence Status Matrix:**
  * **Advisor Input:** Direction suggested by the course advisor after the first title's rejection [Stated by team].
  * **Client Endorsement:** ⛔ **None yet — Gate 0 is the first priority.**
  * **Current Tracer Process:** Expected to be periodic survey + manual consolidation `[HYPOTHESIS — interview]`.
  * **Response Rates / Placement Figures:** `[TO VALIDATE — no numbers may be cited]`.
  * **Data Ownership & RA 10173 Posture:** `[TO VALIDATE — client DPO/office]`.

---

### Slide 7: Problem: Symptoms vs. Root Causes + Stakeholders (Module 1)
* **Symptoms `[HYPOTHESES — TO VALIDATE]`:**
  * Graduate outcome data collected only in periodic survey campaigns.
  * Responses scattered across forms and spreadsheets; consolidation is manual.
  * Figures may be outdated by the time they are reported.
  * No continuous channel for graduates to update status.
* **Root Cause Hypothesis:**
  * **Absence of a continuous, structured channel for graduates to report and update employment outcomes**, so institutional data depends on periodic manual campaigns.
* **Stakeholders (Module 3):**
  * **Alumni / Registry / Careers Office:** Process Owner & Admin (High power, High interest).
  * **Graduates / Alumni:** Direct Users, web + mobile (High interest; privacy-sensitive).
  * **Program Chairs / Leadership:** Report consumers (Medium interest).
  * **Adviser & Panel:** Project Governance and Evaluation.

---

### Slide 8: General and Specific Objectives (Module 2)
* **General Objective:**
  * To develop a web and mobile system that enables a partner higher education institution to continuously collect and monitor graduate employment status, job placement time, and course-to-career alignment.
* **Specific Objectives:**
  1. Develop an **Alumni Submission Interface** (responsive web + mobile/PWA) for graduates to submit and update employment status, placement details, and course-relevance information.
  2. Develop an **Admin Web Panel** to manage programs/cohorts, review submissions, send reminders, and track job placement time per cohort.
  3. Implement **course-to-career alignment summaries** per program using transparent, rule-based categorization (no AI scoring claims).
  4. Implement role-based access, consent capture, and activity logging complying with **RA 10173 (Data Privacy Act of 2012)** — alumni data is personal data.
  5. Evaluate the system with client staff and a graduate sample using selected **ISO/IEC 25010** characteristics, comparing data currency/completeness against baseline `[TO VALIDATE]`.

---

### Slide 9: Proposed Solution and Flow Diagram (Module 2)
* **Step-by-Step Flow:**
  * **Step 1: Setup & Invitation:** Admin defines programs, cohorts, reporting periods; graduates access via invitation link/code `[channel TO VALIDATE]`.
  * **Step 2: Alumni Submission (web/mobile):** Graduate enters employment status, position, industry, start date, and course-relevance; consent captured (RA 10173).
  * **Step 3: Placement Computation:** System computes job placement time (graduation → first employment) and stores program attribution with timestamps.
  * **Step 4: Monitoring & Reporting:** Admin dashboard shows response rates, placement-time views, and course-to-career tables; exports for official reports `[formats TO VALIDATE]`.

---

### Slide 10: Related Systems vs. AlumniTrack (Differentiator)
* **Comparison Matrix:** *[Preliminary comparison — all competitor/platform capabilities require verification before stating in the defense]*
  * **Generic Survey Tools (Google/Microsoft Forms):** One-shot capture; no longitudinal profile, no placement-time tracking, no dashboards; manual consolidation `[verify]`.
  * **Spreadsheet Consolidation:** Stores responses; no update flow or analytics; error-prone `[validate as client's actual method]`.
  * **Institutional MIS/SIS:** Holds student records but typically ends at graduation `[validate]`.
  * **Commercial Tracer Platforms:** Purpose-built but subscription-based; capabilities unknown until reviewed `[verify before naming]`.
* **AlumniTrack Differentiator:**
  * Continuous alumni self-reporting (web + mobile) + placement-time computation + program-level course-to-career view, built for one confirmed institutional process — **the "confirmed" part is Gate 0/2 work still pending.**

---

### Slide 11: Scope and Limitations (Module 1)
* **In Scope (✓):**
  * Alumni submission interface (web/PWA): status updates, placement details, consent, own history.
  * Admin panel: programs/cohorts, review/flag, reminders, dashboards, exports, activity log.
  * Placement-time and course-to-career summaries (transparent rules).
* **Out of Scope (✗):**
  * Job-posting board or recruiter marketplace.
  * Employer/payroll verification (data is self-reported and labeled as such).
  * AI career-matching or employability scoring.
  * Current-student tracking; multi-institution support.
* **Delimitation Note:**
  * Single-client evaluation restricted to the partner institution; findings are self-reported outcomes, not audited statistics.

---

### Slide 12: Key Requirements (Module 3)
* **Functional Requirements (MoSCoW):**
  * **Must:** Alumni access/invitation login; submit/update employment record; consent capture (RA 10173); admin program/cohort management; placement-time computation; dashboard; role-based access; activity log.
  * **Should:** Reminder campaigns; record flagging/review; exports (CSV/PDF); own-submission history.
  * **Could:** SMS reminders; optional salary band field (consent-gated); cohort comparisons over time.
* **Non-Functional & Quality Standards (ISO/IEC 25010):**
  * **Performance Efficiency:** Report/page load target `[X] seconds — to be established during performance testing [post-test criterion]`.
  * **Privacy & Security:** Data minimization, consent records, hashed credentials, HTTPS/TLS, RA 10173 retention/deletion rules `[to define with client DPO]`.
  * **Usability:** Graduate completes a submission within `[N] minutes — target to be validated in usability testing [post-test criterion]`.
  * **Reliability / Accuracy:** Placement time computed consistently from stored dates; no silent overwrites (timestamped updates).

---

### Slide 13: Feasibility Snapshot and Lifecycle Choice (Module 2)
* **Six-Dimensional Feasibility Snapshot (PRE-CLIENT — will be revisited after Gate 0):**
  * **Technical:** Feasible. Standard web frontend, PWA/mobile delivery, and relational database.
  * **Operational:** **Unknown / Conditional — no client secured yet (Gate 0).** Client ownership of the process and alumni willingness are unverified.
  * **Economic:** Conditional. Low expected hosting cost at pilot volume; reminder-channel costs (SMS) `[estimate in PHP]`.
  * **Schedule:** Conditional. Gate 0 timing is the critical path; remaining term is a constraint.
  * **Security:** Conditional. Planned: role-based access, session management, export logging.
  * **Legal & Ethical:** Conditional. RA 10173 applies to alumni personal data — consent, lawful basis, retention, and DPO coordination must be confirmed with the client.
* **Lifecycle Choice:**
  * **Tailored Hybrid Approach:** Prototyping (alumni submission UX with real graduates) + Agile Sprints (core tracking/reporting build) wrapped in Predictive Stage-Gates (Gate 0 client secured → title approval → design approval → pilot sign-off).

---

### Slide 14: Data Gathering Plan and Next Steps (Module 3 & 4)
* **Next Steps for Primary Fact-Finding:**
  * **Gate 0 — Secure the Client:** Identify and secure a real institutional office (alumni/registry/careers/ICT); obtain endorsement. *(This is the lesson from our first title's rejection.)*
  * **Phase A — Client Office Interview:** Current tracer process, data ownership, reporting needs, placement-time definition, RA 10173 posture.
  * **Phase B — Graduate Questionnaire:** Device access, willingness to submit via web/mobile, response habits.
  * **Phase C — Artifact Review:** Existing survey forms, report templates, de-identified spreadsheets to establish baselines.
  * **Phase D — Endorsement Letter:** Execute the signed partnership agreement before the mock defense.
* **Convergence Goal:**
  * Clear Gates 0–2: replace every `[TO VALIDATE]` and `[HYPOTHESIS]` marker with client evidence before the final Title Defense and Chapter 1 documentation.
