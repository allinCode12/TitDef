# Capstone Project Title Proposal — Title 4 (LensCull) — Paste-Ready Fill

**Form:** FEU Institute of Technology · College of Computer Studies · Capstone Project Title Proposal (System Analysis and Design)
**Program:** Bachelor of Science in Information Technology, specialization in Web and Mobile Application
**Group:** AzTech (Group 6) · **Members:** Canido, Felix Jed; Mesina, Patrick Kyle; Borromeo, Zire Niccolai; Oronico, Lee Justin
**Term:** [x] 1st · Academic Year: 2026–2027
**Proposed Project Title 4:** LensCull: An Edge AI-Assisted Visual Culling, Micro-Expression Quality Filtering, and Submodular Album Selection System for Professional Event Photographers

> **Source of truth:** this file mirrors the team's Title 4 proposal draft (`aztech_pdf2`, pages 11–14). Every client-dependent or unverified item is marked `[TO VALIDATE]` — there is no named client yet, and the only real asset is a working Python command-line proof of concept tested at small scale (~28 images). Paste each field directly into the form.

---

### 1.0 Area of Investigation

Analysis, design, and implementation of an edge-computed digital asset curation, micro-expression quality filtering, and submodular album layout optimization system for commercial event photography studios. The study focuses on edge computer vision defect screening (Laplacian focus variance and facial landmark Eye Aspect Ratio analysis), on-device multimodal semantic vector embeddings (OpenCLIP / MobileCLIP), and discrete submodular set optimization under cardinality constraints. The platform combines a heavy-compute desktop web production workstation with an Android mobile companion application for field milestone auditing and client proofing, directly supporting IT0037 Systems Analysis and Design and the BSIT Web and Mobile Application specialization.

---

### 2.0 Background and Rationale of the Project

Commercial event photography teams capture thousands of high-resolution RAW images per shoot, creating an 8- to 12-hour manual culling bottleneck for lead editors `[TO VALIDATE]`. Post-production editors suffer cognitive fatigue, leading to accidental selection of near-identical burst shots and missed chronological milestones `[TO VALIDATE]`. Existing commercial tools rely on proprietary cloud uploads, which are impractical over local upload bandwidth, or only perform isolated binary filtering (Keep vs. Reject) that fails to solve the global problem of assembling a balanced story under strict album size limits.

LensCull addresses this operational bottleneck through a 100% on-premise pipeline running entirely on local client workstation hardware:

- **Decoupled Ingestion:** Extracts lightweight 1080p preview frames directly from EXIF metadata, avoiding heavy RAW decoding.
- **Tier 1 Defect Screening:** Runs OpenCV Laplacian variance to catch blur and MediaPipe Face Mesh Eye Aspect Ratio (EAR) to isolate blinks.
- **Tier 2 Local Semantic Search:** Employs an INT8-quantized OpenCLIP model via ONNX Runtime to enable zero-shot natural language image search (e.g., "cake cutting", "bride crying") locally in milliseconds.
- **Tier 3 Submodular Selection:** Formulates album compilation as a Submodular Facility Location Problem under a Cardinality Constraint (|S| ≤ K). Using an Accelerated Lazy Greedy algorithm, it selects an optimal subset of K photos, maximizing scene coverage and sharpness while penalizing burst duplicate redundancy.

A working Python command-line proof of concept already demonstrates the algorithm and the AI at small scale (~28 images); semantic search and curation work but are not yet perfect. A named industry partner has not yet been secured `[TO VALIDATE]`; the team's immediate next step is to secure a professional event photographer or studio, including written consent because the photos contain identifiable faces under the Data Privacy Act of 2012 (RA 10173).

---

### 3.0 Statement of Objectives

The primary objective is to analyze, design, and implement LensCull, an edge AI-assisted visual culling and multi-objective album layout sequencing system for commercial photography studios. Specifically, the project aims to:

1. Develop a desktop web-based production workstation engine capable of high-throughput local folder ingestion, embedded preview streaming, and XMP/Lightroom export generation without cloud reliance.
2. Develop an Android mobile companion application providing on-venue milestone coverage tracking for field photographers and a swipe-to-approve proofing gallery for studio clients.
3. Implement a two-tier edge computer vision quality pipeline utilizing OpenCV Laplacian focus variance and MediaPipe Face Mesh Eye Aspect Ratio (EAR) to automatically isolate blur and blink defects.
4. Implement an on-device multimodal semantic embedding model (quantized OpenCLIP / MobileCLIP via ONNX Runtime) to facilitate zero-shot natural language search and semantic scene clustering across local image collections.
5. Formulate and implement an Accelerated Lazy Greedy Submodular Facility Location algorithm to select an optimal subset of K photos that balances milestone coverage and visual quality while penalizing duplicate burst shots.
6. Provide a studio analytics dashboard tracking cull compression ratios, per-photographer defect distributions, and chronological timeline milestone coverage.
7. Evaluate defect classification accuracy (Precision, Recall, F1-Score) and algorithmic subset concordance against historical human-curated albums using the Jaccard Similarity Index (J).

---

### 4.0 Scope and Limitations of the Study

**Scope:**
- **Desktop Web Workstation (Editor):** Local directory ingestion, multi-threaded EXIF/preview extraction, two-tier AI defect filtering, natural language search console, submodular album generator, timeline layout canvas, and client proofing manifest generator.
- **Android Mobile App (Field & Client):** On-site milestone coverage checklist for lead photographers and a lightweight swipeable proofing/photo-swapping gallery for clients.
- **Pipeline and evaluation:** Edge CV screening (Laplacian variance + EAR), local semantic embeddings (quantized CLIP via ONNX Runtime), submodular album selection under |S| ≤ K, studio analytics, and defect/set-concordance evaluation.

**Limitations / out of scope:**
- The mobile client is developed and validated specifically for Android mobile devices.
- The system is restricted to image triage, culling, semantic search, and layout sequencing; it does not perform destructive pixel edits, RAW color grading, or exposure retouching.
- Ingestion operates on standard JPEGs and camera RAW formats containing readable embedded preview streams.
- The pipeline is 100% on-premise; there is no cloud upload or cloud processing.
- Single-client study: evaluation is restricted to one photographer/studio `[TO VALIDATE]`; results are not generalized.
- The "under 30 minutes" cull claim is a target, not a measured result `[TO VALIDATE]` — it will be reported from the benchmark study.
- Performance thresholds (search latency, cull time, accuracy) will be established through the validation study rather than assumed in this proposal.

---

### 5.0 Target Beneficiaries

1. **Commercial Photography Studios and Media Teams:** Aims to reduce post-production labor from over 8 hours to under 30 minutes per shoot `[TO VALIDATE — target, not yet measured]`, reducing cognitive fatigue and duplicate burst selection errors.
2. **Field Photographers:** Provides immediate on-venue verification of mandatory shoot milestones before leaving event locations.
3. **Studio Clients and Celebrants:** Delivers faster turnaround of balanced, curated proofing albums with seamless mobile review and swap capabilities.

---

### 6.0 References

- Submodular set-function optimization studies
- Computer vision and multimodal embedding studies (CLIP, eye-blink detection)

> *(Simple/general style for title approval only. Full list kept in reserve below for the final proposal.)*

---

### 7.0 Appendices and Evidence Attachments

- System architecture diagram and hierarchical staged ingestion flowchart
- Submodular objective function formulation and Accelerated Lazy Greedy mathematical schema
- Studio proofing UI wireframes and Jaccard concordance evaluation matrix

> **Evidence status note:** these appendices describe the design and the existing Python proof of concept. There is no client evidence, interview, or formal dataset yet — those are `[TO VALIDATE]` and are not listed here as if they exist.

---

<details>
<summary><b>Reserved for final proposal (Chapter 2 / final defense) — not for this form</b></summary>

**References (full):**
1. Bilmes, J. (2022). *Submodularity in machine learning and artificial intelligence.* arXiv preprint arXiv:2202.00132.
2. FEU Diliman. (n.d.). *IT0037 Module 1: Systems analysis fundamentals and organizational context* [Course material]. Department of Information Technology.
3. FEU Diliman. (n.d.). *IT0037 Module 2: Planning systems projects and preliminary investigation* [Course material]. Department of Information Technology.
4. Nemhauser, G. L., Wolsey, L. A., & Fisher, M. L. (1978). *An analysis of approximations for maximizing submodular set functions I.* Mathematical Programming, 14(1), 265–294.
5. Radford, A., Kim, J. W., Hallacy, C., Ramesh, A., Goh, G., Agarwal, S., … & Sutskever, I. (2021). *Learning transferable visual models from natural language supervision.* In International Conference on Machine Learning (pp. 8748–8763). PMLR.
6. Republic of the Philippines. (2012). *Data Privacy Act of 2012 (Republic Act No. 10173).* Official Gazette.
7. Shelly, G. B., Cashman, T. J., & Rosenblatt, H. J. (2012). *Systems analysis and design* (9th ed.). Cengage Learning. *(verify edition/year against syllabus copy)*
8. Soukupova, T., & Cech, J. (2016). *Real-time eye blink detection using facial landmarks.* In 21st Computer Vision Winter Workshop (pp. 1–8).

**Appendices (full):** Client Endorsement & Photo-Use Consent Letter · Photographer/Editor Interview Guide · Data Privacy & Consent Disclosure (RA 10173) · Evidence Status Matrix · Validation Plan (120-shot benchmark)

> System architecture and use-case diagrams belong to analysis/design after title approval — never list them as appendices at title stage as if they already exist. Note also that this title's photos contain identifiable faces; any real photo use requires written consent.

</details>
