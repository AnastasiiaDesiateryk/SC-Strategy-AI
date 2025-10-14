## 4. Functional Requirements — MVP Study Phase  
*(BFH Innosuisse Pre-Study: SC Strategy & AI)*  

### 4.1 Overview  
The MVP phase establishes a data-driven foundation for strategy mining.  
Functional requirements derive directly from the Innosuisse pre-study scope — namely, the development of a **methodological and analytical framework** for identifying, evaluating, and narrating implicit supply-chain strategies using AI.  

---

### 4.2 Functional Requirements  

| **ID** | **Requirement** | **Description** |
|:------:|-----------------|-----------------|
| **FR-1** | **Data Ingestion & Normalization** | Controlled import of CSV or database extracts with schema mapping per business domain (supplier, logistics, inventory). Validation and anonymisation executed on ingestion; alignment by supplier and time dimensions. |
| **FR-2** | **Pattern Recognition Engine** | Core analytical component detecting recurring parameter configurations or implicit decision rules through clustering, sequence analysis, and LLM-based prompts. Supports per-domain detection (sourcing, inventory, logistics, production). |
| **FR-3** | **Strategy Narration Module** | Converts analytical output into human-readable strategy statements (e.g., “Supplier portfolio reflects a cost-optimised sourcing strategy”), maintaining traceability to underlying data sources. |
| **FR-4** | **Evaluation Model** | Quantitative scoring of discovered strategies along key dimensions: alignment, cost efficiency, resilience/adaptability, sustainability/compliance, and competitiveness. |
| **FR-5** | **Visualization Dashboard** | Interactive visual layer presenting detected patterns and evaluation metrics. Supports drill-down by SCOR stage and domain; enables cross-comparison of strategic dimensions. |
| **FR-6** | **Scenario Recommendation Engine** | Generates optimisation scenarios (e.g., supplier re-allocation, mode shift, inventory policy adjustment) and projects expected KPI impact. |
| **FR-7** | **Reporting & Export Module** | Produces PDF and CSV deliverables for management review. |

---

### 4.3 Non-Functional Requirements — Concept Phase  

| **Domain** | **Requirement** | **Specification** |
|-------------|----------------|-------------------|
| **Architecture** | Modular system design separating data, ML, and presentation layers. Each module independently deployable and testable. |
| **Reproducibility** | All analytical pipelines are logged, version-controlled, and reproducible across environments (DEV → TEST → QUAL). |
| **Interpretability** | Every AI-generated insight must include an explanation layer — model reasoning, key features, and traceable evidence from the dataset. |
| **Security & Compliance** | All processing must comply with Information Security Policy, Swiss FADP and EU GDPR. Data anonymisation applied pre-processing; encryption enforced in transit and at rest. |
| **Performance** | Batch analysis runtime ≤ 5 hours for datasets up to 10 million records. Dashboard latency ≤ 3 seconds per filtered query. |
| **Integration & Extensibility** | Interfaces designed for downstream integration with BI systems (Power BI, Superset, Tableau) and REST-based API endpoints. |

---

### 4.4 Compliance Alignment    
- **Traceability:** Each analytical output is linked to a specific data lineage entry and model version.  
- **Auditability:** All user interactions and configuration changes logged within the ML workspace.  
- **Change Control:** Enhancements follow (RFC > QA > Deploy).  

---

### 4.5 Deliverable Quality Criteria    
- Code repositories include version tagging, data dictionaries, and automated validation reports.  
- Metrics aligned with Innosuisse evaluation KPIs: reproducibility, interpretability, and impact potential.

---

 **Summary:**  
The functional design ensures controlled ingestion, explainable AI pattern extraction, quantitative evaluation, and transparent communication of implicit strategies.
