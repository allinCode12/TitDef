# Capstone Project Title Proposal — Title 3 (AuraMesh) — Paste-Ready Fill

**Form:** FEU Institute of Technology · College of Computer Studies · Capstone Project Title Proposal (System Analysis and Design)
**Program:** Bachelor of Science in Information Technology, specialization in Web and Mobile Application
**Group:** AzTech (Group 6) · **Members:** Canido, Felix Jed; Mesina, Patrick Kyle; Borromeo, Zire Niccolai; Oronico, Lee Justin
**Term:** [x] 1st · Academic Year: 2026–2027
**Proposed Project Title 3:** AuraMesh: A Localized Pedestrian Isochrone Search Coordination and Computer Vision-Assisted Sighting Triage System for Vulnerable Missing Persons

> **Source of truth:** this file restates the team's Title 3 PDF entry (`aztech_pdf2.txt`, pages 8–10) as a clean form fill. The PDF's section numbering (15.0–21.0) has been re-numbered sequentially (1.0–7.0). Client-dependent and unverified items are marked `[TO VALIDATE]` — there is **no client yet**. Paste each field directly into the form.

---

### 1.0 Area of Investigation

Analysis, design, and implementation of a community-based search coordination and sighting triage platform for vulnerable missing persons such as wandering children and elderly individuals with cognitive impairment or dementia. Inspired by municipal "Mimamori" safety meshes `[TO VALIDATE — cite checkable source]`, this investigation integrates GIS pedestrian network isochrone modeling, privacy-preserving visual feature extraction, and targeted mobile mesh dispatching. The architecture combines a responsive web command dashboard for barangay officers with an Android mobile client for community watchmen (tanods) and verified responders, supporting IT0037 Systems Analysis and Design and the BSIT Web and Mobile Application specialization.

---

### 2.0 Background and Rationale of the Project

Community search operations for missing vulnerable persons often suffer from delayed notification dispatches and inefficient coverage distribution, leading to critical delays during early response hours. Traditional manual search efforts lack localized spatial coordination and real-time sighting triage mechanisms.

- Delayed search initiation and lack of real-time geographical tracking during critical early search windows.
- Uncoordinated visual sighting reports and false alarm clutter from unverified public tips.
- Inflexible broadcast radius causing alert fatigue among uninvolved community members.

AuraMesh addresses these challenges through pedestrian network isochrone mapping, privacy-preserving visual feature matching, and targeted responder dispatching. The platform dynamically defines priority search zones based on time elapsed and mobility profiles, streamlining community response efforts.

`[TO VALIDATE]` The project targets a barangay office or municipal DRRM (Disaster Risk Reduction and Management) office as industry partner; no partner has been secured yet, and the proposed workflow and pain points above remain unvalidated hypotheses until a partner confirms them by interview and incident records.

---

### 3.0 Statement of Objectives

The main objective is to analyze, design, and develop AuraMesh, an integrated web and mobile community search-coordination and sighting-triage system for vulnerable missing persons. Specifically, the project aims to:

1. Develop a web administrative command console for barangay officers to manage missing person profiles, initiate incident alerts, and monitor real-time search coverage maps.
2. Develop an Android mobile companion application for community watchmen (tanods) and verified responders to receive targeted alerts and submit visual sighting reports.
3. Implement GIS-based pedestrian network isochrone modeling to calculate dynamic search radii based on last-seen locations and estimated mobility parameters.
4. Implement privacy-preserving computer vision feature extraction algorithms to triage and score crowd-sourced sighting photos against missing person profiles.
5. Evaluate system performance, sighting triage accuracy, and search radius effectiveness using simulated incident scenarios.

> **Note for the team (not for the form):** objective 3 is a computation, not a strong optimization algorithm. Banner the algorithm facet honestly. Consider strengthening it to isochrone-based **coverage optimization** or a **set-covering search-area model**, or carry the CV triage + analytics as the algorithmic weight. See the Context Pack §4.

---

### 4.0 Scope and Limitations of the Study

**Scope:**

- Web Console (Command Admin): Missing person profile registry, pedestrian isochrone search grid modeling, sighting triage verification dashboard, and incident analytics.
- Android Mobile App (Responders & Tanods): Location-based alert notifications, interactive search grid routing, photo-based sighting submission, and active status tracking.

**Limitations:**

- Restricted to community-level pedestrian search scenarios within participating barangay jurisdictions and does not replace official law enforcement operations.
- Not a public facial-recognition database or mass-surveillance system: computer vision triages volunteer-submitted sighting photos against a single missing person profile only, with officer verification.
- Evaluation uses simulated incident scenarios rather than live missing-person cases `[TO VALIDATE — no live data available at capstone time]`.
- Handling of minors' and vulnerable persons' images requires an explicit consent/legal basis and a data retention policy under RA 10173 `[policy TO VALIDATE]`.
- The isochrone modeling step is a spatial computation; it is not claimed to be a strong optimization algorithm.
- No client partner is secured yet; single-partner evaluation is assumed once one is found, and results are not generalized.

---

### 5.0 Target Beneficiaries

- Barangay Command & Local Authorities: Gains real-time operational maps and verified sighting triage to deploy local responders efficiently.
- Barangay Tanods & Community Responders: Receives clear, localized search grid assignments and photo verification tools.
- Families & Community Members: Benefits from rapid search mobilization and privacy-conscious incident management.

---

### 6.0 References

- Community search and rescue / grid-search studies `[verify a checkable source before citing]`
- Geographic information systems and pedestrian isochrone references `[verify toolchain sources]`
- Republic of the Philippines. (2012). Data Privacy Act of 2012 (Republic Act No. 10173). Official Gazette.
- Shelly, G. B., Cashman, T. J., & Rosenblatt, H. J. (2012). *Systems analysis and design* (9th ed.). Cengage Learning. *(verify edition/year against syllabus copy)*

> *(Simple/general style for title approval only. Full list kept in reserve below for the final proposal.)*

---

### 7.0 Appendices and Evidence Attachments

- Pedestrian Isochrone Modeling & Spatial Search Grid Schemas
- Sighting Triage Workflow & Mobile Responder UI Wireframes
- Interview and evaluation forms `[once a partner exists]`

---

<details>
<summary><b>Reserved for final proposal (Chapter 2 / final defense) — not for this form</b></summary>

**References (full):**
1. FEU Diliman. (n.d.). IT0037 Module 1: Systems analysis fundamentals and organizational context [Course material]. Department of Information Technology.
2. FEU Diliman. (n.d.). IT0037 Module 2: Planning systems projects and preliminary investigation [Course material]. Department of Information Technology.
3. Republic of the Philippines. (2012). Data Privacy Act of 2012 (Republic Act No. 10173). Official Gazette.
4. International Organization for Standardization. (2023). ISO/IEC 25010:2023 — Systems and software Quality Requirements and Evaluation (SQuaRE): Product quality model.
5. Shelly, G. B., Cashman, T. J., & Rosenblatt, H. J. (2012). *Systems analysis and design* (9th ed.). Cengage Learning. *(verify edition/year against syllabus copy)*
6. Mimamori-type municipal safety mesh references — `[TO VALIDATE: cite a checkable source, otherwise present as inspiration only]`
7. Pedestrian routing / isochrone toolchain (e.g., pgRouting, OSRM) — verify official documentation before citing

**Appendices (full):** Client Endorsement & Permission Letter (with no-client disclosure) · Barangay / DRRM Officer Interview Guide · Evidence Status Matrix · RA 10173 Data Handling Plan `[when available]`

> System architecture and use-case diagrams belong to analysis/design after title approval — never list them as appendices at title stage (they don't exist yet and would be requested).

</details>
