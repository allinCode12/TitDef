# JobFlow — Project Context Pack

> **Purpose of this file:** Single source of truth for the client-based capstone title. Give this file to any teammate or tool (slides, documentation, design, code) so everything stays consistent with the title, scope, client, and IT0037 course lessons.
>
> **Version:** 0.1 (pre–client fact-finding) · **Owner:** `[assign a team member]` · **Client:** `[TO VALIDATE — print shop]` · **Status:** Title selected (Candidate A); no client secured yet
>
> **Working name:** "JobFlow" is a placeholder. Alternatives: *PrintSeq*, *QueueCraft*, *ShopFlow*, *GanttPrint*. Pick one with the team and client, then find/replace.

---

## 0. Rules for anyone using this file

1. **Do not invent evidence.** No interviews, observations, or job records have been collected yet. Never state job volume, idle time, setup time, late-delivery rate, or any pain point as fact. Use `[TO VALIDATE]`.
2. **Disclose the conflict of interest.** If the shop owner is a relative/neighbor of a team member, state it openly and triangulate with observation and records (Module 1 ethics: "hidden conflicts" is a red flag).
3. **Respect the scope (Section 6).** No printer/hardware integration, no design/proofing editor, no payments, no payments-to-customers, no inventory, no customer-facing ordering in this version.
4. **Framing rule:** The pitch is *production scheduling across machines*, not "an app for a print shop" and **not** a file/format/proof tool.
5. **Owner/planner and operators are the users.** Customers who drop off files are not users.
6. **Keep course lessons traceable (Section 9).**
7. The actual defense, oral checks, quizzes, and exams are **AI-use prohibited**. The presenter must understand and own every claim.

---

## 1. Project identity

| Field | Value |
|---|---|
| **Title (v1 draft — Title 3 candidate, pending prof approval + client)** | JobFlow: An AI-Assisted Web and Mobile-Based System for Production Job Sequencing and Machine Utilization Analytics for a Print Shop Business |
| **Alt. title (client-named variant — only if panel authorizes)** | JobFlow: An AI-Assisted Web and Mobile-Based System for Production Job Sequencing and Machine Utilization Analytics for `[Client Shop Name]` |
| **Specialization** | BSIT — Web and Mobile Application |
| **School / course** | FEU Diliman · IT0037 Systems Analysis and Design |
| **Client** | `[TO VALIDATE]` — a print shop (tarpaulin/large-format, thesis/album, shirt/DTF, or digital-copy) |
| **Users** | Owner / Planner (web panel), Machine Operators (mobile app) |
| **Not a user** | Customers — they submit jobs through the shop's existing channels (walk-in, Messenger, email) |

### One-line pitch
When several jobs are queued, the system decides which job runs on which machine and in what order — minimizing idle time and hitting deadlines — and each operator confirms start/finish on a phone so everyone sees live status.

### Short description
`[Client]` runs several print machines (digital press, large-format, cutter, laminator, etc.) and currently decides the print order by experience, on a whiteboard or in their head `[TO VALIDATE]`. JobFlow lets the owner enter the day's jobs with their machine requirements, due dates, and priorities, and the system auto-generates an optimized schedule that reduces machine idle time and late jobs. Operators confirm job start/finish from the shop floor, feeding actual times back to the system, and the owner sees utilization analytics on one dashboard.

### Title breakdown (Module 1: four title elements)

| Element | In the title |
|---|---|
| Capability | Production Job Sequencing and Machine Utilization Analytics |
| Users / setting | Print Shop Business (`[Client]`) |
| Value / problem direction | Reduced idle time and on-time production; sequence-dependent setup minimization |
| Specialization differentiator | Web and Mobile (owner planning panel + operator mobile status app) |

> Note on naming: Module 1 warns against titles that hide the real transaction. The real transaction here is **"job order → auto-sequence across machines → operator confirms → status/queue tracked."** Keep "job sequencing" in the title.

---

## 2. Problem framing

### Symptom vs. root cause (Module 1)
- **Symptoms (hypothesized, to validate):** jobs pile up with no clear next-step; rush orders disrupt the plan; machines sit idle while work waits; deadlines/pickups are missed; the queue lives in the owner's head or a whiteboard `[TO VALIDATE]`.
- **Root cause (working hypothesis):** there is **no structured process to assign jobs to machines and sequence them**, so production order depends on experience, memory, and ad-hoc decisions rather than a repeatable schedule.

### Problem statement (draft)
`[Client]` processes multiple print jobs across several machines with different capabilities `[TO VALIDATE]`. Production order is currently decided manually `[TO VALIDATE]`, with no systematic handling of machine eligibility, sequence-dependent setup (paper/ink/size changes), due dates, or rush orders. As a result, machines may sit idle `[TO VALIDATE]` and jobs risk missing promised pickup times `[TO VALIDATE]`.

### Evidence status

| Evidence | Status |
|---|---|
| Client exists and runs print jobs on multiple machines | ❌ Pending |
| Client wants a dedicated scheduling system | ❌ Pending (get verbal → written endorsement) |
| Current scheduling workflow (how order is decided today) | ❌ Pending interview + observation |
| Daily/weekly job volume | ❌ Pending records |
| Machine list and job–machine eligibility | ❌ Pending observation |
| Switch categories (paper/ink/size) and setup times | ❌ Pending observation |
| Idle/starved machine incidents | ❌ Pending (owner recall + observation) |
| Missed deadlines / late pickups | ❌ Pending (records) |
| Operators' smartphone access | ❌ Pending questionnaire |

### Stakeholders (Module 3)

| Stakeholder | Role / lens | Interest |
|---|---|---|
| Owner / Planner | Process owner, sponsor, admin user | Hitting deadlines, less idle, clear plan |
| Machine operators | Direct users (mobile) | Clear "what's next on my machine," easy confirm |
| `[Assistant/foreman, if any]` | Possible admin user | Same as owner |
| Customers | Indirectly affected (not users) | Jobs finished on time |
| Adviser / panel | Governance | Evidence, scope, feasibility, ethics |

**Power–interest (Module 1):** Owner = manage closely · Operators = keep informed and involve (high interest, frontline) · Customers = monitor.

---

## 3. Background (secondary context — keep claims general)

- Small print shops typically run a **mix of machines** and take a mix of job types (tarpaulin, thesis, shirts, documents) `[cite a real source before using; otherwise drop]`.
- Many small Philippine businesses plan work on **whiteboards, spreadsheets, or memory** `[TO VALIDATE with client; do not state as fact]`.
- The scheduling problem class is well established: **Job-Shop Scheduling (JSP)**, with idle-time/setup minimization as the objective.

### Japanese research anchor (verified, citable)

| Anchor | Detail |
|---|---|
| **Source** | Nakano Lab, Hiroshima University (with NTT DATA). *Optimizing Heat Treatment Schedules via QUBO Formulation.* Applied Sciences 15(16):8847, 2025. doi:10.3390/app15168847 |
| **What they did** | Scheduled daily work across **multiple parallel furnaces** in an auto-parts heat-treatment factory, minimizing **idle time** from **switches (part group / cooling-fan speed)** while respecting **order priority**; deployed at Nagato Co., Tsukimi Plant; planning time **~2 h → ~1 s**; **human-in-the-loop** (presented to operators, not machine control). |
| **Why it anchors JobFlow** | Same problem family (JSSP-adjacent, multi-machine assignment + sequencing); the **switchover-cost** structure maps onto print-shop **paper/ink/size changeovers**. The paper is a **decision-support** system, not device integration. |
| **Related** | *Flexible Job Shop Scheduling with tool switching using quantum annealing.* JAMDSM 18(2), 2024. |

> Do not add statistics without a checkable source. For this title, **client evidence matters more than national statistics.**

### Related systems / alternatives (for "What's new?")

| Alternative | What it does | Gap JobFlow fills |
|---|---|---|
| Whiteboard / Excel / memory | Ad-hoc job order | No optimization, no idle/setup awareness, no live status |
| Generic job-shop scheduling software | Schedules machines | Built for large factories; subscription; not adapted to a small print shop's machine set `[verify each claim before stating]` |
| Print MIS/ERP suites | Full print management | Expensive, heavy, out of a small shop's reach `[verify]` |
| Manual dispatching rules | Simple priority order | Doesn't minimize sequence-dependent setup/idle |

**Differentiator:** an accessible **web+mobile FJSP scheduler** built for one small print shop's actual machines, with sequence-dependent setup handling, due dates, and human-confirmed execution.

---

## 4. Objectives

### General objective
To develop a web and mobile production scheduling system that helps `[Client]` sequence print jobs across machines, reduce idle time, and meet deadlines.

### Specific objectives (draft)
1. Develop a web panel where the owner records jobs (type, machine requirements, due date, priority) and selects eligible machines.
2. Develop a scheduling engine that assigns each job to a machine and sequences it, minimizing makespan and idle/setup time.
3. Develop a mobile app where operators confirm job start/finish and view their machine's queue.
4. Provide a live job-status board and analytics (machine utilization, idle %, on-time completion, queue length).
5. Implement an AI component for job-duration prediction from actual logged times, with rules-only cold start and human-in-the-loop.
6. Implement role-based access, activity logging, and data handling consistent with RA 10173.
7. Evaluate the system with the owner/operators using selected ISO/IEC 25010 characteristics, comparing planning time and idle before/after `[baseline TO VALIDATE]`.

### Success measures (fill after data gathering)

| Indicator | Baseline | Target | Source |
|---|---|---|---|
| Time to produce the day's plan | `[TO VALIDATE]` | `[set after baseline]` | Observation vs. system |
| Machine idle time per day | `[TO VALIDATE]` | `[set]` | Observation vs. system |
| On-time completion % | `[TO VALIDATE]` | `[set]` | Records vs. system |
| Predicted-vs-actual job duration error | — | `[set]` | System logs |
| ISO/IEC 25010 survey weighted mean | — | `[set]` | Likert survey |

---

## 5. How the system works

1. **Owner enters jobs (web):** job type, size/material, required machine capability, due date, priority, status: **Queued**.
2. **Eligibility filter:** each job is matched to machines that can process it (capability + size) `[rules TO VALIDATE]`.
3. **Scheduling engine:** assigns jobs to eligible machines and sequences them to minimize makespan + idle (sequence-dependent setup from paper/ink/size changes) `[method: dispatching rules + Tabu local search; QUBO optional]`.
4. **Publish schedule:** owner sees the generated plan on a Gantt/queue board; can adjust priorities and re-run.
5. **Operators execute (mobile):** each operator sees their machine's queue; confirms **Start** and **Finish**.
6. **Feedback loop:** actual times are logged → used by the AI to predict future job durations and by analytics.
7. **Rush handling:** owner inserts a rush job; engine re-sequences remaining work `[policy TO VALIDATE]`.
8. **After job:** status → Completed; machine free for next job.

---

## 6. Scope and limitations

### In scope
- **Owner/planner web panel:** login; manage machines and capabilities; manage jobs; run/rerun the scheduler; Gantt/queue board; rush insert; analytics dashboard; activity log
- **Operator mobile app (PWA or cross-platform):** login; view machine queue; confirm start/finish; report delays
- **Scheduling engine:** FJSP assignment + sequencing; sequence-dependent setup handling; due dates; priority; rush re-sequence
- **AI:** job-duration prediction from logged actual times (rules-first cold start; explains inputs; human confirms)
- Database for users, machines, jobs, schedule slots, setups, logs

### System boundary & assumptions (the two big exclusions)

| Excluded | Reason |
|---|---|
| **Printer/hardware integration** (autodiscovery, spooler, SNMP, drivers) | Not scheduling — it is systems integration; fails one-term scope (G4); brand/driver/OS-fragile. JobFlow sits **above** the printers as a decision-support layer and models a machine as a **logical resource** (capabilities + setup categories), so brand/driver never matters. Precedent: the Hiroshima QUBO++ system is human-in-the-loop decision support, not machine control. |
| **Design/proofing/format editing** (viewing files, checking DPI/format, editing designs) | Separate domain (prepress), out of scope; a different (non-OR) system |

### Other limitations / delimitations

| Item | Reason |
|---|---|
| No customer-facing ordering/upload portal | Customers use existing channels; scope control |
| No payments/billing | Separate system; future work |
| No inventory (paper/ink stock) | Out of scope |
| Operators confirm start/finish **manually** (no device signals) | Keeps it brand-agnostic and one-term |
| AI predicts duration only; never decides the schedule | Per 2026-10-08 consultation, AI required in all titles; hard rules stay transparent; human confirms; rules-only cold start; evaluation = predicted-vs-actual duration |
| Single print shop (one client) | Evaluation limited to `[Client]`; results not generalized |

---

## 7. Requirements (draft — validate with client)

### 7.1 Owner/planner web panel

| ID | Requirement | Priority | Acceptance criteria |
|---|---|---|---|
| ADM-01 | Admin login | Must | Only admin manages machines/jobs |
| ADM-02 | Manage machines and capabilities | Must | A job only appears for capable machines |
| ADM-03 | Create/edit/cancel jobs (type, size, due date, priority) | Must | Cancelling frees the machine slot |
| ADM-04 | Run scheduling engine | Must | Produces an assignment + sequence for all queued jobs |
| ADM-05 | Gantt/queue board | Must | Reflects current schedule per machine |
| ADM-06 | Adjust priority and re-run | Should | Updated schedule reflects new priorities |
| ADM-07 | Insert rush job | Should | Remaining jobs are re-sequenced |
| ADM-08 | Analytics dashboard (utilization, idle %, on-time, queue) | Should | Totals match underlying records for the range |
| ADM-09 | Activity log | Should | Who did what, when |

### 7.2 Operator mobile app

| ID | Requirement | Priority | Acceptance criteria |
|---|---|---|---|
| OPR-01 | Operator login | Must | Each confirm is tied to an operator |
| OPR-02 | View machine queue | Must | Shows next/current job with details |
| OPR-03 | Confirm start / finish | Must | Timestamps recorded; status updates live |
| OPR-04 | Report a delay/blocker | Should | Owner sees it on the board |

### 7.3 Non-functional (ISO/IEC 25010 — selected)

| ID | Characteristic | Requirement |
|---|---|---|
| NFR-01 | Performance efficiency | Schedule for a day's jobs generated within `[X]` seconds |
| NFR-02 | Security | Role-based access; hashed passwords; HTTPS |
| NFR-03 | Security / privacy | Store only needed data; RA 10173 |
| NFR-04 | Interaction capability | Operator confirms start/finish in ≤ `[N]` taps |
| NFR-05 | Functional suitability | A job is never scheduled on an incapable machine (system-enforced) |

### 7.4 Deliberately excluded (Won't, this version)
Printer/hardware integration · design/proofing/format tools · customer portal · payments · inventory · multi-shop

---

## 8. Data model and behavior

### 8.1 Entities (logical)

| Entity | Key attributes |
|---|---|
| User | user_id, name, role (Admin/Operator), status |
| Machine | machine_id, name, capabilities, status |
| JobCapability | job_type / machine capability mapping |
| Job | job_id, type, size/material, due_date, priority, status |
| ScheduleSlot | slot_id, job_id, machine_id, sequence_index, planned_start, planned_end |
| SetupRule | setup_id, from_category, to_category, setup_minutes |
| Confirmation | confirm_id, slot_id, operator_id, actual_start, actual_finish |
| ActivityLog | log_id, user_id, action, target, timestamp |

### 8.2 Relationships
- Machine 1—* ScheduleSlot
- Job 1—* ScheduleSlot
- Job *—* Machine (via eligibility)
- SetupRule applies between consecutive ScheduleSlots on a machine
- ScheduleSlot 0..1—1 Confirmation; User (Operator) 1—* Confirmation

### 8.3 Business rules

> **Status: all business rules (BR-01 – BR-08) are PROPOSED — none are confirmed.** Present to the owner during the interview; confirm/adjust/reject before the final proposal. `[TO VALIDATE]` values are starting hypotheses.

- BR-01: A job can only be scheduled on a machine that has its required capability.
- BR-02: The engine assigns each queued job to one eligible machine and sequences it to minimize makespan + idle.
- BR-03: Sequence-dependent setup time applies between consecutive jobs on a machine based on paper/ink/size category change `[categories TO VALIDATE]`.
- BR-04: Jobs with earlier due dates/priorities are favored `[weighting TO VALIDATE]`.
- BR-05: A rush job triggers re-sequencing of remaining work `[policy TO VALIDATE]`.
- BR-06: Operators confirm start/finish; actual times are logged for prediction and analytics.
- BR-07: Only Admin may create/cancel jobs, change priorities, or manage machines.
- BR-08: The AI may propose a duration estimate; the engine and the human determine the actual schedule.

### 8.4 State models
**Job**
```
Queued ──scheduled──► Scheduled ──operator starts──► In Progress ──operator finishes──► Completed
Queued/Scheduled ──cancel──► Cancelled
```
**Machine**
```
Idle ──job active──► Running ──job done──► Idle
Running ──blocked/delay reported──► Delayed ──resolved──► Running
```

---

## 9. IT0037 lessons mapped

### Module 1 — Systems Analysis Fundamentals
| Concept | Application |
|---|---|
| Symptom vs. root cause | Idle machines/late jobs = symptoms; no structured job→machine sequencing = root cause |
| Evidence triangulation | Owner interview + operator input + observation of one production day + records |
| Four title elements | Section 1 |
| Ethics red flags | Conflict of interest disclosed; minimal data; no decorative-AI claims |
| Stakeholder power–interest map | Section 2 |
| Hybrid approach with reasons | Prototyping (schedule board) + Agile sprints + stage gates |
| Web & Mobile lens: service journey | Order → schedule (assign/sequence) → execute (confirm) → track (status) → analyze |

### Shelly Ch. 2 — Systems Planning
| Concept | Application |
|---|---|
| Systems request | The owner's own request — a real "systems request" from a business |
| Reasons for project | Better performance (utilization), more information (analytics), stronger control (repeatable plan) |
| Preliminary investigation (6 steps) | Understand problem → scope/constraints → fact-finding → feasibility → time/cost → present |
| Constraints | Mandatory: RA 10173; External: operators' devices; Present: one shop, no hardware integration |
| Fishbone | Causes of idle/late jobs: People, Process, Technology (no scheduler), Materials (switches), Schedule |
| Tangible / intangible benefits | Tangible: idle time, on-time %; intangible: owner peace of mind, operator clarity |

### Bender — SDLC
| Concept | Application |
|---|---|
| Stepwise commitment | Commit to build after the client confirms machines, jobs, and setup categories |
| Change control | Client requests (printer integration, proofing) handled as scope changes |
| User involvement | Client accessible — strong participation reduces risk |

### Module 2 — Feasibility (six dimensions)
| Dimension | Preliminary view | Condition / unknown |
|---|---|---|
| Technical | Feasible — web panel + mobile/PWA + scheduler + DB are standard | Scheduler quality for day-sized instances `[test]` |
| Operational | Likely feasible if pain is scheduling | Operator adoption; owner's willingness to leave the whiteboard |
| Economic | Conditional | Hosting `[estimate in PHP]` |
| Schedule | Conditional | Team skills; remaining term; client availability |
| Security | Conditional | Role-based access, HTTPS, hashed passwords, activity log |
| Legal and ethical | Conditional | RA 10173; consent for observation; conflict of interest disclosed |

**Assumptions register**

| # | Assumption | Validation action |
|---|---|---|
| A1 | Owner currently plans production manually (whiteboard/Excel/memory) | Interview + observation |
| A2 | Enough daily jobs that manual planning is a burden | Job records 1–3 months |
| A3 | Machines have distinct capabilities and switch categories | Observe machine list + changeovers |
| A4 | Operators have smartphones and can confirm start/finish | Operator questionnaire |
| A5 | Idle/late jobs actually happen | Owner recall + observation |

**Key risks (cause → event → impact)**

| Risk | Response |
|---|---|
| No client (G1 fails) | Line up 2–3 shops; fallback to TimeAlign (Red Line #1) |
| Client pain is files/proofing, not scheduling | Pain-check first; if so, JobFlow loses G8 → switch title |
| Scope creep toward printer integration or proofing | §6 boundary; change control; list as future work |
| Scheduler underperforms manual plan | Compare before/after on real data; tune method |
| Operators don't confirm status | Keep it ≤ N taps; owner override; in-app queue |

### Module 3 — Requirements
| Concept | Application |
|---|---|
| Stakeholder lenses | Owner (decision power), operators (process knowledge) |
| Elicitation | Owner + operator interviews, observation of a production day, document review (job log, machine list) |
| Claim classification | observed fact / reported fact / assumption / decision |
| Testable requirements | Section 7 acceptance criteria |
| MoSCoW | Section 7 priorities |
| ISO/IEC 25010:2023 | Section 7.3 |
| RTM | Link requirement → stakeholder need → evidence → test |

### Module 4 — Structured and OO Modeling
**Context diagram:** System = JobFlow. External entities: **Owner/Planner**, **Operator**. (No printer device external entity — deliberately out of scope. Customer is not an external entity.)

**Level 0 DFD processes**
1.0 Manage Machines and Capabilities · 2.0 Manage Jobs · 3.0 Generate Schedule (assign + sequence) · 4.0 Publish/Adjust Schedule · 5.0 Process Operator Confirmations · 6.0 Handle Rush Jobs · 7.0 Generate Analytics and Reports

**Data stores:** D1 Users · D2 Machines · D3 Jobs · D4 Schedule Slots · D5 Setup Rules · D6 Confirmations · D7 Activity Log

**Use cases**
Owner: Manage Machines · Manage Jobs · Run Scheduler · Adjust/Re-run · Insert Rush · View Analytics
Operator: View Queue · Confirm Start/Finish · Report Delay

**Decision table (job–machine eligibility, BR-01)**

| Condition | R1 | R2 | R3 |
|---|---|---|---|
| Machine has required capability? | Y | N | Y |
| Machine size/format supports job? | Y | – | N |
| **Assign** | X | | |
| **Skip** | | X | X |

**Key sequence (Run schedule):** Owner → System: publish jobs → System: filter eligible machines → Scheduler: assign + sequence (minimize makespan/idle) → Owner: review board → Operator: confirm start/finish → System: log actuals → Analytics update.

---

## 10. Development approach and evaluation

- **Approach:** Hybrid — prototyping (schedule board + operator confirm screen), Agile sprints, stage gates (proposal → design → pilot approval).
- **Pilot:** run the generated schedule alongside the manual method for `[N]` days before full use.
- **Evaluation:** ISO/IEC 25010 Likert survey (functional suitability, interaction capability, performance, reliability) with owner and operators; before/after planning time and machine idle.

### Suggested stack (NOT decided)
- Owner panel: web (React/Vue or Laravel Blade)
- Operator app: PWA (lower cost) or Flutter/React Native — trade-off to discuss
- Backend: Node/Express, Laravel, or Django · DB: MySQL/PostgreSQL
- Scheduler: in-app module (dispatching rules + Tabu local search; QUBO optional)

---

## 11. Data gathering plan

| Method | Participants | Purpose | Target date |
|---|---|---|---|
| Pain-check interview | Owner/foreman | Confirm the pain is scheduling (not files); capture workflow | `[set]` |
| Observation | One production day | Capture job queue, machine list, switches, planning method | `[set]` |
| Document review | Job log / order slips (1–3 months) | Volume, types, deadline misses | `[set]` |
| Questionnaire | Operators | Device access, willingness to confirm on phone | `[set]` |
| Endorsement letter | Owner | Formal client commitment | Before mock defense |

**Honest answer if asked "Is your client real / is this biased?":** `[Fill once client secured — state relationship, if any, and how you triangulate with observation and records.]`

---

## 12. Defense Q&A bank

| Question | Answer |
|---|---|
| Why not just use a whiteboard/Excel? | No optimization; no idle/setup awareness; no live status across machines. `[validate]` |
| Why not buy print-MIS software? | Cost/heaviness for a small shop; not tuned to their machines `[verify]`. |
| What's new? | Accessible web+mobile FJSP scheduler with sequence-dependent setup + human-confirmed execution for one small shop. |
| Does it connect to the printers? | No — deliberately. JobFlow is a decision-support layer above the printers (like Hiroshima's QUBO++ furnace scheduler); machines are logical resources, so brand/driver never matters. |
| Why don't you integrate with printers? | It's systems integration, not scheduling; brand/driver/OS-fragile; out of one-term scope. |
| What if the AI is wrong? | It only predicts durations; the human/machine rule sets the schedule; human-in-the-loop. |
| How do you prove it's better? | Before/after planning time + idle time on the client's real jobs. |
| Is it fair to rush jobs? | Rush handling policy `[BR-05 TO VALIDATE]`; owner control; transparency. |
| Generalizable? | Built for one client; the model suits similar print shops (future work). |
| Privacy? | Minimal operator/job data; RA 10173; role-based access. |
| Methodology? | Hybrid: prototyping + Agile + stage gates. |

---

## 13. Mock defense deck outline

| # | Slide | Source |
|---|---|---|
| 1 | Title + four-element breakdown | §1 |
| 2 | The client: `[Client]` (what they print, machines) + disclosure | §1, §0 |
| 3 | Current production workflow (as-is) + evidence status | §2 |
| 4 | Problem: symptoms vs. root cause (fishbone) + stakeholders | §2 |
| 5 | Objectives | §4 |
| 6 | How it works (flow diagram) | §5 |
| 7 | Key logic: job→machine, sequencing, setup, rush | §8.3 |
| 8 | Japanese anchor + related systems + differentiator | §3 |
| 9 | Scope and **system boundary** (no printer/proofing) | §6 |
| 10 | Context diagram + key requirements | §7, §9 |
| 11 | Feasibility (six dimensions) + key risks | §9 |
| 12 | Methodology + evaluation | §10 |
| 13 | Data gathering plan + endorsement status | §11 |

---

## 14. Sources

- Nakatsukasa, Nakano, Parque, Ito. *Optimizing Heat Treatment Schedules via QUBO Formulation.* Applied Sciences 15(16):8847, 2025. doi:10.3390/app15168847
- Hiroshima University press release (2025-09-29) — QUBO++ furnace scheduling, deployed at Nagato Co., Tsukimi Plant
- *Practical approach to Flexible Job Shop Scheduling with tool switching constraints using quantum annealing.* JAMDSM 18(2), 2024
- Any print-MIS/shift-software claims — verify on official sites before citing

> Client evidence (interview notes, observation, job records, endorsement letter) will be the primary source.

---

## 15. Open items / next steps

- [ ] Run pain-check on 2–3 print shops; secure G1 client
- [ ] Get signed endorsement letter from owner
- [ ] Observe one production day; collect machine list + setup categories
- [ ] Collect sample job records (volume, types, deadline misses)
- [ ] Confirm business rules BR-01–BR-08 with the owner
- [ ] Decide system name with team and client
- [ ] Confirm prof open questions (approval count; AI placement/depth; "seems small" meaning)
- [ ] Replace every `[TO VALIDATE]` with evidence or keep it as a labeled assumption
- [ ] Draft context diagram, Level 0 DFD, ERD, state diagrams
