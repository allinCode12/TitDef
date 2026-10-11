# Capstone Project Title Proposal — Title 2 (AlumniTrack) — Paste-Ready Fill

**Form:** FEU Institute of Technology · College of Computer Studies · Capstone Project Title Proposal (System Analysis and Design)
**Program:** Bachelor of Science in Information Technology, specialization in Web and Mobile Application
**Group:** AzTech (Group 6) · **Members:** Canido, Felix Jed; Mesina, Patrick Kyle; Borromeo, Zire Niccolai; Oronico, Lee Justin
**Term:** [x] 1st · Academic Year: 2026–2027
**Proposed Project Title 2:** AlumniTrack: An AI-Assisted Web and Mobile Platform for Alumni Career Tracking, Job Placement Timeline Analytics, and Skill-to-Market Gap Analysis

> **Status:** Gate 0 — no institutional client secured yet. Do not present as client-backed. Paste each field directly into the form.

---

### 1.0 Area of Investigation

Analysis, design, and implementation of an institutional graduate tracer and longitudinal career progression analytics platform. The study addresses low survey response rates, manual accreditation data aggregation, automated natural language skill extraction from job listings, vector-based curriculum alignment modeling, and job placement timeline analytics. The architecture consists of a web administrative dashboard for institutional administrators and a native Android mobile application for alumni, directly supporting IT0037 Systems Analysis and Design and the BSIT Web and Mobile Application specialization.

---

### 2.0 Background and Rationale of the Project

Higher education institutions face persistent challenges in obtaining timely, accurate data on graduate employment outcomes. Traditional web surveys and paper-based graduate tracer studies suffer from low response rates and delayed data aggregation, impeding institutional quality assurance, Commission on Higher Education (CHED) compliance, and PACUCOA accreditation reporting. AlumniTrack addresses these limitations by pairing an incentivized, low-friction mobile career update portal for alumni with an automated institutional analytics back-end. The system distinctly separates its computational components:

1. **Natural Language Processing (The AI Component):** A tokenization and Named Entity Recognition (NER) pipeline (using spaCy or lightweight transformer models) automatically extracts technical skills, tools, and competencies from alumni job descriptions and industry job vacancies. Extracted skills are normalized to standard taxonomies such as the CHED CMO 25 s. 2015 program outcomes.
2. **Algorithmic Skill Matching and Gap Analysis:** Vector Space Cosine Similarity compares graduate skill profiles against institutional curriculum outcomes and industry job requirements. This quantifies skill-to-market alignment without claiming unvalidated predictive career success.
3. **Longitudinal Career Analytics:** Concrete timeline metrics, including Time-to-First-Employment (elapsed months from graduation to first verified job), employment status distribution by graduation cohort, and underemployment ratios. Emerging skill gaps and curricular alignment trends are modeled empirically across historical posting data.

Data collection and alumni verification protocols are designed in strict compliance with the Data Privacy Act of 2012 (RA 10173).

---

### 3.0 Statement of Objectives

The primary objective is to analyze, design, and implement AlumniTrack, an integrated web and mobile graduate tracer and curriculum alignment analytics platform. Specifically, the project aims to:

1. Develop a web administrative dashboard for the institution to create tracer surveys, view longitudinal employment analytics, and generate automated PACUCOA/CHED accreditation reports.
2. Develop an Android mobile application for alumni to maintain verified career profiles, log employment milestones, and access institutional alumni networks.
3. Implement an AI-based Natural Language Processing pipeline to extract, parse, and normalize skills from alumni job descriptions and industry job postings.
4. Implement a Vector Space Cosine Similarity matching engine to evaluate alignment between graduate skills, CHED CMO 25 s. 2015 curriculum outcomes, and industry labor demands.
5. Implement an empirical skill-gap analytics dashboard identifying missing, emerging, and underrepresented skills across graduating batches.
6. Provide longitudinal career timeline analytics tracking average and median Time-to-First-Employment and employment rates grouped by graduation year.
7. Evaluate the NLP skill extraction model using Precision, Recall, and F1-score against manually annotated job postings, and evaluate overall software quality using ISO/IEC 25010 standards.

---

### 4.0 Scope and Limitations of the Study

**Scope:**
- Web Console (Admin): Graduate records database, tracer survey dispatcher, skill-gap analytics engine, automated accreditation reporting, and curriculum alignment heatmaps.
- Android Mobile App (Alumni): Profile and job status editor, employment timeline logging, career network feed, and a verification badge system.

**Limitations:**
- Data relies on graduate self-reporting supplemented by administrative verification mechanisms such as certificate or ID upload.
- Does not function as an active recruitment agency, staffing service, or commercial job board portal.
- Mobile client development and testing are bounded to Android mobile devices.
- Access to institutional alumni records requires formal authorization from university authorities.

---

### 5.0 Target Beneficiaries

1. University Administration and IT Department (FEU Diliman): Automates mandatory institutional graduate tracer compliance and simplifies accreditation data collection.
2. Academic Curriculum Committees: Identifies empirical, market-driven skill gaps to perform evidence-based curriculum revisions and elective planning.
3. Graduates and Alumni: Gains a persistent professional portfolio platform and ongoing institutional connection.

---

### 6.0 References

1. Commission on Higher Education. (2015). CHED Memorandum Order No. 25, Series of 2015: Revised policies, standards, and guidelines for Bachelor of Science in Information Technology (BSIT) programs.
2. FEU Diliman. (n.d.). IT0037 Module 1: Systems analysis fundamentals and organizational context [Course material]. Department of Information Technology.
3. FEU Diliman. (n.d.). IT0037 Module 2: Planning systems projects and preliminary investigation [Course material]. Department of Information Technology.
4. Republic of the Philippines. (2012). Data Privacy Act of 2012 (Republic Act No. 10173). Official Gazette.
5. Salton, G., Wong, A., & Yang, C. S. (1975). A vector space model for automatic indexing. Communications of the ACM, 18(11), 613–620.
6. Shelly, G. B., Cashman, T. J., & Rosenblatt, H. J. (2012). Systems analysis and design (9th ed.). Cengage Learning.

---

### 7.0 Appendices and Evidence Attachments

1. System Architecture Diagram and NLP Skill Extraction Pipeline Schema
2. Vector Cosine Similarity Metric Model and CMO Alignment Formulations
3. Sample Graduate Tracer Survey Schemas and Analytics Dashboards
4. Evaluation Plan for NLP Information Extraction Accuracy

---

## Open items before submission

- **Gate 0:** secure a real institutional client office (alumni/registry/careers/ICT) and an endorsement letter.
- **Title still lacks the Users/Setting element** (it does not end "…for a Higher Education Institution"). Confirm whether the panel requires this fix.
- Mark the "scraped industry job postings" source and its privacy basis `[TO VALIDATE]`.
- Every client-dependent claim stays `[TO VALIDATE]` until the Gate 2 interview.
