# CrewSync — Project Context Pack

> **Purpose of this file:** Single source of truth for the client-based capstone title. Give this file to any teammate or tool (slides, documentation, design, code) so everything stays consistent with the title, scope, client, and IT0037 course lessons.
>
> **Version:** 0.1 (pre–mock defense) · **Owner:** Frel · **Client:** Kiddie Salon by Nail Brat (owner is a relative of a team member) · **Status:** Client identified; primary data gathering not yet done

> **Working name:** "CrewSync" is a placeholder. Alternatives: *SlotGlam*, *PartyCrew*, *TalentCall*, *BratCrew*. Pick one with the team and client, then find/replace.

---

## 0. Rules for anyone using this file

1. **Do not invent evidence.** No interviews, observations, or booking records have been collected yet. Never state event volume, no-show count, staffing time, or any pain point as fact. Use `[TO VALIDATE]`.
2. **Disclose the conflict of interest.** The client owner is a relative. State it openly; triangulate with talents' input and actual records (Module 1 ethics: "hidden conflicts" is a red flag).
3. **Respect the scope (Section 6).** No customer booking website, payments, payroll, inventory, CRM, or AI auto-assignment in this version.
4. **Framing rule:** The pitch is *talent availability confirmation and event staffing*, not "an app for a salon."
5. **Talents and owner are the users.** Customers (parents/party hosts) are not users.
6. **Keep course lessons traceable (Section 9).**
7. The actual defense, oral checks, quizzes, and exams are **AI-use prohibited**. The presenter must understand and own every claim.

---

## 1. Project identity

| Field | Value |
|---|---|
| **Title (v2 canonical — Title 1, revised after 2026-10-08 consultation: seems small + AI required; has client, re-approval pending)** | CrewSync: An AI-Assisted Web and Mobile-Based System for Event Staffing, Predictive Response Analytics, and Schedule Conflict Prevention for a Party Service Business |
| **Alt. title (client-named variant — only if panel authorizes)** | CrewSync: An AI-Assisted Web and Mobile-Based System for Event Staffing, Predictive Response Analytics, and Schedule Conflict Prevention for Kiddie Salon by Nail Brat |
| **Specialization** | BSIT — Web and Mobile Application |
| **School / course** | FEU Diliman · IT0037 Systems Analysis and Design |
| **Client** | Kiddie Salon by Nail Brat — mobile kiddie salon / party service (nail art, glitter, face painting, styling at events) |
| **Users** | Owner/Admin (web panel), Talents — face painters, nail artists, stylists, etc. (mobile app) |
| **Not a user** | Customers / party hosts — they book through the business's existing channels |

### One-line pitch
When an event is booked, the owner sends the job to the right talents, and each talent confirms availability in the app before a deadline, so every event is fully staffed without chasing people in chat.

### Short description
Kiddie Salon by Nail Brat sends talents such as face painters and nail artists to children's parties. Today, staffing an event likely means messaging talents one by one and waiting for replies `[TO VALIDATE]`. CrewSync lets the owner post a confirmed event with its package tier, schedule, and venue. The system notifies qualified talents, who accept or decline in the mobile app before a set deadline. Unfilled slots move to the next available talent, and the owner sees the staffing status of every event on one dashboard.

### Title breakdown (Module 1: four title elements)

| Element | In the title |
|---|---|
| Capability | Event Staffing, Predictive Response Analytics, and Schedule Conflict Prevention |
| Users / setting | Party Service Business (Kiddie Salon by Nail Brat) |
| Value / problem direction | Confirmed staffing per event; designed to prevent overlapping confirmed assignments |
| Specialization differentiator | Web and Mobile (owner web panel + talent mobile app with notifications) |

> Note on naming: Module 1 warns against titles that hide the real transaction. The real transaction here is **"request talent → talent confirms → event is staffed."** Keep "availability confirmation" or "event staffing" in the title.

---

## 2. Problem framing

### Symptom vs. root cause (Module 1)
- **Symptoms (hypothesized, to validate):** the owner messages talents one by one; replies get buried in chat; unclear who confirmed; last-minute declines or no-shows; double booking of a talent; staffing takes time away from sales and operations.
- **Root cause (working hypothesis):** there is **no structured process to request, track, and confirm talent availability per event**, so confirmation depends on informal chat and the owner's memory.

### Problem statement (draft)
Kiddie Salon by Nail Brat staffs each booked event with freelance or part-time talents such as face painters and nail artists `[TO VALIDATE employment type]`. Talent availability is currently requested and confirmed through informal messaging `[TO VALIDATE]`, with no deadline, no central status, and no automatic check for schedule conflicts. As a result, the owner spends time following up `[TO VALIDATE time]`, and events risk being understaffed or double-booked `[TO VALIDATE incidents]`.

### Evidence status

| Evidence | Status |
|---|---|
| Client exists and offers kiddie salon / party services | ✅ Public pages (Facebook) |
| Client wants a dedicated system | ✅ Verbal (owner) — get it in writing (endorsement letter) |
| Current staffing workflow (how talents are contacted) | ❌ Pending interview + observation |
| Monthly event volume and talents per event | ❌ Pending records |
| Number of talents, roles, employment type | ❌ Pending |
| Past no-shows / double bookings / late declines | ❌ Pending (owner recall + chat records) |
| Talents' smartphone access and preferred notification | ❌ Pending questionnaire |
| Package tiers and required roles per tier | ❌ Pending (price list / package sheet) |

### Stakeholders (Module 3)

| Stakeholder | Role / lens | Interest |
|---|---|---|
| Owner | Process owner, sponsor, admin user | Fully staffed events, less chasing, visibility |
| Talents (face painters, nail artists, stylists, etc.) | Direct users (mobile) | Clear job details, fair offers, easy accept/decline, control of own availability |
| Coordinator / assistant (if any) `[TO VALIDATE]` | Possible admin user | Same as owner |
| Customers / party hosts | Indirectly affected (not users) | Talents arrive on time; booked services delivered |
| Adviser / panel | Governance | Evidence, scope, feasibility, ethics |

**Power–interest (Module 1):** Owner = manage closely · Talents = keep informed and involve (high interest, frontline) · Customers = monitor.

---

## 3. Background (secondary context — keep claims general)

- The client operates a **mobile/event-based** service: work happens at venues, not a fixed shop, so staffing is per event.
- Many small Philippine service businesses manage bookings through social media and messaging apps `[cite a real source before using; otherwise drop]`.
- Most Philippine businesses are micro/small (DTI MSME statistics) — reuse the DTI figures from ResiboCheck only if re-verified.

> Do not add statistics without a checkable source. For this title, **client evidence matters more than national statistics.**

### Related systems / alternatives (for "What's new?")

| Alternative | What it does | Gap CrewSync fills |
|---|---|---|
| Messenger / Viber group chat | Fast messaging | No deadline, no per-slot status, replies get buried, no conflict check |
| Shared Google Calendar / Sheets | Shows schedule | No request/accept flow, no deadline, no escalation, manual |
| General shift-scheduling apps (e.g., When I Work, Connecteam, Homebase) | Shift schedules for staff | Built around fixed shifts/locations; subscription cost; not tied to party package tiers or per-event venues `[verify each claim before stating]` |
| Event/booking platforms | Customer-facing bookings | Focus on customers, not internal talent confirmation |

**Differentiator:** package-tier–based role slots + deadline-bound accept/decline + automatic escalation to the next talent + conflict checking, built for one real event-service business.

---

## 4. Objectives

### General objective
To develop a web and mobile talent scheduling and availability confirmation system that helps Kiddie Salon by Nail Brat staff each booked event by requesting, tracking, and confirming talent availability.

### Specific objectives (draft)
1. Develop a web admin panel where the owner records confirmed events (date, time, venue, package tier) and the system generates the required talent slots per tier.
2. Develop a mobile app where talents receive job requests, view event details, and accept or decline before a response deadline.
3. Implement automatic handling of declined or expired requests by offering the slot to the next eligible talent, plus schedule-conflict checking.
4. Provide a staffing dashboard, talent availability calendar, and reports (events staffed, response times, declines).
5. Implement role-based access, activity logging, and data handling consistent with RA 10173.
6. Evaluate the system with the owner and talents using selected ISO/IEC 25010 characteristics, and compare time-to-fully-staff an event before and after use `[baseline TO VALIDATE]`.

### Success measures (fill after data gathering)

| Indicator | Baseline | Target | Source |
|---|---|---|---|
| Average time from booking to fully staffed | `[TO VALIDATE]` | `[set after baseline]` | Chat timestamps vs. system logs |
| % of requests answered before deadline | — | `[set]` | System logs |
| Double bookings per month | `[TO VALIDATE]` | 0 (system-blocked) | Owner records vs. system |
| Follow-up messages owner sends per event | `[TO VALIDATE]` | `[set]` | Chat sample vs. system |
| ISO/IEC 25010 survey weighted mean | — | `[set]` | Likert survey |

---

## 5. How the system works

1. **Owner posts event (web):** client name/reference, date, start–end time, venue, package tier, notes. Status: **Draft → Open**.
2. **System builds slots:** the tier defines required roles (e.g., Tier 1 = 1 face painter; Tier 3 = 2 face painters + 1 nail artist + 1 stylist) `[tiers TO VALIDATE]`.
3. **System finds eligible talents** per slot: has the skill, is active, is not on a blackout date, and has no overlapping confirmed event (including a travel buffer).
4. **Notify:** eligible talents get a push notification with schedule, tier/role, venue, and **response deadline**.
5. **Talent responds (mobile):** Accept or Decline (with optional reason).
   - Accept → slot **Filled** (first valid acceptance wins, or owner picks — see §8.3).
   - Decline / no response by deadline → slot offered to next eligible talent (**auto-escalation**).
6. **Reminders:** before deadline, and before the event (e.g., day before).
7. **Owner monitors:** dashboard shows each event as Open / Partially Staffed / Fully Staffed / At Risk (deadline close, slots unfilled). Owner can **manually assign or override**.
8. **After event:** owner marks Completed (or Cancelled); talent attendance recorded.

---

## 6. Scope and limitations

### In scope
- **Owner web panel:** login; manage talents (profile, skills, status); manage package tiers and required roles; create/edit/cancel events; auto-generated slots; send requests; staffing dashboard; manual assign/override; calendar view; reports; activity log
- **Talent mobile app (PWA or cross-platform):** login; receive notifications; view job details; accept/decline before deadline; view own schedule; set blackout dates/availability
- Rules: response deadlines, auto-expiry, auto-escalation, conflict checking, reminders
- Database for users, talents, skills, tiers, events, slots, requests, responses, logs

### Limitations / delimitations

| Item | Reason |
|---|---|
| No customer-facing booking or website | Client already takes bookings via existing channels; scope control |
| No payment, payroll, or talent fee computation | Separate system; future work |
| No inventory (nail polish, paints, supplies) | Out of scope |
| AI-assisted response-likelihood scoring — ranks within the eligible set only | Per 2026-10-08 consultation, AI/Analytics are required in all titles. Hard eligibility rules unchanged (transparent, explainable); AI only orders send-order and flags at-risk slots; factors visible; owner confirms; rules-only cold start until data accumulates; evaluation = predicted-vs-actual acceptance |
| No GPS live tracking of talents | Privacy and scope |
| Single business (one client) | Evaluation limited to Kiddie Salon by Nail Brat; results not generalized |
| Notifications depend on talent's device/internet | Owner override + in-app status as fallback |
| SMS optional (Could) | Recurring cost; push/in-app is primary |

---

## 7. Requirements (draft — validate with client)

### 7.1 Owner web panel

| ID | Requirement | Priority | Acceptance criteria |
|---|---|---|---|
| ADM-01 | Admin login | Must | Only admin can create events and manage talents |
| ADM-02 | Manage talent profiles (name, skills/roles, status) | Must | Deactivated talents receive no requests; history kept |
| ADM-03 | Manage package tiers and required roles per tier | Must | Creating an event with a tier auto-creates matching slots |
| ADM-04 | Create/edit/cancel event (date, time, venue, tier, notes) | Must | Cancelling notifies all confirmed talents |
| ADM-05 | Send availability requests with response deadline | Must | Each request shows deadline; expired requests close automatically |
| ADM-06 | Staffing dashboard (Open / Partial / Fully Staffed / At Risk) | Must | Status equals actual slot states |
| ADM-07 | Manual assign / override | Must | Override is logged with admin name and time |
| ADM-08 | Auto-escalation to next eligible talent | Should | On decline/expiry, next eligible talent is notified within `[X]` minutes |
| ADM-09 | Calendar view of events and talent assignments | Should | Filter by date and talent |
| ADM-10 | Reports (events staffed, response times, declines) | Should | Totals match underlying records for date range |
| ADM-11 | Activity log | Should | Who did what, when |
| ADM-12 | SMS fallback notification | Could | Sent only when push not acknowledged `[cost TO VALIDATE]` |

### 7.2 Talent mobile app

| ID | Requirement | Priority | Acceptance criteria |
|---|---|---|---|
| TAL-01 | Talent login | Must | Each response is tied to the talent's account |
| TAL-02 | Receive request notification | Must | Shows date, time, venue, role/tier, deadline |
| TAL-03 | Accept / Decline before deadline | Must | Buttons disabled after deadline; decline reason optional |
| TAL-04 | View own confirmed schedule | Must | Lists upcoming confirmed events |
| TAL-05 | Set blackout dates / unavailable days | Should | Talent receives no requests on blackout dates |
| TAL-06 | Event reminders | Should | Reminder sent `[N]` hours before event |
| TAL-07 | Open venue in maps app | Could | Tapping venue opens external maps |

### 7.3 Non-functional (ISO/IEC 25010 — selected)

| ID | Characteristic | Requirement |
|---|---|---|
| NFR-01 | Performance efficiency | Notification delivered within `[X]` seconds of request under normal connectivity |
| NFR-02 | Security | Role-based access; hashed passwords; HTTPS |
| NFR-03 | Security / privacy | Store only needed talent data (name, contact, skills, availability); customer data limited to event reference and venue; RA 10173 |
| NFR-04 | Interaction capability (usability) | A talent can accept a request in ≤ `[N]` taps after opening the notification |
| NFR-05 | Reliability | A talent can never be confirmed for two overlapping events (system-enforced) |

### 7.4 Deliberately excluded (Won't, this version)
Customer booking site · payments/payroll · inventory · AI ranking · GPS tracking · multi-business

---

## 8. Data model and behavior

### 8.1 Entities (logical)

| Entity | Key attributes |
|---|---|
| User | user_id, name, role (Admin/Talent), contact, status |
| Skill | skill_id, name (Face Painting, Nail Art, Hair Styling, Glitter, …) |
| TalentSkill | user_id, skill_id |
| PackageTier | tier_id, name, description |
| TierRole | tier_id, skill_id, quantity |
| Event | event_id, client_ref, venue, start_time, end_time, tier_id, status, created_by |
| Slot | slot_id, event_id, skill_id, status, assigned_talent_id |
| Request | request_id, slot_id, talent_id, sent_at, deadline, status, responded_at, decline_reason |
| Blackout | blackout_id, talent_id, date_from, date_to |
| ActivityLog | log_id, user_id, action, target, timestamp |

### 8.2 Relationships
- PackageTier 1—* TierRole *—1 Skill
- User (Talent) *—* Skill (via TalentSkill)
- Event *—1 PackageTier
- Event 1—* Slot
- Slot 1—* Request; Request *—1 User (Talent)
- Slot 0..1—1 assigned Talent
- User 1—* Blackout; User 1—* ActivityLog

### 8.3 Business rules

> **Status: all business rules below (BR-01 – BR-09) are PROPOSED design decisions — none are confirmed.** They must be presented to the owner during the client interview and confirmed, adjusted, or rejected before the final proposal. Values marked `[TO VALIDATE]` are starting hypotheses only.

- BR-01: Creating an event generates one Slot per required role quantity of its tier.
- BR-02: A request goes only to talents with the required skill, Active status, no blackout, and no overlapping confirmed event (with travel buffer `[TO VALIDATE, e.g., 1–2 h]`).
- BR-03: Each request has a deadline; default `[TO VALIDATE, e.g., 24 h]`, shortened when the event is near `[e.g., 50% of remaining time, min 2 h]`.
- BR-04: Fill policy `[decide with owner]`: **(a)** first valid acceptance fills the slot, others are auto-closed; or **(b)** owner chooses among acceptors.
- BR-05: On decline or expiry, the slot is offered to the next eligible talent (order: `[TO VALIDATE — e.g., fewest assignments this month for fairness]`).
- BR-06: A talent cannot be confirmed for overlapping events.
- BR-07: Only Admin may create/cancel events, override assignments, or manage talents.
- BR-08: If an event is cancelled, all confirmed talents are notified and slots closed.
- BR-09: Event is **At Risk** when any slot is unfilled within `[N]` hours of the event.

### 8.4 State models
**Request**
```
Sent ──accept──► Accepted
Sent ──decline──► Declined ─► (escalate)
Sent ──deadline passes──► Expired ─► (escalate)
Sent ──slot filled by another / event cancelled──► Withdrawn
```
**Slot**
```
Open ──talent accepts / owner assigns──► Filled ──talent withdraws──► Open
Open ──event cancelled──► Closed
```
**Event**
```
Draft ──publish──► Open ──all slots filled──► Fully Staffed ──event done──► Completed
Open/Fully Staffed ──cancel──► Cancelled
```

---

## 9. IT0037 lessons mapped

### Module 1 — Systems Analysis Fundamentals
| Concept | Application |
|---|---|
| Symptom vs. root cause | Buried chat replies/no-shows = symptoms; no structured request–confirm process = root cause |
| Evidence triangulation | Owner interview + talent questionnaire + chat/booking records + observation of staffing one event |
| Four title elements | Section 1 |
| Ethics red flags | Conflict of interest (relative) disclosed; minimal data; no hidden AI claims |
| Stakeholder power–interest map | Section 2 |
| Hybrid approach with reasons | Prototyping (talent app screens) + Agile sprints + stage gates |
| Web & Mobile lens: service journey | Request → validate (eligibility) → track (status) → resolve (fill/escalate) → support (reminders) |

### Shelly Ch. 2 — Systems Planning
| Concept | Application |
|---|---|
| Systems request | The owner's own request — a real "systems request" from a business |
| Reasons for project | Better performance, more information, stronger controls (no double booking), improved service |
| Preliminary investigation (6 steps) | Understand problem → scope/constraints → fact-finding → feasibility → time/cost → present |
| Constraints | Mandatory: RA 10173; External: talents' devices/internet; Present: one business |
| Fishbone | Causes of understaffed/late-confirmed events: People, Process, Technology, Communication, Schedule |
| Tangible / intangible benefits | Tangible: time to staff, fewer double bookings; intangible: owner peace of mind, talent clarity, customer trust |

### Bender — SDLC
| Concept | Application |
|---|---|
| Stepwise commitment | Commit to build after the client confirms tiers, roles, and workflow |
| Change control | Client requests (payments, customer booking) handled as scope changes |
| User involvement | Client is accessible — strong user participation reduces risk |

### Module 2 — Feasibility (six dimensions)
| Dimension | Preliminary view | Condition / unknown |
|---|---|---|
| Technical | Feasible — web panel + mobile/PWA + push notifications + relational DB are standard | Push reliability on iOS PWA `[test]`; choose PWA vs. cross-platform |
| Operational | Likely feasible — client actively wants it | Talent adoption; smartphone access `[questionnaire]` |
| Economic | Conditional | Hosting, push (free tiers), optional SMS `[estimate in PHP]` |
| Schedule | Conditional | Team skills; remaining term; client availability for reviews |
| Security | Conditional | Role-based access, HTTPS, hashed passwords, activity log |
| Legal and ethical | Conditional | RA 10173 for talent/customer data; consent for data gathering; conflict of interest disclosed; fair request distribution |

**Assumptions register**

| # | Assumption | Validation action |
|---|---|---|
| A1 | Owner currently staffs events through chat/messaging | Interview + de-identified chat sample |
| A2 | Enough events per month to make manual staffing a burden | Booking records for 1–3 months |
| A3 | Talents have smartphones and will install/use the app | Talent questionnaire |
| A4 | Package tiers map to fixed role requirements | Collect package/price sheet |
| A5 | No-shows or late confirmations have happened | Owner recall + records |
| A6 | Talents are freelancers who can decline jobs | Ask owner |

**Key risks (cause → event → impact)**

| Risk | Response |
|---|---|
| Talents ignore notifications → slots unfilled → event at risk | Reminders, escalation, At Risk alert, owner override |
| Push not delivered (device/OS) → missed request | In-app inbox; optional SMS (Could); test devices |
| Owner keeps using chat → low adoption | Prototype with owner early; one-click event creation |
| Unfair request distribution → talent complaints | Transparent rotation rule; configurable by owner |
| Conflict of interest biases findings | Disclose; include talent voices and records; adviser review |
| Scope creep (payments, customer booking) | Change control; list as future work |

### Module 3 — Requirements
| Concept | Application |
|---|---|
| Stakeholder lenses | Owner (decision power), talents (process knowledge, change impact) |
| Elicitation | Owner interview, talent interviews/questionnaire, observation of staffing an event, document review (package list, chat sample, booking records) |
| Claim classification | Mark items as observed fact / reported fact / assumption / decision |
| Testable requirements | Section 7 acceptance criteria |
| MoSCoW | Section 7 priorities |
| ISO/IEC 25010:2023 | Section 7.3 |
| RTM | Link requirement → stakeholder need → evidence → test |

### Module 4 — Structured and OO Modeling
**Context diagram:** System = CrewSync. External entities: **Owner/Admin**, **Talent**, **Notification service** (push/SMS provider). Customer is not an external entity (interacts with the owner outside the system).

**Level 0 DFD processes**
1.0 Manage Talents and Skills · 2.0 Manage Package Tiers · 3.0 Manage Events and Slots · 4.0 Send Availability Requests · 5.0 Process Talent Responses · 6.0 Escalate and Resolve Unfilled Slots · 7.0 Generate Dashboard and Reports

**Data stores:** D1 Users · D2 Skills · D3 Package Tiers · D4 Events · D5 Slots · D6 Requests · D7 Blackouts · D8 Activity Log

**Use cases**
Owner: Manage Talents · Manage Tiers · Create Event · Send Requests · Monitor Staffing · Override Assignment · Cancel Event · View Reports
Talent: View Request · Accept/Decline · View Schedule · Set Blackout Dates

**Decision table (eligibility, BR-02)**

| Condition | R1 | R2 | R3 | R4 | R5 |
|---|---|---|---|---|---|
| Has required skill? | Y | N | Y | Y | Y |
| Active? | Y | – | N | Y | Y |
| On blackout? | N | – | – | Y | N |
| Overlapping confirmed event? | N | – | – | – | Y |
| **Send request** | X | | | | |
| **Skip** | | X | X | X | X |

**Key sequence (Accept request):** Owner → System: publish event → System: create slots, find eligible talents → Notification service → Talent app → Talent: Accept → System: check deadline + conflict → System: Slot Filled, withdraw other requests → Owner dashboard updates.

---

## 10. Development approach and evaluation

- **Approach:** Hybrid — prototyping (talent app and event form with owner/talents), Agile sprints (build), stage gates (proposal approval → design approval → pilot approval).
- **Pilot:** run alongside the current chat method for `[N]` events before full use.
- **Evaluation:** ISO/IEC 25010 Likert survey (functional suitability, interaction capability, reliability, security) with owner and talents; before/after time-to-fully-staff.

### Suggested stack (NOT decided)
- Owner panel: web (React/Vue or Laravel Blade)
- Talent app: PWA (lower cost) or Flutter/React Native (more reliable push) — trade-off to discuss
- Backend: Node/Express, Laravel, or Django · DB: MySQL/PostgreSQL
- Notifications: Firebase Cloud Messaging (free tier) · SMS optional
- Scheduler: cron/queue job for deadlines, expiry, reminders

---

## 11. Data gathering plan

| Method | Participants | Purpose | Target date |
|---|---|---|---|
| Interview | Owner | Workflow, tiers, volume, pain points, constraints | `[set]` |
| Interview / questionnaire | Talents (as many as available) | Current experience, devices, notification preference, fairness concerns | `[set]` |
| Document review | Package/price list; de-identified chat sample; booking records (1–3 months) | Tier–role mapping, response times, volume | `[set]` |
| Observation | Owner staffing one real event | Time to staff, number of follow-ups | `[set]` |
| Endorsement letter | Owner | Formal client commitment | Before mock defense |

**Honest answer if asked "Is your client real / is this biased?":** "Yes, the client is a real business owned by a relative of a team member, and we disclose that. To reduce bias, we'll also gather input from the talents and use actual booking and chat records, not just the owner's word."

---

## 12. Defense Q&A bank

| Question | Answer |
|---|---|
| Why not just use a group chat? | Chat has no deadline, no per-slot status, no conflict check, and no escalation. Replies get buried `[validate with chat sample]`. |
| Why not Google Calendar or a shift app? | They show schedules but don't handle request → accept → escalate per event and package tier. Shift apps assume fixed shifts and cost a subscription `[verify]`. |
| What's new? | Tier-based role slots + deadline-bound confirmation + auto-escalation + conflict blocking for an event-based service. |
| Is your client biased (relative)? | Disclosed; triangulated with talents and records; endorsement letter. |
| What if talents don't respond? | Deadline → auto-expire → next eligible talent; reminders; At Risk alert; owner override. |
| What if two talents accept at once? | Fill policy BR-04 — first valid acceptance wins (server-side check); other request withdrawn. |
| Double booking? | System blocks overlapping confirmed events (BR-06). |
| Is it fair to talents? | Rotation rule for who gets offered first; talents set blackout dates; decline has no penalty `[confirm with owner]`. |
| Why not AI to pick the best talent? | Not needed and not supported by evidence; rule-based eligibility is explainable. |
| Customers? | Not users; owner keeps existing booking channels. |
| Payments? | Out of scope; future work. |
| Privacy? | Minimal talent data; customer data limited to event reference and venue; RA 10173; role-based access. |
| Generalizable? | Built for one client; design may suit similar event-service businesses (future work). |
| Methodology? | Hybrid: prototyping + Agile + stage gates. |
| Evaluation? | ISO/IEC 25010 survey + before/after time to fully staff. |

---

## 13. Mock defense deck outline

| # | Slide | Source |
|---|---|---|
| 1 | Title + four-element breakdown | §1 |
| 2 | The client: Kiddie Salon by Nail Brat (what they do, how events work) + conflict-of-interest disclosure | §1, §0 |
| 3 | Current staffing workflow (as-is) + evidence status | §2 |
| 4 | Problem: symptoms vs. root cause (fishbone) + stakeholders | §2 |
| 5 | Objectives | §4 |
| 6 | How it works (flow diagram) | §5 |
| 7 | Key logic: tiers → slots, deadline, escalation, conflict check | §8.3 |
| 8 | Related systems + differentiator | §3 |
| 9 | Scope and limitations | §6 |
| 10 | Context diagram + key requirements | §7, §9 |
| 11 | Feasibility (six dimensions) + key risks | §9 |
| 12 | Methodology + evaluation | §10 |
| 13 | Data gathering plan + endorsement status | §11 |

---

## 14. Sources

- Kiddie Salon by Nail Brat — public Facebook page (confirm URL and services with owner)
- DTI MSME statistics (only if re-verified)
- Any shift-app claims (When I Work, Connecteam, Homebase) — verify on official sites before citing

> Client evidence (interview notes, records, endorsement letter) will be the primary source.

---

## 15. Open items / next steps

- [ ] Agree on system name with team and client
- [ ] Get signed endorsement letter from owner
- [ ] Interview owner; collect package/price list
- [ ] Talent questionnaire (devices, preferences, fairness)
- [ ] De-identified chat sample + 1–3 months booking records
- [ ] Decide fill policy (BR-04), deadline rule (BR-03), rotation order (BR-05), travel buffer (BR-02)
- [ ] Decide PWA vs. cross-platform for talent app
- [ ] Replace every `[TO VALIDATE]` with evidence or keep as labeled assumption
- [ ] Draft context diagram, Level 0 DFD, ERD, state diagrams
