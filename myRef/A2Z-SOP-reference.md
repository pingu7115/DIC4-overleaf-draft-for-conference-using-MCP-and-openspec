# A2Z SOP Reference Guide (DIC4 IEEE Conference Paper)

This reference maps the 26-letter A2Z paper structure to our IEEE conference paper sections for the **AI SOC Analyst Agent** project:

## Abstract (Checkpoints A–F)
- **A (Attention Getter)**: National Security Bureau 2025 report (2.63M daily infrastructure intrusions, +6%) and IBM 2026 report (\$4.99M average breach cost, 247-day lifecycle); <5% of SOC alerts are true positives.
- **B (But / Challenge)**: Alert fatigue causes missed threats; standalone ML lacks attack-chain causality; tool-using LLM agents suffer >=40.4% miss rates and premature closure on missing telemetry; automation complacency.
- **C (Cure)**: AI SOC Analyst Agent — evidence-grounded, escalation-aware hybrid framework combining GBDT, MITRE ATT&CK, and LLM reasoning.
- **D (Development)**: 8-module architecture, LightGBM + SHAP, Chroma ATT&CK/NIST RAG, ReAct planner, Algorithm 1 & 2 evidence fusion, proactive human-in-the-loop escalation.
- **E (Experiments)**: Planned evaluation on Microsoft GUIDE (~1M incidents) and ExCyTIn-Bench (57 SQL log tables) against majority, heuristic, standalone GBDT, and standalone LLM baselines.
- **F (Findings / Expected Outcomes)**: Proposal-stage expected outcomes (no fabricated numbers): lower TP miss rate than baselines, Pareto frontier of miss rate vs. escalation rate, improved ATT&CK mapping and auditability.

## Paper Sections (G–Z)
- **G (General)**, **H (However)**, **I (In literature)**, **J (Judgement)**, **K (Keypoint)**, **L (List the organization)** -> `01_introduction.tex`
- **M (Methods)**, **N (New proposed)**, **O (Organize - Article Summary Table)** -> `02_related_work.tex`
- **PA–PM (Aim, Based on, Cure, Design, Paper Element, Formulation, Graph, How, Implementation, Jump to example, Key points, Later simulation, Math/Logic)** -> `03_proposed_design.tex`
- **Q (Quality & Quantity)**, **R (Related method)**, **S (Simulation Setup)**, **T (Tuning)**, **U (Useful results)**, **V (Verify)** -> `04_experiment.tex`
- **W (What proposed)**, **X (eXcel)**, **Y (Yields)**, **Z (Zen)** -> `05_conclusion.tex`
