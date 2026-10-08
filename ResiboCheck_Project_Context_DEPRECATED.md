# ⚠️ DEPRECATED — ResiboCheck Project Context Pack

> **STATUS: DEPRECATED — DO NOT USE AS A SOURCE OF TRUTH.**
> This title was **rejected by the course advisor/panel**. The team's feedback loop was: *rejected → advised to secure a real client → pivoted to CrewSync (Kiddie Salon by Nail Brat)*, with the AlumniTrack direction also suggested by the advisor afterward.
> This file is retained **only as a rejection trace / history record**. The live projects live in `CrewSync/` and `AlumniTrack/`.

> **Purpose of this file (historical):** This was the single source of truth for the ResiboCheck capstone title during its proposal stage.

---

## 0. Rules for any agent or collaborator using this file

1. **Do not invent evidence.** No interviews, observations, or shop data have been collected yet. Never state a shop's payment volume, tallying time, error rate, or any pain point as fact. Use `[TO VALIDATE]` placeholders.
2. **Only cite the sources in Section 14.** If a new statistic is needed, it must come from a real, checkable source.
3. **Respect the scope (Section 6).** Do not add POS, menu, inventory, payment processing, customer app, multi-branch, or AI fake-detection features.
4. **Framing rule:** The primary pitch is *payment recording and reconciliation*. Fraud/fake-screenshot detection is a **secondary** point, raised only when the panel asks why matching matters (Section 12).
5. **No customer app.** Only the shop (cashier + owner) uses the system.
6. **Keep the course lessons traceable (Section 9).** Every design choice should map back to an IT0037 module concept.
7. The actual defense, oral checks, quizzes, and exams are **AI-use prohibited** under the course policy. The presenter must understand and own every claim.

---

## 1. Project identity

| Field | Value |
|---|---|
| **Title** | ResiboCheck: A Web and Mobile E-Wallet Payment Recording and Reconciliation System for Small Food Businesses |
| **Short name** | ResiboCheck |
| **Specialization** | BSIT — Web and Mobile Application |
| **School / course** | FEU Diliman · IT0037 Systems Analysis and Design (title-defense semester) |
| **Target setting** | Small food businesses (milk tea shops, canteens, small food stalls) receiving GCash payments |
| **Users** | Cashier (mobile app), Owner/Admin (web admin panel) |
| **Not a user** | Customers — they pay with GCash as usual and show their screenshot |
| **End-state of capstone** | Working system + IEEE-format paper + exhibit/judging at TICaP (joint FEU Tech x FEU Diliman capstone showcase; judged on technicality, creativity, impact) |

### One-line pitch
Small food shops accept GCash screenshots as proof of payment, but those records end up scattered across phones. ResiboCheck records each e-wallet payment at the counter and matches it against the shop's official GCash transaction history.

### Poll / abstract description
Small food shops receive many GCash payments daily, but proof of payment ends up as screenshots scattered across phones, making end-of-day tallying slow and error-prone. With ResiboCheck, the cashier records each e-wallet payment by snapping the customer's screenshot, with no app needed for customers. The owner's dashboard organizes these records, matches them against the shop's official GCash transaction history, and exports clean CSV reports.

### Title breakdown (Module 1: four title elements)

| Element | In the title |
|---|---|
| Capability | E-Wallet Payment Recording and Reconciliation System |
| Users / setting | Small Food Businesses |
| Value / problem direction | Recording + reconciliation (organized records, confirmed payments) |
| Specialization differentiator | Web and Mobile (cashier mobile capture + owner web dashboard) |

---

## 2. Problem framing

### Symptom vs. root cause (Module 1)
- **Symptoms (hypothesized, to validate):** screenshots scattered across phones/galleries; slow, manual end-of-day tallying; mismatched totals; uncertainty whether every e-wallet payment actually arrived.
- **Root cause (working hypothesis):** e-wallet payments have **no structured record at the point of sale**, so the shop cannot reconcile what it was *told* it received (the screenshot) against what it *actually* received (official GCash history).

### Problem statement (draft)
Small food businesses that accept GCash payments commonly rely on customer screenshots as proof of payment `[TO VALIDATE with partner shop]`. Because these payments are not recorded in a structured way at the point of sale, owners must tally and verify them manually against their GCash history `[TO VALIDATE]`, which is slow and error-prone. There is no simple, low-cost tool for micro food businesses to record e-wallet payments at the counter and reconcile them with official transaction records.

### Evidence status

| Evidence | Status |
|---|---|
| National shift to digital payments (BSP) | ✅ Secondary, sourced |
| Screenshots are not reliable proof of payment (GCash advisory) | ✅ Secondary, sourced |
| Official GCash history can be exported (CSV for GCash for Business; emailed PDF for personal) | ✅ Secondary, sourced |
| Partner shop's payment mix (cash vs. e-wallet) | ❌ Pending |
| Partner shop's current tallying workflow and time | ❌ Pending |
| Partner shop's GCash account type (personal vs. business) | ❌ Pending |
| Partner shop's interest/endorsement | ❌ Pending |

### Stakeholders (Module 3)

| Stakeholder | Role / lens | Interest |
|---|---|---|
| Shop owner | Process owner, approver, admin user | Accurate totals, confirmed payments, less tallying time |
| Cashier(s) | Direct user (mobile) | Fast recording without slowing service |
| Customers | Indirectly affected (not users) | No extra steps; privacy of their name/number on screenshots |
| GCash (G-Xchange) | External data source (via exported file only) | — (no integration) |
| Adviser / panel | Governance | Evidence quality, scope, feasibility |

---

## 3. Background research (secondary evidence)

All figures below are from Section 14 sources. Use the exact framing given.

- **Digital payments are now the majority of retail volume nationally.** BSP: digital payments were **64.7%** of total retail payment volume in **2025**, up from **57.4%** in 2024. Cash and other non-digital methods were still **more than one-third** of retail payment activity.
  - ⚠️ Caveat to state: this is *all retail nationwide*, not small food shops specifically. It shows a trend, not the partner shop's reality.
- **QR Ph overtook cards.** BSP: QR Ph transactions exceeded debit and credit card transactions for the first time in 2025 (2.47 billion QR Ph transactions).
- **Screenshots are not proof that money arrived.** GCash (July 2025 advisory) warns of AI-generated fake receipts and advises verifying the reference number, sender's name, amount, and timestamp in the **Transactions** tab, not relying on screenshots. *(Secondary point — use only when asked.)*
- **It still happens.** May 2026 report: a Baguio store detected a fake GCash screenshot for P11,874 because the fonts and alignment looked wrong. *(Secondary point.)*
- **Official records are exportable.**
  - GCash for Business: dashboard has Export / Download CSV for transaction history.
  - Personal GCash: "Request transaction history" sends a password-protected PDF by email; it lists reference number, description, date, time, debit, credit, balance. A developer notes transactions may take ~24 hours to appear in the export.
- **Most Philippine businesses are micro enterprises.** 2024: 99.63% of registered establishments are MSMEs; 2022: micro enterprises were 90.49%. Micro = PHP 3,000,000 or less in assets and 1–9 employees.
- **Small businesses are only partially digital.** A digital readiness study found most started digitalizing through social media (e.g., Facebook) but need more skills to use digital platforms well.

### Related systems / alternatives (for "What's new?")

| Alternative | What it does | Gap ResiboCheck fills |
|---|---|---|
| Manual checking in GCash app | Owner scrolls Transactions tab | No link to sales; slow; no reports |
| GCash for Business dashboard | Merchant transaction history + CSV | Not linked to the shop's own sales records; many micro shops use personal GCash `[TO VALIDATE]` |
| Payment gateways / payment links (e.g., PayMongo) | Customer pays via link; auto-marked paid | Fees and setup; not how walk-in counter payments to static QR/personal GCash work |
| Full POS systems | Sales, menu, inventory | Heavy and costly for micro shops; usually no screenshot-to-official-history reconciliation `[verify any specific POS claim before stating]` |
| Spreadsheets / notebooks | Manual tally | Error-prone; no matching |

**Differentiator:** structured capture at the counter + automatic matching against the official GCash history + clean CSV export, built for micro food shops.

---

## 4. Objectives

### General objective
To develop a web and mobile e-wallet payment recording and reconciliation system that helps small food businesses record e-wallet payments at the point of sale and verify them against official GCash transaction records.

### Specific objectives (draft — targets to validate)
1. Develop a mobile app for cashiers to record sales and capture e-wallet payment screenshots, with automatic extraction of reference number, amount, and time.
2. Develop a web admin panel for the owner to import official GCash transaction history (CSV) and automatically match it against recorded payments.
3. Provide discrepancy listing and resolution, daily/weekly reports, and CSV export.
4. Implement role-based access, an activity log, and screenshot retention controls consistent with RA 10173.
5. Evaluate the system with the owner and cashiers using selected ISO/IEC 25010 quality characteristics, and compare end-of-day reconciliation time before and after use `[baseline TO VALIDATE]`.

### Success measures (fill after data gathering)

| Indicator | Baseline | Target | Source |
|---|---|---|---|
| End-of-day reconciliation time | `[TO VALIDATE]` | `[set after baseline]` | Timed observation |
| % of e-wallet payments recorded in system | — | `[set]` | System records vs. official history |
| Unmatched payments resolved with a reason | — | `[set]` | Discrepancy log |
| ISO/IEC 25010 survey weighted mean | — | `[set]` | Likert survey |

---

## 5. How the system works

1. **At the counter (cashier app):** record sale → choose payment method → if e-wallet, snap/upload customer screenshot → OCR extracts reference no., amount, time → cashier confirms or corrects → saved as **Pending**. Instant duplicate check warns if the reference number was already recorded.
2. **End of day (owner panel):** import official GCash transaction history file.
3. **Auto-match:** match by reference number; confirm amount and time are within a tolerance window `[window TO VALIDATE]`.
4. **Flag:** unmatched records become discrepancies with amount, time, cashier, and screenshot (if still retained).
5. **Resolve:** owner marks each discrepancy (Late Posting / Data-Entry Error / Confirmed Fake / Other + note).
6. **Report & export:** daily/weekly totals by payment method, discrepancy summary, CSV export.

---

## 6. Scope and limitations

### In scope
- Cashier mobile app (PWA): login, record sale, capture screenshot, OCR extraction, manual correction, duplicate reference warning, view own records' status
- Owner web admin panel: CSV import of official GCash history, automatic matching, discrepancy list and resolution, dashboard, reports, CSV export, cashier account management, activity log, screenshot retention setting
- Database for users, sales, payment records, proofs, imports, official transactions, discrepancies, logs
- GCash as the supported e-wallet

### Limitations / delimitations

| Item | Reason |
|---|---|
| No direct GCash API connection | Relies on official exported files; no assumed API access |
| No payment processing | Records and verifies only; does not move money |
| No AI-based fake-image detection | Unsupported claim; matching against official records is the verification method |
| Personal GCash reconciliation is end-of-day, not instant | Export delay for personal transaction history |
| No full POS, menu, or inventory | Separate system; scope control |
| No customer app | Customers already use GCash |
| GCash only | Maya and bank transfers are future work |
| Single branch | Fits micro enterprises |
| Personal GCash PDF import is optional (Could) | File is password-protected; parsing is fragile |
| Evaluation limited to one partner shop | Results not generalized to all food businesses |

> Check the school template: "Scope and Delimitation" (boundaries chosen) vs. "Limitations" (constraints outside your control). Split the table if required.

---

## 7. Requirements (draft — validate with partner shop)

### 7.1 Cashier app (mobile PWA)

| ID | Requirement | Priority | Acceptance criteria |
|---|---|---|---|
| APP-01 | Cashier logs in with own account | Must | Each recorded payment shows which cashier recorded it |
| APP-02 | Record sale with amount and payment method (cash / e-wallet) | Must | Sale saved with timestamp; e-wallet requires payment proof |
| APP-03 | Capture or upload payment screenshot | Must | Accepts camera photo or gallery image |
| APP-04 | Extract reference number, amount, time via OCR | Must | Extracted fields shown for confirmation before saving |
| APP-05 | Manual correction of extracted fields | Must | Edited fields flagged as "manually corrected" |
| APP-06 | Instant duplicate reference-number check | Must | Warning shown before saving if reference already exists |
| APP-07 | View own payments' status (Pending/Matched/Flagged) | Should | Cashier sees own records for the day |
| APP-08 | Offline queue with later sync | Could | Offline records upload automatically when online |

### 7.2 Owner admin panel (web)

| ID | Requirement | Priority | Acceptance criteria |
|---|---|---|---|
| ADM-01 | Admin role login | Must | Only admin can import, match, manage users |
| ADM-02 | Import official history (CSV) | Must | Valid file loaded; invalid format rejected with error |
| ADM-03 | Import personal GCash history PDF | Could | Parsed rows behave like CSV imports |
| ADM-04 | Automatic matching | Must | Match on reference no.; amount and time within tolerance |
| ADM-05 | Discrepancy list | Must | Shows amount, time, cashier, screenshot (if retained) |
| ADM-06 | Resolve discrepancy with reason | Must | Reason + note saved and logged |
| ADM-07 | Dashboard of daily totals and discrepancies | Should | Totals equal underlying records for selected date |
| ADM-08 | CSV export | Must | Respects date range and filters |
| ADM-09 | Manage cashier accounts | Must | Deactivated users cannot log in; past records kept |
| ADM-10 | Activity log | Should | Who did what, when |
| ADM-11 | Screenshot retention setting | Should | Images auto-deleted after set period; extracted fields kept |

### 7.3 Non-functional (ISO/IEC 25010 — selected)

| ID | Characteristic | Requirement |
|---|---|---|
| NFR-01 | Performance efficiency | OCR result within `[X]` seconds on a mid-range phone |
| NFR-02 | Security | Role-based access; hashed passwords; HTTPS for all traffic |
| NFR-03 | Security / privacy | Long-term storage limited to reference no., amount, time; screenshots deleted per retention; aligned with RA 10173 |
| NFR-04 | Usability (interaction capability) | New cashier can record an e-wallet payment after `[N]` minutes of training |
| NFR-05 | Reliability | Imports are all-or-nothing (no partial data on failure) |

### 7.4 Deliberately excluded (Won't, this version)
AI fake-image detection · direct GCash API · payment processing · POS/menu/inventory · customer app · multi-branch · multi-wallet

---

## 8. Data model and behavior

### 8.1 Entities (logical — Module 4: meaning before implementation)

| Entity | Key attributes |
|---|---|
| User | user_id, name, role (Admin/Cashier), status, created_at |
| Sale | sale_id, user_id, amount, payment_method, recorded_at |
| PaymentRecord | payment_id, sale_id, reference_no, amount, paid_at, manually_corrected, status |
| PaymentProof | proof_id, payment_id, image_path, delete_after |
| ImportBatch | batch_id, user_id, file_name, imported_at, row_count |
| OfficialTransaction | txn_id, batch_id, reference_no, amount, txn_time |
| Discrepancy | discrepancy_id, payment_id, resolution, note, resolved_by, resolved_at |
| ActivityLog | log_id, user_id, action, target, timestamp |

### 8.2 Relationships
- User 1—* Sale
- Sale 1—0..1 PaymentRecord (e-wallet sales only)
- PaymentRecord 1—0..1 PaymentProof
- ImportBatch 1—* OfficialTransaction
- PaymentRecord 0..1—0..1 OfficialTransaction (match)
- PaymentRecord 1—0..1 Discrepancy (when unmatched)
- User 1—* ActivityLog

### 8.3 Business rules
- BR-01: An e-wallet sale must have a PaymentRecord.
- BR-02: A reference number may be matched to only one PaymentRecord.
- BR-03: Match = same reference no. AND amount equal AND time within tolerance `[TO VALIDATE]`.
- BR-04: Only Admin may resolve discrepancies or import files.
- BR-05: Screenshot images are deleted after the retention period; extracted fields remain.

### 8.4 PaymentRecord state model
```
Pending ──(match found on import)──► Matched
Pending ──(no match after import)──► Flagged ──(owner resolves)──► Resolved
                                       Resolved reasons: Late Posting | Data-Entry Error | Confirmed Fake | Other
```
Blocked transitions: Flagged → Matched without a re-import that produces a match; Resolved → Pending.

---

## 9. IT0037 lessons mapped to ResiboCheck

### Module 1 — Systems Analysis Fundamentals
| Concept | Application |
|---|---|
| Symptom vs. root cause | Scattered screenshots = symptom; no structured point-of-sale record = root cause |
| Evidence triangulation | Plan: interview + observation + document review (GCash history vs. screenshots) |
| Four title elements | See Section 1 |
| Avoid unsupported AI claims | OCR assists only; no AI fake detection claim |
| Tailored/hybrid approach (not "use everything") | Prototyping (cashier screens) + Agile sprints (build) + stage gates (approvals) — each part solves a specific condition |

### Shelly Ch. 2 — Systems Planning
| Concept | Application |
|---|---|
| Business case | Justify by time saved in reconciliation and confirmed payments `[quantify after data gathering]` |
| Reasons for systems projects | Better performance, more information, stronger controls |
| Preliminary investigation (6 steps) | 1 Understand problem → 2 Define scope/constraints → 3 Fact-finding → 4 Evaluate feasibility → 5 Estimate time/cost → 6 Present to management |
| Discretionary vs. nondiscretionary | Discretionary → must justify with economic/operational value |
| Fishbone / Pareto | Fishbone for causes of reconciliation errors; Pareto once shop data exists |
| Constraint types | Mandatory: RA 10173 compliance; External: GCash export format and delay |
| Tangible vs. intangible benefits | Tangible: reconciliation time; intangible: owner confidence, cashier accountability |

### Bender — SDLC
| Concept | Application |
|---|---|
| SDLC objectives (quality, management control, productivity) | Stage gates give the owner/adviser control |
| Stepwise commitment | Commit to build only after data gathering confirms the problem and GCash file format |
| Change control (time, function, resources, quality) | Feature requests (e.g., POS) handled as scope changes, not silently added |

### Module 2 — Initiation, Lifecycle, Feasibility (six dimensions)
| Dimension | Preliminary view | Condition / unknown |
|---|---|---|
| Technical | Feasible: PWA + web panel + relational DB + OCR are standard | OCR accuracy on real screenshots `[test]`; CSV format of partner's account `[confirm]` |
| Operational | Conditional | Cashier must capture screenshot without slowing service `[observe]` |
| Economic | Conditional | Hosting + OCR service costs `[estimate ranges in PHP]` |
| Schedule | Conditional | Depends on team skills and remaining term |
| Security | Conditional | Role-based access, HTTPS, hashed passwords, activity log |
| Legal and ethical | Conditional | RA 10173: minimal data, retention, counter notice `[confirm with adviser]` |

**Assumptions register (validate during data gathering)**

| # | Assumption | Validation action |
|---|---|---|
| A1 | Partner shop receives enough daily e-wallet payments for manual tallying to be a burden | Record payment mix for 1–2 weeks |
| A2 | Shop uses personal GCash or static QR (not a full gateway) | Ask owner |
| A3 | Official history can be exported in a usable format for that account | Owner exports a sample (de-identified) |
| A4 | Cashiers can capture a screenshot in a few seconds | Observe a shift |
| A5 | OCR reads GCash receipts reliably | Test on de-identified sample screenshots |

**Key risks (cause → event → impact)**

| Risk | Response |
|---|---|
| GCash changes export format → import fails → reconciliation stops | Isolate parser; manual column mapping fallback |
| OCR misreads → wrong data saved → false flags | Mandatory cashier confirmation; correction flag |
| Personal export delay → late matches → false discrepancies | "Late Posting" resolution; re-import support |
| Cashiers skip recording during rush → incomplete records | Simple one-screen flow; owner sees unrecorded official transactions in reports |
| Screenshots store customer data → privacy breach | Retention deletion; minimal fields; role-based access |

### Module 3 — Requirements
| Concept | Application |
|---|---|
| Stakeholder lenses | Section 2 table |
| Elicitation | Interview owner + cashiers; observation; document review; short questionnaire |
| Claim classification | Mark items as evidence / assumption / requirement / constraint |
| Testable requirements | Section 7 acceptance criteria |
| MoSCoW | Section 7 priorities |
| ISO/IEC 25010:2023 | Section 7.3 + evaluation instrument |
| Requirements traceability (RTM) | Link each requirement → stakeholder need → evidence → test |

### Module 4 — Structured and OO Modeling
**Context diagram (Level 0 boundary)**
- External entities: **Cashier**, **Owner/Admin**, **GCash transaction history file** (data source via owner import — no direct connection), **OCR service** (only if a cloud OCR is used).
- Customer is **not** an external entity of the system: the customer interacts with the cashier, not the system.

**Level 0 DFD processes**
1.0 Manage Users · 2.0 Record Sale and Payment · 3.0 Extract Payment Details · 4.0 Import Official Transactions · 5.0 Reconcile Payments · 6.0 Resolve Discrepancies · 7.0 Generate Reports and Exports

**Data stores**
D1 Users · D2 Sales · D3 Payment Records · D4 Payment Proofs · D5 Official Transactions · D6 Discrepancies · D7 Activity Log

**Use cases**
Cashier: Record E-Wallet Payment · Correct Extracted Details · View Own Records
Owner: Import Transaction History · Run Reconciliation · Resolve Discrepancy · Export Report · Manage Cashier Accounts · Set Retention Period

**Key sequence (Record E-Wallet Payment)**
Cashier → App: enter sale, choose e-wallet → App: capture image → OCR: extract fields → App: show fields → Cashier: confirm/correct → App → DB: duplicate check → DB: save PaymentRecord (Pending) + PaymentProof → App: confirmation

**State diagram:** Section 8.4
**ERD:** Section 8.1–8.2
**Cross-model consistency checks:** every DFD data store maps to an ERD entity; every use case maps to at least one requirement; every state in 8.4 is reachable by a process in the DFD.

---

## 10. Development approach and evaluation

- **Approach:** Hybrid — prototyping (validate cashier screens with owner/cashiers), Agile sprints (build), stage gates (proposal approval → design approval → test/pilot approval).
- **Pilot:** run alongside the shop's current method for a short period before relying on it.
- **Evaluation:** Likert-scale survey of owner and cashiers on selected ISO/IEC 25010 characteristics (functional suitability, interaction capability/usability, reliability, security), reported as weighted mean; plus before/after reconciliation time if the shop allows.

### Suggested technical stack (NOT decided — pick based on team skills)
- Frontend: PWA (e.g., React/Vue or similar) for cashier app; same codebase or separate web app for admin panel
- Backend: REST API (e.g., Node.js/Express, Laravel, or Django)
- Database: relational (e.g., PostgreSQL or MySQL)
- OCR: on-device/open-source (e.g., Tesseract) or a cloud OCR service — trade-off: cost and privacy vs. accuracy
- Hosting: low-cost cloud or student-tier hosting `[cost TO VALIDATE in PHP]`

---

## 11. Data gathering plan (replaces interviews for mock defense)

| Method | Participants | Purpose | Target date |
|---|---|---|---|
| Interview | Owner, 1–2 cashiers | Confirm workflow, pain points, account type | `[set]` |
| Observation | One busy shift | Time to record payments; end-of-day tallying process | `[set]` |
| Document review | De-identified screenshots + official GCash history sample | OCR test; file format check | `[set]` |
| Payment mix log | 1–2 weeks of sales | Cash vs. e-wallet share | `[set]` |
| Questionnaire | Owner + cashiers | Baseline satisfaction and effort | `[set]` |

**Honest answer if asked "Who confirmed this problem?":** "Our problem is currently grounded in secondary data from the BSP and GCash's own guidance. Primary data gathering with a partner shop is scheduled per this plan, and our problem statement will be revised against it."

---

## 12. Defense Q&A bank (condensed)

| Question | Answer |
|---|---|
| How are you sure most payments are online? | We don't claim that for the shop yet. Nationally, BSP reports 64.7% of retail volume was digital in 2025, but that's all retail, not food shops. We'll log the partner shop's payment mix. The system only needs enough daily e-wallet payments to make manual tallying a burden. |
| Problem or symptom? | Scattered screenshots are the symptom; no structured point-of-sale record is the root cause. |
| What's new? | Matching each recorded payment against the official GCash history — not just storing records. |
| Why not GCash for Business or a POS? | Many micro shops use personal GCash/static QR without a full POS `[validate]`. ResiboCheck targets that group. |
| Direct GCash connection? | No. Owner imports the official history file. |
| OCR errors? | Cashier confirms/corrects before saving; corrections are flagged. |
| Real-time? | Not for personal accounts (export delay) — end-of-day reconciliation. Stated as a limitation. |
| Privacy? | Store only reference no., amount, time; delete screenshots after retention; role-based access; RA 10173. |
| Customer consent? | Customers already show screenshots voluntarily; add a counter notice; confirm approach with adviser. |
| *(Secondary)* Why does matching matter? | A screenshot is not proof money arrived; GCash itself advises verifying in the Transactions tab. |
| *(Secondary)* Can it catch fakes? | Indirectly — unmatched payments are flagged for review. No AI detection claimed. |
| Methodology? | Hybrid: prototyping + Agile + stage gates (stepwise commitment). |
| Evaluation? | ISO/IEC 25010 Likert survey + before/after reconciliation time. |
| Out of scope? | Payment processing, API, AI detection, POS, customer app, multi-branch. |

---

## 13. Mock defense deck outline

| # | Slide | Content source |
|---|---|---|
| 1 | Title + four-element breakdown | §1 |
| 2 | Background: digital payment shift + micro enterprises | §3 |
| 3 | Current workflow (hypothesized) + evidence status | §2, §11 |
| 4 | Problem: symptom vs. root cause (fishbone) | §2 |
| 5 | Objectives (general + specific) | §4 |
| 6 | How it works (flow diagram) | §5 |
| 7 | Related systems + differentiator | §3 |
| 8 | Scope and limitations | §6 |
| 9 | Context diagram + key requirements | §7, §9 (Module 4) |
| 10 | Methodology + evaluation | §10 |
| 11 | Feasibility (six dimensions) + key risks | §9 (Module 2) |
| 12 | Data gathering plan + next steps | §11 |

---

## 14. Sources (verified during research)

- BSP 2025 digital payments share (64.7%), QR Ph surpassing cards — Manila Bulletin, Aug 17, 2026: https://mb.com.ph/2026/08/17/digital-payments-hit-647-of-philippine-retail-transactions-nearing-bsps-70-target
- BSP 2025 share; cash still >1/3 of retail activity — Daily Tribune, Aug 19, 2026: https://tribune.net.ph/2026/08/19/bsp-digital-payments-account-for-nearly-two-thirds-of-retail-volume
- BSP 2024 share (57.4% volume, 59% value) — Manila Times, Jul 8, 2025: https://www.manilatimes.net/2025/07/08/business/top-business/digital-payments-use-up-in-2024-bsp/2144869
- GCash advisory on AI-generated fake receipts — Mynt newsroom, Jul 14, 2025: https://mynt.com.ph/newsroom/gcash-warns-public-on-emerging-ai-generated-fake-receipts-scams-urges-users-to-always-check-transactions-tab
- Fake GCash screenshot incident, Baguio — PhilNews, May 14, 2026: https://philnews.ph/2026/05/14/business-owner-warns-others-about-fake-gcash-payment-screenshot-scam
- Payment screenshot risk for sellers — PayMongo blog: https://www.paymongo.com/blog/how-to-prevent-payment-scams-philippines
- GCash for Business transaction history CSV export — GCash Help Center: https://help.gcash.com/hc/en-us/articles/48457463083545-How-do-I-review-and-download-my-GCash-for-Business-Transaction-History
- Personal GCash transaction history request (emailed PDF) — GCash Help Center: https://help.gcash.com/hc/en-us/articles/360034155433-View-and-download-your-Transaction-history
- Transaction history fields (ref no., date, time, debit, credit, balance) — ListPH: https://www.listph.com/2021/02/see-your-complete-gcash-transactions-history.html
- ~24h availability note for exports — GitHub (joshuactk): https://github.com/joshuactk/GCash-Transaction-History-Extraction
- 2024 Philippine MSME statistics — DTI (via search results; cite DTI MSME Statistics page)
- Micro enterprise share 2022 and definition — DTI MSME statistics (via search results)
- TICaP showcase (joint FEU Tech x FEU Diliman; judged on technicality, creativity, impact) — FEU Tech / TICaP public pages

> Before final submission, open each source and re-confirm the figure, date, and wording. Format citations in IEEE style for the paper.

---

## 15. Open items / next steps

- [ ] Find and secure a partner food shop (endorsement letter)
- [ ] Confirm GCash account type and export format with the shop
- [ ] Collect de-identified sample screenshots for OCR testing
- [ ] Log payment mix and time end-of-day tallying (baseline)
- [ ] Replace every `[TO VALIDATE]` with evidence or keep it labeled as an assumption
- [ ] Decide tech stack based on team skills
- [ ] Draft context diagram, Level 0 DFD, ERD, and state diagram (Module 4)
