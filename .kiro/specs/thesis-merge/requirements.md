# Requirements Document

## Introduction

This document specifies the requirements for merging two separate MTech thesis reports into a single unified thesis document. The first report (Phase 1/2) covers automated ICD-10-CM code prediction from clinical notes with a focus on rare codes, and was partially completed due to high infrastructure costs. The second report (Phase 3) covers early mortality prediction for Sepsis-Associated Acute Kidney Injury (SA-AKI) patients using machine learning and survival analysis, and is fully complete with results. Both reports use the MIMIC-IV dataset, which provides a natural unifying thread under a clinical decision support framing. The merged thesis must satisfy the advisor's requirement of a single report containing all work from phases 1, 2, and 3, with unified chapters for introduction, literature review, problem definition, methodology, dataset understanding, results, and conclusions.

## Glossary

- **Merged_Thesis**: The single unified LaTeX thesis document produced by combining content from the Phase 1/2 ICD coding report and the Phase 3 SA-AKI mortality report.
- **Old_Report**: The Phase 1/2 thesis report on "Hybrid Data Augmentation Techniques for Disease Identification from Clinical Notes," located in `Old_project_feb_2025_thesis_folder/thesis/`.
- **Current_Report**: The Phase 3 thesis report on "Mortality Analysis Of Patients With Sepsis Associated Acute Kidney Injury (SAAKI) Cohort from MIMIC-IV dataset," located in `tex files/IIT_Madras_MTech_in_Industrial_AI_Thesis_Template/`.
- **Problem_1**: The ICD-10-CM code prediction task from the Old_Report (partially completed).
- **Problem_2**: The SA-AKI mortality prediction task from the Current_Report (fully completed with results).
- **Chapter_File**: A LaTeX `.tex` file in the `2-mainmatter/chapters/` directory of the Current_Report that contains one chapter of the thesis.
- **Thesis_Metadata**: The title, author, date, guide names, and other metadata fields defined in `thesis.tex`.
- **MIMIC-IV**: The Medical Information Mart for Intensive Care version IV database, the common data source for both problems.
- **Advisor_Feedback**: The set of feedback items from the thesis advisor documented in `final_feedback.md`.

## Requirements

### Requirement 1: Unified Thesis Title and Metadata

**User Story:** As a student, I want the thesis to have a single unified title and updated metadata, so that the document presents both research problems under one coherent identity.

#### Acceptance Criteria

1. WHEN the Merged_Thesis is compiled, THE Thesis_Metadata SHALL display a unified title that references both clinical decision support themes (ICD code prediction and mortality risk stratification) and the MIMIC-IV dataset.
2. THE Thesis_Metadata SHALL retain the author name "Kaustabh Ganguly," the department "Department of Chemical Engineering," the degree "Master Of Technology in Industrial Artificial Intelligence," and the guide names from the Current_Report.
3. THE Thesis_Metadata SHALL set the dissertation year and certificate date to 2026 and the month to the appropriate submission month.

### Requirement 2: Unified Introduction Chapter (Chapter 1)

**User Story:** As a reader, I want a single introduction chapter that motivates both research problems under a clinical decision support framing, so that the thesis reads as a coherent body of work.

#### Acceptance Criteria

1. THE Chapter_File for the introduction SHALL open with a broad clinical decision support motivation that establishes MIMIC-IV as the common data foundation for both problems.
2. THE Chapter_File for the introduction SHALL present Problem_1 (ICD code prediction for rare diseases) as the first research direction, summarizing its clinical importance, the challenge of rare codes, and the proposed approach from the Old_Report.
3. THE Chapter_File for the introduction SHALL present Problem_2 (SA-AKI early mortality prediction) as the second research direction, preserving all content from the Current_Report introduction including clinical background, literature gaps, research objectives, proposed approach, and evaluation plan with zero information loss.
4. THE Chapter_File for the introduction SHALL state that Problem_1 was partially completed due to high infrastructure costs and that Problem_2 was fully executed with results.
5. THE Chapter_File for the introduction SHALL include a chapter roadmap that describes the structure of all subsequent chapters in the Merged_Thesis.
6. THE Chapter_File for the introduction SHALL preserve all citations from both the Old_Report and Current_Report introductions.

### Requirement 3: Unified Literature Review Chapter (Chapter 2)

**User Story:** As a reader, I want a single literature review that covers both ICD coding automation and SA-AKI mortality prediction, so that the theoretical foundation for both problems is established in one place.

#### Acceptance Criteria

1. THE Chapter_File for the literature review SHALL contain a section on ICD coding literature covering the evolution of ICD coding, early rule-based and ML approaches, deep learning approaches (CNN, RNN, transformers), curriculum learning, knowledge-based methods, synthetic data generation for rare codes, and evaluation metrics, drawing from the Old_Report literature review.
2. THE Chapter_File for the literature review SHALL contain all sections from the Current_Report literature review on SA-AKI, including clinical definitions and epidemiology, conventional severity indices, datasets and cohort construction, feature engineering and leakage risks, missing data mechanisms, class imbalance and evaluation strategy, model classes and calibration, external validity, and the detailed appraisal of representative studies, with zero information loss.
3. THE Chapter_File for the literature review SHALL include a synthesis section that ties both bodies of literature together under the common theme of machine learning for clinical decision support using MIMIC-IV.
4. THE Chapter_File for the literature review SHALL preserve all citations from both reports.

### Requirement 4: Unified Problem Definition Chapter (Chapter 3)

**User Story:** As a reader, I want a single problem definition chapter that formally states both research problems, so that the scope and mathematical formulation of each task is clear.

#### Acceptance Criteria

1. THE Chapter_File for the problem definition SHALL present Problem_1 (automated ICD-10-CM multi-label classification with focus on rare codes) including the scope, central challenges, mathematical formulation (input space, label space, function definition, composite metric), significance of rare codes, proposed methodological focus, and evaluation framework from the Old_Report.
2. THE Chapter_File for the problem definition SHALL present Problem_2 (SA-AKI early mortality prediction) preserving all content from the Current_Report problem definition including clinical decision and scope, observational unit and information sets, data-generating view, the three sub-problems (phenotyping, supervised classification, survival analysis), evaluation protocol, assumptions and risks, and compact statement of aims, with zero information loss.
3. THE Chapter_File for the problem definition SHALL clearly label the two problems (e.g., "Problem 1: Automated ICD Code Prediction" and "Problem 2: SA-AKI Mortality Risk Stratification") within a unified chapter structure.
4. THE Chapter_File for the problem definition SHALL note that Problem_1 methodology was proposed but not fully executed due to infrastructure constraints.

### Requirement 5: Unified Methodology Chapter (Chapter 4)

**User Story:** As a reader, I want a single methodology chapter that describes the approaches for both problems, so that the technical design of each pipeline is documented.

#### Acceptance Criteria

1. THE Chapter_File for the methodology SHALL present the Problem_1 methodology including ontology-based disease grouping, synthetic discharge summary generation pipeline, deep learning model training approach, and evaluation metrics from the Old_Report, clearly noting that this methodology was proposed but not fully executed.
2. THE Chapter_File for the methodology SHALL present the Problem_2 methodology preserving all content from the Current_Report methodology chapter including data sources and ETL, cohort construction, data split and leakage control, preprocessing and feature engineering, EDA and phenotyping approach, supervised binary mortality prediction pipeline (benchmarking, LightGBM selection, calibration, thresholding, SHAP), survival analysis (CoxPH and DeepSurv), and TRIPOD adherence sections (including the data leakage discussion and the 24-hour window heterogeneity discussion), with zero information loss.
3. THE Chapter_File for the methodology SHALL preserve all mathematical notation, equations, and algorithmic details from both reports.

### Requirement 6: Unified Dataset Understanding and EDA Chapter (Chapter 5)

**User Story:** As a reader, I want a single dataset chapter that covers the MIMIC-IV dataset from both perspectives, so that the data foundation for both problems is documented together.

#### Acceptance Criteria

1. THE Chapter_File for dataset understanding SHALL present the MIMIC-IV overview and dataset exploration for Problem_1 including the database structure, patient and admission volumes, discharge summaries, ICD code distributions, long-tail analysis, visual explorations (all 10 plots), and final data preparation from the Old_Report.
2. THE Chapter_File for dataset understanding SHALL present the SA-AKI cohort dataset understanding for Problem_2 preserving all content from the Current_Report EDA chapter including source tables, ontology-driven concept identification, cohort construction (CONSORT flow), clinical labeling rules, timeline conventions, data harmonization, statistical validation, missing data analysis, and clinical phenotyping of survivor vs. non-survivor groups, with zero information loss.
3. THE Chapter_File for dataset understanding SHALL preserve all figures, tables, and their references from both reports.

### Requirement 7: Unified Results Chapter (Chapter 6)

**User Story:** As a reader, I want a single results chapter that presents findings from both problems, so that the outcomes of the thesis work are consolidated.

#### Acceptance Criteria

1. THE Chapter_File for results SHALL present Problem_1 partial results including the KNN baseline (Macro F1 of 0.12), MinHash similarity detection findings, key observations on data imbalance and text complexity, and the rare disease co-occurrence pipeline output from the Old_Report, clearly noting that full model training and synthetic data generation were not completed due to infrastructure costs.
2. THE Chapter_File for results SHALL present Problem_2 results preserving all content from the Current_Report results chapter including model benchmarking table, final LightGBM test performance (AUROC 0.749, F1 0.522), confusion matrix and ROC curve, SHAP analysis, the "Why LightGBM Outperforms" section, the "Evidence for Trustworthiness" section, the comparison with prior work table, the external validation limitations section, CoxPH results (C-index 0.693) with forest plot and KM curves, DeepSurv results (C-index 0.688) with KM curves, calibration plots, DCA, and the survival analysis synthesis, with zero information loss.
3. THE Chapter_File for results SHALL preserve all figures, tables, and their references from both reports.

### Requirement 8: Unified Conclusions Chapter (Chapter 7)

**User Story:** As a reader, I want a single conclusions chapter that summarizes findings from both problems and outlines future work, so that the thesis ends with a coherent summary.

#### Acceptance Criteria

1. THE Chapter_File for conclusions SHALL summarize Problem_1 work, stating that the literature review, problem formulation, dataset understanding, and preliminary results (baseline model, co-occurrence pipeline) were completed, but synthetic data generation and full model training were not executed due to high infrastructure costs.
2. THE Chapter_File for conclusions SHALL summarize Problem_2 work preserving all content from the Current_Report conclusions including the four key contributions (cohort construction, leakage-aware preprocessing, interpretable predictive modeling with specific metrics, dynamic risk assessment with survival analysis) and all future work items (external validation, Monte Carlo simulation, multi-database risk framing, temporal window exploration, model fairness audit, prospective clinical impact study), with zero information loss.
3. THE Chapter_File for conclusions SHALL present a unified future work section that includes remaining steps for Problem_1 (completing synthetic data generation and model training when infrastructure becomes available) alongside the Problem_2 future work items.

### Requirement 9: Address Advisor Feedback on Data Leakage Explanation

**User Story:** As a student, I want the thesis to better explain the data leakage phenomenon, so that the advisor's feedback is addressed.

#### Acceptance Criteria

1. THE Chapter_File for the methodology SHALL contain a dedicated subsection that defines data leakage in clinical prediction modeling, describes the three principal mechanisms (temporal leakage, preprocessing leakage, selection leakage), and explains the specific safeguards implemented in this work.
2. WHEN the data leakage discussion references prior studies, THE Chapter_File SHALL provide concrete examples of how leakage manifests (e.g., inclusion of length of stay as a predictor, global fitting of imputation models).

### Requirement 10: Address Advisor Feedback on 24-Hour Window Rationale

**User Story:** As a student, I want the thesis to explain what is "holistic" about the 24-hour data collection and how patients arriving at different ICU stages impacts findings, so that the advisor's feedback is addressed.

#### Acceptance Criteria

1. THE Chapter_File for the methodology SHALL contain a subsection that explains the clinical rationale for the 24-hour observation window, including its alignment with the natural clinical decision point at the end of the first ICU day.
2. THE Chapter_File for the methodology SHALL discuss the heterogeneity introduced by patients arriving at ICUs at different stages of illness and explain how specific features (APACHE III, SOFA, Charlson comorbidity index, first/last/delta/slope suffixes) partially account for this variation.
3. THE Chapter_File for the methodology SHALL acknowledge this heterogeneity as a limitation and suggest stratified analyses by admission source as future work.

### Requirement 11: Address Advisor Feedback on LightGBM Performance Justification

**User Story:** As a student, I want the thesis to explain why LightGBM performs better, what the AUROC score means, and provide evidence for trustworthiness, so that the advisor's feedback is addressed.

#### Acceptance Criteria

1. THE Chapter_File for results SHALL contain a subsection explaining why LightGBM outperforms other model classes, including its leaf-wise growth strategy, native interaction capture, and effective class imbalance handling through built-in class weighting.
2. THE Chapter_File for results SHALL contain a subsection on evidence for trustworthiness covering methodological integrity (leakage prevention), calibration (isotonic regression), clinical face validity (SHAP alignment with known risk factors), decision-curve analysis (net benefit over default strategies), and cross-model concordance (consistent results across LightGBM, CoxPH, and DeepSurv).
3. THE Chapter_File for results SHALL state the validation dataset (MIMIC-IV held-out test set with strict 80/20 split) and identify the eICU Collaborative Research Database as the candidate for external validation.
4. THE Chapter_File for results SHALL include the comparison table contrasting this work's methodology with prior studies (Chen 2025, Li 2023, Hu 2021).

### Requirement 12: Address Advisor Feedback on Monte Carlo Methods and Multi-Database Framing

**User Story:** As a student, I want the thesis to mention Monte Carlo methods for synthetic data generation and provide more details on datasets for risk framing, so that the advisor's feedback is addressed.

#### Acceptance Criteria

1. THE Chapter_File for conclusions SHALL include a future work item on Monte Carlo simulation for synthetic data augmentation, describing copula-based simulation or parametric bootstrap approaches for generating physiologically coherent synthetic patients.
2. THE Chapter_File for conclusions SHALL include a future work item on multi-database risk framing, identifying specific external databases (eICU, Amsterdam UMCdb, HiRID, ANZICS) and describing how a federated or meta-analytic approach could strengthen evidence for the 24-hour risk signal.

### Requirement 13: Content Integrity Constraint

**User Story:** As a student, I want all content from the Current_Report (Phase 3 SA-AKI work) to be preserved with zero information loss, so that my complete research is fully represented.

#### Acceptance Criteria

1. THE Merged_Thesis SHALL preserve every section, subsection, paragraph, equation, table, figure reference, and citation from the Current_Report across all chapters.
2. THE Merged_Thesis SHALL integrate Old_Report content as additional sections within each unified chapter without removing, abbreviating, or paraphrasing any Current_Report content.
3. IF a conflict arises between Old_Report content and Current_Report content, THEN THE Merged_Thesis SHALL prioritize the Current_Report content and note the Old_Report content as supplementary context for Problem_1.

### Requirement 14: LaTeX Compilation Integrity

**User Story:** As a student, I want the merged thesis to compile without errors, so that I can generate a valid PDF.

#### Acceptance Criteria

1. THE Merged_Thesis SHALL maintain valid LaTeX syntax across all modified Chapter_Files.
2. THE Merged_Thesis SHALL preserve all `\label{}` and `\ref{}` cross-references, updating them where necessary to avoid conflicts between labels originating from the two reports.
3. THE Merged_Thesis SHALL include all necessary `\usepackage{}` declarations in `thesis.tex` for packages used by content from both reports (e.g., `pgfgantt` for the Gantt chart from the Old_Report).
4. THE Merged_Thesis SHALL ensure all figure paths reference files that exist in the workspace (images from the Old_Report must use correct relative paths or be noted for manual copying).
