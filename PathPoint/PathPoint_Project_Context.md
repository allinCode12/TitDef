# PathPoint — Project Context Pack
*AzTech (Group 6) · IT0037 Systems Analysis and Design · Specialization: BSIT WMA*

---

## 1. Project Identity

| Field | Value |
|---|---|
| **Proposed Working Title** | PathPoint: An AI-Assisted Web and Mobile Indoor Navigation and Store Discovery System with $A^*$ Shortest-Path Algorithm, Local LLM Spatial Query Parsing, and Foot-Traffic Analytics for a Multi-Level Commercial Center |
| **Short Name** | PathPoint (Reframed from MallWay) |
| **Specialization** | BSIT — Web and Mobile Application |
| **Course / Program** | FEU Diliman · IT0037 Systems Analysis and Design |
| **Target Setting** | An Independent Multi-Level Commercial Complex, Strip Mall, or Community Trade Center (e.g., Fairview Center Mall - FCM, or a local commercial plaza — *NOT corporate SM Prime*) |
| **Users** | Commercial Center Administration / Marketing (Web Console), Shoppers / Visitors (Mobile Web / PWA) |
| **Not a User** | Individual store cashiers (tenants manage listings via self-service or admin import) |

---

## 2. Problem Framing

### A. Symptom vs. Root Cause
* **Symptoms:** Shoppers get disoriented inside complex multi-level commercial complexes; long walks to find specific specialty clinics, ATMs, or restrooms; upper-floor stores experience lower foot-traffic discovery.
* **Root Cause:** **Complete failure of GPS satellite signals inside reinforced concrete and steel commercial buildings.** Shoppers rely on static physical directory boards that lack search, route visualization, or multi-floor path guidance.

### B. Problem Statement
In multi-level commercial centers and bazaars, satellite GPS cannot penetrate building structures, making outdoor navigation apps useless. Visitors struggle to locate stores across floors, while building administration lacks data on foot-traffic circulation. PathPoint solves indoor disorientation using stationary QR proximity anchors, $A^*$ pathfinding, and local LLM conversational directory search without requiring app installation.

---

## 3. The Technical Trinity

### A. Dedicated Optimization Algorithm: $A^*$ (A-Star) Topological Pathfinding
* **Mathematical Graph Representation:**
  Models the commercial complex as an indoor coordinate graph $G = (V, E)$, where $V$ represents corridor intersections, shop entrances, stairs, elevators, and escalators, and $E$ represents walkable pathway segments with physical distance weights.
* **Algorithm Execution:**
  $$f(n) = g(n) + h(n)$$
  - $g(n)$: Exact walking distance from starting QR anchor to current node $n$.
  - $h(n)$: Euclidean / Manhattan distance heuristic from node $n$ to target shop entrance.
* **Multi-Floor & Accessibility Constraints:**
  - Evaluates vertical edge weights (stairs vs. escalators vs. elevators).
  - Enforces accessible routing toggles (e.g., avoiding stairs for users with strollers or wheelchairs).

### B. Functional Local AI Subsystem: Google Gemma 2B via Ollama
* **Role:** Conversational Spatial Intent & Multi-Criteria Constraint Parsing.
* **Why Local:** Self-hosted on the web server; zero token billing; zero visitor data leaks.
* **Sample Interaction:**
  - *User Query:* `"Saan may kainan ng ramen malapit sa CR na may BDO ATM sa 2nd floor?"`
  - *Extracted Spatial Metadata:*
    ```json
    {
      "category": "restaurant",
      "cuisine": "japanese_ramen",
      "near_facility": "restroom",
      "near_service": "ATM_BDO",
      "floor_constraint": 2,
      "target_node_ids": ["N_204", "N_218"]
    }
    ```
  - The parsed node ID is fed directly to the $A^*$ pathfinder to render the turn-by-turn route.

### C. Descriptive Analytics Engine
* **Foot-Traffic Density Heatmaps:** Aggregated scan timestamps by QR anchor zone.
* **Search-to-Visit Latency & Conversion:** Identifies which categories are most frequently searched but have poor upper-floor store discovery.
* **Corridor Congestion & Dead-Zone Analytics:** Helps building managers optimize tenant leasing and promotional signage.

---

## 4. WMA Dual-Interface Operational Split

* **Web Management Portal (Commercial Center Admin / Operations):**
  - Interactive floorplan graph editor (node/edge coordinate calibration).
  - Tenant directory management, promotional event overlays.
  - Foot-traffic spatial analytics dashboard.
* **Mobile Web / PWA (Shoppers & Visitors):**
  - **Zero Install Friction:** Triggered immediately when scanning any stationary QR code anchor inside the building.
  - Interactive SVG canvas rendering turn-by-turn walking paths with floor-switch indicators.
  - Conversational natural-language search bar powered by local Gemma.

---

## 5. Scope Boundaries

* **In Scope:** Static QR proximity anchoring, $A^*$ topological multi-floor routing, Gemma spatial search, tenant directory, admin analytics.
* **Out of Scope:** Bluetooth beacon hardware deployment, live indoor GPS trilateration, AR camera navigation, in-app tenant e-commerce purchasing.
