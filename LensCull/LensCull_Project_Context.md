# LensCull — Project Context Pack

> **Purpose of this file:** Single source of truth for the client-based capstone title. Give this file to any teammate or tool (slides, documentation, design, code) so everything stays consistent with the title, scope, client, and IT0037 course lessons.
>
> **Version:** 0.1 (initial pack built from the Title 4 proposal draft) · **Owner:** AzTech (Group 6) · **Client:** [TO VALIDATE] — no named professional event photographer or studio has agreed yet · **Status:** PROOF OF CONCEPT EXISTS IN PYTHON CLI, BUT NO NAMED CLIENT YET

> **Working name:** "LensCull" is the name used in the Title 4 proposal draft. Alternatives if the team prefers: *CullFlow*, *PrimeCull*, *AlbumLens*, *KeeperPick*. Pick one with the team and the prospective client, then find/replace.

---

## 0. Rules for anyone using this file

1. **Do not invent evidence.** No client, interview, observation, or formal dataset has been collected yet. Never state cull time, image counts, editor hours, or accuracy as fact. Use `[TO VALIDATE]`.
2. **Disclose the missing client openly.** There is no signed industry partner at this stage. Every client-dependent item is `[TO VALIDATE]`. Never imply that a studio or photographer has already agreed.
3. **Prototype claim rule.** The only real asset is a working **Python command-line proof of concept** tested at small scale (about 28 images), where semantic search and curation work but are not yet perfect. State it exactly that way. Do not claim a finished product, a web app, or a mobile app.
4. **The "8 hours to 30 minutes" claim is unvalidated.** Always write it as a *target* with `[TO VALIDATE]`. Never present it as a measured result.
5. **Respect the scope (Section 6).** No destructive pixel edits, RAW color grading, or exposure retouching. No cloud-upload dependency. No customer booking or payment.
6. **Privacy first (RA 10173).** Event photos contain identifiable faces. Any use of real photos requires written consent from the photographer/studio and a lawful basis under the Data Privacy Act of 2012 (RA 10173).
7. **Keep course lessons traceable (Section 9).**
8. The actual defense, oral checks, quizzes, and exams are **AI-use prohibited**. The presenter must understand and own every claim.

---

## 1. Project identity

| Field | Value |
|---|---|
| **Title (canonical — Title 4 of the AzTech proposal set)** | LensCull: An Edge AI-Assisted Visual Culling, Micro-Expression Quality Filtering, and Submodular Album Selection System for Professional Event Photographers |
| **Alt. title (client-named variant — only if panel authorizes)** | LensCull: An Edge AI-Assisted Visual Culling, Micro-Expression Quality Filtering, and Submodular Album Selection System for [Prospective Photography Studio] |
| **Specialization** | BSIT — Web and Mobile Application |
| **School / course** | FEU Diliman · IT0037 Systems Analysis and Design |
| **Client** | [TO VALIDATE] — a prospective professional event photographer or commercial photography studio. No client has been secured yet. |
| **Users** | Lead editors / post-production staff — **heavy-compute desktop web production workstation**; Field photographers and studio clients — **Android mobile companion app** for milestone auditing and swipe-to-approve proofing |
| **Not a user** | The party/wedding hosts (end clients of the studio) — they review proofs through the studio, not by logging into the system |

### One-line pitch
LensCull turns a shoot's overload of near-identical RAW files into a short, balanced, story-aware album — screen the defects on-site, search the shoot in plain language, then let a submodular selector pick the K best photos under the album's size limit.

### Short description
Commercial event photography teams capture thousands of high-resolution RAW images per shoot, which forces the lead editor into an 8- to 12-hour manual culling bottleneck `[TO VALIDATE]`. Fatigue leads to picking near-identical burst shots and missing chronological milestones `[TO VALIDATE]`. LensCull runs a 100% on-premise pipeline on the client's own workstation: it ingests lightweight 1080p preview frames instead of decoding full RAW, screens out blur and blinks with edge computer vision, indexes each frame with a local (INT8-quantized) CLIP model for zero-shot natural-language search, and then selects an optimal album subset K using an Accelerated Lazy Greedy submodular algorithm that rewards scene coverage and sharpness while penalizing burst duplicates. An editor's desktop web workstation drives the heavy compute; a field photographer and studio client use an Android companion app for milestone auditing and swipe-to-approve proofing.

### Title breakdown (Module 1: four title elements)

| Element | In the title |
|---|---|
| Capability | Visual Culling, Micro-Expression Quality Filtering, and Submodular Album Selection |
| Users / setting | Professional Event Photographers (commercial event photography studios) |
| Value / problem direction | Faster cull, fewer duplicate or missed shots, a balanced album under a strict size limit |
| Specialization differentiator | Edge AI (on-premise computer vision + local semantic search) with a desktop web production workstation and an Android mobile companion |

> Note on naming: Module 1 warns against titles that hide the real transaction. The real transaction here is **"ingest a shoot → screen defects → search → select the album → proof with the client."** Keep "culling / album selection" in the title.
>
> **Algorithm facet (added with this pack):** *Album Selection* is implemented as a **Submodular Facility Location Problem under a Cardinality Constraint (|S| ≤ K)**, solved with an **Accelerated Lazy Greedy** algorithm. The objective maximizes scene coverage and sharpness while penalizing burst duplicate redundancy. The advisor's Algorithm requirement is satisfied by this discrete set-optimization formulation — it is the strongest algorithm in the team's portfolio.
>
> **AI facet:** Tier 1 edge computer vision — **OpenCV Laplacian variance** for blur and **MediaPipe Face Mesh Eye Aspect Ratio (EAR)** to isolate blinks. Tier 2 — an **INT8-quantized OpenCLIP or MobileCLIP** model via **ONNX Runtime** for zero-shot natural-language image search, running locally in milliseconds.
>
> **Analytics facet:** A studio analytics dashboard tracks cull compression ratios, per-photographer defect distributions, and chronological timeline milestone coverage.

---

## 2. Problem framing

### Symptom vs. root cause (Module 1)
- **Symptoms (hypothesized, to validate):** editors spend long hours going through thousands of images; near-identical burst frames get selected; important chronological moments get missed; editors report fatigue; turnaround to the client is slow `[TO VALIDATE]`.
- **Root cause (working hypothesis):** culling and album assembly are done **manually and image-by-image**, with no automated defect screening, no way to search a whole shoot by meaning, and no global method to choose the best balanced set under an album size limit.

### Problem statement (draft)
Commercial event photography teams capture thousands of high-resolution RAW images per shoot, creating an 8- to 12-hour manual culling bottleneck for lead editors `[TO VALIDATE]`. Post-production editors suffer cognitive fatigue, leading to accidental selection of near-identical burst shots and missed chronological milestones `[TO VALIDATE]`. Existing commercial tools rely on proprietary cloud uploads, which are impractical over local upload bandwidth, or only perform isolated binary Keep-versus-Reject filtering that fails the global problem of assembling a balanced story under strict album size limits.

### Evidence status

| Evidence | Status |
|---|---|
| A photography client exists and agrees to partner | ❌ No named client yet — `[TO VALIDATE]` |
| Editor cull time of 8–12 hours per shoot | ❌ Hypothesis — `[TO VALIDATE]` |
| Fatigue causing duplicate/missed selections | ❌ Hypothesis — `[TO VALIDATE]` |
| Cloud-upload tools are impractical over local upload bandwidth | ⚠️ General claim — verify against a real studio's connection before stating `[TO VALIDATE]` |
| Existing tools only do binary Keep/Reject filtering | ⚠️ Market claim — verify against named tools before stating `[TO VALIDATE]` |
| Working implementation of the pipeline | ✅ Python command-line proof of concept (small scale, ~28 images) — algorithm and AI demonstrated, not yet perfect |
| Measured cull-time reduction, precision/recall/F1, Jaccard concordance | ❌ Not yet measured — pending the validation study (see `LensCull_Validation_Plan.md`) |

### Stakeholders (Module 3)

| Stakeholder | Role / lens | Interest |
|---|---|---|
| Lead editor / post-production staff | Process owner, admin user (desktop web) | Faster cull, no duplicates, no missed milestones, less fatigue |
| Field photographer | Direct user (Android mobile) | On-site verification that mandatory shoot milestones were captured before leaving |
| Studio client / celebrant | Direct user (Android proofing) | Fast, balanced proofing album; easy swipe-to-approve and swap |
| Studio owner / manager `[TO VALIDATE]` | Sponsor, decision maker | Turnaround time, consistency across editors, studio analytics |
| Adviser / panel | Governance | Evidence, scope, feasibility, ethics (esp. facial data) |

**Power–interest (Module 1):** Lead editor = manage closely (high power, high interest) · Field photographer and client = keep satisfied / keep informed · Studio owner = involve where identified · Panel = monitor.

---

## 3. Background (secondary context — keep claims general)

- Commercial event photography (weddings, debuts, graduations, corporate events) is a **high-volume** activity: a single shoot can produce thousands of RAW files `[verify count with a real studio]`.
- Culling — deciding which images to keep — is the first and most time-consuming post-production step `[cite a real source or drop]`.
- On-device vision and multimodal models (CLIP-family) have become small enough to run locally on consumer hardware with quantization (INT8) `[cite Radford et al. 2021 and a quantization source]`.

> Do not add statistics without a checkable source. For this title, **a real client's measured numbers matter more than industry statistics.**

### Related systems / alternatives (for "What's new?")

| Alternative | What it does | Gap LensCull fills |
|---|---|---|
| Manual culling in Lightroom / Bridge / Photo Mechanic | Human selects keepers | Slow; fatigue; no global album optimization; no semantic search across the shoot |
| Cloud AI culling services (proprietary upload) | AI scores/ranks on their servers | Requires uploading thousands of RAWs, impractical over local bandwidth; privacy concern with client faces; subscription |
| Binary AI cullers (auto Keep vs. Reject) | Removes blur/duplicates | Isolated per-image decisions; does not assemble a balanced album under a size limit |
| Face/emotion tagging tools | Group by person/expression | Organizes, does not optimize a final subset; no submodular coverage objective |

**Differentiator:** a 100% on-premise pipeline that combines **edge defect screening + local semantic search + global submodular album selection** under a cardinality constraint — the whole flow stays on the editor's workstation, no cloud upload required.

---

## 4. Objectives

### General objective
To design and develop LensCull, an edge AI-assisted visual culling, micro-expression quality filtering, and submodular album selection system that helps professional event photographers cull a shoot faster and assemble a balanced album under a strict size limit.

### Specific objectives (draft)
1. Develop a desktop web-based production workstation engine for high-throughput local folder ingestion, embedded preview streaming, and XMP/Lightroom export generation without cloud reliance.
2. Develop an Android mobile companion app for on-venue milestone coverage tracking (field photographers) and swipe-to-approve proofing (studio clients).
3. Implement a two-tier edge computer-vision quality pipeline using OpenCV Laplacian focus variance and MediaPipe Face Mesh Eye Aspect Ratio (EAR) to automatically isolate blur and blink defects.
4. Implement an on-device multimodal semantic embedding model (quantized OpenCLIP / MobileCLIP via ONNX Runtime) for zero-shot natural-language search and semantic scene clustering across local image collections.
5. Formulate and implement an Accelerated Lazy Greedy Submodular Facility Location algorithm that selects an optimal subset of K photos balancing milestone coverage and visual quality while penalizing duplicate burst shots.
6. Provide a studio analytics dashboard tracking cull compression ratios, per-photographer defect distributions, and chronological timeline milestone coverage.
7. Evaluate defect classification accuracy (precision, recall, F1) and algorithmic subset concordance against historical human-curated albums using the Jaccard Similarity Index (J).

### Success measures (fill after the validation study)

| Indicator | Baseline | Target | Source |
|---|---|---|---|
| Time to cull one shoot | `[TO VALIDATE — measure baseline first]` | `< 30 min` target `[TO VALIDATE]` | Timed 120-shot benchmark before vs. after |
| Selection agreement with the human set | — | `[set after baseline]` | Jaccard Similarity Index vs. photographer's own set |
| Blur/blink defect detection | — | `[set after baseline]` | Precision, recall, F1 vs. human labels |
| Duplicate burst rate in the final album | `[TO VALIDATE]` | Reduced `[set]` | Count near-identical frames in the selected subset |
| ISO/IEC 25010 survey weighted mean | — | `[set]` | Likert survey with the photographer |

---

## 5. How the system works

1. **Ingestion (on-premise):** the workstation reads a shoot folder and extracts lightweight **1080p preview frames** directly from EXIF-embedded previews, avoiding heavy full RAW decoding.
2. **Tier 1 defect screening (edge CV):** OpenCV **Laplacian variance** flags blur; MediaPipe **Face Mesh Eye Aspect Ratio (EAR)** isolates blinks. Output: per-image defect flags and scores.
3. **Tier 2 semantic search (local model):** an INT8-quantized **OpenCLIP / MobileCLIP** model embeds each frame via **ONNX Runtime**, enabling zero-shot natural-language search (e.g., "cake cutting", "bride crying") locally in milliseconds and semantic scene clustering.
4. **Tier 3 submodular selection:** the album is compiled as a **Submodular Facility Location Problem under a Cardinality Constraint (|S| ≤ K)**, solved with an **Accelerated Lazy Greedy** algorithm — maximizing scene coverage and sharpness while penalizing burst duplicate redundancy.
5. **Proofing:** the client reviews the proposed album through swipe-to-approve in the Android app, with photo swapping; the editor approves the final set.
6. **Export:** the editor exports the album / manifest (XMP / Lightroom) for downstream editing — LensCull itself does not perform destructive edits.

> Mobile side: the field photographer uses the Android app to check off **required milestones** on-site before leaving the venue.

---

## 6. Scope and limitations

### In scope
- **Desktop web production workstation (editor):** local directory ingestion; multi-threaded EXIF/preview extraction; two-tier AI defect filtering; natural-language search console; submodular album generator; timeline layout canvas; client proofing-manifest generator
- **Android mobile app (field and client):** on-site milestone coverage checklist for the lead photographer; lightweight swipeable proofing / photo-swapping gallery for clients
- **Pipeline:** edge CV screening (Laplacian variance + EAR), local semantic embeddings (quantized CLIP via ONNX), submodular album selection under |S| ≤ K
- **Analytics:** cull compression ratio, per-photographer defect distributions, timeline milestone coverage
- **Evaluation:** precision / recall / F1 for defect detection; Jaccard Similarity Index for subset concordance against a human-curated album

### Limitations / delimitations

| Item | Reason |
|---|---|
| Android only for the mobile companion | Declared scope; team is an Android team. iOS proofing can use a responsive web view as future work |
| No destructive pixel edits, RAW color grading, or exposure retouching | The system is triage, culling, semantic search, and layout sequencing only |
| Ingestion limited to standard JPEGs and camera RAW formats that contain readable embedded preview streams | Requires a preview stream to avoid full RAW decode |
| 100% on-premise (no cloud pipeline) | Avoids upload bandwidth and keeps client faces local; also a privacy choice (RA 10173) |
| Single-client study | Evaluation restricted to one photographer/studio `[TO VALIDATE]`; results not generalized |
| "Under 30 minutes" is a target, not a measured result | `[TO VALIDATE]` — must be proven by the benchmark study before it is claimed as delivered |
| No live shoot control, no camera tethering, no booking or payment | Out of scope |
| Accuracy is measured, not assumed | The Python proof of concept works but is not yet perfect; the validation plan reports measured numbers honestly |

---

## 7. Requirements (draft — validate with client)

### 7.1 Editor desktop web production workstation

| ID | Requirement | Priority | Acceptance criteria |
|---|---|---|---|
| EDW-01 | Local folder / shoot ingestion | Must | Ingests a shoot folder; reads EXIF + embedded previews without full RAW decode |
| EDW-02 | Multi-threaded preview extraction | Must | Generates 1080p preview frames for all images; progress is visible |
| EDW-03 | Tier 1 defect screening (blur + blink) | Must | Each image tagged with blur (Laplacian variance) and blink (EAR) flags and scores |
| EDW-04 | Natural-language semantic search | Must | Query like "cake cutting" returns ranked matching frames locally |
| EDW-05 | Submodular album generation under \|S\| ≤ K | Must | User sets K; engine returns a subset maximizing coverage/sharpness while penalizing duplicates |
| EDW-06 | Timeline layout canvas | Should | Selected frames arranged along a chronological milestone timeline |
| EDW-07 | Proofing manifest generation | Should | Produces a manifest/list the client app can read for proofing |
| EDW-08 | XMP / Lightroom export | Should | Exports selection metadata for downstream editing |
| EDW-09 | Manual override of selection | Must | Editor can add/remove any frame; overrides are logged |
| EDW-10 | Studio analytics dashboard | Should | Shows compression ratio, defect distribution, milestone coverage |

### 7.2 Android companion app (field and client)

| ID | Requirement | Priority | Acceptance criteria |
|---|---|---|---|
| FLD-01 | Milestone coverage checklist | Must | Field photographer confirms required milestones on-site before leaving |
| FLD-02 | Swipe-to-approve proofing gallery | Must | Client approves/rejects each proposed photo with a swipe |
| FLD-03 | Photo swap | Should | Client can propose a swap from a candidate set for editor approval |
| FLD-04 | Progress indicator | Should | Shows covered vs. uncovered milestones for the current shoot |
| FLD-05 | Offline-tolerant local capture/state | Should | Works on weak connectivity at the venue and reconciles later |

### 7.3 Non-functional (ISO/IEC 25010 — selected)

| ID | Characteristic | Requirement |
|---|---|---|
| NFR-01 | Performance efficiency | Tier 2 semantic search returns results locally in milliseconds per query `[measure target]` |
| NFR-02 | Performance efficiency | Culling throughput requires no cloud round-trip; runs on the workstation's local GPU/CPU |
| NFR-03 | Security / privacy | Photos with faces never leave the workstation by default; RA 10173 data handling; consent captured |
| NFR-04 | Interaction capability (usability) | A client can approve a photo in ≤ `[N]` taps/swipes |
| NFR-05 | Reliability | Selection respects the cardinality constraint \|S\| ≤ K in every run |
| NFR-06 | Maintainability | Model/runtime versions (ONNX, CLIP variant, MediaPipe) are pinned and documented |

### 7.4 Deliberately excluded (Won't, this version)
Cloud upload pipeline · destructive edits / RAW grading · iOS native app · camera tethering / live shoot control · booking and payments · multi-studio tenancy

---

## 8. Data model and behavior

### 8.1 Entities (logical)

| Entity | Key attributes |
|---|---|
| User | user_id, name, role (Editor / Field / Client), status |
| Shoot | shoot_id, title, shoot_date, venue, status, created_by |
| Image | image_id, shoot_id, file_path, exif_timestamp, width, height, format |
| PreviewFrame | preview_id, image_id, path, resolution |
| Defect | defect_id, image_id, type (blur/blink), score, threshold_used |
| Embedding | embedding_id, image_id, model_version, vector_ref |
| Milestone | milestone_id, shoot_id, label (e.g., "cake cutting"), time_expected |
| MilestoneCoverage | shoot_id, milestone_id, coverage_status |
| Selection | selection_id, shoot_id, K, algorithm_params, objective_value |
| SelectionItem | selection_id, image_id, coverage_gain, rank |
| Proof | proof_id, selection_id, image_id, client_action (approve/swap), proposed_swap_id |
| Metric | metric_id, shoot_id, cull_compression_ratio, defect_distribution, milestone_coverage |
| ActivityLog | log_id, user_id, action, target, timestamp |

### 8.2 Relationships
- Shoot 1—* Image; Image 1—1 PreviewFrame
- Image 1—* Defect; Image 1—1 Embedding
- Shoot 1—* Milestone; Shoot 1—* Selection; Selection 1—* SelectionItem
- SelectionItem *—1 Image
- Selection 1—* Proof; Proof *—1 Image; Proof 0..1—1 proposed_swap Image
- Shoot 1—* Metric; User 1—* ActivityLog

### 8.3 Business rules

> **Status: all business rules below (BR-01 – BR-10) are PROPOSED design decisions — none are confirmed with a client.** They must be reviewed during the client interview and confirmed, adjusted, or rejected before the final proposal. Values marked `[TO VALIDATE]` are starting hypotheses only.

- BR-01: An album selection never exceeds K images (|S| ≤ K), where K is set by the editor for that shoot.
- BR-02: The submodular objective rewards scene-coverage and sharpness gains and penalizes burst-duplicate redundancy `[weights TO VALIDATE]`.
- BR-03: An image flagged as a hard defect (blur below threshold, blink detected as closed) is excluded from the candidate set unless the editor overrides.
- BR-04: Blur and blink thresholds are configurable per shoot / per photographer `[defaults TO VALIDATE]`.
- BR-05: Semantic search runs entirely locally; queries never send images off the workstation.
- BR-06: Every automatic selection decision is reviewable and overridable by the editor; overrides are logged.
- BR-07: The client proofing action (approve / request swap) does not mutate the album until the editor confirms.
- BR-08: Photos containing identifiable faces are processed on-premise by default; any export is an explicit editor action.
- BR-09: The milestone coverage report is derived from the selection, not from the full shoot, so it reflects what the album actually tells as a story.
- BR-10: No destructive edit is applied to any original file; LensCull only writes selection/export metadata.

### 8.4 State models
**Image**
```
Ingested ──preview extracted──► Indexed ──Tier 1 screened──► Screened
Screened ──Tier 2 embedded──► Embedded ──selected by algorithm──► InAlbum
Screened/Embedded ──defect / not chosen──► Rejected (recoverable)
InAlbum ──editor override──► Rejected (recoverable)
```
**Shoot**
```
Ingested ──screened──► Screened ──album generated──► Album Proposed
Album Proposed ──client proofs──► Proofing ──editor confirms──► Locked ──export──► Delivered
```
**Proof**
```
Pending ──client approves──► Approved
Pending ──client requests swap──► Swap Proposed ──editor confirms──► Approved
Pending ──editor overrides──► Overridden
```

---

## 9. IT0037 lessons mapped

### Module 1 — Systems Analysis Fundamentals
| Concept | Application |
|---|---|
| Symptom vs. root cause | Editor fatigue and duplicate picks = symptoms; manual image-by-image culling with no global album objective = root cause |
| Evidence triangulation | Client interview + observed cull of a real shoot + comparison of the proof-of-concept output against the editor's own album |
| Four title elements | Section 1 |
| Ethics red flags | No hidden AI claims; on-premise handling of face data disclosed; consent for any real photo use |
| Stakeholder power–interest map | Section 2 |
| Hybrid approach with reasons | Prototyping (workstation + mobile UI) + Agile sprints + stage gates |
| Web & Mobile lens: service journey | Ingest → screen → search → select → proof → export |

### Shelly Ch. 2 — Systems Planning
| Concept | Application |
|---|---|
| Systems request | Would come from a studio/photographer `[TO VALIDATE]`; the pain is currently hypothesized, not yet evidenced |
| Reasons for project | Better performance (faster cull), more information (semantic search, coverage), stronger controls (size-constrained album) |
| Preliminary investigation (6 steps) | Understand problem → scope/constraints → fact-finding → feasibility → time/cost → present |
| Constraints | Mandatory: RA 10173; External: local hardware/GPU limits; Present: one studio |
| Fishbone | Causes of slow/duplicate culling: People, Process, Technology, Data, Fatigue/Schedule |
| Tangible / intangible benefits | Tangible: cull time, duplicates removed; intangible: editor well-being, client trust, consistency across editors |

### Bender — SDLC
| Concept | Application |
|---|---|
| Stepwise commitment | Commit to build the web/mobile apps only after the benchmark validates the pipeline and a client signs on |
| Change control | Requests (cloud sync, iOS, RAW edits) are handled as scope changes |
| User involvement | A real editor must be accessible for the benchmark and proofing; without a client, involvement is blocked `[TO VALIDATE]` |

### Module 2 — Feasibility (six dimensions)
| Dimension | Preliminary view | Condition / unknown |
|---|---|---|
| Technical | Feasible at small scale (Python CLI PoC works) | Full-scale throughput on the editor's hardware; ONNX + quantized CLIP + MediaPipe integration `[test]` |
| Operational | Conditional | No client yet; adoption by editors and clients unconfirmed `[TO VALIDATE]` |
| Economic | Conditional | Uses free/open tooling, but needs a workstation with enough GPU/CPU; hosting only for the web shell `[estimate in PHP]` |
| Schedule | Conditional (highest risk) | Very large scope for one term; many components to integrate and evaluate `[see risks]` |
| Security | Conditional | On-premise processing reduces exposure; access control + consent for face data |
| Legal and ethical | Conditional | RA 10173 for identifiable faces; written consent required; model licenses (CLIP/MediaPipe/ONNX) must be checked |

**Assumptions register**

| # | Assumption | Validation action |
|---|---|---|
| A1 | A studio capture produces thousands of RAWs per shoot | Measure with a real shoot |
| A2 | Manual culling takes 8–12 hours per shoot | Time the photographer's own baseline |
| A3 | Fatigue causes duplicate/missed selections | Compare editor's album to a coverage-aware set |
| A4 | The editor's workstation can run the local models | Hardware/GPU check with the client |
| A5 | Photographers will accept on-premise processing | Client interview |
| A6 | A prospective studio will partner and sign consent | Gate 0 outreach + endorsement letter |

**Key risks (cause → event → impact)**

| Risk | Response |
|---|---|
| Very large scope for one term (ingestion, edge CV, ONNX, quantized CLIP, submodular engine, web + Android) → partial delivery | Stage-gate the build; validate the Python pipeline first; deliver web + Android after; MoSCoW the features |
| No named client → no real data → weak evidence | Run Gate 0 outreach now; keep the validation plan ready; use consented sample data only |
| The "8 hours → 30 minutes" claim is unvalidated → credibility risk if stated as fact | Always mark `[TO VALIDATE]`; report measured numbers from the benchmark |
| Two of the four portfolio titles are computer-vision heavy (AuraMesh and LensCull) → may look like one idea twice | Emphasize the distinct problem (album curation + submodular optimization vs. spatial search triage), distinct user, and distinct algorithm; be ready to defend uniqueness |
| Model/runtime integration breaks (ONNX, quantization) | Pin versions; keep a fallback path; test on the client's hardware |
| Face-data privacy | RA 10173; on-premise by default; written consent; no cloud upload |

### Module 3 — Requirements
| Concept | Application |
|---|---|
| Stakeholder lenses | Editor (decision power, process knowledge), field photographer, studio client |
| Elicitation | Client interview, observation of a real cull, document review (a sample shoot + the editor's own album as ground truth) |
| Claim classification | Mark items as observed fact / reported fact / assumption / decision |
| Testable requirements | Section 7 acceptance criteria |
| MoSCoW | Section 7 priorities |
| ISO/IEC 25010:2023 | Section 7.3 |
| RTM | Link requirement → stakeholder need → evidence → test |

### Module 4 — Structured and OO Modeling
**Context diagram:** System = LensCull. External entities: **Editor** (desktop web), **Field photographer** (Android), **Studio client** (Android proofing), and optionally a **Camera/card folder** as a data source. The end celebrant/host is not a system entity.

**Level 0 DFD processes**
1.0 Ingest Shoot Folder · 2.0 Extract Preview Frames · 3.0 Screen Defects (Tier 1) · 4.0 Build Semantic Index (Tier 2) · 5.0 Select Album (Submodular, Tier 3) · 6.0 Track Milestone Coverage · 7.0 Manage Proofing · 8.0 Generate Analytics and Export

**Data stores:** D1 Shoots · D2 Images · D3 PreviewFrames · D4 Defects · D5 Embeddings · D6 Milestones · D7 Selections · D8 Proofs · D9 Metrics · D10 Activity Log

**Use cases**
Editor: Ingest Shoot · Screen Defects · Search Shoot · Generate Album · Override Selection · Export
Field photographer: Track Milestones · View Coverage
Client: Review Proofs · Approve Photos · Request Swap

**Submodular album selection (Accelerated Lazy Greedy):** maximize a monotone submodular objective f(S) = coverage(S) + quality(S) − redundancy(S) subject to |S| ≤ K. Lazy greedy exploits submodularity to skip provably suboptimal evaluations while guaranteeing a (1 − 1/e) approximation of the optimum, so the K-photo album can be assembled without an exhaustive search over all subsets.

**Decision table (include an image in the candidate set)**

| Condition | R1 | R2 | R3 | R4 |
|---|---|---|---|---|
| Readable preview available? | Y | N | Y | Y |
| Hard blur below threshold? | N | – | Y | N |
| Blink (closed eyes) detected? | N | – | – | Y |
| **Eligible for selection** | X | | | |
| **Excluded (recoverable via override)** | | X | X | X |

**Key sequence (Generate Album):** Editor → System: ingest folder → System: extract previews → System: Tier 1 screen → System: Tier 2 embed → Editor: set K → System: run Accelerated Lazy Greedy over candidate set → System: return album + coverage report → Editor: review/override → Client: swipe-to-approve proofing → Editor: confirm → export.

---

## 10. Development approach and evaluation

- **Approach:** Hybrid — validate the Python CLI proof of concept first (the algorithm and AI are already demonstrated), then prototype the workstation and mobile UI, then Agile sprints, behind stage gates (proposal approval → benchmark validation → design approval → pilot approval).
- **Why the Python-first order matters:** the CLI PoC already demonstrates the algorithm and AI, so the controlled benchmark study can run **before** the web and mobile apps are built. The apps are then built and re-tested with the photographer.
- **Pilot:** once a client is secured, run LensCull beside the photographer's normal cull for the benchmark shoots before wider use.
- **Evaluation:** defect classification precision / recall / F1; subset concordance vs. the human album via the **Jaccard Similarity Index**; ISO/IEC 25010 Likert survey with the photographer; before/after cull time on a 120-shot benchmark (see `LensCull_Validation_Plan.md`).

### Suggested stack (NOT decided)
- Workstation: desktop web app (Electron or a local web server + browser UI); local processing in Python/OpenCV, ONNX Runtime for the CLIP model
- Mobile: Android (Kotlin/Compose or Flutter); offline-tolerant
- Models: INT8-quantized OpenCLIP or MobileCLIP; MediaPipe Face Mesh
- Export: XMP sidecars / Lightroom-compatible output
- No cloud requirement; optional local metadata DB (SQLite)

---

## 11. Data gathering plan

| Method | Participants | Purpose | Target date |
|---|---|---|---|
| Gate 0 outreach | Prospective event photographer / studio owner | Secure an industry partner + written consent | `[set]` |
| Interview | Photographer / studio owner / lead editor | Current cull workflow, volume, tools, pain points, hardware | `[set]` |
| Observation | Time a real or simulated cull of one shoot | Baseline cull time and method | `[set]` |
| Document review | Sample shoot + the editor's own selected album | Ground-truth set for Jaccard concordance | `[set]` |
| Benchmark study | Photographer (named partner) | 120-shot controlled study (see validation plan) | `[set]` |
| Endorsement letter | Photographer / studio owner | Formal client commitment + consent to use photos | Before mock defense |

**Honest answer if asked "Do you have a client?":** "Not yet. We have a working Python proof of concept and a validation plan ready, and our immediate next step is to secure a named event photographer or studio as the industry partner, including written consent because the photos contain identifiable faces under the Data Privacy Act."

**Honest answer if asked "Does it work?":** "The algorithm and AI work at small scale — about 28 images — but the results are not yet perfect. Our validation plan reports measured accuracy, not a claim that it is finished."

---

## 12. Defense Q&A bank

| Question | Answer |
|---|---|
| Why not just use Lightroom / Photo Mechanic? | Manual tools make you decide image-by-image; LensCull adds automated defect screening, whole-shoot semantic search, and a global subset that maximizes coverage under the album size limit. |
| Why not a cloud AI culling service? | It needs uploading thousands of RAWs — impractical over local bandwidth — and sends client faces off-site. LensCull runs 100% on-premise. |
| What's new? | Edge CV screening + local semantic search + submodular album selection under \|S\| ≤ K, all on the editor's workstation. |
| What is the algorithm, exactly? | Album compilation is a Submodular Facility Location Problem under a Cardinality Constraint, solved with Accelerated Lazy Greedy; the objective maximizes coverage and sharpness and penalizes burst duplicates, with a (1 − 1/e) approximation guarantee. |
| Why submodular and not just sorting by score? | Sorting is greedy per-image and can pick five near-identical frames. Submodular coverage rewards diversity across the story and penalizes redundancy — it is the right model for "balanced album under a size limit." |
| How fast is "under 30 minutes"? | That is a target, not a measured result. We mark it `[TO VALIDATE]` and will report the real number from the 120-shot benchmark. |
| Is the AI perfect? | No. The Python proof of concept works at small scale (~28 images) but is not perfect. We measure precision, recall, and F1 rather than claim perfection. |
| Do you have a client? | Not yet. Securing a named photographer/studio with written consent is our immediate next step. |
| Privacy of people's faces? | On-premise processing by default; RA 10173; written consent from the photographer/studio; no cloud upload; export is an explicit editor action. |
| Why Android only? | Declared scope; team is an Android team. iOS can use a responsive web proofing view as future work. |
| Does it edit photos? | No destructive edits, RAW grading, or retouching — triage, cull, search, and layout sequencing only. |
| How will you evaluate it? | Precision/recall/F1 for defects; Jaccard Similarity Index vs. the photographer's own album; before/after cull time on a 120-shot benchmark; ISO/IEC 25010 survey. |
| Isn't item 4 (LensCull) too close to item 3 (AuraMesh)? | Different problem (album curation vs. spatial search triage), different user (event photographer vs. barangay responders), different algorithm (submodular selection vs. isochrone GIS). |
| Is the scope too big for one term? | Yes, it is the top risk. We stage it: validate the Python pipeline first, then build web + Android, MoSCoW the features. |

### Open risks / panel questions (be ready to answer honestly)

| Open risk / likely question | Honest position |
|---|---|
| Very large scope for one term (ONNX, quantized CLIP, MediaPipe, web + Android, analytics) | Too big to do everything at once; stage-gate and MoSCoW. The Python PoC already de-risks the hard core. |
| No named client yet | True. Gate 0 outreach is the immediate next step; all client-dependent items are `[TO VALIDATE]`. |
| The 8-hours-to-30-minutes claim is unvalidated | Correct. Present it as a target; the benchmark will produce the real number. |
| Two of four titles are computer-vision heavy | Acknowledge it; defend the distinct problem, user, and algorithm. |

---

## 13. Mock defense deck outline

| # | Slide | Source |
|---|---|---|
| 1 | Title + four-element breakdown | §1 |
| 2 | The problem: 8–12h cull bottleneck, fatigue, duplicates `[TO VALIDATE]` + evidence status | §2 |
| 3 | Current workflow (as-is) + why cloud/manual tools fall short | §2, §3 |
| 4 | Objectives | §4 |
| 5 | How it works: 6-step pipeline | §5 |
| 6 | Tier 1 edge CV (Laplacian + EAR) | §5, §9 |
| 7 | Tier 2 local semantic search (quantized CLIP / ONNX) | §5, §9 |
| 8 | Tier 3 submodular album selection (Facility Location, Lazy Greedy) | §5, §9 |
| 9 | Scope and limitations | §6 |
| 10 | Requirements + context diagram / Level 0 DFD | §7, §9 |
| 11 | Feasibility (six dimensions) + key risks (scope, no client, unvalidated claim, CV overlap) | §9 |
| 12 | Evaluation: precision/recall/F1 + Jaccard + before/after time | §10 |
| 13 | Proof-of-concept status (Python CLI, ~28 images) + validation plan + next steps | §9, §15 |

---

## 14. Sources

- Bilmes, J. (2022). *Submodularity in machine learning and artificial intelligence.* arXiv:2202.00132.
- Nemhauser, G. L., Wolsey, L. A., & Fisher, M. L. (1978). *An analysis of approximations for maximizing submodular set functions I.* Mathematical Programming, 14(1), 265–294.
- Radford, A., Kim, J. W., Hallacy, C., Ramesh, A., Goh, G., Agarwal, S., … & Sutskever, I. (2021). *Learning transferable visual models from natural language supervision.* ICML (pp. 8748–8763). PMLR.
- Soukupova, T., & Cech, J. (2016). *Real-time eye blink detection using facial landmarks.* 21st Computer Vision Winter Workshop (pp. 1–8).
- Republic of the Philippines. (2012). *Data Privacy Act of 2012 (Republic Act No. 10173).* Official Gazette.
- FEU Diliman. (n.d.). *IT0037 Module 1 / Module 2* [Course material].
- Shelly, G. B., Cashman, T. J., & Rosenblatt, H. J. (2012). *Systems analysis and design* (9th ed.). Cengage Learning.

> Client evidence (interview notes, benchmark results, endorsement letter, consent form) will be the primary source once a partner is secured.

---

## 15. Open items / next steps

- [ ] Confirm the system name (LensCull) with the team
- [ ] **Gate 0:** approach a named event photographer or studio; secure a written endorsement + photo-use consent
- [ ] Interview the photographer/editor; capture the current cull workflow, volume, tools, and hardware
- [ ] Capture the baseline: current manual cull time and the photographer's own selected album for the same 120-shot set
- [ ] Run the Python CLI proof of concept on the 120 shots; compute precision/recall/F1 and Jaccard concordance
- [ ] Run 2–3 shoots under different lighting and burst conditions rather than one large shoot
- [ ] Decide blur/blink thresholds (BR-04) and submodular weights (BR-02) with the client
- [ ] Decide the K default and per-shoot override behavior
- [ ] Confirm the mobile scope (Android only) and the iOS future-work path
- [ ] Verify model licenses (OpenCLIP, MediaPipe, ONNX Runtime)
- [ ] Replace every `[TO VALIDATE]` with evidence, or keep it as a labeled assumption
- [ ] Draft context diagram, Level 0 DFD, ERD, and state diagrams
