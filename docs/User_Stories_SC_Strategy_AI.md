##  User Stories — SC Strategy & AI (BFH Innosuisse Pre-Study)

###  Overview  
The following user stories define the functional scope of the *SC Strategy & AI* proof-of-concept.  
They describe end-to-end user interactions required to support the project’s research goals — data ingestion, pattern recognition, strategy narration, evaluation, recommendation, and reporting.  
Each story aligns with the corresponding research component described in the Innosuisse application:  
- *Strategy Mining Framework*  
- *Pattern Recognition Methodology*  
- *Strategy Evaluation Model*  

---

### US-1 — Data Import & Validation  
**Role:** Data Analyst  
**Objective:** Upload and prepare multi-domain supply-chain datasets (procurement, logistics, inventory, production) for analytical processing.  
**Business Value:** Enables consistent data integration and ensures readiness for pattern recognition.  
**Acceptance Criteria:**  
- Upload wizard validates schema conformity and field completeness.  
- Summary report displays record count, coverage period, and data quality indicators.  
- Data anonymisation enforced prior to ingestion.  
- Audit log created for each upload event.  
**Traceability:** Linked to *“What data are available and accessible?”* in the Innosuisse scope.

---

### US-2 — Pattern Detection  
**Role:** Data Analyst  
**Objective:** Detect recurring operational and procurement behaviours to identify implicit decision logic.  
**Business Value:** Reveals non-documented (“as-is”) strategic behaviour embedded in operations.  
**Acceptance Criteria:**  
- ML/NLP engine clusters data patterns (e.g., supplier bias, lead-time tolerance, stock policy).  
- Each cluster described with quantitative metrics (size, variance, confidence).  
- Output stored with model metadata and version ID.  
**Traceability:** Aligned with *Pattern Recognition Methodology* — supplier selection, inventory, transport, production planning.

---

### US-3 — Strategy Narration  
**Role:** Supply-Chain Manager  
**Objective:** Translate analytical findings into business-readable strategy narratives for internal stakeholders.  
**Business Value:** Promotes transparency and shared understanding of operational behaviour.  
**Acceptance Criteria:**  
- AI-generated text summarises detected strategies in clear language.  
- Confidence level displayed for each narrative.  
- Users may edit and approve narratives for reporting.  
- All narratives maintain linkage to data source and model ID.  
**Traceability:** Corresponds to *“Layer of reflection based on data — What are we doing, how, and what is our performance?”*

---

### US-4 — Evaluation Model  
**Role:** Decision-Maker / Controller  
**Objective:** Assess performance of each detected strategy across defined key dimensions (cost, resilience, sustainability, competitiveness).  
**Business Value:** Enables evidence-based strategic alignment and prioritisation of improvements.  
**Acceptance Criteria:**  
- Each strategy receives a composite score (0–100) per KPI dimension.  
- Visual gauge and benchmark comparison provided.  
- Drill-down available by SCOR stage (Plan, Source, Make, Deliver).  
- KPI calculations traceable and reproducible.  
**Traceability:** Derived from *Strategy Evaluation Model* section — alignment, cost efficiency, resilience, sustainability, compliance.

---

### US-5 — Recommendation Preview  
**Role:** Supply-Chain Manager  
**Objective:** Review AI-generated alternative strategies and simulate expected performance outcomes before adoption.  
**Business Value:** Facilitates proactive scenario planning and risk-aware decision-making.  
**Acceptance Criteria:**  
- System generates at least one “to-be” scenario per domain (procurement, inventory, logistics).  
- Expected KPI deltas visualised (cost, lead-time, CO₂ intensity).  
- Scenario assumptions and parameters recorded for auditability.  
- Manager can accept, reject, or mark for further analysis.  
**Traceability:** Linked to *“Recommend optimised or alternative strategies (‘to-be’)”* in the innovation scope.

---

### US-6 — Report Generation & Export  
**Role:** Executive / Board User  
**Objective:** Generate consolidated reports summarising identified strategies, performance scores, and recommendations.  
**Business Value:** Provides a clear, compliant communication layer for strategic review.  
**Acceptance Criteria:**  
- Downloadable PDF report includes executive summary, KPI table, and recommendations.  
- Charts embedded or linked to dashboard views.  
- Report footer includes dataset ID, model version, and timestamp.  
- Exports comply with UBS Records Retention & Confidentiality Policy.  
**Traceability:** Matches *Prototype Conceptualisation* — interface and reporting layer.

---

### Traceability Matrix  

| **User Story** | **Innosuisse Reference** | **Scope Linkage** |
|-----------------|--------------------------|-------------------|
| US-1 | Data availability & accessibility | Data ingestion and preparation pipeline. |
| US-2 | Pattern Recognition Methodology | Detection of implicit strategic behaviour. |
| US-3 | Layer of reflection / Controlling | Narration of operational reality. |
| US-4 | Strategy Evaluation Model | Quantitative assessment of strategic performance. |
| US-5 | Recommend optimised strategies | Generation of alternative “to-be” scenarios. |
| US-6 | Prototype Conceptualisation | Executive reporting and presentation layer. |




