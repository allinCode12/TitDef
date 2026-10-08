# Mottainai-Mark — Project Context Pack
*AzTech (Group 6) · IT0037 Systems Analysis and Design · Specialization: BSIT WMA*

---

## 1. Project Identity

| Field | Value |
|---|---|
| **Proposed Working Title** | Mottainai-Mark: An AI-Assisted Web and Mobile Dynamic Markdown and Perishable Food Waste Reduction System with Bellman Dynamic Programming, Local LLM Shelf-Life Extraction, and Price Elasticity Analytics for a Neighborhood Bakery |
| **Short Name** | Mottainai-Mark (Inspired by the Japanese *Mottainai* Philosophy of Zero Waste) |
| **Specialization** | BSIT — Web and Mobile Application |
| **Course / Program** | FEU Diliman · IT0037 Systems Analysis and Design |
| **Target Setting** | Independent Neighborhood Bakery, Cake Shop, or Pasteleria (e.g., local artisanal bakeries, panaderias, or pastry cafes) |
| **Users** | Bakery Owner / Head Baker (Web Management Console), Store Floor Staff & Cashiers (Mobile Staff App), Neighborhood Shoppers (Mobile Web / PWA Clearance Radar) |
| **Not a User** | Central flour/ingredient agricultural suppliers |

---

## 2. Problem Framing

### A. Symptom vs. Root Cause
* **Symptoms:** Trays of unsold artisanal bread, filled buns, and pastries discarded into waste bins at closing time (8:00 PM – 9:00 PM); arbitrary, blunt clearance discounts (e.g., blanket "50% off everything at 8:30 PM") that cannibalize profit on popular items while still failing to clear slow-moving pastries; severe financial loss for micro-bakery owners.
* **Root Cause:** **Static, non-adaptive retail pricing.** Perishable baked goods lose 100% of their economic value within 12–24 hours, yet store managers lack an algorithmic dynamic pricing mechanism that continuously adjusts markdowns based on hourly foot-traffic velocity, remaining batch inventory, and expiring shelf-life.

### B. Problem Statement
Neighborhood bakeries operate with razor-thin margins on baked goods with strict 24-hour shelf-life horizons. Because owners rely on static shelf prices or crude, last-minute flat markdowns, hundreds of kilograms of edible food are wasted daily while potential evening revenue is lost. Mottainai-Mark provides an automated dynamic markdown pricing engine that utilizes Bellman Dynamic Programming to optimize hourly price depreciation, alerting nearby shoppers through a mobile clearance radar while tracking waste diversion metrics.

---

## 3. The Technical Trinity

### A. Dedicated Optimization Algorithm: Bellman Dynamic Programming for Dynamic Pricing
* **Mathematical Formulation:**
  Solves a finite-horizon **Stochastic Dynamic Pricing Problem (Markov Decision Process)**:
  Let $t \in \{1, 2, \dots, T\}$ represent the discrete operating hours until store closing ($T$).  
  Let $I_t$ denote the remaining perishable inventory of batch $b$ at hour $t$.  
  The optimal value function $V_t(I_t)$ satisfies the **Bellman Optimality Equation**:
  $$V_t(I_t) = \max_{p_t \in \mathcal{P}} \left\{ \mathbb{E}\left[ \min(D(p_t, t), I_t) \cdot p_t \right] + \mathbb{E}\left[ V_{t+1}(I_t - \min(D(p_t, t), I_t)) \right] \right\}$$
  With terminal boundary condition:
  $$V_{T+1}(I) = - c_{\text{waste}} \cdot I$$
  Where:
  - $\mathcal{P}$: Feasible discrete markdown price set (e.g., $0\%, 15\%, 30\%, 50\%$ discount).
  - $D(p_t, t)$: Price- and time-dependent stochastic customer demand function.
  - $c_{\text{waste}}$: Disposal penalty and ingredient cost loss per unsold unit.
* **Algorithmic Outcome:**
  Instead of guessing, the algorithm outputs the mathematically optimal discount rate for each product batch at each hour of the afternoon/evening to maximize revenue recovery while driving end-of-day unsold stock to zero.

### B. Functional Local AI Subsystem: Google Gemma 2B via Ollama
* **Role:** Unstructured Batch Log & Shelf-Life Parsing.
* **Why Local:** Runs on-premise on the store's POS/laptop via Ollama. Incurs **zero cloud API fees** and operates fully offline during local broadband outages.
* **Sample Extraction:**
  - *Input (Baker Daily Batch Scratchpad Note):*  
    `"Batch 3 cheese roll nilabas kaninang 11:30 am 40 pcs, delicate cheese topping bawal lampas 10 hours sa room temp, push discount bago mag 7pm."`
  - *Extracted JSON Schema:*
    ```json
    {
      "product_name": "Cheese Roll",
      "batch_id": "CR-B03",
      "quantity_baked": 40,
      "time_baked": "11:30",
      "shelf_life_hours": 10,
      "expiry_cutoff": "21:30",
      "markdown_target_start": "19:00",
      "perishability_class": "HIGH_DAIRY"
    }
    ```
  - Directly seeds the inventory state $I_0$ and time horizon $T$ in the Bellman DP engine.

### C. Descriptive & Predictive Analytics Engine
* **Food Waste Diversion Metric:** Total kilograms of baked goods and total PHP saved from landfill disposal.
* **Price Elasticity of Demand (PED):** Computes empirical price elasticity curves across bakery product lines:
  $$\epsilon = \frac{\% \Delta Q}{\% \Delta P}$$
* **Revenue Recovery Lift Rate:** Side-by-side comparative dashboard comparing actual dynamic markdown yield against traditional flat-clearance baseline.

---

## 4. WMA Dual-Interface Operational Split

* **Web Management Portal (Bakery Owner / Head Baker):**
  - Recipe cost cards, shelf-life rule matrices, and baseline retail pricing.
  - Dynamic pricing policy engine (configure discount bounds, floor prices, and decay speeds).
  - Executive waste-reduction and price-elasticity analytics dashboards.
* **Mobile Field App (Two Views):**
  1. **Staff Operations App (Floor Clerks / Cashiers):**
     - Scan batch QR/barcode to view current system-calculated markdown price.
     - One-tap label printer sync or digital shelf tag update.
  2. **Customer Clearance Radar (Shoppers PWA / Mobile Web):**
     - Zero-friction web app for neighborhood residents.
     - Real-time map/list showing live active markdowns at the bakery during evening hours, driving walk-in traffic before store closing.

---

## 5. Defense Armor: Shutting Down Panel Traps

### A. The "Isn't this just a Point-of-Sale (POS) or Inventory System?" Trap
* **Panel Objection:** *"This is just an inventory system with discounts."*
* **The Defense:**
  > *"Sir/Ma'am, a standard POS or inventory system is strictly **historical and transactional**—it records transactions that humans already decided, and deducts items from a table.  
  > Mottainai-Mark is an **Operations Research pricing engine**. It solves the **Stochastic Dynamic Pricing Problem via Bellman Dynamic Programming**. In perishable retail, calculating the exact time and discount percentage to optimize the trade-off between price realization and waste probability under stochastic evening demand is an established Operations Research problem that cannot be calculated by manual staff intuition. The POS is merely a display terminal; the core contribution is the **intertemporal dynamic programming algorithm**."*

---

## 6. Scope Boundaries

* **In Scope:** Batch production intake, local Gemma batch parser, Bellman DP dynamic markdown calculator, mobile staff price verification, customer clearance radar PWA, food waste analytics.
* **Out of Scope:** Online banking credit card processing gateways, long-haul cold chain logistics, automated bakery hardware ovens.
