# AlumniTrack — Project Context Pack

> **Purpose of this file:** Single source of truth for the AlumniTrack capstone title. Give this file to any teammate or tool (slides, documentation, design, code) so everything stays consistent with the title, scope, client status, and IT0037 course lessons.
>
> **Version:** 0.1 (pre–client, pre–mock defense) · **Owner:** AzTech (Group 6) · **Proposer:** Canido · **Status:** ⛔ **Gate 0 — NO CLIENT YET.** Title suggested by the course advisor after the ResiboCheck rejection. Title not yet approved.
>
> **Governing lesson (from ResiboCheck):** *Have a real client.* No pack content below this line may be treated as fact until a real institutional client is secured and interviewed. Every client-dependent item is `[TO VALIDATE]`.

---

## 0. Gates

| Gate | Requirement | Status |
|---|---|---|
| **Gate 0 — Client** | Secure a real institutional client (alumni/registry/careers office or similar) willing to be interviewed and endorse the project | ⛔ **OPEN — first priority** |
| **Gate 1 — Title** | Panel approves the title (including the Users/Setting element fix in §1) | ⛔ Not yet approved |
| **Gate 2 — Evidence** | Complete client interview + document review; clear `[TO VALIDATE]` items | Not started |
| **Gate 3 — Full proposal** | Requirements baselined, feasibility confirmed, endorsement signed | Not started |

---

## 0.1 Rules for anyone using this file

1. **Do not invent evidence.** No interviews, observations, or graduate records have been collected. Never state response rates, employment statistics, placement times, or pain points as fact. Use `[TO VALIDATE]`.
2. **Gate 0 discipline.** Do not present AlumniTrack as a client-backed project. It is an *advisor-suggested direction without a secured client* — that gap is exactly what sank ResiboCheck.
3. **Alumni data is personal data (RA 10173).** Employment status, salary, contact details, and career outcomes are personal information under the Data Privacy Act. Privacy-by-design is mandatory from Day 1.
4. **Respect the scope (Section 6).** No job-posting board, no recruiter marketplace, no social network, no payroll verification, no AI career coach in this version.
5. **Treat "low survey response rates" and "spreadsheet chaos" as hypotheses**, not findings, until the client interview says so.
6. **Keep course lessons traceable (Section 9).**
7. The actual defense, oral checks, quizzes, and exams are **AI-use prohibited**. The presenter must understand and own every claim.
8. **Own-institution relationship (disclose, don't hide):** the prospective client is an office within FEU Diliman, our own school. There is **no family/relative relationship** (unlike CrewSync) — but access to our own institution must still be disclosed, and the endorsement must come from the office head in official capacity, never from a classmate/teacher doing the team a favor. If the office says the current process is fine, we report that honestly.

---

## 1. Project identity

| Field | Value |
|---|---|
| **Title (submitted by Canido — missing Users/Setting element)** | AlumniTrack: A Web and Mobile-Based System for Monitoring Graduate Employment Status, Job Placement Time, and Course-to-Career Alignment |
| **Title (v2 — per 2026-10-08 consultation: AI/algorithm/analytics required for all titles; pending approval)** | AlumniTrack: An AI-Assisted Web and Mobile-Based System for Graduate Employment Monitoring, Placement Analytics, and Course-to-Career Alignment for a Higher Education Institution |
| **Alt. title (client-named variant — only after Gate 0 + panel authorization)** | AlumniTrack: … for [Client Institution Name] |
| **Specialization** | BSIT — Web and Mobile Application |
| **School / course** | FEU Diliman · IT0037 Systems Analysis and Design |
| **Client** | ⛔ **Gate 0 — prospective only:** an office **within our own institution (FEU Diliman)** — alumni/registry/careers/ICT office `[OFFICE TO IDENTIFY; endorsement not yet secured]` |
| **Users (planned)** | Alumni/graduates (web + mobile), Institutional admin — alumni office/staff (web) |
| **Not users** | Students (current), recruiters, general public |

> **Module 1 note:** the submitted title covers Capability (monitoring employment status, placement time, course-to-career alignment) and Value, but is **missing the Users/Setting element** — CrewSync's title ends "…for a Party Service Business"; ours must end "…for [a HEI / named client]". Fixing this is part of Gate 1.

### One-line pitch (working)
Graduates update their employment status from their phones, and the institution sees, on one dashboard, how long graduates take to land jobs and how well each course aligns with where graduates actually end up.

### Short description (draft — every claim tagged)
AlumniTrack lets a graduate submit or update employment status, job placement, and course-relevant career information through a web or mobile interface `[TO VALIDATE — is this the client's actual need?]`. The institution's admin panel consolidates responses, tracks job placement time, and summarizes course-to-career alignment per program `[TO VALIDATE — existing process?]`. The current process is expected to be a periodic tracer survey with manual consolidation `[HYPOTHESIS — confirm in Gate 2 interview]`.

---

## 2. Problem framing (all hypotheses until Gate 2)

### Symptom vs. root cause (Module 1)
- **Symptoms (hypothesized, to validate):** tracer/survey data scattered across forms and spreadsheets; graduates contacted in batches once or twice a year; employment figures outdated by the time they are reported; no way to see updates between survey cycles.
- **Root cause (working hypothesis):** **no continuous, structured channel for graduates to report employment status**, so institutional data depends on periodic manual survey campaigns.
- Neither line above is a finding. Both die if the client says otherwise.

### Problem statement (draft)
Higher education institutions are expected to report graduate employment outcomes `[TO VALIDATE — which office, which reports?]`. Data is currently gathered through [periodic survey / manual interview / other — `[TO VALIDATE]`], which makes [specific pain — `[TO VALIDATE]`]. AlumniTrack proposes a continuous web and mobile channel for graduates to self-report, with an admin dashboard for consolidation and course-to-career analysis `[TO VALIDATE need]`.

### Evidence status

| Evidence | Status |
|---|---|
| Advisor suggested this direction after ResiboCheck rejection | ✅ Stated by team |
| A real institutional client exists | ⛔ **No — Gate 0** |
| Current tracer/survey process | ❌ Pending client interview |
| Graduate volume per year | ❌ Pending |
| Response rate of current process | ❌ Pending (no numbers may be cited) |
| Who owns/holds alumni data today | ❌ Pending |
| Reporting obligations (who consumes the figures) | ❌ Pending |
| RA 10173 / consent arrangements for graduate data | ❌ Pending |
| Device/connectivity habits of alumni | ❌ Pending questionnaire |

### Stakeholders (Module 3 — preliminary, to confirm at Gate 2)

| Stakeholder | Role / lens | Interest |
|---|---|---|
| Alumni office / registrar / ICT staff | Process owner, sponsor, admin user | Accurate, current, reportable graduate outcomes data |
| Graduates / alumni | Direct users (web + mobile) | Easy, privacy-respecting updates; something in return (network value) |
| Academic departments / program chairs | Consumers of course-to-career summaries | Program-level alignment insight |
| School leadership / accreditation bodies | Report consumers `[TO VALIDATE]` | Compliant, defensible figures |
| Adviser & panel | Governance | Evidence, scope, feasibility, ethics |

**Power–interest (Module 1):** Sponsor office = manage closely · Graduates = keep informed / involve (high interest, direct users) · Departments = keep informed.

---

## 3. Background (secondary context — keep claims general)

- Tracer studies / graduate outcome surveys are a recognized practice in higher education, often tied to accreditation `[cite a real source before using; otherwise drop]`.
- Institutions commonly collect responses through forms and consolidate in spreadsheets `[HYPOTHESIS — verify with client]`.
- Alumni employment data is **personal data under RA 10173** — collection requires a lawful basis, transparency, and retention limits.

> Do not add statistics (national employment rates, response-rate benchmarks) without a checkable source. **Client evidence matters more than national statistics.**

### Related systems / alternatives (for "What's new?")

| Alternative | What it does | Gap AlumniTrack fills |
|---|---|---|
| Generic survey tools (Google Forms, Microsoft Forms) | One-shot data capture | No continuous profile, no longitudinal placement-time tracking, no course-alignment view, consolidation is manual `[verify each claim before stating]` |
| Spreadsheet consolidation | Stores responses | No update flow, no dashboards, error-prone consolidation `[validate as client's actual method]` |
| Institutional MIS / SIS | Holds student records | Usually stops at graduation; alumni outcomes not maintained `[validate]` |
| Commercial tracer-study platforms | Purpose-built outcome tracking | Subscription cost; confirm capabilities before naming `[verify]` |

**Differentiator (claimed design intent, not proven novelty):** continuous alumni self-reporting (web + mobile) + job-placement-time tracking + program-level course-to-career alignment view for one real institutional process.

---

## 4. Objectives (draft)

### General objective
To develop a web and mobile system that enables a partner higher education institution to continuously collect and monitor graduate employment status, job placement time, and course-to-career alignment.

### Specific objectives (draft)
1. Develop an alumni-facing interface (responsive web + mobile/PWA) for graduates to submit and update employment status, position, industry, and course-relevance information.
2. Develop an admin web panel for the client office to manage programs, review submissions, and track job placement time per graduate/cohort.
3. Implement course-to-career alignment summaries (per program) using AI-assisted career-track classification with an editable, transparent mapping — flags and indicators only, never employability verdicts on graduates.
4. Implement role-based access, consent capture, and activity logging consistent with RA 10173.
5. Evaluate the system with the client office and a sample of graduates using selected ISO/IEC 25010 characteristics, and compare data currency/completeness before and after use `[baseline TO VALIDATE]`.

### Success measures (fill after Gate 2)

| Indicator | Baseline | Target | Source |
|---|---|---|---|
| Response/completion rate of graduate submissions | `[TO VALIDATE]` | `[set after baseline]` | Current survey records vs. system logs |
| Time to produce a consolidated employment report | `[TO VALIDATE]` | `[set]` | Client interview + document timestamps |
| % of records updated within the reporting cycle | `[TO VALIDATE]` | `[set]` | System logs |
| ISO/IEC 25010 survey weighted mean | — | `[set]` | Likert survey |

---

## 5. How the system works (draft workflow — confirm with client)

1. **Admin sets up:** academic programs, batches/cohorts, survey/reporting periods.
2. **Graduate is invited** (link/code via email/social page) to create or update a profile `[invitation channel TO VALIDATE]`.
3. **Graduate submits (web/mobile):** employment status (employed/self-employed/further studies/searching `[categories TO VALIDATE]`), position, industry, date of first employment, salary band **(optional — RA 10173 sensitivity, consent-gated)**, course-relevance rating/field.
4. **System computes:** job placement time (graduation date → first employment date) and stores program attribution.
5. **Admin dashboard:** cohort summaries, placement-time views, course-to-career alignment tables; export for reports `[report formats TO VALIDATE]`.
6. **Reminders:** follow-up prompts to non-respondents through agreed channel `[TO VALIDATE]`.
7. **Privacy:** consent recorded; data access restricted by role; retention/deletion rules `[TO VALIDATE with client DPO]`.

---

## 6. Scope and limitations

### In scope (draft)
- Alumni-facing responsive web + mobile/PWA submission interface
- Admin panel: programs, cohorts, submissions review, reminders, dashboards, exports
- Placement-time and course-to-career summaries (transparent rules)
- Accounts/roles, consent capture, activity log, data export/deletion tools

### Limitations / delimitations

| Item | Reason |
|---|---|
| No job-posting board or recruiter marketplace | Different product; scope control |
| No salary/payroll verification with employers | Out of scope; self-reported data is labeled as such |
| AI-assisted career-track classification + placement-risk flags (no judgmental employability scores) | Per 2026-10-08 consultation, AI/Analytics required across titles. Classification is factual; mapping editable by the client office; risk flags prompt attention, never verdicts; no autonomy — office confirms; evaluation = agreement vs. manual coding |
| No current-student tracking | Graduates only |
| Self-reported data caveat | System reports *reported* outcomes, not audited outcomes — must be stated in evaluations |
| Single institution (one client) | Results not generalized |
| Data availability depends on alumni participation | Response rate is a client-side challenge `[TO VALIDATE]` |

---

## 7. Requirements (draft — validate with client)

### 7.1 Alumni interface (web + mobile/PWA)

| ID | Requirement | Priority | Acceptance criteria |
|---|---|---|---|
| ALU-01 | Graduate login / invitation-code access | Must | Only verified graduate can submit own record `[method TO VALIDATE]` |
| ALU-02 | Submit/update employment status | Must | Save and edit own record before deadline; changes timestamped |
| ALU-03 | Placement details (position, industry, employment type, start date) | Must | Required fields enforced per client's form `[fields TO VALIDATE]` |
| ALU-04 | Course-relevance input | Must | Graduate maps own role to program per transparent options |
| ALU-05 | Consent + privacy notice | Must | Consent recorded with timestamp; withdraw/delete path offered (RA 10173) |
| ALU-06 | View own submission history | Should | Own record only |

### 7.2 Admin panel

| ID | Requirement | Priority | Acceptance criteria |
|---|---|---|---|
| ADM-01 | Admin login / role-based access | Must | Only authorized staff access alumni data |
| ADM-02 | Manage programs, cohorts, reporting periods | Must | Submissions map to correct program/cohort |
| ADM-03 | Review/flag submitted records | Should | Flags visible; edits logged (no silent edits) |
| ADM-04 | Reminder campaigns to non-respondents | Should | Channel per client policy `[TO VALIDATE]` |
| ADM-05 | Dashboard: response rate, placement time, course-to-career tables | Must | Figures reproducible from underlying records |
| ADM-06 | Export (CSV/PDF) for reports | Should | Matches agreed report format `[TO VALIDATE]` |
| ADM-07 | Activity log + consent report | Must | Who accessed/changed what, when |

### 7.3 Non-functional (ISO/IEC 25010 — selected)

| ID | Characteristic | Requirement |
|---|---|---|
| NFR-01 | Performance efficiency | Page/report load `[X]` seconds `[set post-test]` |
| NFR-02 | Security | Role-based access; hashed passwords; HTTPS |
| NFR-03 | Privacy (RA 10173) | Data minimization; consent records; retention/deletion rules `[to define]` |
| NFR-04 | Usability | Graduate completes a submission in `[N]` minutes/taps `[set post-test]` |
| NFR-05 | Reliability / accuracy | Placement-time computed consistently from stored dates; no silent overwrites |

### 7.4 Deliberately excluded (Won't, this version)
Job board · recruiter portal · employer verification · AI matching · current-student features · social features · multi-institution support

---

## 8. Data model and behavior (draft)

### 8.1 Entities (logical)

| Entity | Key attributes |
|---|---|
| User | user_id, name, role (Admin/Alumni), contact, status |
| Program | program_id, name, college/dept |
| Cohort | cohort_id, program_id, graduation_date |
| Graduate | grad_id, cohort_id, user_id, consent_status, consent_date |
| EmploymentRecord | record_id, grad_id, status, position, industry, employment_type, start_date, salary_band (optional), course_relevance, submitted_at, updated_at |
| ReportingPeriod | period_id, name, open/close dates |
| ActivityLog | log_id, user_id, action, target, timestamp |

### 8.2 Relationships
- Program 1—* Cohort *—1 Graduate 1—* EmploymentRecord
- Graduate 1—1 Consent (timestamped, withdrawable)
- ReportingPeriod 1—* submissions; User 1—* ActivityLog

### 8.3 Business rules

> **Status: all business rules below are PROPOSED design decisions — none are confirmed until the Gate 2 client interview.**

- BR-A01: A graduate may hold only one *active* record per reporting period; later submissions update (timestamped), never silently overwrite.
- BR-A02: Job placement time = first employment start date − cohort graduation date (formula `[TO VALIDATE — client's official definition]`).
- BR-A03: Course-to-career alignment is derived from transparent, admin-configurable field/industry mappings — no hidden scoring.
- BR-A04: Non-respondents may be reminded only through channels covered by the consent/privacy notice `[TO VALIDATE]`.
- BR-A05: Salary band is optional and consent-gated; refusal never blocks submission `[TO VALIDATE — client requirement]`.
- BR-A06: Only admins in authorized roles can view/export identifiable records; exports are logged.
- BR-A07: Graduates may request copy/deletion of their data subject to institutional retention obligations (RA 10173) `[retention rule TO VALIDATE]`.

---

## 9. IT0037 lessons mapped

### Module 1 — Systems Analysis Fundamentals
| Concept | Application |
|---|---|
| Symptom vs. root cause | Hypothesized symptoms in §2; root cause = no continuous reporting channel (unverified) |
| Four title elements | §1 — capability present, **users/setting missing → Gate 1 fix** |
| Ethics red flags | RA 10173 personal data; consent; no inflated claims; **Gate 0 honesty (no client yet)** |
| Stakeholder power–interest | §2 |
| Hybrid approach (rationale) | Prototyping (alumni form UX) + Agile sprints + stage gates |
| Web & Mobile lens: service journey | Invite → identify → submit → consent → track → reminder → report |

### Shelly Ch. 2 — Systems Planning
| Concept | Application |
|---|---|
| Systems request | Expected from the client office — **must be real (Gate 0)** |
| Preliminary investigation (6 steps) | Gates 0–3 map to understand → scope → fact-find → feasibility → time/cost → present |
| Constraints | Mandatory: RA 10173; External: alumni participation/device access; Present: one institution |
| Tangible / intangible benefits | Tangible: consolidation time, response tracking; intangible: accreditation confidence, graduate engagement `[all TO VALIDATE]` |

### Bender — SDLC
| Concept | Application |
|---|---|
| Stepwise commitment | Commit only after Gate 0 client confirms process and data ownership |
| Change control | Job board / recruiter features handled as scope changes |
| User involvement | Admin office accessible; alumni sampled for usability |

### Module 2 — Feasibility (preliminary — pre-client)
| Dimension | Preliminary view | Condition / unknown |
|---|---|---|
| Technical | Feasible — form/web/PWA + dashboard + relational DB are standard | Institution's IT constraints; email/SMS channels `[test]` |
| Operational | **Unknown / Conditional — no client yet (Gate 0)** | Who owns the process; alumni willingness |
| Economic | Conditional | Hosting trivial at low volume; reminder channel costs (SMS) `[estimate in PHP]` |
| Schedule | Conditional | Gate 0 timing dominates; remaining term |
| Security | Conditional | Role-based access, HTTPS, hashed passwords, export logging |
| Legal and ethical | Conditional | **RA 10173 core:** lawful basis, consent, retention, DPO coordination `[TO VALIDATE]` |

**Assumptions register**

| # | Assumption | Validation action |
|---|---|---|
| A1 | A HEI office wants/needs continuous alumni outcome data | Gate 2 interview |
| A2 | Current process is periodic manual survey | Interview + artifact review |
| A3 | Graduates will respond through web/mobile | Sample alumni questionnaire |
| A4 | Placement time & course-to-career are official reporting needs | Interview + report templates |
| A5 | Institution can lawfully collect listed fields | DPO/consent review |
| A6 | Response channel (email/social) reachable | Interview |

**Key risks (cause → event → impact)**

| Risk | Response |
|---|---|
| Gate 0 fails — no client endorses | **Project cannot proceed** (ResiboCheck lesson); widen candidate list |
| Low alumni response → empty dashboards | Reminders, multi-channel invite, simple UX; honest evaluation of limits |
| RA 10173 complaint over graduate data | Consent-first design, minimization, DPO involvement |
| Panel says "this is just a Google Form" | Differentiator = longitudinal tracking + dashboards + alignment — **only if client evidence supports** |
| Self-reported data challenged as unverifiable | Label findings as self-reported; scope excludes audit |
| Scope creep (job board, AI matching) | Change control; future work |

---

## 10. Development approach and evaluation

- **Approach:** Hybrid — prototyping (alumni submission flow with real graduates) + Agile sprints + stage gates (Gate 0 client → title approval → design approval → pilot).
- **Pilot:** one cohort or reporting period alongside existing method `[N TO VALIDATE]`.
- **Evaluation:** ISO/IEC 25010 Likert survey (usability, functional suitability, security/privacy, reliability) with admin users and graduate sample; before/after comparison of consolidation effort and response tracking `[baseline TO VALIDATE]`.

### Suggested stack (NOT decided)
- Alumni interface: responsive web / PWA (low friction, no install barrier) `[PWA vs native TO VALIDATE — where are the alumni?]`
- Admin: web panel · Backend: Node/Laravel/Django · DB: PostgreSQL/MySQL
- Reminders: email first; SMS optional `[cost]` · Analytics: server-side, consent-aware

---

## 11. Data gathering plan

| Method | Participants | Purpose | Gate |
|---|---|---|---|
| Interview | Prospective client office (alumni/registry/careers/ICT) | Current tracer process, data ownership, reporting needs, endorsement | **Gate 0/2** |
| Document review | Existing survey forms, report templates, spreadsheets (de-identified) | Field list, placement-time definition, formats | Gate 2 |
| Questionnaire | Sample graduates `[channel TO VALIDATE]` | Device access, willingness, response habits | Gate 2 |
| Observation | Admin consolidating a report | Baseline effort/time | Gate 2 |
| Endorsement letter | Client office head | Formal commitment | Before mock defense |

**Honest answer if asked "Where is your client?":** *"This direction was suggested by our course advisor after our first title was rejected for lacking a real client. Securing and interviewing a real institutional client is our first gate — we will not claim client evidence before that exists."*

---

## 12. Defense Q&A bank (draft — expand in the cheat sheet)

| Question | Answer |
|---|---|
| Where is your client? | Gate 0 — being secured; that gap is precisely the lesson from our first title's rejection. |
| Isn't this just a Google Form? | A form captures one response; the system is for longitudinal status tracking, placement-time computation, and program-level alignment views — **subject to confirmation that this matches the client's real need**. |
| Why web + mobile? | Alumni are off-campus and phone-first `[TO VALIDATE with sample survey]`; admin work is desk-based. |
| Isn't alumni data sensitive? | Yes — RA 10173 applies; consent, minimization, retention rules, role-based access are designed in from the start. |
| Will graduates actually respond? | Unknown — response rate is our first empirical question `[TO VALIDATE]`; reminders and simple UX are designed against it. |
| What's new? | Continuous self-reporting + placement-time + course-to-career view for one real institutional process `[novelty TO VALIDATE]`. |
| Methodology? | Hybrid: prototyping + Agile + stage gates. |
| Evaluation? | ISO/IEC 25010 survey + before/after consolidation effort. |

---

## 13. Mock defense deck outline

| # | Slide | Source |
|---|---|---|
| 1 | Title (+ four-element breakdown; note Gate 1 fix) | §1 |
| 2 | The client setting + Gate 0 status disclosure | §1, §0 |
| 3 | Current tracer process (as-is) + evidence status | §2 |
| 4 | Problem: symptoms vs. root cause + stakeholders | §2 |
| 5 | Objectives | §4 |
| 6 | How it works (flow) | §5 |
| 7 | Key logic: records, placement time, alignment rules | §8 |
| 8 | Related systems + differentiator | §3 |
| 9 | Scope and limitations (incl. self-reported caveat) | §6 |
| 10 | Context diagram + key requirements | §7, §9 |
| 11 | Feasibility (six dimensions — pre-client) + risks | §9 |
| 12 | Methodology + evaluation | §10 |
| 13 | Data gathering plan + Gate 0/endorsement status | §11 |

---

## 14. Sources

- Course advisor's suggestion of the direction (record when/what was said `[TO VALIDATE exact advice]`)
- No client sources yet — this section stays empty until Gate 0 clears
- Any tracer-study practice claims: cite real, checkable sources before using

---

## 15. Open items / next steps

- [ ] **Gate 0: identify and secure a real client office** (candidate list + approach script — see Interview Guide)
- [ ] Agree on final title wording (incl. Users/Setting element) with team, advisor, panel
- [ ] Interview client office; collect existing survey form/report templates
- [ ] Graduate questionnaire (devices, willingness, channel)
- [ ] Confirm RA 10173 posture with client (consent text, retention, DPO)
- [ ] Decide placement-time definition (BR-A02) with client
- [ ] Decide PWA vs native after alumni device survey
- [ ] Replace every `[TO VALIDATE]` with evidence or keep as labeled assumption
- [ ] Draft context diagram, Level 0 DFD, ERD, state diagrams
