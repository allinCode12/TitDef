# AquaRoute — Project Context Pack
*AzTech (Group 6) · IT0037 Systems Analysis and Design · Specialization: BSIT WMA*

---

## 1. Project Identity

| Field | Value |
|---|---|
| **Proposed Working Title** | AquaRoute: An AI-Assisted Web and Mobile Delivery Dispatch and Route Optimization System with Capacitated Vehicle Routing Algorithm, Local LLM Note Extraction, and Fleet Fuel Analytics for a Neighborhood Water Refilling Cooperative |
| **Short Name** | AquaRoute (or FleetRoute) |
| **Specialization** | BSIT — Web and Mobile Application |
| **Course / Program** | FEU Diliman · IT0037 Systems Analysis and Design |
| **Target Client** | Neighborhood Water Refilling Station (WRS) Network or Local LPG/Cargo Delivery Cooperative |
| **Users** | Station Owner / Dispatcher (Web Admin Console), Tricycle / Motorcycle Delivery Riders (Mobile Field App) |
| **Not a User** | End customers (they continue ordering through existing messaging, phone calls, or walk-ins) |

---

## 2. Problem Framing

### A. Symptom vs. Root Cause
* **Symptoms:** Delivery riders take disorganized, overlapping trips across neighborhoods; missed customer delivery time slots; high fuel consumption and motorcycle wear-and-tear; frequent disputes over lost or uncollected empty 5-gallon containers.
* **Root Cause:** **Absence of a structured, capacity-constrained vehicle routing and dispatch engine.** Dispatchers rely on manual memory and handwritten slips, leaving route choice entirely to driver intuition.

### B. Problem Statement
Neighborhood water refilling stations process dozens of daily delivery orders through informal messaging and paper slips. Because delivery drops are not clustered or sequenced based on vehicle capacity (e.g., sidecar limits of 20–25 containers) and customer delivery windows, riders incur excessive fuel waste, delayed deliveries, and inventory loss. AquaRoute provides a dedicated dispatch and mobile navigation platform that optimizes multi-stop delivery sequences and tracks container balances in real time.

---

## 3. The Technical Trinity

### A. Dedicated Optimization Algorithm: CVRPTW via Clarke-Wright Savings Heuristic
* **Mathematical Formulation:**
  Solves the **Capacitated Vehicle Routing Problem with Time Windows (CVRPTW)**:
  $$\text{Savings } s(i, j) = c(\text{depot}, i) + c(\text{depot}, j) - c(i, j)$$
  Where $c(i, j)$ is the network travel cost/distance between customer drop nodes $i$ and $j$.
* **Constraints Enforced:**
  1. *Capacity Constraint:* Total gallon weight on a single run $\le \text{Vehicle Capacity Limit}$ (e.g., 25 slim jugs).
  2. *Time Window Constraint:* Arrival time must fall within the customer's specified delivery window ($[e_i, l_i]$).
  3. *Depot Return:* Each route starts and terminates at the refilling station depot.

### B. Functional Local AI Subsystem: Google Gemma 2B via Ollama
* **Role:** Unstructured Taglish Customer Order Extraction.
* **Why Local:** Runs completely on-premise on the station's computer via Ollama. Incurs **zero cloud API fees** and guarantees 100% compliance with the Philippine Data Privacy Act (RA 10173).
* **Sample Extraction:**
  - *Input:* `"Padeliver po 3 slim container sa 142 Tandang Sora tapat ng bakery mamayang 2pm, gcash bayad."`
  - *Extracted JSON Schema:*
    ```json
    {
      "delivery_address": "142 Tandang Sora",
      "landmark": "tapat ng bakery",
      "quantity_slim": 3,
      "quantity_round": 0,
      "time_window": "14:00-15:00",
      "payment_mode": "GCASH",
      "is_urgent": false
    }
    ```

### C. Descriptive & Predictive Analytics Engine
* **Descriptive Metrics:** Mean delivery turnaround time, fuel cost per drop-off, driver idle time, empty container return rate.
* **Predictive ML (Scikit-Learn Random Forest Regressor):** Daily container demand forecasting correlating day-of-week, weather temperature, and historical household consumption frequency.

---

## 4. WMA Dual-Interface Operational Split

* **Web Management Portal (Dispatcher / Station Owner):**
  - Map-centric dispatch console (Leaflet/Mapbox + PostGIS).
  - Bulk order intake, route visualization, driver assignment, container inventory ledger.
* **Mobile Field App (Motorcycle / Tricycle Delivery Riders):**
  - Handlebar-mounted, distraction-free interface.
  - Sequenced stop-by-stop navigation with one-tap handoff to Google Maps/Waze.
  - Offline-first caching (SQLite) for dead cellular signal spots.
  - Proof-of-Delivery: Customer QR code scan, digital signature, and empty container balance update.

---

## 5. Scope Boundaries

* **In Scope:** Order batching, CVRPTW route optimization, local Gemma order parser, mobile driver sequence, container ledger, dispatch analytics.
* **Out of Scope:** Online payment processing gateway, customer e-commerce store, vehicle hardware telematics/OBD tracking.
