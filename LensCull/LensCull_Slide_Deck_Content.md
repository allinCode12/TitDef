# LensCull — Mock Title Defense Slide Deck Blueprint
*(13-slide drop-in blueprint for the LensCull portion of the AzTech Mock Title Defense)*

---

### Slide 1: Title Slide
* **Title:** LensCull: An Edge AI-Assisted Visual Culling, Micro-Expression Quality Filtering, and Submodular Album Selection System for Professional Event Photographers
* **Subtitle:** Capstone Title Proposal — Title 4
* **Client Partner:** `[TO VALIDATE — no photographer/studio secured yet]`
* **Specialization:** BSIT — Web and Mobile Application
* **Presenter / Proponent:** [Your Name] (Team AzTech)

---

### Slide 2: Title and Four-Element Breakdown (Module 1)
* **Title Breakdown Table:**
  * **System / Capability:** Visual Culling, Micro-Expression Quality Filtering, and Submodular Album Selection
  * **Users / Setting:** Professional Event Photographers (commercial photography studios)
  * **Value / Problem Direction:** Faster cull, fewer duplicate or missed shots, a balanced album under a strict size limit
  * **Specialization Differentiator:** Edge AI (on-premise CV + local semantic search) with a desktop web production workstation and an Android mobile companion
* **One-Line Value Pitch:**
  * Turns a shoot's overload of near-identical RAW files into a short, balanced, story-aware album — screen defects, search the shoot in plain language, then let a submodular selector pick the K best photos.

---

### Slide 3: Background and Evidence Status (Module 1)
* **Industry & Setting Context:**
  * Commercial event shoots (weddings, debuts, graduations) produce thousands of high-resolution RAWs per shoot.
  * Culling is the first and heaviest post-production step and is done manually, image by image.
* **Evidence Status Matrix:**
  * **Editor cull time (8–12 h per shoot):** `[TO VALIDATE — hypothesis, no client measured]`.
  * **Fatigue causing duplicates / missed milestones:** `[TO VALIDATE — hypothesis]`.
  * **Cloud tools impractical over local bandwidth:** `[TO VALIDATE — verify with a real studio connection]`.
  * **Existing tools only do binary Keep/Reject:** `[TO VALIDATE — verify against named tools]`.
  * **Working implementation:** ✅ Python command-line proof of concept (small scale, ~28 images) — semantic search and curation work but are not yet perfect.
  * **Named client:** ❌ none yet — `[TO VALIDATE]`.

---

### Slide 4: Problem: Symptoms vs. Root Cause + Stakeholders (Module 1)
* **Symptoms `[TO VALIDATE]`:**
  * Editors spend long hours going through thousands of images.
  * Near-identical burst frames get selected by mistake.
  * Chronological milestones get missed.
  * Editors report fatigue; client turnaround is slow.
* **Root Cause Hypothesis:**
  * Culling and album assembly are manual and image-by-image, with no automated defect screening, no way to search a whole shoot by meaning, and no global method to choose the best balanced set under an album size limit.
* **Stakeholders (Module 3):**
  * **Lead Editor / Post-Production Staff:** Process Owner & Admin (Desktop web; High power, High interest).
  * **Field Photographer:** Direct Mobile User (Milestone coverage auditing on-site).
  * **Studio Client / Celebrant:** Direct Mobile User (Swipe-to-approve proofing).
  * **Adviser & Panel:** Project Governance and Evaluation.

---

### Slide 5: General and Specific Objectives (Module 2)
* **General Objective:**
  * To design and develop LensCull, an edge AI-assisted visual culling, micro-expression quality filtering, and submodular album selection system that helps professional event photographers cull a shoot faster and assemble a balanced album under a strict size limit.
* **Specific Objectives:**
  1. Develop a **desktop web production workstation** for high-throughput local ingestion, embedded preview streaming, and XMP/Lightroom export without cloud reliance.
  2. Develop an **Android mobile companion** for on-venue milestone tracking (field photographers) and swipe-to-approve proofing (studio clients).
  3. Implement a **two-tier edge CV pipeline** — OpenCV Laplacian focus variance (blur) + MediaPipe Face Mesh EAR (blinks).
  4. Implement an **on-device multimodal semantic embedding** model (quantized OpenCLIP / MobileCLIP via ONNX Runtime) for zero-shot natural-language search.
  5. Implement an **Accelerated Lazy Greedy Submodular Facility Location** algorithm to select K photos balancing milestone coverage and quality while penalizing duplicate bursts.
  6. Provide a **studio analytics dashboard** (cull compression ratios, per-photographer defect distributions, milestone coverage).
  7. **Evaluate** defect accuracy (Precision/Recall/F1) and subset concordance vs. human albums with the Jaccard Similarity Index.

---

### Slide 6: Proposed Solution and Flow Diagram (Module 2)
* **Step-by-Step Flow:**
  * **Step 1: Ingestion (on-premise):** Read a shoot folder; extract lightweight 1080p preview frames from EXIF metadata — no full RAW decode.
  * **Step 2: Tier 1 Defect Screening:** OpenCV Laplacian variance flags blur; MediaPipe Face Mesh EAR isolates blinks.
  * **Step 3: Tier 2 Local Semantic Search:** INT8-quantized OpenCLIP / MobileCLIP (ONNX Runtime) embeds each frame for zero-shot natural-language search and scene clustering — locally in milliseconds.
  * **Step 4: Tier 3 Submodular Selection:** Solve the Submodular Facility Location Problem under |S| ≤ K with Accelerated Lazy Greedy — maximize coverage and sharpness, penalize burst duplicates.
  * **Step 5: Proofing & Export:** Client swipe-to-approve in the Android app; editor confirms; export XMP/manifest. No destructive edits.

---

### Slide 7: Tier 1 — Edge Computer Vision Defect Screening
* **Blur detection:** OpenCV **Laplacian variance** — low variance indicates a soft/out-of-focus frame; threshold `[TO VALIDATE]`.
* **Blink detection:** MediaPipe **Face Mesh Eye Aspect Ratio (EAR)** — a closed eye produces a low EAR; used to isolate blinks (Soukupova & Cech, 2016).
* **Output:** per-image defect flags and scores that feed the candidate set for album selection.
* **Why on the edge:** runs on the editor's workstation, no cloud round-trip, so it scales to thousands of frames.

---

### Slide 8: Tier 2 — Local Zero-Shot Semantic Search
* **Model:** INT8-quantized **OpenCLIP or MobileCLIP**, executed via **ONNX Runtime** (Radford et al., 2021).
* **Capability:** zero-shot natural-language search over the whole shoot (e.g., "cake cutting", "bride crying") and semantic scene clustering — no manual tags.
* **Latency:** local inference in milliseconds per query `[measure target]`; 100% on-premise, so client faces never leave the workstation.
* **Why quantized:** keep the model small and fast enough for consumer workstation hardware.

---

### Slide 9: Tier 3 — Submodular Album Selection (The Algorithm)
* **Formulation:** album compilation as a **Submodular Facility Location Problem under a Cardinality Constraint (|S| ≤ K)**.
* **Objective:** maximize **scene coverage + sharpness** while **penalizing burst duplicate redundancy** — a monotone submodular objective f(S).
* **Solver:** **Accelerated Lazy Greedy** — exploits submodularity to skip provably suboptimal evaluations, giving a **(1 − 1/e) approximation** of the optimum without exhaustive search (Nemhauser, Wolsey, & Fisher, 1978; Bilmes, 2022).
* **Why not rank by score:** per-image ranking can pick five near-identical frames; submodular coverage forces diversity across the story under the size limit.
* **Note:** this is the strongest algorithm in the AzTech portfolio.

---

### Slide 10: Scope and Limitations (Module 1)
* **In Scope (✓):**
  * Desktop web workstation — ingestion, preview extraction, two-tier AI filtering, NL search console, submodular album generator, timeline canvas, proofing manifest.
  * Android mobile app — on-site milestone coverage checklist + swipeable proofing / photo-swapping gallery.
  * Pipeline — edge CV screening, local CLIP embeddings, submodular selection under |S| ≤ K, studio analytics.
* **Out of Scope (✗):**
  * Destructive pixel edits, RAW color grading, exposure retouching.
  * Cloud upload / cloud processing (100% on-premise).
  * iOS native app; camera tethering; booking or payments.
* **Delimitation Note:**
  * Single-client evaluation `[TO VALIDATE]`; the "under 30 minutes" claim is a target, not a measured result.

---

### Slide 11: Key Requirements (Module 3)
* **Functional Requirements (MoSCoW):**
  * **Must:** Shoot-folder ingestion; preview extraction; Tier 1 blur/blink screening; NL semantic search; submodular album generation under |S| ≤ K; editor manual override; milestone coverage checklist.
  * **Should:** Timeline layout canvas; proofing manifest; XMP/Lightroom export; swipe-to-approve proofing; photo swap; analytics dashboard.
  * **Could:** iOS responsive proofing view; offline-tolerant field sync.
* **Non-Functional & Quality Standards (ISO/IEC 25010):**
  * **Performance Efficiency:** Local semantic search in milliseconds per query `[target to measure]`; no cloud round-trip.
  * **Reliability:** Selection always respects |S| ≤ K; candidate set follows the defect rules.
  * **Usability:** Client can approve a photo in minimal swipes `[target to validate in testing]`.
  * **Security & Privacy:** On-premise processing of face data, RA 10173 handling, written consent, no cloud upload by default.

---

### Slide 12: Feasibility Snapshot and Lifecycle Choice (Module 2)
* **Six-Dimensional Feasibility Snapshot:**
  * **Technical:** Feasible at small scale — the Python CLI proof of concept already demonstrates the algorithm and AI (~28 images). Full-scale integration (ONNX + quantized CLIP + MediaPipe) on the editor's hardware needs testing `[test]`.
  * **Operational:** Conditional — no client yet `[TO VALIDATE]`; editor and client adoption unconfirmed.
  * **Economic:** Conditional — free/open tooling, but needs a workstation with enough GPU/CPU; hosting only for the web shell `[estimate in PHP]`.
  * **Schedule:** Conditional (highest risk) — very large scope for one term; staged delivery planned.
  * **Security:** Conditional — on-premise processing reduces exposure; access control + consent for face data.
  * **Legal & Ethical:** Conditional — RA 10173 for identifiable faces; written consent; model licenses (CLIP / MediaPipe / ONNX) to be checked.
* **Lifecycle Choice:**
  * **Tailored Hybrid Approach:** validate the Python pipeline first (benchmark), then Prototyping (workstation + mobile UI) + Agile Sprints (core build) inside Predictive Stage-Gates (proposal approval → benchmark validation → design approval → pilot approval).

---

### Slide 13: Evaluation, Proof-of-Concept Status, and Next Steps (Module 3 & 4)
* **Evaluation Plan:**
  * **Defect detection:** Precision, Recall, F1 vs. human labels.
  * **Subset concordance:** Jaccard Similarity Index (J) vs. the photographer's own curated album.
  * **Before/after cull time:** controlled 120-shot benchmark.
  * **Software quality:** ISO/IEC 25010 Likert survey with the photographer.
* **Proof-of-Concept Status (honest):**
  * Working **Python CLI proof of concept** at small scale (~28 images); semantic search and curation work but are not yet perfect. Accuracy will be **measured**, not claimed.
* **Convergence Goal / Next Steps:**
  * **Gate 0:** secure a named photographer/studio + written photo-use consent.
  * Capture the baseline (manual cull time + the photographer's own album) for the same 120 shots.
  * Run the PoC on the same set; run 2–3 shoots under different lighting/burst conditions.
  * Replace every `[TO VALIDATE]` with measured data before the final defense.
