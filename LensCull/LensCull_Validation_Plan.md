# LensCull — Validation Plan (One Page)

**Goal:** Validate the existing **Python command-line proof of concept** with a real photographer before the web and mobile apps are built. The plan is a controlled **120-shot benchmark study** that measures cull time before vs. after, defect-detection quality (precision, recall, F1), and selection agreement against the photographer's own hand-picked set using the **Jaccard Similarity Index**. The current prototype is framed honestly as **not yet perfect** — we report measured accuracy rather than claim it works.

**Status:** The Python CLI proof of concept already demonstrates the algorithm and AI at small scale (~28 images). Validation can therefore run **before** the apps exist.

---

## 1. Secure an industry partner + written consent (prerequisite)

- Recruit one named professional event photographer or studio owner as the industry partner (see `Client_Interview_Guide.md`).
- Obtain a **signed endorsement and photo-use consent** letter (`Client_Endorsement_Letter_Template.md`). Event photos contain identifiable faces, so the **Data Privacy Act of 2012 (RA 10173)** applies.
- Process **on-premise by default**; share only the minimum number of de-identified photos needed; allow withdrawal and deletion on request.
- **Gate:** no study starts until consent is signed. No partner yet means status stays `[TO VALIDATE]`.

## 2. Capture the baseline first (ground truth)

- Time the photographer's **current manual cull** of the same 120 shots: the **before** number `[TO VALIDATE]`.
- Have the photographer **hand-select their own final set** from those 120 shots. This becomes the **ground truth** album for agreement scoring.
- Record their current tools (Lightroom / Bridge / Photo Mechanic / other) and the album size target **K**.

## 3. Run the proof of concept on the same 120 shots

- Feed the identical 120 images into the Python CLI PoC (ingestion → Tier 1 screening → Tier 2 embeddings → Tier 3 submodular selection).
- Fix the configuration for the study: blur and blink thresholds, submodular weights, and **K = the photographer's album size**.
- No cloud; runs on the photographer's workstation where possible.

## 4. Compare before vs. after, and agreement vs. the human set

| Measure | Method |
|---|---|
| **Time to cull (before vs. after)** | Wall-clock time, manual baseline vs. PoC run, for the same 120 shots. Report the change; the "under 30 minutes" figure stays `[TO VALIDATE]` until measured. |
| **Selection agreement** | **Jaccard Similarity Index** J(A, B) = \|A ∩ B\| / \|A ∪ B\| between the PoC's selected set and the photographer's hand-selected set. Report J (0 = no overlap, 1 = identical). |
| **Defect detection quality** | Against human labels on the same images, report **precision**, **recall**, and **F1** for blur and blink detection (overall and per type). |

## 5. Run two or three shoots, not one large shoot

- Repeat the study across **2–3 shoots** chosen to differ in **lighting** (indoor/low-light vs. bright outdoor) and **burst conditions** (heavy burst sequences vs. mostly single frames).
- Report each shoot separately and note where accuracy drops, rather than claiming one average tells the whole story.

## 6. Frame the prototype honestly

- State plainly that the current prototype is **not yet perfect** and reports **measured accuracy** — not an assertion that it works.
- Publish the real Jaccard, precision, recall, and F1 numbers, including the failure cases (e.g., low-light blur, motion-heavy bursts).
- Never present the 8-hours-to-30-minutes claim as a result; it is a **target** `[TO VALIDATE]`.

## 7. Then build and re-test the apps

- Because the Python CLI already demonstrates the algorithm and AI, validation runs first; the **desktop web workstation** and **Android companion app** are built afterward and **re-tested with the same photographer**.
- Re-run the benchmark on the apps to confirm the pipeline behaves the same once wrapped in the UI.

---

### Success criteria (set after baseline)

| Indicator | Source | Target |
|---|---|---|
| Reduction in time to cull 120 shots | before/after timing | `[set after baseline]`; "< 30 min" is a target `[TO VALIDATE]` |
| Jaccard agreement vs. human album | \|A ∩ B\| / \|A ∪ B\| | `[set after baseline]` |
| Blur detection F1 | vs. human labels | `[set after baseline]` |
| Blink detection F1 | vs. human labels | `[set after baseline]` |

### Known open risks for this study

- **No named client yet** — blocks the whole plan until Gate 0 closes.
- **Very large scope for one term** — the benchmark validates the achieved core; the apps are staged after.
- **Unvalidated time claim** — reported as a target until measured here.
- **Two CV-heavy portfolio titles** — this study's distinct metrics (Jaccard album agreement, submodular selection) help show LensCull is its own idea.
