# SC Strategy & AI
_A Strategy-Mining Framework for Supply Chains_

![Status](https://img.shields.io/badge/status-Preliminary-blue)
![Version](https://img.shields.io/badge/version-1.0-black)
![Language](https://img.shields.io/badge/lang-English-lightgrey)
![Domain](https://img.shields.io/badge/domain-ICT%20%2F%20Data%20Sciences-informational)
![Privacy](https://img.shields.io/badge/privacy-CH--FADP%20%7C%20GDPR-forestgreen)
![License](https://img.shields.io/badge/license-Private%20%2F%20Confidential-critical)

**Author:** Anastasiia Desiateryk  
**Date:** 2025-10-09  
**Version:** 1.0

---

## 0) Executive Snapshot
**Problem.** Many Swiss manufacturing and logistics firms run without an explicit supply-chain strategy. Yet historical operational data (procurement, inventory, transport, production) contains consistent patterns—_implicit strategies_—that shape cost, service, and resilience outcomes.

**Idea.** _SC Strategy & AI_ applies generative AI and machine-learning to operational datasets to:
- **Identify** recurring decision patterns (_“as-is” strategic behaviour_).  
- **Evaluate** their effectiveness against KPIs and objectives.  
- **Recommend** optimized _“to-be”_ strategies.

This **inverts** classic top-down planning: instead of declaring a strategy and testing it with data, **the data reveals the strategy**.

**Context.** Innosuisse pre-study (Innovation Council subgroup: ICT; Innovation Cluster: Data Sciences). Research partners include **BFH** (Prof. Dr. Jörg Grimm, Moritz Maier) and **BEG Analytics** (Lars Baacke). 

---

## 1) What problem does this solve?
Executives lack instruments to _extract_ and _evaluate_ hidden strategies embedded in daily operations. As a result, they cannot assess coherence with business goals or readiness for disruptions.

**Our approach:**
1. **Pattern Discovery** — Learn strategy-like behaviours from procurement, inventory, logistics and production traces (e.g., sourcing bias, reorder logics, transport choices).
2. **Effectiveness Assessment** — Benchmark discovered patterns vs. targets (cost, service, resilience, sustainability).
3. **Scenario & Recommendation** — Propose alternative policies; quantify trade-offs.

**Outcomes:**
- Transparency on _what strategy the firm actually runs_.  
- Evidence-based alignment to business goals.  
- Foundation for a prototype AI assistant that narrates strategy rationales from data. 

---

## 2) Who are the users?

| **User Type** | **Description** | **Primary Goal** |
| --- | --- | --- |
| **Supply Chain Analyst** | Works with internal datasets (procurement, inventory, logistics). | Discover and visualise implicit strategies. |
| **Operations Manager** | Balances cost, service, resilience. | Identify misalignments and improvement levers. |
| **Executive / Board** | Uses synthesised insights for strategic alignment. | Assess strategic coherence and risk posture. |
| **AI Researcher / Data Scientist** | Extends analytical methods (pattern recognition, NLP). | Improve model accuracy and interpretability. |

---

## 3) Main workflows (MVP)

### 3.1 Data Acquisition → Preparation → Feature Mapping
- Ingest multi-domain datasets (procurement, transport, inventory, production).  
- Normalise, anonymise, and align by time, SKU, supplier, lane, and plant.  
- Map domain features (lead-time, MOQ, Incoterms, lane cost, fill-rate, stockout events).

### 3.2 Pattern Recognition / Strategy Extraction
- Apply ML/NLP to detect strategic patterns (e.g., preferred supplier logic, safety-stock heuristics, shipment consolidation rules).  
- Translate quantitative behaviours into human-readable **strategy narratives**.

### 3.3 Strategy Evaluation / Recommendation
- Compare discovered strategies with objectives/benchmarks (cost-to-serve, OTIF, ETA accuracy, CoV of lead-time, DIO/DSO, CO₂/ton-km) .  
- Generate improvement scenarios (what-ifs) and dashboards for decision-making.

---

## 4) Scope & Non-Scope
**In-scope (pre-study):**
- Methodology for discovery/evaluation of implicit strategies.  
- Reference data model and minimal feature set.  
- Prototype notebooks + BI views for narratives and scenarios.

**Out-of-scope (pre-study):**
- Enterprise rollout, real-time optimisation, full MDM programme, or production-grade integrations (considered in subsequent project).

---

## 5) Architecture at a glance (cloud-agnostic)
**Data lake (raw → curated)** → **Feature store** → **Model layer (pattern mining, NLP)** → **Narrative engine** → **BI & APIs**.  
Target stacks: object storage (Azure Blob/S3), Parquet/Delta for curated layers, Python (pandas, scikit-learn), graph features for relationships, and a lightweight API for strategy cards. Integration with existing BI (Superset/Power BI/Tableau).

---

## 6) Minimum Viable Dataset (examples)
- **Procurement:** PO lines (SKU, supplier, MOQ, price, Incoterm, lead-time, lateness).  
- **Inventory:** daily stock, safety-stock rule, reorder events, backorders.  
- **Logistics:** shipments (lane, mode, cost, ETA/ATA, delays, consolidation).  
- **Production:** work orders, changeovers, capacity, scrap.  
- **Reference:** SKU master, supplier master, calendar, geo/lane dictionary.

---

## 7) KPIs & Evaluation (examples)
- **Service:** OTIF, ETA-MAE/90p, backorder rate.  
- **Cost:** cost-to-serve per SKU/customer, freight per ton-km, premium freight share.  
- **Flow:** lead-time by SCOR stage, CoV of lead-time, dock-to-stock.  
- **Resilience:** time-to-recover proxy, disruption sensitivity.  
- **Sustainability:** CO₂/ton-km (by lane/mode).  
- **Model quality:** stability of patterns across time, uplift vs. baseline in what-ifs, narrative fidelity (expert ratings).

---

## 8) Security, Privacy & Compliance
- **Data minimisation & anonymisation** at ingestion; PII excluded by design.  
- **Encryption** in transit (TLS 1.2+) and at rest (KMS-managed keys).  
- **Access control** via least privilege; auditable data lineage.  
- **Compliance:** CH-FADP and GDPR principles; DPIA template included for client data.  
- **Isolation:** research sandbox; no connection to production systems.

---

## 9) Deliverables (Pre-study)
1. **Methodology** for strategy mining (discovery → evaluation → recommendation).  
2. **Reference data model** and ingestion templates.  
3. **Prototype notebooks** for pattern mining and narrative generation.  
4. **Strategy dashboard** (scenarios, KPIs, risk view).  
5. **Partner report** with taxonomy of strategy patterns and next-phase blueprint. 

---

## 10) Governance & Partners
- **Project owner:** Anastasiia Desiateryk  
- **Research partners:** BEG Analytics (Lars Baacke), BFH (Prof. Dr. Jörg Grimm; Moritz Maier).
- **Advisory cadence:** bi-weekly research stand-up; monthly steering.

---

## 11) Risks & Mitigations
- **Data sparsity / quality.** Start with a minimum dataset; robust cleaning & imputation; sensitivity analyses.  
- **Spurious patterns.** Holdout validation; business sign-off checkpoints; stability tests across seasons.  
- **Interpretability.** Human-readable strategy cards; traceable rules and features; counterfactual examples.  
- **Change management.** Executive workshops; side-by-side metrics vs. current practice.

---

## 12) Roadmap (indicative)
- **Month 1:** Data model, ingestion templates, anonymisation pipeline.  
- **Month 2:** Pattern discovery PoC (supplier bias, safety-stock, consolidation).  
- **Month 3:** Evaluation framework, what-if scenarios, dashboard & report; follow-up proposal.

---

## 13) Glossary (select)
- **Strategy mining:** Data-driven extraction of persistent decision patterns that function as de-facto strategy.  
- **Strategy narrative:** Plain-language summary explaining what the pattern does, where, and with which trade-offs.  
- **SCOR stages:** Plan, Source, Make, Deliver (used for stage-wise lead-time).

---


