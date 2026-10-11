# AuraMesh — Project Context Pack

> **Purpose of this file:** Single source of truth for the community search coordination capstone title. Give this file to any teammate or tool (slides, documentation, design, code) so everything stays consistent with the title, scope, client, and IT0037 course lessons.
>
> **Version:** 0.1 (initial pack built from the AzTech Title 3 PDF entry) · **Owner:** AzTech Group 6 · **Client:** none yet — no barangay or DRRM partner has been secured · **Status:** NO CLIENT YET; title suggested by the team; everything client-dependent is unvalidated

> **Working name:** "AuraMesh" is the team's suggested name from the Title 3 PDF. Alternatives: *SearchMesh*, *IsoGrid*, *MeshSight*, *TanodGrid*. Keep the name if the team agrees, then find/replace.

> **Honest status flag:** This title is the most ambitious of the four AzTech proposals and carries the greatest number of open questions. Read Section 0, Section 6, and Section 12 before pitching it.

---

## 0. Rules for anyone using this file

1. **Do not invent evidence.** There is **no client, no interview, no data, and no endorsement letter.** Never state incidents, response times, sighting volume, or barangay pain points as fact. Mark every client-dependent or unverified item `[TO VALIDATE]`.
2. **The client does not exist yet.** A barangay or municipal DRRM office is only a **target** partner. Any statement that a barangay "wants this" or "will provide data" is false until an endorsement letter is signed.
3. **Disclose the client-instrumentation risk.** The team has previously dropped barangay-dependent ideas because barangays are hard to instrument (access, approvals, staff time, data privacy). Say this openly rather than hiding it (Module 1 ethics).
4. **Respect the scope (Section 6).** No law-enforcement replacement, no mass biometric surveillance, no face database of the general public. The system triages **volunteer-submitted sighting photos** against **one missing person's** profile, with consent and minimal data.
5. **Framing rule:** The pitch is *localized search-coverage coordination and sighting triage in the critical early hours*, not "an app that finds missing people."
6. **The algorithm facet is the weakest part of this title.** Isochrone modeling is a **computation**, not a strong optimization algorithm. See the note in Section 1 and the stronger framings in Section 4 — never oversell it.
7. **Privacy is the highest risk.** Faces of missing persons and crowd-sourced photos are sensitive personal data. Frame every AI step as privacy-preserving and verifiable (Section 9, Section 12).
8. **Keep course lessons traceable (Section 9).**
9. The actual defense, oral checks, quizzes, and exams are **AI-use prohibited**. The presenter must understand and own every claim — especially the DPA posture and the isochrone math.

---

## 1. Project identity

| Field | Value |
|---|---|
| **Title (v1 canonical — Title 3 from the AzTech PDF, suggested by the team)** | AuraMesh: A Localized Pedestrian Isochrone Search Coordination and Computer Vision-Assisted Sighting Triage System for Vulnerable Missing Persons |
| **Alt. title (client-named variant — only if a partner is secured)** | AuraMesh: A Localized Pedestrian Isochrone Search Coordination and Computer Vision-Assisted Sighting Triage System for Vulnerable Missing Persons in `[Barangay / LGU — TO VALIDATE]` |
| **Specialization** | BSIT — Web and Mobile Application |
| **School / course** | FEU Diliman · IT0037 Systems Analysis and Design |
| **Client** | `[TO VALIDATE]` — no partner yet. Target: a barangay office or municipal DRRM (Disaster Risk Reduction and Management) office |
| **Users** | Barangay officers / command staff (responsive web command dashboard); community watchmen (tanods) and verified responders (Android mobile client) |
| **Not a user** | The general public / unverified tipsters — they submit sightings through a lightweight, moderated channel, not the responder app |

### One-line pitch
When a vulnerable person goes missing, the command dashboard turns the last-seen location into time-based pedestrian search zones, dispatches the right responders to the right zones, and triages volunteer sighting photos against the missing person's profile so false alarms do not drown out real leads.

### Short description
Community searches for vulnerable missing persons — wandering children and elderly people with cognitive impairment or dementia — are often delayed at the start and poorly distributed across an area `[TO VALIDATE]`. AuraMesh lets a barangay officer register a missing-person profile, generate pedestrian-network isochrone search zones from the last-seen location and an estimated mobility profile, and dispatch targeted alerts. Community watchmen (tanods) and verified responders receive zone assignments on an Android client and submit geotagged sighting photos. A privacy-preserving computer vision step extracts visual features and scores each sighting against the profile, so officers see the most-likely leads first. An analytics view tracks incident progress and triage verification.

### Title breakdown (Module 1: four title elements)

| Element | In the title |
|---|---|
| Capability | Localized Pedestrian Isochrone Search Coordination and Computer Vision-Assisted Sighting Triage |
| Users / setting | Vulnerable missing persons search in a community / barangay setting (barangay officers + tanods / verified responders) |
| Value / problem direction | Faster, better-distributed coverage in the critical early search window; verified leads instead of clutter |
| Specialization differentiator | Web and Mobile (responsive barangay command dashboard + Android responder mobile client) |

> **Note on naming and honesty:** Module 1 warns against titles that hide the real transaction. The real transaction here is **"create incident → define search zones → dispatch responders → collect and triage sightings."** Keep "search coordination" and "sighting triage" in the title.
>
> **Algorithm facet (honest framing):** The PDF proposes *GIS pedestrian network isochrone modeling* to compute dynamic search radii. This is a **computation**, not a strong optimization algorithm — it converts a last-seen point and a mobility profile into reachable-by-time polygons along walkable paths. That alone will draw a "where is the algorithm?" question. **Stronger framings to consider (see Section 4):** treat zone selection as an **isochrone-based coverage optimization** or a **set-covering search-area model** — i.e., choose a small set of responder assignments that covers the highest-priority reachable area under a responder/time budget. Flag this openly: **the algorithm facet is the weakest element of this title and must be strengthened or honestly delimited.**
>
> **AI facet:** Privacy-preserving computer vision feature extraction that triages and scores crowd-sourced sighting photos against a missing-person profile. "Privacy-preserving" must mean something concrete (on-device or server-side feature matching, no public face database, minimal retention) — not a buzzword.
>
> **Analytics facet:** Incident analytics and a sighting triage verification dashboard.

---

## 2. Problem framing

### Symptom vs. root cause (Module 1)
- **Symptoms (hypothesized, to validate):** alerts go out late; searchers cover the same streets while other areas are ignored; officers receive a flood of unverified photos and messages; real leads get lost in the clutter; uninvolved residents are spammed by wide broadcast alerts and start ignoring them.
- **Root cause (working hypothesis):** there is **no localized, time-aware way to (a) turn a last-seen location into an ordered set of search areas, (b) assign responders to those areas, and (c) triage the sighting reports that come in** — so coordination depends on manual calling and messaging.

### Problem statement (draft)
Community search operations for vulnerable missing persons (wandering children, elderly with cognitive impairment or dementia) suffer delayed notification dispatch and inefficient coverage distribution, causing critical delays in the early response hours `[TO VALIDATE]`. Traditional manual searches lack localized spatial coordination and real-time sighting triage `[TO VALIDATE]`. AuraMesh is proposed to define priority pedestrian search zones from the last-seen location and mobility profile, dispatch targeted responder alerts, and triage crowd-sourced sighting photos against the missing person's profile.

### Sub-problems (from the Title 3 PDF)
1. **Delayed search initiation and lack of real-time geographical tracking** during the critical early search window.
2. **Uncoordinated visual sighting reports and false-alarm clutter** from unverified public tips.
3. **Inflexible broadcast radius causing alert fatigue** among uninvolved community members.

### Evidence status

| Evidence | Status |
|---|---|
| PostgreSQL/postgis isochrone computation is technically standard | ✅ General technical fact — verify toolchain before citing |
| A barangay / DRRM partner exists and wants this system | ❌ No client yet — `[TO VALIDATE]` |
| Current barangay search workflow (how alerts go out, who responds) | ❌ Pending partner + interview |
| Typical number of missing-person incidents per year in a target area | ❌ Pending records — `[TO VALIDATE]` |
| Whether tanods / responders have smartphones and data | ❌ Pending survey — `[TO VALIDATE]` |
| Whether the barangay already has a hazard-mapping or DRRM system | ❌ Pending (collision check — see Section 12) |
| Willingness to handle faces / photos under RA 10173 | ❌ Pending — no DPA clearance, no consent process |
| Equipment, maps, and GIS data availability for the target area | ❌ Pending — `[TO VALIDATE]` |

### Stakeholders (Module 3)

| Stakeholder | Role / lens | Interest |
|---|---|---|
| Barangay officer / command staff | Process owner, sponsor, admin user (web) | Faster mobilization, clear coverage, fewer false alarms |
| Tanods / community watchmen | Direct users (mobile) | Clear zone assignments, simple sighting submission |
| Verified responders (BDRRMC / volunteers) | Direct users (mobile) | Accurate alerting, coordination |
| Family of the missing person | Indirectly affected (consent/source of profile) | Fast, dignified, privacy-safe search |
| General public / tipsters | External, moderated channel | Easy reporting, no spam |
| Barangay / municipal DRRM office | Governance, data controller | Legal, privacy, scope |
| Adviser / panel | Governance | Evidence, scope, feasibility, ethics |

**Power–interest (Module 1):** Barangay command = manage closely · tanods/responders = keep informed and involve (frontline) · families = monitor and protect · public = inform and moderate.

---

## 3. Background (secondary context — keep claims general)

- Municipal "Mimamori" safety meshes in Japan are a recognized inspiration — coordinated community watch and check-in networks for vulnerable residents `[TO VALIDATE — cite a checkable source for Mimamori; otherwise present as general inspiration only, not as a citable system]`.
- Community-based search and rescue commonly uses **grid/task-area search** and **probability-of-area** thinking from SAR practice `[verify a checkable source before stating]`.
- Barangays are the smallest Philippine local-government unit and already operate tanod (watchmen) and BDRRMC structures `[cite a checkable source or LGU page before using as fact]`.
- Pedestrian isochrones (walkable-area-by-time) are a standard GIS concept built on a road/path network `[verify the specific toolchain, e.g., pgRouting / OSRM, before citing]`.

> Do not add statistics without a checkable source. For this title, **partner evidence (once one exists) matters more than national statistics.**

### Related systems / alternatives (for "What's new?")

| Alternative | What it does | Gap AuraMesh fills |
|---|---|---|
| Facebook / Messenger posts + group chats | Broadcasts a missing-person appeal | No zone assignment, no deadlines, no triage, replies buried, alert fatigue |
| Barangay megaphone / house-to-house announcements | Local manual alerting | No spatial coverage logic, slow, no sighting capture |
| Consumer find-my-phone / family tracker apps | Tracks a device by consent | Only works if the person carries a charged, enabled device with consent |
| Commercial GIS / SAR tools | Professional mapping and coverage analysis | Heavy, costly, built for trained GIS/SAR operators, not barangay officers |
| CCTV rooms | Passive monitoring | Reactive, not dispatched search coordination |

**Differentiator:** pedestrian-isochrone **search-zone generation** + **targeted responder dispatch** (instead of a blunt broadcast radius) + **privacy-preserving sighting triage** for a barangay-level team.

---

## 4. Objectives

### General objective
To analyze, design, and develop AuraMesh, a web and mobile community search-coordination and sighting-triage system that helps a barangay command team define localized pedestrian search zones, dispatch responders, and triage crowd-sourced sighting photos for vulnerable missing persons.

### Specific objectives (draft)
1. Develop a responsive web command dashboard for barangay officers to manage missing-person profiles, initiate incident alerts, and view search-coverage maps.
2. Develop an Android mobile companion app for community watchmen (tanods) and verified responders to receive targeted zone alerts and submit geotagged visual sighting reports.
3. Implement GIS-based pedestrian network isochrone modeling to compute dynamic search zones/radii from last-seen locations and estimated mobility parameters.
4. Implement a privacy-preserving computer vision feature-extraction step to triage and score crowd-sourced sighting photos against a missing-person profile.
5. Provide an incident analytics and sighting-triage verification dashboard (coverage progress, triage outcomes, verification status).
6. Apply role-based access, activity logging, and data handling consistent with RA 10173 (Data Privacy Act of 2012), with a defined retention and consent policy.
7. Evaluate the system with the partner using selected ISO/IEC 25010 characteristics, and measure search-zone and triage accuracy using **simulated incident scenarios**.

> **Strengthening the algorithm objective (do this before defense):** reframe objective 3 from "compute radii" to a coverage decision. Candidate framings: (a) **isochrone-based coverage optimization** — choose zone priorities that maximize reachable area covered per responder-hour; or (b) a **set-covering search-area model** — select the minimum set of zones/assignments that covers the highest-probability area. If neither is committed, state plainly that the isochrone step is a **computation, not an optimization algorithm**, and carry a different facet (analytics + CV triage) as the algorithmic weight. See Section 0, rule 6.

### Success measures (fill after partner + simulation)

| Indicator | Baseline | Target | Source |
|---|---|---|---|
| Time from incident creation to first dispatch | `[TO VALIDATE]` | `[set after baseline]` | Partner logs vs. system logs |
| Zonal coverage completeness | `[TO VALIDATE]` | `[set]` | System coverage map |
| Sighting-triage precision / recall | — | `[set]` | Simulated scenarios with ground truth |
| False-alarm ratio (unverified tips) | `[TO VALIDATE]` | `[set]` | System logs |
| ISO/IEC 25010 survey weighted mean | — | `[set]` | Likert survey |

---

## 5. How the system works

1. **Incident opened (web):** officer creates a missing-person profile (name, age, photo, description, vulnerability type, last-seen location and time, estimated mobility profile). Status: **Draft → Active**.
2. **Search zones generated:** the system builds pedestrian-network isochrones from the last-seen point using the mobility profile (e.g., child walking vs. elderly with dementia), producing an **ordered set of time-based search zones** `[mobility parameters TO VALIDATE]`.
3. **Responders dispatched:** tanods and verified responders are alerted with their assigned zone(s), the profile's essential details, and a per-zone task — instead of a single wide broadcast. `[assignment logic TO VALIDATE — see Section 8.3]`.
4. **Field activity (mobile):** responders move through their zones; the dashboard shows zone assignment and progress.
5. **Sightings submitted (mobile / moderated channel):** responders and the public submit geotagged sighting photos and notes.
6. **Triage (privacy-preserving CV):** the system extracts visual features and scores each sighting against the missing-person profile, ranking probable matches; officers review and verify. Status per sighting: **Submitted → Scored → Verified / Dismissed**.
7. **Coverage updates (dashboard):** zones show Searched / In Progress / Uncovered; priority zones expand as time elapses.
8. **Resolution:** the officer marks the incident **Resolved**, **Referred to authorities**, or **Closed**; collected personal data follows the retention policy.

> **Panel risk:** steps 4 and 7 describe a **coverage dashboard**, which a panel may call "just a monitoring system." Section 6 and Section 12 address this directly — the defensible value is the **zone generation + dispatch + triage**, not the map alone.

---

## 6. Scope and limitations

### In scope
- **Web command dashboard (barangay officer):** login; missing-person profile registry; incident creation and status; pedestrian isochrone search-zone modeling; responder dispatch; sighting-triage verification view; coverage map; incident analytics; activity log
- **Android responder app (tanods / verified responders):** login; location-based zone alerts; view assigned zone; geotagged photo/note sighting submission; own status
- **Sighting triage:** privacy-preserving CV feature extraction and scoring against a single missing-person profile; officer verification
- **Rules:** zone priority by elapsed time and mobility; dispatch logic; sighting state flow; data retention
- **Database** for users, missing persons, incidents, zones, assignments, sightings, triage results, logs

### Limitations / delimitations

| Item | Reason |
|---|---|
| Not a law-enforcement system; does not replace police/SAR operations | Community-level scope; legal and ethical boundary |
| No public face-recognition database; no biometric identity search of the general public | High DPA risk; the system triages volunteer sightings against **one profile only** |
| No mass CCTV ingestion or live facial surveillance | Privacy; out of scope |
| No real-time GPS body-tracking of responders beyond zone status | Privacy; scope |
| Algorithm facet = isochrone computation (or a bounded coverage/set-covering model) | Honestly delimited — not a strong optimizer; see Section 4 |
| CV triage accuracy is evaluated on **simulated scenarios**, not live cases | No live incident data available at capstone time |
| Restricted to a participating barangay / LGU jurisdiction | Single-partner scope; results not generalized |
| Notifications depend on device/internet and on responder adoption | Owner/broader channel fallback |
| Handling of minors' and vulnerable persons' faces requires explicit consent/legal basis | RA 10173; consent process `[TO VALIDATE]` |

### Open risks / panel questions (honest)

1. **The barangay client is hard to instrument.** Barangays have limited staff time, shifting officials, approval layers, and data-privacy duties. The team has **previously dropped barangay-dependent ideas for exactly this reason.** Securing and keeping a real, engaged partner is the single biggest risk to this title.
2. **Possible title collision.** A batch group may already have a **barangay hazard-mapping** title. AuraMesh is search coordination, not hazard mapping, but the panel may see overlap — differentiate clearly or confirm no collision before pitching.
3. **High privacy and DPA risk.** Handling faces of missing persons and crowd-sourced photos is sensitive personal data, and may involve minors. Without a concrete consent, retention, and access policy, this is a blocking ethics issue.
4. **"It's just a monitoring dashboard."** The coverage map can read as passive monitoring rather than analysis. The defense must lead with **zone generation, dispatch logic, and triage**, and show the map as an output, not the product.

---

## 7. Requirements (draft — validate with partner)

### 7.1 Barangay command dashboard

| ID | Requirement | Priority | Acceptance criteria |
|---|---|---|---|
| ADM-01 | Officer login (role-based) | Must | Only authorized officers create incidents and view data |
| ADM-02 | Manage missing-person profiles (photo, description, vulnerability, mobility) | Must | Profile stored under consent/legal basis; access logged |
| ADM-03 | Create / update / close an incident | Must | Status transitions recorded with officer and time |
| ADM-04 | Generate pedestrian isochrone search zones | Must | Zones computed from last-seen point + mobility profile `[params TO VALIDATE]` |
| ADM-05 | Dispatch responders to zones | Must | Each dispatch names a zone, responder, and task |
| ADM-06 | Sighting-triage verification view | Must | Officer can verify or dismiss each scored sighting |
| ADM-07 | Coverage map (Searched / In Progress / Uncovered) | Should | Map matches underlying zone states |
| ADM-08 | Incident analytics | Should | Coverage progress, triage outcomes, response times |
| ADM-09 | Manual override / re-dispatch | Should | Override logged with officer and time |
| ADM-10 | Activity log | Should | Who did what, when |
| ADM-11 | Data retention/expiry controls | Should | Personal data auto-expires per policy `[period TO VALIDATE]` |
| ADM-12 | SMS fallback for urgent alerts | Could | Sent only when push not acknowledged `[cost TO VALIDATE]` |

### 7.2 Responder mobile app (Android)

| ID | Requirement | Priority | Acceptance criteria |
|---|---|---|---|
| RSP-01 | Responder login | Must | Each action is tied to a responder account |
| RSP-02 | Receive zone alert | Must | Shows zone, profile essentials, task |
| RSP-03 | View own assigned zone / route | Must | Zone shown on a map |
| RSP-04 | Submit geotagged sighting (photo + note) | Must | Photo, location, and time captured |
| RSP-05 | Set active/inactive status | Should | No alerts when inactive |
| RSP-06 | View triage feedback on own sighting | Could | Tells responder if a sighting was verified |
| RSP-07 | Open zone in external maps app | Could | Tapping a zone opens external navigation |

### 7.3 Non-functional (ISO/IEC 25010 — selected)

| ID | Characteristic | Requirement |
|---|---|---|
| NFR-01 | Performance efficiency | Zone generation completes within `[X]` seconds for a target area |
| NFR-02 | Security | Role-based access; hashed passwords; HTTPS/TLS |
| NFR-03 | Security / privacy | Minimal personal data; no public face database; consensual handling of missing-person photos; RA 10173; access logging; retention limits |
| NFR-04 | Interaction capability (usability) | A responder can open an alert and start a sighting in ≤ `[N]` taps |
| NFR-05 | Reliability | A sighting is never lost; submission retries on weak connectivity |
| NFR-06 | Functional correctness | Triage scoring reported with precision/recall on simulated scenarios |

### 7.4 Deliberately excluded (Won't, this version)
Law-enforcement replacement · public facial recognition database · mass CCTV ingestion · live GPS body-tracking · multi-LGU deployment

---

## 8. Data model and behavior

### 8.1 Entities (logical)

| Entity | Key attributes |
|---|---|
| User | user_id, name, role (Officer/Tanod/Responder), contact, status |
| MissingPerson | person_id, name, age, photo_ref, description, vulnerability_type, mobility_profile, consent_ref |
| Incident | incident_id, person_id, last_seen_location, last_seen_time, status, opened_by, opened_at |
| SearchZone | zone_id, incident_id, geometry, priority_rank, time_band, status |
| Assignment | assignment_id, zone_id, responder_id, assigned_at, status |
| Sighting | sighting_id, incident_id, submitted_by, photo_ref, geolocation, submitted_at, status |
| TriageResult | triage_id, sighting_id, match_score, features_summary, scored_at, verified_by, outcome |
| ActivityLog | log_id, user_id, action, target, timestamp |

### 8.2 Relationships
- MissingPerson 1—* Incident
- Incident 1—* SearchZone
- Incident 1—* Sighting
- SearchZone 1—* Assignment; Assignment *—1 User (Responder)
- Sighting 1—0..1 TriageResult; TriageResult *—1 User (Officer, verifier)
- User 1—* ActivityLog

### 8.3 Business rules

> **Status: all business rules below (BR-01 – BR-09) are PROPOSED design decisions — none are confirmed.** They must be presented to the partner during the client interview and confirmed, adjusted, or rejected before the final proposal. Values marked `[TO VALIDATE]` are starting hypotheses only.

- BR-01: An incident requires a missing-person profile with a recorded consent/legal basis before zones are generated.
- BR-02: Search zones are computed as pedestrian-network isochrones from the last-seen point using the mobility profile; each zone carries a time band and a priority rank `[params TO VALIDATE]`.
- BR-03: Zone priority increases with elapsed incident time and with presumed mobility of the missing person `[rule TO VALIDATE]`.
- BR-04: A responder receives at most `[N]` active zone assignments at once `[N TO VALIDATE]`.
- BR-05: Every sighting is scored by the CV triage step before officer review; scoring never auto-declares a match `[threshold TO VALIDATE]`.
- BR-06: Only an officer may verify, dismiss, or close a sighting; only an officer may close an incident.
- BR-07: Sightings from unverified public tipsters pass through moderation before entering the triage queue.
- BR-08: Personal data (photos, sightings) expires per the retention policy once the incident is closed `[period TO VALIDATE]`.
- BR-09: A dispatch is only valid if the responder is Active and their zone is not already covered.

### 8.4 State models
**Incident**
```
Draft ──activate──► Active ──resolve──► Resolved ──refer──► Referred
Active ──close──► Closed (retention clock starts)
```
**Sighting**
```
Submitted ──score──► Scored ──officer verify──► Verified
Scored ──officer dismiss──► Dismissed
Submitted ──moderation rejects──► Rejected
```
**SearchZone**
```
Uncovered ──dispatch──► In Progress ──reported clear──► Searched
In Progress ──expired / re-prioritized──► Uncovered
```

---

## 9. IT0037 lessons mapped

### Module 1 — Systems Analysis Fundamentals
| Concept | Application |
|---|---|
| Symptom vs. root cause | Late alerts / clutter = symptoms; no localized zone-and-triage process = root cause |
| Evidence triangulation | Partner interview + responder survey + incident records + observation of one drill |
| Four title elements | Section 1 |
| Ethics red flags | No client yet; vulnerable persons' and minors' data; missing consent process; possible title collision |
| Stakeholder power–interest map | Section 2 |
| Hybrid approach with reasons | Prototyping (commander + responder screens) + Agile sprints + stage gates |
| Web & Mobile lens: service journey | Detect (incident) → locate (zones) → dispatch (responders) → collect (sightings) → triage (verify) → resolve |

### Shelly Ch. 2 — Systems Planning
| Concept | Application |
|---|---|
| Systems request | No partner request yet — this is a team-suggested title, a planning risk |
| Reasons for project | Better performance (faster dispatch), better information (coverage/triage), improved service |
| Preliminary investigation (6 steps) | Understand problem → scope/constraints → fact-finding → feasibility → time/cost → present |
| Constraints | Mandatory: RA 10173; External: device/internet; Present: one barangay, no live data |
| Fishbone | Causes of slow/uneven searches: People, Process, Technology, Communication, Geography, Data |
| Tangible / intangible benefits | Tangible: dispatch time, coverage; intangible: family reassurance, privacy confidence, coordination trust |

### Bender — SDLC
| Concept | Application |
|---|---|
| Stepwise commitment | Commit to build only after a partner confirms workflow and data access |
| Change control | Zoom/role expansions handled as scope changes |
| User involvement | Requires an engaged barangay partner — the main risk if none is secured |

### Module 2 — Feasibility (six dimensions)
| Dimension | Preliminary view | Condition / unknown |
|---|---|---|
| Technical | Conditional — routing engine + CV pipeline + mobile/web are standard, but the toolchain and GIS data are heavy for one term | Routing engine choice; CV model; target-area road data `[TO VALIDATE]` |
| Operational | High risk — depends on a willing barangay and tanod adoption | No client; responder smartphone access `[survey]` |
| Economic | Conditional | Routing/tiling + hosting + CV compute `[estimate in PHP]` |
| Schedule | High risk — two platforms + GIS + CV within one term | Team skills; remaining term; partner availability for drills |
| Security | Conditional — sensitive personal data, minors, faces | Role-based access, encryption, retention, access logs |
| Legal and ethical | High risk — RA 10173, consent, minors, no public face database, no LE role | DPA compliance plan `[TO VALIDATE]`; ethics review |

**Assumptions register**

| # | Assumption | Validation action |
|---|---|---|
| A1 | A barangay / DRRM office will partner and stay engaged | Secure a signed endorsement letter early |
| A2 | The barangay has a current manual/digital search process worth improving | Partner interview + incident records |
| A3 | Tanods / responders have smartphones and data | Responder survey |
| A4 | Pedestrian network data for the target area is obtainable | Check OSM / LGU GIS data |
| A5 | Sighting triage can be evaluated with simulated scenarios | Build a small labeled simulation set |
| A6 | A lawful basis/consent exists for handling faces and minors' data | Consult partner + adviser; DPA policy |

**Key risks (cause → event → impact)**

| Risk | Response |
|---|---|
| No partner is secured → cannot validate → title weakens | Approach multiple barangays/DRRM offices early; keep a fallback title |
| Partner disengages mid-term → data access lost | Signed endorsement letter; early milestone sign-offs; alternative partner |
| DPA/privacy violation → ethics rejection | Concrete consent, retention, access policy; no public face database; adviser review |
| Title collides with a barangay hazard-mapping group | Differentiate scope now; confirm with panel before pitching |
| "Just a monitoring dashboard" critique | Lead with zones + dispatch + triage; map is an output |
| CV triage overclaimed → accuracy questioned | Report precision/recall on simulated scenarios; state limits |
| Weak algorithm facet → panel rejection | Reframe as coverage optimization / set-covering, or delimit honestly |
| Scope too large for one term | Trim to one barangay, one mobility type, simulated incidents |

### Module 3 — Requirements
| Concept | Application |
|---|---|
| Stakeholder lenses | Barangay command (decision power), tanods/responders (process knowledge, change impact), families (consent) |
| Elicitation | Partner interview, responder survey, incident record review, observation of a drill |
| Claim classification | Mark items as observed fact / reported fact / assumption / decision |
| Testable requirements | Section 7 acceptance criteria |
| MoSCoW | Section 7 priorities |
| ISO/IEC 25010:2023 | Section 7.3 |
| RTM | Link requirement → stakeholder need → evidence → test |

### Module 4 — Structured and OO Modeling
**Context diagram:** System = AuraMesh. External entities: **Barangay Officer**, **Responder/Tanod**, **Public tipster** (moderated channel), **Notification service**, **GIS/Routing service**. Law enforcement is **outside** the system (referral only).

**Level 0 DFD processes**
1.0 Manage Missing-Person Profiles · 2.0 Manage Incidents · 3.0 Generate Search Zones (isochrone) · 4.0 Dispatch Responders · 5.0 Collect Sightings · 6.0 Triage Sightings (CV) · 7.0 Verify and Resolve · 8.0 Generate Analytics and Reports

**Data stores:** D1 Users · D2 Missing Persons · D3 Incidents · D4 Search Zones · D5 Assignments · D6 Sightings · D7 Triage Results · D8 Activity Log

**Use cases**
Officer: Manage Profiles · Open Incident · Generate Zones · Dispatch Responders · Verify Sightings · Monitor Coverage · Close Incident · View Analytics
Responder: View Zone Alert · View Assigned Zone · Submit Sighting · Set Status

**Search-zone model (honest):** pedestrian isochrone = reachable-area polygon per time band from the last-seen point on a walkable network. **If committed as an algorithm:** model zone selection as **coverage optimization** (maximize priority-weighted reachable area covered under a responder-hour budget) or **set covering** (minimum zone set covering the target area). Otherwise present as a computation.

**Decision table (sighting triage routing, BR-05/BR-07)**

| Condition | R1 | R2 | R3 | R4 |
|---|---|---|---|---|
| From verified responder? | Y | N | Y | N |
| Passes moderation? | – | Y | – | N |
| Score above threshold? | Y | Y | N | – |
| **Fast-track to officer** | X | | | |
| **Queue for officer review** | | X | X | |
| **Reject** | | | | X |

**Key sequence (Submit sighting):** Responder → System: submit photo+location → System: extract features, score vs. profile → System: TriageResult (Scored) → Officer dashboard → Officer verifies/dismisses → coverage and incident update.

---

## 10. Development approach and evaluation

- **Approach:** Hybrid — prototyping (commander and responder screens), Agile sprints (build), stage gates (proposal approval → design approval → simulation approval).
- **Pilot:** run **simulated incident scenarios** in one barangay; no live missing-person data required for evaluation.
- **Evaluation:** ISO/IEC 25010 Likert survey (functional suitability, interaction capability, reliability, security) with officers and responders; triage precision/recall against simulated ground truth; zone coverage completeness.

### Suggested stack (NOT decided)
- Command dashboard: web (React/Vue)
- Responder app: native Android (Kotlin/Java or Flutter)
- Backend: Node/Express, Laravel, or Django · DB: PostgreSQL + PostGIS
- Routing / isochrones: pgRouting or OSRM `[choose which]`
- CV triage: on-device or server-side feature extraction/embedding (e.g., a lightweight face/visual embedding model) — **no public face database** `[choose model]`
- Notifications: Firebase Cloud Messaging (free tier) · SMS optional
- Scheduler: queue/cron job for zone re-prioritization, expiry, reminders

---

## 11. Data gathering plan

| Method | Participants | Purpose | Target date |
|---|---|---|---|
| Partner search | Candidate barangays / DRRM offices | Find a willing, engaged partner | `[set]` — do this first |
| Interview | Barangay officer / DRRM officer | Current search workflow, incident volume, constraints, equipment | `[set]` |
| Survey | Tanods / responders | Devices, data access, willingness to use the app | `[set]` |
| Document review | De-identified incident/blotter records (1–3 months or 1 year) | Volume, response patterns, pain points | `[set]` |
| Observation | One search drill or tabletop exercise | Time to dispatch, coverage gaps | `[set]` |
| Endorsement letter | Barangay / DRRM office | Formal partner commitment + DPA undertaking | Before mock defense |

**Honest answer if asked "Do you have a client?":** "Not yet. A barangay or DRRM office is our target partner, and the first risk we are managing is securing a real, engaged one — we have seen how hard barangays are to instrument, so we are approaching several and will not treat the problem as proven until a partner confirms it."

---

## 12. Defense Q&A bank

| Question | Answer |
|---|---|
| Do you have a client? | Not yet. A barangay or DRRM office is a target partner; securing one is our top open risk. We disclose that. |
| Isn't this just a monitoring dashboard? | No — the product is zone generation, dispatch, and triage. The coverage map is an output, not the system. |
| What is the algorithm? | Honestly, isochrone modeling is a computation, not a strong optimizer. Our stronger framing is isochrone-based **coverage optimization** or a **set-covering** search-area model. We flag this as the title's weakest facet. |
| Where does AI fit? | Privacy-preserving computer vision feature extraction that scores volunteer sighting photos against a single missing-person profile, then an officer verifies. No autonomous decisions. |
| Isn't that facial recognition? Isn't that illegal/risky? | It is not a public face database or mass surveillance. It matches **volunteer-submitted photos** against **one consented profile**, with retention limits and access logs. DPA handling is a blocking requirement `[TO VALIDATE policy]`. |
| What about minors' and vulnerable persons' data? | Highest-risk item. Requires explicit consent/legal basis, minimal data, and a retention policy before any real use; evaluation uses simulated scenarios. |
| How is it different from Facebook posts or a megaphone? | Structured zones + responder dispatch + triage, instead of a blunt broadcast that causes alert fatigue. |
| Why not a commercial GIS/SAR tool? | Built for trained operators and budgets a barangay does not have; AuraMesh targets barangay-level use. |
| Where does the isochrone data come from? | A pedestrian road/path network for the target area (e.g., OSM); availability is `[TO VALIDATE]`. |
| How do you evaluate without live cases? | Simulated incident scenarios with known ground truth; measure dispatch time, coverage, and triage precision/recall. |
| Does this replace the police / SAR? | No. Community-level coordination only; it refers and hands off to authorities. |
| What if there's no internet/weak signal? | Sighting submission retries; offline-tolerant capture; alerts queue. |
| Could this collide with a barangay hazard-mapping title? | Different scope — search coordination, not hazard mapping — but we will confirm no overlap with the panel before pitching. |
| Generalizable? | Built for one partner barangay; not claimed beyond it until tested elsewhere. |
| Methodology? | Hybrid: prototyping + Agile + stage gates. |
| Evaluation? | ISO/IEC 25010 survey + triage precision/recall + coverage completeness on simulations. |

---

## 13. Mock defense deck outline

| # | Slide | Source |
|---|---|---|
| 1 | Title + four-element breakdown | §1 |
| 2 | Target setting: barangay search operations + no-client disclosure statement | §1, §0 |
| 3 | Current search workflow (as-is) + evidence status | §2 |
| 4 | Problem: symptoms vs. root cause (fishbone) + stakeholders | §2 |
| 5 | Objectives (with honest algorithm-facet note) | §4 |
| 6 | How it works (flow diagram) | §5 |
| 7 | Key logic: isochrone zones → dispatch → triage | §8.3 |
| 8 | Related systems + differentiator | §3 |
| 9 | Scope, limitations, privacy/DPA posture | §6 |
| 10 | Context diagram + key requirements | §7, §9 |
| 11 | Feasibility (six dimensions) + key risks (incl. client risk) | §9 |
| 12 | Methodology + evaluation | §10 |
| 13 | Data gathering plan + open risks / panel questions | §11, §6 |

---

## 14. Sources

- AzTech Title 3 PDF entry (Title 3, AuraMesh) — internal team document
- Mimamori municipal safety mesh concept — `[TO VALIDATE]` (cite a checkable source or present as inspiration only)
- Pedestrian isochrone / routing toolchain (pgRouting, OSRM) — verify on official docs before citing
- Republic of the Philippines. (2012). Data Privacy Act of 2012 (Republic Act No. 10173)
- ISO/IEC 25010:2023 — product quality model
- Any SAR coverage / grid search references — verify before citing

> Partner evidence (interview notes, incident records, endorsement letter) will be the primary source once a partner exists.

---

## 15. Open items / next steps

- [ ] Secure a barangay or DRRM partner; get a signed endorsement letter + DPA undertaking
- [ ] Confirm no title collision with the barangay hazard-mapping group
- [ ] Decide the algorithm framing: coverage optimization / set covering vs. honest isochrone-computation delimitation
- [ ] Confirm target-area pedestrian network data (OSM / LGU GIS)
- [ ] Choose the CV triage model and confirm a privacy-preserving design (no public face database)
- [ ] Draft the RA 10173 consent, retention, and access-log policy
- [ ] Interview barangay/DRRM officer; collect de-identified incident records
- [ ] Responder survey (devices, data, willingness)
- [ ] Agree on system name with the team
- [ ] Replace every `[TO VALIDATE]` with evidence or keep as labeled assumption
- [ ] Draft context diagram, Level 0 DFD, ERD, state diagrams, and a simulated-scenario evaluation set
