# AzTech (Group 6) — Capstone Title Defense Strategy & Portfolio
**Course:** IT0037 Systems Analysis and Design (Title Defense Semester)  
**Program:** BS Information Technology — Web and Mobile Application (WMA)  
**Institution:** FEU Diliman / FEU Institute of Technology  
**Members:** Canido, Felix Jed · Mesina, Patrick Kyle · [Group Member]  

---

## 📌 Executive Summary & Defense Strategy

Our team has completed two consultations and is preparing for **Consultation #3 / Final Title Defense**.

### The Professor's Mandate (From Consultation #2):
1. **Three Distinct Titles Required** (with a 4th candidate prepared so the advisor can pick and approve 3).
2. **Dedicated Provable Algorithm** in each title (No basic CRUD/management systems).
3. **Functional AI Integration** (specifically using lightweight, on-premise/local AI like **Google's Gemma 2B** via Ollama to guarantee zero cloud API costs and 100% compliance with the Philippine Data Privacy Act / RA 10173).
4. **Descriptive & Predictive Analytics Engine** in each title.
5. **Real-World Client Evidence (Gate 1)** (No unverified/hypothetical ideas like the rejected ResiboCheck).

---

## 🚨 Batch Competitor Conflict Audit (Why Our Lineup Is 100% Blue Ocean)

We audited all other groups in our section (CodePuff, Tiger Commando, The Websters, Techonoraws) to avoid duplicated topics:
* **The Barangay Hazard Trap Avoided:** Group 2 (Tiger Commando) already received approval from 2 professors for `BALAMAP: A Mobile-Based Crime and Hazard Mapping System for Barangay Matandang Balara`. We intentionally **avoided any Barangay hazard mapping topic** to eliminate direct collision.
* **The Commute Congestion Avoided:** Groups 1, 2, and 3 all proposed city-wide outdoor public transit commuting (`CommuteNCR`, `CommutePH`, `Smart Public Transport Marikina`). Our transport/navigation titles focus strictly on **private micro-fleet vehicle routing (AquaRoute)** and **indoor building navigation (PathPoint)**.

---

## 🏆 The Official Capstone Portfolio & Defense Lineup

| Rank | Title | Client Setting | Dedicated Algorithm | Local AI (Gemma 2B) | Analytics Focus |
| :---: | :--- | :--- | :--- | :--- | :--- |
| **RANK 1** | **CrewSync:** Event Staffing Optimization System | Kiddie Salon by Nail Brat *(Secured, Disclosed Relative)* | **Maximum Weight Bipartite Matching** (Kuhn-Munkres) with Haversine Spatio-Temporal Buffers | Ingests messy chat inquiries into JSON + generates explainable assignment rationales | Fulfillment lead-time, response decay curves, Slot At-Risk warning index |
| **RANK 2** | **AquaRoute:** Micro-Logistics & Delivery Route Optimization | Neighborhood Water Refilling Station / Courier *(Accessible)* | **Clarke-Wright Savings Heuristic** for Capacitated Vehicle Routing (CVRPTW) | Extracts delivery addresses, landmarks, and drop quantities from informal Taglish text | Fleet mileage/fuel efficiency, on-time delivery rate, demand forecasting |
| **RANK 3 (A)** | **LifelinePack:** Disaster Evacuation Ration & Triage Optimizer | Barangay DRRM / Relief Center *(High Social Impact)* | **Multi-Dimensional 0-1 Knapsack Problem (MKP)** with family caloric/vulnerability quotas | Parses messy triage notes (infant, elderly, medical alerts) into structured constraint bounds | Stock depletion burn-rate forecasting, Nutritional Equity Index (Gini/Variance) |
| **RANK 3 (B)** | **Mottainai-Mark:** Bakery Perishable Dynamic Markdown System | Neighborhood Bakery / Pasteleria *(Accessible Retail)* | **Bellman Dynamic Programming** for Finite-Horizon Dynamic Markdown Pricing | Extracts recipe shelf-life limits, batch baking logs, and product category perishability | Food waste diversion metric (kg & PHP saved), price elasticity of demand curves |
| **RANK 3 (C)** | **PathPoint:** Indoor Store Discovery & Wayfinding | Local Multi-Level Commercial Center / FCM *(Reachable)* | **$A^*$ (A-Star) Topological Pathfinding** across multi-floor transitions | Natural language spatial intent search ("Find ramen near ATM on 2nd floor") | Foot-traffic density heatmaps, scan frequencies, search-to-visit conversion |
| **RANK 4** | **AlumniTrack:** Graduate Employment & Curriculum Alignment | FEU Diliman Alumni / Placement Office *(Gate 0)* | **Vector Semantic Cosine Similarity** against CHED CMO 25 s. 2015 competencies | Maps free-text job roles into standard PSOC 2012 taxonomy | Kaplan-Meier job placement velocity survival curves, curriculum gap heatmaps |

---

## 📂 Repository Directory Structure

```
Title Def - SysAd/
├── README.md                                  # This master portfolio strategy & alignment guide
├── Title3_Selection_Worksheet.md              # 8-Gate rejection-proofing worksheet & consultation log
├── CrewSync_BSIT_WMA_Research_Mentor_Skill.md # Mentor prompts, research queries (Q1-Q20), anti-hallucination rules
├── ResiboCheck_Project_Context_DEPRECATED.md  # Post-mortem & rejection trace of Title 1 (ResiboCheck)
│
├── CrewSync/                                  # RANK 1 PROJECT PACK (Event Staffing)
│   ├── CrewSync_Project_Context.md            # Single source of truth (entities, state models, rules)
│   ├── CrewSync_Defense_Cheat_Sheet_UPDATED.md# Q&A defense armor (answers for 'seems small', 5 talents, AI)
│   ├── CrewSync_Slide_Deck_Content.md         # Slide blueprint for Title Defense (Slides 4–14)
│   ├── Title_Proposal_Form_Filled.md          # Official paste-ready proposal form fill
│   ├── Client_Owner_Interview_Guide.md        # 12-question fact-finding interview guide for Nail Brat owner
│   └── Client_Endorsement_Letter_Template.md  # Partnership endorsement letter with relative disclosure
│
├── AquaRoute/                                 # RANK 2 PROJECT PACK (Micro-Logistics CVRPTW)
│   └── AquaRoute_Project_Context.md           # Project pack, CVRPTW algorithm, Gemma parser, metrics
│
├── LifelinePack/                              # RANK 3 (OPTION A) PROJECT PACK (Disaster Relief MKP)
│   └── LifelinePack_Project_Context.md        # Project pack, Multi-Dimensional Knapsack, triage parser, burn rates
│
├── MottainaiMark/                             # RANK 3 (OPTION B) PROJECT PACK (Perishable Dynamic Markdown)
│   └── MottainaiMark_Project_Context.md       # Project pack, Bellman DP dynamic pricing, waste diversion metrics
│
├── PathPoint/                                 # RANK 3 (OPTION C) PROJECT PACK (Indoor Wayfinding A*)
│   └── PathPoint_Project_Context.md           # Project pack, A* graph pathfinder, spatial NLP, analytics
│
├── AlumniTrack/                               # RANK 4 PROJECT PACK (HEI Institutional)
│   ├── AlumniTrack_Project_Context.md         # Single source of truth (Gate 0 status, data model, RA 10173)
│   ├── AlumniTrack_Defense_Cheat_Sheet.md     # Q&A defense armor (Gate 0 honesty, Form vs. System)
│   ├── AlumniTrack_Slide_Deck_Content.md      # Slide blueprint for Title Defense (Slides 4–14)
│   ├── Client_Interview_Guide.md              # 19-question interview guide for FEU office head
│   ├── Gate0_Approach_Message.md              # Email & DM copy to request interview with FEU office
│   └── Client_Endorsement_Letter_Template.md  # Endorsement template for university office director
│
└── scratch/                                   # Course lecture extracts, modules, and activity drafts
    ├── Bender-SDLC.txt
    ├── IT0037_Module_1_Systems_Analysis_Fundamentals.txt
    ├── IT0037_Module_3_Information_Requirements_Analysis.txt
    ├── IT0037_Module_4_Structured_and_Object_Oriented_Modeling.txt
    └── aztech2.txt
```

---

## 🛡️ Standard Defense Script (How to Defend the AI, Scope, & "Inventory" Traps)

When the panel asks:

### 1. "Isn't this just another Inventory Management System (IMS) or CRUD?" (For LifelinePack / AquaRoute / Mottainai-Mark)
> *"Sir/Ma'am, a standard inventory system is strictly **descriptive**—it only acts as a passive database ledger recording stock in and stock out. It has zero intelligence to make operational decisions.  
> Our systems are **prescriptive optimization engines**.  
> - For **LifelinePack**, it solves the **Multi-Dimensional 0-1 Knapsack Problem (MKP)** to calculate customized nutritional survival blueprints under severe stockpile scarcity.  
> - For **AquaRoute**, it solves the **Capacitated Vehicle Routing Problem with Time Windows (CVRPTW)** to optimize multi-stop motorcycle routes.  
> - For **Mottainai-Mark**, it solves the **Stochastic Dynamic Pricing Problem via Bellman Dynamic Programming** to optimize hourly markdown price depreciation.  
> The database is merely an input parameter; the core research contribution is the **mathematical optimization algorithm**."*

### 2. "Why do all your titles need AI? What if it hallucinates or costs too much?"
> *"We do not use proprietary cloud APIs like OpenAI or Anthropic. We run Google's lightweight open-weights **Gemma 2B** model locally via Ollama. It incurs **zero recurring API costs**, runs in under 600ms on a local server, and complies with **RA 10173 (Data Privacy Act)** because no client or citizen data leaves the premises. Most importantly, the AI does not make operational decisions—it strictly parses unstructured human text into clean JSON parameters. The operational decisions (matching, routing, pathfinding, knapsack allocation) are executed by our deterministic, mathematically provable algorithms, guaranteeing 100% mathematical correctness."*

### 3. "Why both Web and Mobile?"
> *"The split follows context of use, not headcount. The **Web Application** is engineered for desktop command, configuration, geospatial planning, and high-density analytics dashboards. The **Mobile Application** is engineered strictly for frontline mobile actors (freelance artists, motorcycle delivery riders, triage gym volunteers, shoppers, alumni) who are away from a desk and require push alerts, GPS integration, offline caching, and single-tap task completion."*

---

## ⏱️ Immediate Next Steps for Group 6
1. **Mesina (CrewSync):** Conduct the 15-minute owner interview and have the endorsement letter signed.
2. **Canido (AlumniTrack):** Send the `Gate0_Approach_Message.md` to the FEU Diliman Alumni/Careers office this week.
3. **Team:** Review the 3 core defense choices (CrewSync + AquaRoute + LifelinePack/Mottainai-Mark/PathPoint).
4. **Consultation #3:** Present the portfolio matrix on Slide 1 and walk through the portfolio with complete confidence!
