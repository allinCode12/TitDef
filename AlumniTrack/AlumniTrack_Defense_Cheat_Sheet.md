# AlumniTrack Defense Cheat Sheet

**Proposed Working Title:**  
*AlumniTrack: An AI-Assisted Web and Mobile-Based System for Graduate Employment Monitoring, Placement Analytics, and Course-to-Career Alignment for a Higher Education Institution*  
*(Base wording by Canido lacked the "…for a Higher Education Institution" element — added for Module 1 compliance; pending approval)*  
**Client Partner:** ⛔ Gate 0 — none yet

---

## 1. 30-Second Elevator Pitch (pre-client version — honest)

> *"AlumniTrack is our proposed web and mobile system for continuously monitoring graduate employment status, job placement time, and course-to-career alignment. Graduates update their employment outcomes from their phones, and the client office sees consolidated, program-level views on one dashboard instead of periodic manual consolidation. This direction was suggested by our course advisor after our first title was rejected for lacking a real client — so our first gate is securing and interviewing that real institutional client before we claim any problem as proven."*

---

## 2. The Golden Defense Rules for this Title

1. **Lead with the Gate 0 story, don't hide it (The ResiboCheck Lesson):**
   - If asked: *"Where is your client?"*
   - **Answer:** *"We don't have one secured yet — and that is exactly the lesson from our first title, which was rejected for lacking a real client. Our advisor suggested this direction, and our first gate is to secure a real institutional office, interview them, and obtain an endorsement before claiming any problem as fact."*
2. **Never Invent Baseline Figures:** No response rates, employment percentages, or placement-time numbers — ever — until client records exist. Use `[TO VALIDATE]`.
3. **Alumni data = personal data (RA 10173):** Privacy-by-design, consent, data minimization, and retention rules are part of the design, not an afterthought.
4. **Respect Scope Boundaries (Don't let the panel expand your project):**
   - **NO** job-posting board or recruiter marketplace.
   - **NO** employer/payroll verification (data is self-reported).
   - **AI is scoped, not judgmental** (per 2026-10-08 consultation — the advisor requires AI/Analytics in all titles): career-track classification of reported roles with an editable, transparent mapping (office staff correct misclassifications) + placement-risk flags that prompt attention — never employability verdicts on graduates, no autonomous decisions.
   - **NO** current-student tracking or social features.
5. **Self-reported ≠ audited:** The system reports what graduates *say*; never present its outputs as verified employment statistics.

---

## 3. High-Frequency Panel Questions & Winning Answers

| Panel Question | Best Defensible Answer | Course Traceability |
|---|---|---|
| **Where is your client?** | Gate 0, openly stated: none secured yet. Our first title was rejected for exactly this gap; the advisor's feedback was to work with a real client, and this direction came from that advice. Securing the office + endorsement is our first action item. | Shelly Ch. 2: Systems request must be real |
| **Isn't this just a Google Form?** | A form captures one response; the design is for continuous status *updates*, placement-time computation, and program-level alignment views with dashboards. Whether that matches the client's actual need is what the Gate 2 interview decides. | Module 1: root cause vs. symptom |
| **Why web AND mobile for alumni?** | The two roles differ: alumni are dispersed and phone-first after graduation `[TO VALIDATE with graduate survey]`; the admin office works at a desk consolidating reports. The split follows context of use, not headcount. | WMA: context-of-use justification |
| **Will graduates actually respond?** | Unknown — response rate is our first empirical question. The design answers it with simple UX and consented reminders, and we will report honest limits if participation stays low. | Module 2: Operational feasibility |
| **Isn't alumni data sensitive?** | Yes — RA 10173 applies. Consent capture, data minimization, role-based access, export logging, and retention/deletion rules are designed in from the start, coordinated with the client's DPO. | Module 1: Ethics; Module 3: NFR |
| **What's new vs existing systems?** | Continuous self-reporting + placement-time + course-to-career view in one flow — *novelty claimed only for the client's confirmed process, pending verification of what they use now.* | Module 3: Claim classification |
| **What if data is false/fabricated?** | Data is labeled self-reported; the system timestamps and flags but does not audit — verification is out of scope and stated as a limitation. | Module 1: Scope/delimitation |
| **Which comes first — client or title?** | Client. The title's final wording (including the named setting) depends on who endorses it; the panel approves the wording after Gate 0. | Bender: stepwise commitment |
| **Why is your client your own school? Isn't that convenient?** | It is a real institutional office with a real process and a real process owner — the endorsement must come from that office head in official capacity, not from a teacher doing us a favor. We are students of the institution, which gives access but not authority: if the office tells us their current process works, we report that honestly. We disclose the relationship the same way CrewSync discloses its. | Module 1: Ethics — disclosed relationships |
| **How will you evaluate success?** | ISO/IEC 25010 Likert survey (usability, functional suitability, security/privacy) with admin users and a graduate sample, plus before/after comparison of consolidation effort and response tracking `[baseline TO VALIDATE]`. | Module 3: Quality model & evaluation |
| **Why does this need AI?** | Per advisor requirement, AI and analytics are integrated across all titles. Scoped component: career-track classification of reported roles (editable mapping, correctable by the office) and placement-risk flags (e.g., still searching at 6+ months) that prompt the office to act — never employability verdicts and no autonomous decisions. Evaluated by agreement with the office's manual coding. | Module 4: Rules + Module 3: Evaluation · consultation 2026-10-08 |
| **Isn't this redundant with CrewSync?** | Same team, different client, different problem: CrewSync = internal event-staffing workflow for a service business; AlumniTrack = institutional outcome monitoring for a HEI. Both follow the same evidence-first method. | Portfolio framing |

---

## 4. Key `[TO VALIDATE]` Items to Clear with your Client (Gate 2)

| Item | What to Ask / Validate with the Client Office |
|---|---|
| **Current Tracer Process** | How are graduates surveyed today — tool, frequency, who consolidates, where data lives? |
| **Volume & Cadence** | Graduates per year? Reporting deadlines? How many reporting periods? |
| **Response Rate** | What was the actual response rate of the last cycle? *(Ask for records — do not estimate.)* |
| **Placement-Time Definition** | How does the institution officially define job placement time? (BR-A02 needs their formula.) |
| **Course-to-Career Mapping** | Which fields/industries count as "aligned" per program? Who decides? |
| **Data Ownership & RA 10173** | Who owns alumni data? Is there a DPO? Existing consent/retention rules? |
| **Reporting Consumers** | Who reads the outputs — accreditation? leadership? departments? In what format? |
| **Channel Reach** | How can graduates be reached (email, FB page, SMS)? Device habits? |
| **Endorsement** | Will the office sign the endorsement letter? |

---

## 5. "Isn't the Scope Too Big / Too Small?" Questions

### Q1. "Isn't a survey dashboard too simple for a capstone?"
> "The dashboard is the visible surface. Underneath are longitudinal records (updates over time, never silent overwrites), placement-time computation per cohort, transparent course-to-career mapping, consent management under RA 10173, and role-based access to personal data. The client interview determines which of these the institution actually needs — we will cut anything they don't."

### Q2. "Why not just use Google Forms + Sheets?"
> "That is likely what we will find the client doing today — and if the client confirms that method fully meets their needs, operational feasibility weakens and we must resize the project honestly. The design argument is that forms capture one moment; tracking placement time and alignment across cohorts needs stored, updatable, attributable records with dashboards — but that argument is a hypothesis until Gate 2."

---

## 6. Red Flags: Claims You Should NOT Make Without Evidence

Avoid these statements unless primary evidence supports them:

- "Response rates are low." / "Response rates are X%."
- "The current process takes hours/days."
- "Employment data is outdated."
- "Graduates prefer mobile apps."
- "There is no system for this today."
- "Our system verifies employment."
- "This is the first system of its kind."
- "The client will definitely adopt it."
- "We have a client." *(Not until Gate 0 clears.)*
- "Salary data will be collected." *(Only if client + consent justify it.)*

Use `[TO VALIDATE]` or `[HYPOTHESIS]` where appropriate.

---

## 7. Defense Mindset

The goal is **not to impress the panel with a polished problem that you haven't proven**.

The goal is to demonstrate:

1. We took the rejection feedback seriously — client first, evidence second.
2. We can frame a plausible problem *as a hypothesis*.
3. We have a proposed solution aligned to WMA specialization.
4. We know exactly which parts are still assumptions.
5. We have a gate plan (0 → 1 → 2 → 3) to validate before committing.

### Strong closing statement

> **"We treat this title as an advisor-suggested direction, not a proven problem. Our first gate is a real institutional client; our second is evidence from their actual process. We will not claim response rates, pain points, or novelty before those gates clear — that discipline is exactly what our first title's rejection taught us."**

---

## 8. Evidence Status Snapshot

**Confirmed:**
- Advisor suggested this direction after the first title's rejection (team-reported).
- Team + specialization (WMA) + course (IT0037).

**Everything else is open:**
- Client identity and endorsement ⛔ Gate 0
- Current tracer process, volumes, response rates
- Placement-time definition; course-to-career mapping rules
- RA 10173 posture (consent, retention, DPO)
- Graduate device/channel habits

**Do not convert any of these into facts in the defense.**
