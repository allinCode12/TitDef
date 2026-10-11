# AuraMesh — Mock Title Defense Slide Deck Blueprint
*(13-slide drop-in deck for the AzTech Mock Title Defense — Title 3)*

---

### Slide 1: Title Slide
* **Title:** AuraMesh: A Localized Pedestrian Isochrone Search Coordination and Computer Vision-Assisted Sighting Triage System for Vulnerable Missing Persons
* **Subtitle:** Capstone Title Proposal
* **Client Partner:** `[TO VALIDATE]` — no barangay / DRRM partner secured yet
* **Specialization:** BSIT — Web and Mobile Application
* **Presenter / Proponent:** [Your Name] (Team AzTech — Group 6)

---

### Slide 2: Title and Four-Element Breakdown (Module 1) + No-Client Disclosure
* **Title Breakdown Table:**
  * **System / Capability:** Localized Pedestrian Isochrone Search Coordination and Computer Vision-Assisted Sighting Triage
  * **Users / Setting:** Vulnerable missing-person search in a community / barangay setting (barangay officers + tanods / verified responders)
  * **Value / Problem Direction:** Faster, better-distributed coverage in the critical early hours; verified leads instead of clutter
  * **Specialization Differentiator:** Web and Mobile (responsive barangay command dashboard + Android responder client)
* **Honest Disclosure (say this out loud):**
  * No client partner is secured yet; a barangay or DRRM office is only the target.
  * Barangays are hard to instrument; the team has previously dropped barangay-dependent ideas for this reason.

---

### Slide 3: The Target Setting and Current Workflow (Module 1)
* **Setting Context:**
  * Vulnerable missing persons — wandering children and elderly with cognitive impairment or dementia.
  * Early response hours are decisive; coordination is usually manual (calls, messages, megaphone).
* **As-Is Search Flow (hypothesized, `[TO VALIDATE]`):**
  * Alert raised informally → people spread out without a shared map → sightings arrive as scattered messages/photos → duplicates and false alarms → effort overlaps while other areas stay uncovered.

---

### Slide 4: Problem: Symptoms vs. Root Cause + Stakeholders (Module 1)
* **Symptoms `[TO VALIDATE]`:**
  * Alerts dispatched late; coverage uneven across the area.
  * Flood of unverified sighting reports; real leads buried.
  * Wide, inflexible broadcast radius → alert fatigue among uninvolved residents.
* **Root Cause Hypothesis:**
  * **No localized, time-aware process to turn a last-seen point into ordered search zones, assign responders, and triage sightings.**
* **Stakeholders (Module 3):**
  * **Barangay Officer / Command Staff:** Process owner & admin user (High power, High interest).
  * **Tanods / Community Watchmen:** Direct mobile users (High interest, Operational).
  * **Verified Responders (BDRRMC / volunteers):** Direct mobile users.
  * **Families:** Indirect, affected; source of consent (High interest).
  * **Public / Tipsters:** External, moderated channel.
  * **Adviser & Panel:** Governance and evaluation.

---

### Slide 5: General and Specific Objectives (Module 2)
* **General Objective:**
  * To develop a web and mobile community search-coordination and sighting-triage system that helps a barangay command team define localized pedestrian search zones, dispatch responders, and triage sighting photos for vulnerable missing persons.
* **Specific Objectives:**
  1. Develop a **Web Command Console** for barangay officers to manage missing-person profiles, open incidents, and view search coverage.
  2. Develop an **Android Responder App** for tanods / verified responders to receive targeted zone alerts and submit sighting reports.
  3. Implement **GIS pedestrian isochrone modeling** to compute dynamic search zones from last-seen location and mobility.
  4. Implement **privacy-preserving computer vision triage** to score crowd-sourced sighting photos against a missing-person profile.
  5. Provide an **incident analytics and triage verification dashboard**.
  6. Evaluate performance, triage accuracy, and coverage using **simulated incident scenarios** (ISO/IEC 25010 + precision/recall).
* **Honest Facet Note (small text):**
  * The isochrone step is a **computation, not a strong optimization**; our stronger framing is coverage optimization / set covering — flagged as the title's weakest facet.

---

### Slide 6: Proposed Solution and Flow Diagram (Module 2)
* **Step-by-Step Flow:**
  * **Step 1 — Incident Opened:** Officer registers a missing-person profile (photo, description, vulnerability, mobility, last-seen location/time) under a consent basis.
  * **Step 2 — Zones Generated:** Pedestrian-network isochrones produce an ordered set of time-based search zones.
  * **Step 3 — Responders Dispatched:** Tanods/responders get targeted zone assignments instead of a blunt broadcast.
  * **Step 4 — Sightings Submitted:** Geotagged photos and notes come from responders and a moderated public channel.
  * **Step 5 — Triage:** Privacy-preserving CV scores each sighting against the profile; officer verifies or dismisses.
  * **Step 6 — Coverage & Resolution:** Dashboard shows Searched / In Progress / Uncovered; officer resolves or refers.

---

### Slide 7: Key Logic — Zones, Dispatch, Triage (Module 4)
* **Search Zones:** isochrone on a walkable network from the last-seen point; priority rises with elapsed time and presumed mobility.
* **Dispatch:** each responder gets a named zone and task; no duplicate coverage; inactive responders excluded.
* **Triage:** every sighting is scored before review — scoring never auto-declares a match; only an officer verifies.
* **Proposed rules `[TO VALIDATE]`:** consent required before zone generation; retention/expiry on incident close; moderation before triage for public tips.

---

### Slide 8: Related Systems vs. AuraMesh (Differentiator)
* **Comparison Matrix:**
  * **Facebook / Messenger appeals + group chats:** broadcast only; no zones, no triage, replies buried, alert fatigue.
  * **Megaphone / house-to-house:** slow, manual, no spatial coverage logic.
  * **Find-my-phone / family trackers:** only work with a charged, enabled, consented device.
  * **Commercial GIS / SAR tools:** professional-grade, costly, built for trained operators.
* **AuraMesh Differentiator:**
  * Pedestrian-isochrone **zone generation** + **targeted responder dispatch** + **privacy-preserving triage**, sized for a barangay team. *[Preliminary comparison based on publicly described features; competitor capabilities and pricing require verification — see Context Pack §3.]*

---

### Slide 9: Scope and Limitations + Privacy Posture (Module 1)
* **In Scope (✓):**
  * Web Command Console (profiles, incident lifecycle, isochrone zones, dispatch, triage verification, coverage, analytics, logs).
  * Android Responder App (zone alerts, assigned zone, geotagged sighting submission, status).
  * Privacy-preserving CV triage against a single profile; simulated-scenario evaluation.
* **Out of Scope (✗):**
  * No law-enforcement replacement; no public face database; no mass CCTV; no live GPS body-tracking.
* **Privacy Posture (say clearly):**
  * Volunteer sightings matched against **one consented profile** only; minimal data; retention limits; access logs; RA 10173. DPA policy is a **blocking requirement** `[TO VALIDATE]`.

---

### Slide 10: Key Requirements (Module 3)
* **Functional Requirements (MoSCoW):**
  * **Must:** Officer authentication; missing-person profile registry; incident lifecycle; isochrone zone generation; responder dispatch; sighting submission; CV triage + officer verification.
  * **Should:** Coverage map; incident analytics; manual re-dispatch; activity log; retention controls.
  * **Could:** SMS fallback; external map navigation; triage feedback to responders.
* **Non-Functional & Quality Standards (ISO/IEC 25010):**
  * **Performance Efficiency:** zone generation within `[X] seconds — target to be established during testing [post-test criterion]`.
  * **Security & Privacy:** role-based access, hashed credentials, HTTPS/TLS, retention limits, RA 10173.
  * **Reliability:** no sighting is lost; submission retries on weak connectivity.
  * **Functional Correctness:** triage precision/recall reported on simulated scenarios.

---

### Slide 11: Feasibility Snapshot and Lifecycle Choice (Module 2)
* **Six-Dimensional Feasibility Snapshot:**
  * **Technical:** Conditional. Routing/isochrone engine + CV pipeline + web/mobile are standard, but the toolchain and GIS data are heavy for one term `[TO VALIDATE]`.
  * **Operational:** High risk. Depends on a willing barangay and tanod adoption; no partner secured yet.
  * **Economic:** Conditional. Routing/tiling hosting + CV compute; final PHP estimate pending.
  * **Schedule:** High risk. Two platforms + GIS + CV inside one term; phased hybrid sprints.
  * **Security:** Conditional. Sensitive personal data, minors, faces — role-based access, encryption, retention, logs.
  * **Legal & Ethical:** High risk. RA 10173, consent, minors, no public face database, no LE role — advisor review required.
* **Lifecycle Choice:**
  * **Tailored Hybrid Approach:** Prototyping (officer + responder screens) + Agile Sprints (zone/triage build) wrapped in Predictive Stage-Gates (partner and academic sign-offs).

---

### Slide 12: Risks and Open Panel Questions (Be First to Raise Them)
* **Client risk:** barangays are hard to instrument; we have dropped barangay-dependent ideas before. A signed partner + DPA undertaking is the first milestone.
* **Title-collision risk:** a batch group may have a barangay **hazard-mapping** title; ours is search coordination — we will confirm no overlap before pitching.
* **Privacy/DPA risk:** faces of missing persons and minors + crowd photos are sensitive data.
* **"Just monitoring" critique:** the map is an output; the system is zones + dispatch + triage.
* **Algorithm critique:** isochrone is a computation — we will reframe as coverage optimization / set covering or delimit it honestly.

---

### Slide 13: Data Gathering Plan and Next Steps (Module 3 & 4)
* **Next Steps for Primary Fact-Finding:**
  * **Phase A — Partner Search (do this first):** approach multiple barangays / DRRM offices; secure one partner.
  * **Phase B — Officer Interview:** current search workflow, incident volume, constraints, equipment.
  * **Phase C — Responder Survey:** devices, data access, willingness to use the app.
  * **Phase D — Records & Drill:** de-identified incident records + one search drill for baseline.
  * **Phase E — Endorsement Letter + DPA undertaking:** formal partner commitment.
* **Convergence Goal:**
  * Replace all `[TO VALIDATE]` markers with partner evidence and a simulated-scenario evaluation set for the final Title Defense.
