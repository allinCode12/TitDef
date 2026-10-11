# Client Interview Guide (Fact-Finding) — LensCull
*(Use this 20-minute interview with a prospective professional event photographer or photography studio owner to clear Gate 0 and replace `[TO VALIDATE]` tags before your defense)*

---

### Gate 0: Before the interview — pick the right person

Approach a photographer or studio that **actually runs high-volume event post-production**. Screen with one message:

> *"We are BSIT capstone students (Team AzTech, FEU Diliman) building a system to help event photographers cull large shoots faster and assemble balanced albums without cloud uploads. We are looking for a professional event photographer or studio owner who will act as our industry partner so we can learn your real culling workflow. We are not selling anything, we run the processing on your own machine, and we will disclose how we handle any photos."*

| Candidate partner | Why approach | If they say "that's not us" |
|---|---|---|
| Professional event photographer (independent) | Owns the whole cull workflow end-to-end | Ask for a referral to a busier studio |
| Commercial photography studio owner | Higher volume; may have multiple editors | Ask which staff member owns post-production |
| Lead editor / post-production staff | Closest to the actual pain | Ask who approves the album and tooling |
| Wedding / debut / graduation photography teams | High burst counts and strict album limits | Redirect per their answer |

**Gate 0 closes only when:** (a) the interview is completed, **and** (b) the photographer/studio agrees in principle to partner and signs the endorsement + photo-use consent letter before the mock defense.

> **Privacy note (RA 10173):** event photos contain identifiable faces. Written consent from the photographer/studio is required before using any real photo in the study. Prefer de-identified samples where possible, and process on-premise by default.

---

### Section 1: Role & Business Context
1. **Your Role:** What is your role in the studio — owner, lead photographer, or lead editor? Who does the culling today?
2. **Your Work:** What kinds of events do you shoot (weddings, debuts, graduations, corporate), and roughly how often? `[TO VALIDATE]`
3. **Team Size:** How many photographers and editors are involved per shoot, if any?

---

### Section 2: Current Post-Production Workflow (as-is)
4. **Step-by-Step:** Walk us through what happens after a shoot — from importing the memory card to delivering the final album. (Import tool? Cull method? Editing? Proofing?)
5. **Tooling:** What software do you use today — Lightroom, Bridge, Photo Mechanic, a cloud culling service? What works and what frustrates you?
6. **The Cull Step:** How exactly do you decide which photos to keep? Do you go image-by-image, use ratings/flags, or something else?
7. **Album Size:** When you deliver the album, do you have a target number of photos per shoot, or is it open-ended? `[TO VALIDATE — feeds K]`
8. **Proofing:** How do clients review and approve photos today (gallery link, prints, in person)?

---

### Section 3: Volume, Time & Pain Points *(the baseline metrics — do not accept estimates as fact)*
9. **Images per Shoot:** On average, how many photos do you capture per shoot? Do burst sequences make up much of it? `[TO VALIDATE]`
10. **Baseline Cull Time:** How long does culling one shoot actually take you from start to finish? *(Ask for records/timestamps if possible; this is the before number for the benchmark.)* `[TO VALIDATE]`
11. **Duplicates & Missed Shots:** Have you ever kept near-identical burst shots by mistake, or later realized a key moment was missed? `[TO VALIDATE]`
12. **Fatigue:** Do long culling sessions affect your focus or consistency? `[TO VALIDATE]`
13. **Hardware:** What computer and GPU do you edit on? Could it run a small local AI model? `[TO VALIDATE]`
14. **Consistency:** Do different editors on your team cull to the same standard, or does it vary?

---

### Section 4: Data, Privacy & Readiness (RA 10173)
15. **Photo Consent:** Do your client contracts already cover using/anonymizing photos for internal processing or tool testing?
16. **Sensitive Content:** Are there shoots or clients whose photos must never be processed outside your machine?
17. **Your Curated Album:** Could you provide your own hand-selected album for a sample set so we can measure how closely our selection matches yours? *(This becomes our ground truth.)* `[TO VALIDATE]`
18. **Milestones:** For on-site coverage, what are the "must-capture" moments a field photographer should confirm before leaving a venue?

---

### Section 5: Endorsement Close
19. **Interest:** Would a tool that screens blur/blinks locally, lets you search a shoot in plain language, and proposes a balanced album under your size limit be useful — or does your current process already cover this?
20. **Commitment:** If this fits your need, will you:
    - let us interview/observe and review de-identified sample shoots,
    - provide a baseline cull time and your own selected album for a 120-shot set,
    - **sign an endorsement + photo-use consent letter** for our capstone?
21. **Scope Guard:** If they ask for extras (cloud sync, RAW editing, iOS, live tethering): *"Noted — we will log that as future work; our current version must stay small enough to deliver and evaluate honestly."*

---

### After the interview
- Convert answers: `[TO VALIDATE]` → `VERIFIED` / `REPORTED (client)` in the Context Pack evidence table.
- Save de-identified artifacts (sample album, baseline time) under `LensCull/evidence/`.
- If Gate 0 succeeds: draft the endorsement letter from `Client_Endorsement_Letter_Template.md` with the partner's exact name and signatory.
- Capture the baseline before running the proof of concept, so the 120-shot benchmark has a real "before" number.
