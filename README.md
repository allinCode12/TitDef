# AzTech (Group 6) — Capstone Title Defense Strategy & Portfolio

**Course:** IT0037 Systems Analysis and Design (Title Defense Semester)
**Program:** BS Information Technology — Web and Mobile Application (WMA)
**Institution:** FEU Diliman / FEU Institute of Technology
**Members:** Canido, Felix Jed · Mesina, Patrick Kyle · Borromeo, Zire Niccolai · Oronico, Lee Justin

> **Source of truth for the lineup:** `AzTech_ Title Proposal.pdf` (4 titles). This README mirrors that PDF. Older title packs are archived in the notes at the bottom.

---

## 📌 Executive Summary & Defense Strategy

The team has completed consultations and is preparing the title portfolio for the advisor's pick. The submitted PDF proposes **four titles**, each built on a real operating context with a distinct algorithm, functional AI, and analytics.

### The Professor's Mandate
1. **Three distinct titles** (plus a fourth candidate so the advisor can approve three).
2. **Dedicated provable algorithm** in each title (no basic CRUD or management systems).
3. **Functional AI integration** where possible using lightweight, on-premise or edge models (low or zero cloud cost, RA 10173 compliant).
4. **Descriptive and predictive analytics** in each title.
5. **Real-world client evidence.** AI approval is not panel approval: the lesson from the rejected ResiboCheck is that a real, nameable client is what matters.

---

## 🚨 Batch Competitor Conflict Audit

We audited other groups in our section (CodePuff, Tiger Commando, The Websters, Techonoraws) to avoid duplicated topics:
- **Barangay hazard mapping is already taken.** Group 2 (Tiger Commando) received approval for `BALAMAP: A Mobile-Based Crime and Hazard Mapping System for Barangay Matandang Balara`. AuraMesh touches the barangay space, so we must differentiate it from hazard mapping on sight.
- **Outdoor public-transit commuting is taken.** Groups 1, 2, and 3 proposed city-wide transit titles. Our lineup does not use public-transit commuting as a value proposition.

---

## 🏆 The Capstone Portfolio & Defense Lineup

| # | Title | Client Setting | Dedicated Algorithm | Local / Edge AI | Analytics Focus |
| :---: | :--- | :--- | :--- | :--- | :--- |
| **1** | **CrewSync:** AI-Assisted Event Staffing and Schedule Coordination | Kiddie Salon by Nail Brat *(secured; disclosed relative)* | **Constrained bipartite assignment** (Kuhn-Munkres) with overlap and travel-buffer constraints | Response-likelihood scoring, data-permitting, with rules-only cold start | Events per month/year, package mix, time-to-full-staffing, talent utilization |
| **2** | **AlumniTrack:** Graduate Career Tracking and Skill-to-Market Gap Analysis | FEU Diliman office *(Gate 0 — no client yet)* | **Vector Space Cosine Similarity** against CHED CMO 25 s. 2015 outcomes | NLP tokenization + Named Entity Recognition to extract skills | Longitudinal Time-to-First-Employment, employment distribution, skill-gap trends |
| **3** | **AuraMesh:** Missing-Person Search Coordination and Sighting Triage | Barangay DRRM / responders *(no client yet)* | **GIS pedestrian isochrone modeling** (coverage optimization framing `[TO VALIDATE]`) | Privacy-preserving computer vision sighting triage | Incident analytics and sighting triage verification |
| **4** | **LensCull:** Edge AI Visual Culling and Submodular Album Selection | Event photography studio *(no client yet; POC exists)* | **Submodular Facility Location** with Accelerated Lazy Greedy | Edge CV (OpenCV Laplacian + MediaPipe EAR) and quantized OpenCLIP semantic search | Cull compression ratio, per-photographer defect distribution, milestone coverage |

**Portfolio-level caution:** Titles 3 and 4 are both computer-vision heavy. Be ready to show they are distinct (AuraMesh is spatial search coordination for people; LensCull is on-premise photo curation).

---

## 📂 Repository Directory Structure

```
TitDef/
├── README.md                                  # This master portfolio strategy & alignment guide
├── Title3_Selection_Worksheet.md              # 8-Gate rejection-proofing worksheet & consultation log
├── CrewSync_BSIT_WMA_Research_Mentor_Skill.md # Mentor prompts, research queries, anti-hallucination rules
├── ResiboCheck_Project_Context_DEPRECATED.md  # Post-mortem & rejection trace of the first rejected title
│
├── CrewSync/                                  # TITLE 1 PACK (Event Staffing)
│   ├── CrewSync_Project_Context.md            # Single source of truth
│   ├── CrewSync_Defense_Cheat_Sheet_UPDATED.md
│   ├── CrewSync_Slide_Deck_Content.md
│   ├── Title_Proposal_Form_Filled.md          # Paste-ready proposal form
│   ├── Client_Owner_Interview_Guide.md
│   └── Client_Endorsement_Letter_Template.md
│
├── AlumniTrack/                               # TITLE 2 PACK (Graduate Tracer)
│   ├── AlumniTrack_Project_Context.md         # Single source of truth (Gate 0 status, RA 10173)
│   ├── Title_Proposal_Form_Filled.md          # Paste-ready proposal form
│   ├── AlumniTrack_Defense_Cheat_Sheet.md
│   ├── AlumniTrack_Slide_Deck_Content.md
│   ├── Client_Interview_Guide.md
│   ├── Gate0_Approach_Message.md
│   └── Client_Endorsement_Letter_Template.md
│
├── AuraMesh/                                  # TITLE 3 PACK (Missing-Person Search)
│   ├── AuraMesh_Project_Context.md            # Single source of truth (no client yet)
│   ├── Title_Proposal_Form_Filled.md          # Paste-ready proposal form
│   ├── AuraMesh_Defense_Cheat_Sheet.md
│   ├── AuraMesh_Slide_Deck_Content.md
│   ├── Client_Interview_Guide.md
│   └── Client_Endorsement_Letter_Template.md
│
├── LensCull/                                  # TITLE 4 PACK (Photo Culling; POC exists)
│   ├── LensCull_Project_Context.md            # Single source of truth (no named client yet)
│   ├── Title_Proposal_Form_Filled.md          # Paste-ready proposal form
│   ├── LensCull_Defense_Cheat_Sheet.md
│   ├── LensCull_Slide_Deck_Content.md
│   ├── LensCull_Validation_Plan.md            # 120-shot benchmark plan for the Python CLI POC
│   ├── Client_Interview_Guide.md
│   └── Client_Endorsement_Letter_Template.md
│
├── AquaRoute/                                 # ARCHIVED (Micro-logistics CVRPTW) — not in the PDF lineup
├── JobFlow/                                   # ARCHIVED (Print-shop FJSP scheduling) — not in the PDF lineup
├── LifelinePack/                              # ARCHIVED (Disaster relief MKP) — not in the PDF lineup
├── PathPoint/                                 # ARCHIVED (Indoor wayfinding A*) — not in the PDF lineup
│
└── scratch/                                   # Course lecture extracts, modules, and activity drafts
```

**Archived packs** (`AquaRoute`, `JobFlow`, `LifelinePack`, `PathPoint`, and the deleted `MottainaiMark`) are **not** part of the PDF lineup. Keep them as backups only. Do not present them as current titles unless the advisor re-adds them. The old `MottainaiMark/MottainaiMark_Project_Context.md` is deleted in the working tree.

---

## 🛡️ Standard Defense Script

When the panel asks:

### 1. "Isn't this just CRUD or a management system?"
> *"A management system is descriptive. It is a passive ledger. Our systems are prescriptive optimization engines. CrewSync solves a constrained bipartite assignment. AlumniTrack measures curriculum-to-market alignment with Vector Space Cosine Similarity. AuraMesh computes pedestrian isochrone search coverage. LensCull solves a Submodular Facility Location problem. The database is only an input. The research contribution is the mathematical optimization."*

### 2. "Why does every title need AI?"
> *"The AI is scoped to a narrow, checkable job and never makes the operational decision. CrewSync scores response likelihood and the owner confirms. AlumniTrack runs NLP skill extraction, evaluated with precision, recall, and F1. AuraMesh triages sighting photos for human verification. LensCull screens blur and blink defects and enables local semantic search. The final decisions stay with the deterministic algorithm or the human in the loop."*

### 3. "Why both Web and Mobile?"
> *"The split follows context of use. The web application is for desktop command, configuration, planning, and dense analytics. The mobile application is for frontline actors who are away from a desk and need alerts, GPS, offline use, and single-tap task completion."*

### 4. "What about the Data Privacy Act?"
> *"Every title that handles personal data, alumni records, missing-person photos, or event photos, designs consent, minimization, retention limits, and role-based access from Day 1. Sensitive data stays on-premise or on-device wherever the design allows."*

---

## ⏱️ Immediate Next Steps
1. **CrewSync:** conduct the owner interview and have the endorsement letter signed.
2. **AlumniTrack:** send `AlumniTrack/Gate0_Approach_Message.md` to a FEU Diliman office this week; the title still needs the Users/Setting element.
3. **AuraMesh:** decide whether to keep the barangay client given the hard-to-instrument risk, and firm up the algorithm facet (isochrone is a computation, not an optimization).
4. **LensCull:** secure a named photographer and run the `LensCull_Validation_Plan.md` 120-shot benchmark.
5. **All:** replace every `[TO VALIDATE]` with evidence or keep it labeled as an assumption.
