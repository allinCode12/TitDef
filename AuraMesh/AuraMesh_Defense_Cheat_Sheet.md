# AuraMesh Defense Cheat Sheet

**Proposed Working Title:**
*AuraMesh: A Localized Pedestrian Isochrone Search Coordination and Computer Vision-Assisted Sighting Triage System for Vulnerable Missing Persons*
*(Client Partner: none yet — a barangay / DRRM office is the target `[TO VALIDATE]`)*

---

## 1. 30-Second Elevator Pitch
> *"Community searches for missing vulnerable persons — wandering children and elderly people with dementia — are often slow to start and badly distributed. People spread out without a shared map, and officers get flooded with unverified photos where real leads get lost. AuraMesh turns the last-seen location into time-based pedestrian search zones, dispatches tanods and verified responders to specific zones, and uses privacy-preserving computer vision to score volunteer sighting photos against the missing person's profile — so the team covers the right area first and sees the most likely leads first."*

---

## 2. The Golden Defense Rules for this Title

1. **Say up front that there is no client yet.** Do not pretend a barangay "wants this" or "will provide data." The target partner is a hypothesis until an endorsement letter is signed.
2. **Admit the client-instrumentation risk first (Module 1 ethics).** Barangays are hard to instrument; the team has dropped barangay-dependent ideas before. Owning this is stronger than hiding it.
3. **Never invent incident numbers or response times.** Use `[TO VALIDATE]` for every metric. State what you will measure during the preliminary investigation.
4. **Never overclaim the algorithm.** Isochrone modeling is a **computation, not a strong optimizer**. Offer coverage optimization / set covering as the stronger framing, or delimit it honestly. This is the title's weakest facet — do not defend it as if it were strong.
5. **Lead with privacy, not features.** Faces of missing persons and minors plus crowd photos are sensitive data. "Privacy-preserving" must be concrete: no public face database, one consented profile, retention limits, access logs, RA 10173.
6. **Do not let "monitoring system" stick.** The map is an output; the system is zones + dispatch + triage.
7. **Respect scope (don't let the panel expand it):** NO law-enforcement replacement, NO public face database, NO mass CCTV, NO live GPS body-tracking.

---

## 3. High-Frequency Panel Questions & Winning Answers

| Panel Question | Best Defensible Answer | Course Traceability |
|---|---|---|
| **Do you have a client?** | "Not yet. A barangay or DRRM office is our target partner, and securing a real, engaged one is our top open risk. We disclose that the problem is a hypothesis until a partner confirms it." | Module 1: Ethics / reporting confidence |
| **Isn't this just a monitoring dashboard?** | "No. The product is search-zone generation, targeted dispatch, and sighting triage. The coverage map is an output of that logic, not the system itself." | Module 1: Root cause vs. symptom · Module 4: Process modeling |
| **What is the algorithm?** | "Honestly, isochrone modeling is a spatial computation, not a strong optimization algorithm. Our stronger framing is isochrone-based coverage optimization or a set-covering search-area model. We flag the algorithm facet as the weakest part of this title." | Module 4: Algorithm transparency |
| **Aren't you claiming isochrones are an algorithm when they're just GIS math?** | "That is a fair critique. An isochrone is a computation on a walkable network. To make the algorithmic contribution defensible, we are considering a coverage-optimization or set-covering formulation that selects which zones to assign under a responder-time budget — otherwise we delimit the step honestly." | Module 4: Modeling honesty |
| **Where does the AI fit?** | "Privacy-preserving computer vision feature extraction that scores volunteer sighting photos against a single missing person's profile, ranked for an officer to verify. It never auto-declares a match." | Module 4: Rules + Module 3: Evaluation |
| **Isn't that facial recognition? Isn't that dangerous?** | "It is not a public face database or mass surveillance. It matches volunteer-submitted photos against one consented profile, with retention limits and access logs. The DPA handling plan is a blocking requirement, not an afterthought." | Module 1: Ethics · Module 2: Legal feasibility |
| **How do you handle minors' and vulnerable persons' data?** | "It is our highest-risk item. It requires explicit consent/legal basis, minimal data, and a retention policy before any real use — so evaluation uses simulated scenarios, not live cases." | Module 2: Legal & ethical · NFR privacy |
| **How is this different from a Facebook post or a megaphone?** | "Those are broadcasts. AuraMesh assigns specific zones to specific responders and triages the sightings that come back — it removes the overlap and the clutter." | Module 1: Root cause |
| **Why not use an existing GIS or SAR tool?** | "Professional SAR/GIS tools assume trained operators and budgets a barangay does not have. AuraMesh targets barangay-level officers and tanods." | Module 2: Operational & economic feasibility |
| **Where does the pedestrian map data come from?** | "A walkable road/path network for the target area, such as OpenStreetMap data. Availability for the specific barangay is `[TO VALIDATE]`." | Module 2: Technical feasibility |
| **How do you evaluate without live incidents?** | "Simulated incident scenarios with known ground truth. We measure dispatch time, coverage completeness, and triage precision/recall." | Module 3: Quality model & evaluation |
| **Does this replace the police or SAR teams?** | "No. It is community-level coordination only. It refers and hands off to authorities; it does not replace them." | Module 1: System boundary |
| **What if there's weak or no internet in the field?** | "Sighting submission retries and captures offline; alerts queue. Reliability is a stated non-functional requirement." | Module 2 & 3: NFR |
| **Could this collide with a barangay hazard-mapping title from another group?** | "Different scope — ours is search coordination for missing persons, not hazard mapping. We will confirm no overlap with the panel before pitching." | Module 1: Scope clarity |
| **Is this feasible in one term?** | "It is ambitious: two platforms plus GIS plus CV. We are managing that by limiting to one partner barangay, one mobility type, and simulated scenarios, and by phasing the build in hybrid sprints." | Module 2: Schedule feasibility |
| **Will you generalize it to other barangays?** | "Not claimed. It is built for one partner; other deployments would need their own preliminary investigation and reconfiguration." | Module 1: Boundaries · Module 2: New client = new analysis |

---

## 4. Key `[TO VALIDATE]` Items to Clear with a Future Partner

| Item | What to Ask / Validate |
|---|---|
| **Partner willingness** | Will a barangay or DRRM office formally partner, and can they sustain engagement through the term? |
| **Current search workflow** | Step by step, how is a missing-person alert raised and who responds today? |
| **Incident volume** | How many missing-person incidents occur per year in the area? (de-identified records) |
| **Responder pool & devices** | How many tanods / responders, and do they carry smartphones with data? |
| **Pedestrian map data** | Is there a usable walkable-network source for the target area? |
| **Consent & DPA** | What lawful basis/consent is required to handle faces and minors' data? |
| **Existing systems** | Is there already a DRRM or hazard-mapping system this could collide with or reuse? |
| **Dispatch & coverage rules** | How are responders currently assigned, and per-zone or per-radius? |

---

## 5. New High-Risk Panel Questions: Client and Scope

### Q1. "You have no client. How can you defend this title?"

> "We are being explicit: this is a solution hypothesis, not a proven problem. A barangay or DRRM office is our target partner, and securing one is the first risk we manage. We chose to disclose that up front instead of implying a partnership we do not have. If we cannot secure a partner, we would reconsider the title."

### Q2. "Barangays are notoriously hard to work with. Why should the panel believe you'll get data?"

> "That is exactly why it is our stated top risk. We have seen it before, and we are approaching multiple offices, asking for a signed endorsement and a DPA undertaking early, and planning to evaluate with simulated scenarios so we do not depend on live sensitive cases. If partner access is not secured by our milestone, we will adjust the scope."

### Q3. "Isn't this just a monitoring dashboard with a map?"

> "No. The core logic is: convert a last-seen point and mobility profile into ordered search zones, assign those zones to specific responders, and triage the sighting photos that come back. The coverage map is an output of those decisions, not the product."

---

## 6. The Algorithm Facet — Answer Carefully

### Q4. "Where is the algorithm in your system?"

> "We are honest about this: the isochrone modeling is a computation on a walkable network, not a strong optimization algorithm. To make the algorithmic contribution defensible, we are considering reframing it as isochrone-based coverage optimization or a set-covering search-area model — choosing the minimum set of zones/assignments that covers the highest-priority reachable area under a responder-time budget. If we do not commit to that, we delimit the step honestly and lean on the CV triage and analytics facets."

**Do not claim:** that an isochrone by itself is a strong capstone algorithm.

---

## 7. Privacy and Data Protection Defense

### Q5. "You're processing faces of missing persons, and possibly children. How is that legal?"

> "This is the highest-risk part of the project and we treat it as a blocking requirement. The design uses no public face database and no mass surveillance: volunteer-submitted photos are matched against one consented profile only, with minimal data, a defined retention period, and access logs, under RA 10173. We will not process real cases until a partner confirms a lawful basis and consent process."

### Q6. "Could this be abused for surveillance?"

> "The scope explicitly forbids it: no general-public biometric search, no CCTV ingestion, no live tracking. The only matching is a single consented missing-person profile against volunteered sightings, reviewed by an officer."

---

## 8. "Why Not Just Use a Group Chat / Facebook?"

### Q7. "If it's a small community, why not one group chat and a megaphone?"

> "Communication is not the same as coordinated coverage. A broadcast does not tell you which areas are already searched, who is responsible for what, or which of the forty photos is a real match. AuraMesh is structured coverage and triage, not just messaging. If a partner shows the manual process already handles coverage and triage well, we would reconsider the scope."

**Core distinction:**
**Broadcast = communication**
**AuraMesh = zones + dispatch + triage**

---

## 9. "Is Web + Mobile Overkill?"

### Q8. "Why not one responsive web app for everyone?"

> "That is a valid design decision we should validate. The reason we propose two interfaces is that officers command and coordinate, while tanods respond in the field and submit sightings from a phone. If research shows one responsive app serves both groups, that may be the better implementation — the specialization should not force unnecessary technology."

---

## 10. What You Must Validate Before the Defense

| Question | Why it matters |
|---|---|
| Is there a willing, sustainable partner? | Without one, the title weakens. |
| What is the current search workflow? | Establishes the as-is process and the real root cause. |
| How many incidents per year? | Establishes real volume vs. hypothetical need. |
| Who responds today, and with what devices? | Determines mobile feasibility and adoption. |
| Is walkable-network data available for the area? | Determines technical feasibility of isochrones. |
| What consent/legal basis applies? | Determines whether the CV facet is even legal. |
| Is there a competing barangay hazard-mapping title? | Determines collision risk. |
| Can you build a simulated-scenario evaluation set? | Determines whether triage accuracy can be measured. |

---

## 11. The "No Client" Defense in One Sentence

> **"Our proposal is a solution hypothesis, not a proven problem; a barangay or DRRM office is our target partner, we openly disclose that no partner is secured yet, and we will validate the workflow and data before claiming the system is necessary."**

---

## 12. The "Monitoring Dashboard" Defense in One Sentence

> **"The coverage map is an output; the system itself is the generation of pedestrian search zones, the assignment of responders to those zones, and the privacy-preserving triage of the sighting reports that come back."**

---

## 13. The "Weak Algorithm" Defense in One Sentence

> **"We do not oversell the isochrone step — it is a spatial computation; if we want a defensible algorithm facet we commit to a coverage-optimization or set-covering model, and otherwise we delimit it honestly and carry CV triage and analytics as the algorithmic weight."**

---

## 14. Red Flags: Claims You Should NOT Make Without Evidence

Avoid these statements unless primary evidence supports them:

- "The barangay wants this system."
- "The barangay will give us data."
- "There are X missing-person cases per year."
- "Alerts currently take X minutes to go out."
- "Tanods all have smartphones and data."
- "The isochrone model is a strong optimization algorithm."
- "The system will find missing people."
- "The face-matching is fully accurate."
- "This will replace the police or SAR teams."
- "Residents will stop spamming alerts because of our app."
- "This works for every barangay."
- "The DPA issue is already solved."

Use `[TO VALIDATE]` where appropriate.

---

## 15. Defense Mindset

The goal is **not to convince the panel that AuraMesh must exist no matter what**.

The goal is to demonstrate:

1. We identified a real, high-stakes process (community search for vulnerable persons).
2. We identified a plausible problem (delayed, uneven coverage and untriaged sightings).
3. We have a proposed solution (zones + dispatch + triage).
4. We know the biggest unknowns — no client, high DPA risk, weak algorithm facet.
5. We have a plan to validate them (partner search, interviews, simulated scenarios).
6. We will adjust or drop the scope if the evidence does not support it.

### Strong closing statement

> **"Our proposal is a solution hypothesis, not a claim that the problem is proven. Our first step is to secure a barangay or DRRM partner and a data-protection undertaking. The next step is to validate the real search workflow, incident volume, responder capability, and map-data availability. If those findings support the problem, we proceed — with zones, dispatch, and privacy-preserving triage. If they reveal a different or smaller problem, or a blocking legal issue, we adjust the scope or the title."**

---

## 16. Evidence Status Reminder

The project context currently identifies these as **pending validation** (no client, no data):

- A partner barangay / DRRM office
- The current search workflow
- Incident volume and typical response patterns
- Number of responders / tanods and their devices
- Availability of pedestrian network data
- Consent / DPA requirements for faces and minors
- Whether a barangay hazard-mapping title collides with this one

**Do not convert any of these into facts in the defense until partner evidence confirms them.**
