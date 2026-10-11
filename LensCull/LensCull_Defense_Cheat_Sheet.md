# LensCull Defense Cheat Sheet

**Proposed Working Title:**
*LensCull: An Edge AI-Assisted Visual Culling, Micro-Expression Quality Filtering, and Submodular Album Selection System for Professional Event Photographers*
*(Client Partner: `[TO VALIDATE]` — no photographer/studio secured yet)*

---

## 1. 30-Second Elevator Pitch
> *"Commercial event photographers shoot thousands of RAW images per shoot and then face an 8- to 12-hour manual culling bottleneck that leaves editors fatigued and lets near-identical burst shots and missed milestones slip through. LensCull runs entirely on the editor's own workstation: it screens blur and blinks with edge computer vision, indexes the whole shoot with a small local CLIP model so you can search it in plain language, and then picks the best K photos for the album with a submodular optimizer that rewards story coverage and penalizes duplicates. We already have a working Python proof of concept at small scale, and our next step is to validate it with a named photographer."*

---

## 2. The Golden Defense Rules for this Title

1. **Do not invent a client.**
   - If asked *"Who is your client?"*
   - **Answer:** *"We don't have a named industry partner yet — every client-dependent item is marked `[TO VALIDATE]`. Our immediate next step is to secure a professional event photographer or studio as our partner, including written consent because the photos contain identifiable faces under the Data Privacy Act."*
2. **Report the prototype exactly as it is.**
   - The only real asset is a **working Python command-line proof of concept**, tested at small scale (**~28 images**), where semantic search and curation work but are **not yet perfect**. Never call it a finished product, web app, or mobile app.
3. **Never state the 8-hours-to-30-minutes claim as a result.**
   - It is a **target**. Always mark it `[TO VALIDATE]` and state that measured numbers come from the 120-shot benchmark.
4. **Own the privacy issue (RA 10173).**
   - Event photos contain identifiable faces. Pipeline is **100% on-premise** by default; any real photo use requires **written consent** from the photographer/studio.
5. **Respect scope (don't let the panel expand it).**
   - **NO** destructive pixel edits, RAW grading, or retouching.
   - **NO** cloud upload / cloud processing.
   - **NO** iOS native app (Android only, declared), **NO** camera tethering, **NO** booking/payments.
6. **Know the algorithm cold.**
   - Submodular Facility Location under a Cardinality Constraint (|S| ≤ K), solved with Accelerated Lazy Greedy, (1 − 1/e) approximation.

---

## 3. High-Frequency Panel Questions & Winning Answers

| Panel Question | Best Defensible Answer | Course Traceability |
|---|---|---|
| **Why not just cull in Lightroom or Photo Mechanic?** | Manual tools make the editor decide image-by-image. LensCull adds three things they don't: automated defect screening (blur + blinks), whole-shoot natural-language search, and a global subset that maximizes story coverage under the album size limit while penalizing duplicates. | Module 1: root cause · Module 3: requirements |
| **Why not a cloud AI culling service?** | Those services need you to upload thousands of RAWs — impractical over a typical local connection — and they move client faces off-site. LensCull runs 100% on-premise on the editor's workstation. | Module 1: root cause · Module 2: operational feasibility |
| **What exactly is the algorithm?** | Album selection is a Submodular Facility Location Problem under a Cardinality Constraint (|S| ≤ K), solved with Accelerated Lazy Greedy. The objective maximizes scene coverage and sharpness and penalizes burst-duplicate redundancy, with a (1 − 1/e) approximation guarantee. | Module 4: modeling · Bilmes 2022, Nemhauser et al. 1978 |
| **Why submodular instead of sorting by a quality score?** | Per-image ranking is greedy and can select five near-identical frames. A submodular coverage objective forces diversity across the story and penalizes redundancy — the correct model for "balanced album under a size limit." | Module 4: problem formulation |
| **How does Tier 1 detect blur and blinks?** | Blur via OpenCV Laplacian variance (low variance = soft frame); blinks via MediaPipe Face Mesh Eye Aspect Ratio — a closed eye lowers the EAR. | Module 4 · Soukupova & Cech 2016 |
| **How does semantic search work with no tags?** | An INT8-quantized OpenCLIP / MobileCLIP model embeds each frame via ONNX Runtime, so a plain-language query like "cake cutting" matches by meaning, locally, in milliseconds. | Module 4 · Radford et al. 2021 |
| **Is the AI perfect / does it work?** | The algorithm and AI work at small scale (~28 images), but the results are **not yet perfect**. We measure precision, recall, and F1 rather than claim perfection. | Module 3: evaluation |
| **Is the "under 30 minutes" claim real?** | No — it is a **target**, not a measured result. It is marked `[TO VALIDATE]` and will be reported from the 120-shot benchmark. | Module 2: feasibility · Module 3: evaluation |
| **How will you evaluate the system?** | Defect detection: precision/recall/F1. Subset concordance vs. the photographer's own album: Jaccard Similarity Index. Time to cull: before/after on a controlled 120-shot benchmark. Software quality: ISO/IEC 25010 Likert survey. | Module 3: quality model & evaluation |
| **Privacy of the people in the photos?** | On-premise processing by default; RA 10173 handling; written consent from the photographer/studio; no cloud upload; export is an explicit editor action. | Module 1: ethics · Legal & ethical feasibility |
| **Why Android only?** | Declared scope — we are an Android team. iOS clients can use a responsive web proofing view as future work. | Module 2: technical feasibility |
| **Does the system edit photos?** | No. It is triage, culling, semantic search, and layout sequencing only — no destructive edits, RAW grading, or retouching. | Module 1: system boundary |
| **Isn't this the same as your AuraMesh title (both computer vision)?** | Different problem, user, and algorithm. AuraMesh is spatial search-and-triage for missing persons (GIS isochrones + sighting triage); LensCull is album curation for photographers (submodular set optimization + local CLIP search). | Module 1: problem framing |
| **Isn't the scope too big for one term?** | It is our top risk, and we say so. We stage it: validate the Python pipeline first, then build the web and Android apps, and MoSCoW the features. The proof of concept already de-risks the hard core. | Module 2: schedule feasibility |

---

## 4. Key `[TO VALIDATE]` Items to Clear with your Client

| Item | What to Ask / Validate with the Photographer or Studio |
|---|---|
| **Named partner** | Will a named photographer or studio agree to be the industry partner, with a signed endorsement and photo-use consent? |
| **Shoot volume** | How many images per shoot, and how many shoots per month? |
| **Baseline cull time** | How long does the current manual cull actually take per shoot? |
| **Current tools** | What does the editor use today (Lightroom, Bridge, Photo Mechanic, cloud service)? |
| **Editor's own album** | Can we obtain the photographer's own hand-selected album for a sample set to use as ground truth? |
| **Hardware** | What workstation/GPU does the editor have? Can it run the local models? |
| **Thresholds** | What counts as "too blurry to keep"? What blink rate is acceptable? |
| **K (album size)** | What is a typical album size limit per shoot, and does it vary by package? |
| **Milestones** | What are the mandatory shoot milestones the field photographer must confirm on-site? |
| **Proofing** | How does the client currently review and approve proofs? |

---

## 5. The "Does it even work?" Defense

**Q: "You said you have a prototype. Does it work?"**

> "The algorithm and the AI work at small scale — about 28 images. Semantic search and curation produce sensible results but are **not yet perfect**. What we have is a **Python command-line proof of concept** that demonstrates the core pipeline; the web and mobile apps are not built yet. Our validation plan is a controlled 120-shot benchmark where we measure the real numbers: defect precision, recall, and F1, and how closely the system's album matches the photographer's own selection using the Jaccard Similarity Index."

**Key point:** Do not oversell. Measured accuracy beats a claim.

**If the panel pushes:** *"Then why propose it?"* → *"Because the hard part — the algorithm and the AI — is already demonstrated, and the remaining work is integration and evaluation. That is exactly what a capstone should validate."*

---

## 6. The "Why Does a Photographer Need AI?" Defense

**Q: "Isn't culling just something photographers do? Why AI?"**

> "Culling is a human judgment call, and LensCull doesn't replace it. It removes the repetitive part: screening obvious blur and blinks, and searching a folder that may hold thousands of files. The editor still reviews and can override every decision. The AI and the submodular optimizer make the editor faster and reduce fatigue-driven mistakes; they do not take the editor out of the loop."

---

## 7. The "Scope Is Too Big" Defense

**Q: "ONNX, quantized CLIP, MediaPipe, a web app, an Android app, analytics — that's a lot for one term. Can you finish?"**

> "We agree it is the top risk, and we planned around it. First, we treat the Python proof of concept as the de-risking step — the hard algorithm and AI are already demonstrated. Second, we stage the build behind stage gates and MoSCoW the features, so the must-haves (ingestion, screening, search, album selection, override) come first and the shoulds/coulds follow. If time runs short, we deliver a smaller but working slice rather than a broad broken one."

---

## 8. The "Two CV Titles" Defense

**Q: "Title 3 (AuraMesh) and Title 4 (LensCull) are both computer-vision heavy. Isn't that one idea twice?"**

> "They share a technology area but not a problem. AuraMesh solves spatial search-and-triage for missing persons — GIS isochrones and sighting verification. LensCull solves album curation for photographers — local semantic search plus submodular set optimization under a size limit. Different problem, different user, different algorithm. The fact that both use computer vision reflects the team's strength, not a duplicated idea."

---

## 9. Red Flags: Claims You Should NOT Make Without Evidence

- "Editors spend exactly 8–12 hours culling each shoot." → `[TO VALIDATE]`
- "LensCull reduces culling to under 30 minutes." → target, `[TO VALIDATE]`
- "The AI is accurate." → say "measured accuracy, not yet perfect"
- "The system is finished / has a web app / has a mobile app." → only a Python CLI PoC exists
- "We have a client." → no named client yet
- "Cloud tools always fail." → verify before stating; state as a general gap
- "The system replaces the editor." → the editor stays in the loop and can override
- "It edits or color-grades photos." → no destructive edits, by scope

Use `[TO VALIDATE]` where appropriate.

---

## 10. Defense Mindset

The goal is **not** to convince the panel that LensCull must exist no matter what.

The goal is to demonstrate:

1. We identified a real process (high-volume culling in event photography).
2. We identified a plausible problem (time, fatigue, duplicates, missed milestones, size-limited albums).
3. We have a proposed solution with a strong algorithm (submodular selection).
4. We know which parts are still assumptions (client, baseline time, accuracy).
5. We have a concrete plan to validate them (the 120-shot benchmark).
6. We will adjust scope if the evidence does not support it.

### Strong closing statement

> **"Our proposal is a solution hypothesis backed by a working proof of concept, not a claim that the problem and the numbers are already proven. Our next step is to secure a named photographer, capture a real baseline, and run the controlled 120-shot benchmark so our claims rest on measured data. If those findings support the problem, we proceed; if they reveal a smaller or different problem, we adjust the scope."**

---

## 11. Evidence Status Update

The project context currently identifies these as **pending validation**:

- A named client (photographer or studio) and written photo-use consent
- Actual cull time per shoot (baseline)
- Images per shoot and shoots per month
- Current tools used by the editor
- The photographer's own curated album (ground truth)
- Editor workstation/GPU capability
- Defect detection accuracy and Jaccard concordance

**Do not convert these into facts in the defense until real evidence confirms them.** The only confirmed fact is the **Python CLI proof of concept at ~28 images, working but not perfect**.
