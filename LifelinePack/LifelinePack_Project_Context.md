# LifelinePack — Project Context Pack
*AzTech (Group 6) · IT0037 Systems Analysis and Design · Specialization: BSIT WMA*

---

## 1. Project Identity

| Field | Value |
|---|---|
| **Proposed Working Title** | LifelinePack: An Automated Multi-Dimensional Knapsack Rationing and Triage Optimization System with Local LLM Intake Parsing and Burn-Rate Analytics for Community Evacuation Centers |
| **Short Name** | LifelinePack (Inspired by Apollo 13 & Japanese *Bosai* Disaster Informatics) |
| **Specialization** | BSIT — Web and Mobile Application |
| **Course / Program** | FEU Diliman · IT0037 Systems Analysis and Design |
| **Target Setting** | Local Barangay Disaster Risk Reduction and Management Council (BDRRMC) or Evacuation Relief Center (e.g., Barangay Relief Gym, Local Red Cross Chapter, or Parish Caritas Center) |
| **Users** | Evacuation Relief Center Supervisor / DRRM Head (Web Admin Console), Gym Floor Intake & Packing Volunteers (Mobile Field App) |
| **Not a User** | Displaced evacuee citizens (they receive physical printed/color-coded ration vouchers or wristband QR codes upon intake) |

---

## 2. Problem Framing

### A. Symptom vs. Root Cause
* **Symptoms:** Evacuation centers experience rapid, premature stockouts of critical supplies (infant formula, potable water, maintenance medicines); families receive inappropriate rations (e.g., diabetic elders given high-sodium canned goods, infants receiving adult instant noodles); perishable donations spoil unopened at the rear of gymnasiums; post-relief supply inequity disputes.
* **Root Cause:** **The "One-Size-Fits-All" manual relief packing bottleneck.** Relief workers assemble uniform, generic grocery bags under severe physical fatigue and cognitive overload, without algorithmic consideration of family headcount, vulnerability profiles, or remaining stockpile exhaustion horizons.

### B. Problem Statement
During disaster relief operations, evacuation centers receive heterogeneous, finite donations while registering families with widely asymmetric nutritional and medical requirements. Because volunteer teams pack bags manually using arbitrary guesswork, scarce items are exhausted within hours while surplus goods spoil. LifelinePack provides a prescriptive mobile and web rationing engine that solves the multi-dimensional knapsack problem to compute customized, equitable survival rations per family while tracking stockpile burn rates in real time.

---

## 3. The Technical Trinity

### A. Dedicated Optimization Algorithm: Multi-Dimensional 0-1 Knapsack Problem (MKP)
* **Mathematical Formulation:**
  Let $x_i \in \{0, 1\}$ denote whether candidate ration item $i$ (from $N$ available supply items) is included in the family's survival pack:
  $$\max \sum_{i=1}^{N} v_i \cdot x_i$$
  Subject to $K$ multi-dimensional resource and demographic constraints:
  $$\sum_{i=1}^{N} w_{i, k} \cdot x_i \le C_k, \quad \forall k \in \{1, \dots, K\}$$
* **The Constraints ($K$ Dimensions):**
  1. *Caloric Minimum:* $\sum \text{Calories}_i \ge \text{Daily Caloric Baseline} \times \text{Family Headcount}$.
  2. *Vulnerability Quotas:* Specialized item allocation gated by verified demographic flags (e.g., infant formula allocated if and only if $\text{Infants} \ge 1$; low-sodium foods prioritized if $\text{Hypertension/Elderly} \ge 1$).
  3. *Physical Carrying Capacity:* Pack total weight and volume must not exceed carrying limits for walking evacuees ($C_{\text{weight}} \le 12\text{ kg}$).
  4. *Dynamic Stock Scarcity Weighting ($v_i$):* Item utility weights scale inversely with remaining warehouse inventory, preventing premature exhaustion of scarce supplies before replenishment convoys arrive.

### B. Functional Local AI Subsystem: Google Gemma 2B via Ollama
* **Role:** Unstructured Evacuee Triage Intake Extraction & Priority Tagging.
* **Why Local:** Runs 100% offline on a local laptop in the evacuation center via Ollama. Requires **zero cloud API fees**, operates even when municipal internet/cellular towers collapse, and strictly preserves citizen privacy under the Philippine Data Privacy Act (RA 10173).
* **Sample Extraction:**
  - *Input (Volunteer Raw Intake Note):*  
    `"Fam of 5, lola may maintenance sa altapresyon, may 7 month old na baby wala ng gatas at diapers, bawal sa seafood yung tatay."`
  - *Extracted JSON Schema:*
    ```json
    {
      "family_headcount": 5,
      "infants": 1,
      "infant_age_months": 7,
      "elderly_count": 1,
      "medical_conditions": ["hypertension"],
      "dietary_allergies": ["shellfish_seafood"],
      "urgency_level": "CRITICAL_INFANT_CARE"
    }
    ```
  - The parsed JSON parameters directly populate the constraint bounds ($C_k$) in the MKP algorithm to produce the instant packing blueprint.

### C. Descriptive & Predictive Analytics Engine
* **Stock Depletion Burn-Rate Curves:** Real-time linear regression forecasting the exact hour each critical commodity (potable water, diapers, rice) will hit 0% based on registered evacuee consumption velocity.
* **Nutritional Equity Index (Gini Coefficient / Variance):** Evaluates caloric distribution equity across all registered families to mathematically prove that no family was under-rationed relative to needs.
* **Spoilage Risk Metric:** Tracks FEFO (First-Expired, First-Out) compliance across donated perishable crates.

---

## 4. WMA Dual-Interface Operational Split

* **Web Management Portal (DRRM Officer / Relief Camp Commander):**
  - Live stockpile inventory matrix and donation intake ledger.
  - Global rationing policy controls (adjust caloric thresholds, set emergency scarcity dampers).
  - High-density burn-rate monitoring and supply convoy requisition reports.
* **Mobile Field App (Gym Triage Volunteers & Packing Staff):**
  - **Context of Use:** Volunteers working on the noisy, crowded gym floor away from desks.
  - Rapid family intake barcode/wristband scanning.
  - **Dynamic Packing Blueprint:** Step-by-step assembly checklist showing exactly which items to pack into the specific family's bag with barcode confirmation.
  - Offline-first local SQLite sync when gymnasium network connectivity is intermittent.

---

## 5. Defense Armor: Shutting Down Panel Traps

### A. The "Isn't this just another Inventory Management System (IMS)?" Trap
* **Panel Objection:** *"This sounds like basic inventory management. You just add donations and subtract rations."*
* **The Defense:**
  > *"Sir/Ma'am, a standard inventory system is strictly **descriptive**—it only acts as a passive database ledger recording stock in and stock out. It has zero intelligence to decide who gets what.  
  > LifelinePack is a **prescriptive rationing optimization engine**. It solves the **Multi-Dimensional 0-1 Knapsack Problem (MKP)**. In a crisis, a human volunteer packing boxes cannot compute how to balance caloric targets, infant nutritional needs, diabetic restrictions, and carrying weight limits across 200 asymmetric families while warehouse stock is depleting. The database is merely an input; the core research contribution is the **combinatorial algorithm that generates the optimal survival pack per family**."*

### B. The Competitor Batch Collision Check (Zero Overlap with BALAMAP)
* **Competitor:** Group 2 (Tiger Commando) has `BALAMAP: A Mobile-Based Crime and Hazard Mapping System for Barangay Matandang Balara`.
* **The Distinction:**
  * `BALAMAP` is an **outdoor GIS map** (plotting flood zones and crime pins on Google Maps).
  * `LifelinePack` is an **indoor Operations Research allocation engine** (inside the evacuation center). It contains zero mapping, zero crime reporting, and zero hazard tracking.

---

## 6. Scope Boundaries

* **In Scope:** Family triage intake, local Gemma entity parser, Multi-Dimensional Knapsack pack generator, mobile packing checklist, stockpile burn-rate analytics, offline SQLite sync.
* **Out of Scope:** Online public donation payment processing, drone delivery dispatch, municipal outdoor GIS flood hazard mapping.
