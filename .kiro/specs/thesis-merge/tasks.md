# Implementation Plan: Thesis Merge

## Overview

Merge two MTech thesis reports into a single unified document, working chapter by chapter. The Current Report (SA-AKI, Phase 3) is the base template in `tex files/IIT_Madras_MTech_in_Industrial_AI_Thesis_Template/`. The Old Report (ICD coding, Phase 1/2) content from `Old_project_feb_2025_thesis_folder/thesis/` is woven into each chapter as additional sections. Zero information loss from the Current Report is the cardinal rule.

## Tasks

- [x] 1. Prerequisites: Images, Bibliography, and Metadata
  - [x] 1.1 Copy Old Report images to target directory
    - Copy all files from `Old_project_feb_2025_thesis_folder/thesis/mimic_plots/` (plot1.jpg through plot10.jpg) to `tex files/IIT_Madras_MTech_in_Industrial_AI_Thesis_Template/mimic_plots/`
    - Verify all 10 plot files are present after copy
    - _Requirements: 14.4_

  - [x] 1.2 Merge references.bib
    - Read `Old_project_feb_2025_thesis_folder/thesis/references/references.bib` and `tex files/IIT_Madras_MTech_in_Industrial_AI_Thesis_Template/references.bib`
    - Append all Old Report bib entries to the Current Report's references.bib
    - Deduplicate entries that appear in both files (keep Current Report's citation key, preserve Old Report's key if different)
    - Ensure both `johnson2023mimicivscidata` (Old) and `Johnson_2023_MIMIC` (Current) keys are present so citations from both reports resolve
    - _Requirements: 2.6, 3.4, Property 2_

  - [x] 1.3 Update thesis.tex metadata and packages
    - Update `\dissertationTitle` to unified title: "Machine Learning for Clinical Decision Support: Automated ICD Code Prediction and Early Mortality Risk Stratification in the MIMIC-IV Dataset"
    - Verify `\dissertationYear` is `2026`, `\dissertationMonth` and `\dissertationCertificateDate` are correct
    - Add `\usepackage{pgfgantt}` and `\usepackage{float}` if not already present
    - Retain author, department, degree, and guide names from Current Report
    - _Requirements: 1.1, 1.2, 1.3, 14.3_

- [x] 2. Checkpoint — Verify prerequisites
  - Ensure images are copied, references.bib merges cleanly, and thesis.tex metadata is correct. Ask the user if questions arise.

- [x] 3. Chapter 1: Unified Introduction
  - [x] 3.1 Read source content for introduction
    - Read `Old_project_feb_2025_thesis_folder/thesis/2-mainmatter/chapters/chap-introduction.tex` to extract ICD coding introduction content
    - Read `tex files/IIT_Madras_MTech_in_Industrial_AI_Thesis_Template/2-mainmatter/chapters/chap-1-introduction.tex` to understand current structure
    - _Requirements: 2.1, 2.2, 2.3_

  - [x] 3.2 Merge introduction chapter
    - Preserve ALL existing Current Report content verbatim (sections: Clinical background, Literature gaps, Problem focus, Proposed approach, Evaluation plan)
    - Add new opening section: `\section{Clinical Decision Support and the MIMIC-IV Foundation}` — broad CDS motivation establishing MIMIC-IV as common data foundation
    - Add new section: `\section{Problem 1: Automated ICD Code Prediction for Rare Diseases}` — from Old Report, summarizing clinical importance, rare code challenges, proposed approach, and noting partial completion due to infrastructure costs
    - Update chapter roadmap section to describe all 7 chapters of the merged thesis
    - Prefix Old Report labels with `p1:` to avoid conflicts (e.g., `\label{sec:p1:icd_intro}`)
    - Preserve all citations from both reports
    - Target structure per design: unified opener → Problem 1 (Old) → Problem 2 sections (Current, preserved) → updated roadmap
    - _Requirements: 2.1, 2.2, 2.3, 2.4, 2.5, 2.6, 13.1, 13.2, 14.2_

- [x] 4. Chapter 2: Unified Literature Review
  - [x] 4.1 Read source content for literature review
    - Read `Old_project_feb_2025_thesis_folder/thesis/2-mainmatter/chapters/chap-literature-review.tex` to extract ICD coding literature content
    - Read `tex files/IIT_Madras_MTech_in_Industrial_AI_Thesis_Template/2-mainmatter/chapters/chap-2-literature-review.tex` to understand current structure
    - _Requirements: 3.1, 3.2_

  - [x] 4.2 Merge literature review chapter
    - Preserve ALL existing Current Report literature review content verbatim as "Part II: SA-AKI Mortality Prediction"
    - Add "Part I: Automated ICD Coding" section from Old Report with subsections: Evolution of ICD Coding, Early Approaches, Deep Learning, Transformers, Curriculum Learning, Challenges, Synthetic Data Generation, Benchmarks/Metrics, Summary
    - Add new "Synthesis: Machine Learning for Clinical Decision Support Using MIMIC-IV" section tying both bodies of literature together
    - Prefix Old Report labels with `p1:` to avoid conflicts
    - Preserve all citations from both reports
    - _Requirements: 3.1, 3.2, 3.3, 3.4, 13.1, 13.2, 14.2_

- [x] 5. Checkpoint — Verify Chapters 1–2
  - Ensure all content is preserved, labels are unique, and citations are intact. Ask the user if questions arise.

- [x] 6. Chapter 3: Unified Problem Definition
  - [x] 6.1 Read source content for problem definition
    - Read `Old_project_feb_2025_thesis_folder/thesis/2-mainmatter/chapters/chap-problem-definition.tex` to extract ICD coding problem formulation
    - Read `tex files/IIT_Madras_MTech_in_Industrial_AI_Thesis_Template/2-mainmatter/chapters/chap-3-problem-definition.tex` to understand current structure
    - _Requirements: 4.1, 4.2_

  - [x] 6.2 Merge problem definition chapter
    - Preserve ALL existing Current Report problem definition content verbatim as "Problem 2: SA-AKI Early Mortality Risk Stratification"
    - Add "Problem 1: Automated ICD-10-CM Code Prediction" section from Old Report with subsections: Scope, Central Challenges, Mathematical Formulation, Significance of Rare Codes, Proposed Methodological Focus, Evaluation Framework
    - Add note that Problem 1 methodology was proposed but not fully executed due to infrastructure constraints
    - Clarify Current Report's internal "Problem 1/2/3" (phenotyping, classification, survival) with a note or relabel as sub-problems to avoid confusion with thesis-level Problem 1/Problem 2
    - Prefix Old Report labels with `p1:`
    - _Requirements: 4.1, 4.2, 4.3, 4.4, 13.1, 13.2, 14.2_

- [x] 7. Chapter 4: Unified Methodology
  - [x] 7.1 Read source content for methodology
    - Read `Old_project_feb_2025_thesis_folder/thesis/2-mainmatter/chapters/chap-methodology.tex` to extract ICD coding methodology
    - Read `tex files/IIT_Madras_MTech_in_Industrial_AI_Thesis_Template/2-mainmatter/chapters/chap-4-methodology.tex` to understand current structure
    - _Requirements: 5.1, 5.2_

  - [x] 7.2 Merge methodology chapter
    - Preserve ALL existing Current Report methodology content verbatim as "Problem 2: SA-AKI Mortality Prediction Methodology" (including Data Sources/ETL, Cohort Construction, Data Split/Leakage Control, Preprocessing, EDA/Phenotyping, Supervised Prediction, Survival Analysis, TRIPOD Adherence with Data Leakage and 24-Hour Window subsections)
    - Add "Problem 1: ICD Code Prediction Methodology (Proposed)" section from Old Report with subsections: Ontology-Based Disease Grouping, Synthetic Discharge Summary Generation, Deep Learning Model Training, Evaluation Metrics, Processing MIMIC-IV
    - Clearly mark Problem 1 methodology as proposed but not fully executed
    - Preserve all mathematical notation, equations, and algorithmic details from both reports
    - Verify the data leakage subsection and 24-hour window rationale subsection are preserved (addresses advisor feedback)
    - Prefix Old Report labels with `p1:`
    - _Requirements: 5.1, 5.2, 5.3, 9.1, 9.2, 10.1, 10.2, 10.3, 13.1, 13.2, 14.2_

- [x] 8. Checkpoint — Verify Chapters 3–4
  - Ensure all content is preserved, labels are unique, mathematical notation is intact, and advisor feedback items on data leakage and 24-hour window are addressed. Ask the user if questions arise.

- [x] 9. Chapter 5: Unified Dataset Understanding and EDA
  - [x] 9.1 Read source content for dataset understanding
    - Read `Old_project_feb_2025_thesis_folder/thesis/2-mainmatter/chapters/chap-dataset-understanding.tex` to extract MIMIC-IV ICD coding dataset content
    - Read `tex files/IIT_Madras_MTech_in_Industrial_AI_Thesis_Template/2-mainmatter/chapters/chap-5-dataset-understanding.tex` to understand current structure
    - _Requirements: 6.1, 6.2_

  - [x] 9.2 Merge dataset understanding chapter
    - Preserve ALL existing Current Report EDA content verbatim as "Part II: SA-AKI Cohort (Problem 2)" (Source Tables, Ontology-Driven Concepts, Cohort Construction/CONSORT, Clinical Labeling, Timeline Conventions, Data Harmonization, Statistical Validation, Missing Data, Phenotyping)
    - Add "Part I: MIMIC-IV for ICD Coding (Problem 1)" section from Old Report with subsections: Overview of MIMIC-IV, SQL Query Results, Visual Explorations (all 10 plots referencing `mimic_plots/plotN.jpg`), Key Insights, Final Data Preparation
    - Update figure paths in Old Report content to reference `mimic_plots/` relative to thesis root
    - Preserve all figures, tables, and their references from both reports
    - Prefix Old Report labels with `p1:`
    - _Requirements: 6.1, 6.2, 6.3, 13.1, 13.2, 14.2, 14.4, Property 4_

- [x] 10. Chapter 6: Unified Results
  - [x] 10.1 Read source content for results
    - Read `Old_project_feb_2025_thesis_folder/thesis/2-mainmatter/chapters/chap-results.tex` to extract ICD coding partial results
    - Read `tex files/IIT_Madras_MTech_in_Industrial_AI_Thesis_Template/2-mainmatter/chapters/chap-6-results.tex` to understand current structure
    - _Requirements: 7.1, 7.2_

  - [x] 10.2 Merge results chapter
    - Preserve ALL existing Current Report results content verbatim as "Problem 2: SA-AKI Mortality Prediction Results" (Model Benchmarking, LightGBM Performance, Confusion Matrix/ROC, SHAP, "Why LightGBM Outperforms", "Evidence for Trustworthiness", Comparison Table, External Validation Limitations, CoxPH Results, DeepSurv Results, Calibration/DCA, Survival Synthesis)
    - Add "Problem 1: ICD Coding Partial Results" section from Old Report with subsections: KNN Baseline (Macro F1 0.12), MinHash Similarity Detection, Key Observations/Challenges, Rare Disease Co-Occurrence Pipeline
    - Note that full model training and synthetic data generation were not completed due to infrastructure costs
    - Verify "Why LightGBM Outperforms" and "Evidence for Trustworthiness" subsections are preserved (addresses advisor feedback)
    - Verify comparison table with prior studies (Chen 2025, Li 2023, Hu 2021) is preserved
    - Preserve all figures, tables, and references from both reports
    - Prefix Old Report labels with `p1:`
    - _Requirements: 7.1, 7.2, 7.3, 11.1, 11.2, 11.3, 11.4, 13.1, 13.2, 14.2_

- [x] 11. Checkpoint — Verify Chapters 5–6
  - Ensure all content is preserved, all figures render with correct paths, advisor feedback on LightGBM is addressed, and labels are unique. Ask the user if questions arise.

- [x] 12. Chapter 7: Unified Conclusions and Future Work
  - [x] 12.1 Read source content for conclusions
    - Read `Old_project_feb_2025_thesis_folder/thesis/2-mainmatter/chapters/chap-conclusion.tex` to extract ICD coding conclusions
    - Read `tex files/IIT_Madras_MTech_in_Industrial_AI_Thesis_Template/2-mainmatter/chapters/chap-7-conclusions.tex` to understand current structure
    - _Requirements: 8.1, 8.2_

  - [x] 12.2 Merge conclusions chapter
    - Preserve ALL existing Current Report conclusions content verbatim: four key contributions (cohort construction, leakage-aware preprocessing, interpretable predictive modeling with metrics, dynamic risk assessment with survival analysis)
    - Add "Summary of Problem 1: ICD Code Prediction" section summarizing completed work (literature review, problem formulation, dataset understanding, preliminary results) and noting incomplete work (synthetic data generation, full model training) due to infrastructure costs
    - Create unified "Future Work" section with two subsections:
      - "Problem 1: Remaining Steps" — completing synthetic data generation and model training when infrastructure available
      - "Problem 2: Future Directions" — preserve ALL existing future work items verbatim (External Validation, Monte Carlo Simulation, Multi-Database Risk Framing, Temporal Windows, Model Fairness, Prospective Clinical Impact Study)
    - Verify Monte Carlo simulation and multi-database risk framing items are preserved (addresses advisor feedback)
    - Prefix Old Report labels with `p1:`
    - _Requirements: 8.1, 8.2, 8.3, 12.1, 12.2, 13.1, 13.2, 14.2_

- [x] 13. Final Verification
  - [x] 13.1 Content preservation check
    - For each chapter, verify that every `\section`, `\subsection`, `\begin{equation}`, `\begin{table}`, `\begin{figure}`, `\label{}`, and `\caption{}` from the original Current Report files appears in the merged files
    - _Requirements: 13.1, Property 1_

  - [x] 13.2 Label uniqueness check
    - Scan all merged `.tex` files for `\label{...}` definitions and verify no duplicates exist
    - _Requirements: 14.2, Property 3_

  - [x] 13.3 Citation key check
    - Extract all `\cite{}` and `\citep{}` keys from all merged `.tex` files and verify each key exists in the merged `references.bib`
    - _Requirements: 2.6, 3.4, Property 2_

  - [x] 13.4 Figure path check
    - Extract all `\includegraphics{...}` paths from all merged `.tex` files and verify the referenced files exist on disk relative to `tex files/IIT_Madras_MTech_in_Industrial_AI_Thesis_Template/`
    - _Requirements: 14.4, Property 4_

  - [x] 13.5 LaTeX syntax review
    - Review all modified files for valid LaTeX syntax: matched braces, proper `\begin`/`\end` pairs, correct `\input` paths in thesis.tex
    - _Requirements: 14.1_

- [x] 14. Final checkpoint — Compilation readiness
  - Ensure all checks pass. Recommend the user run `latexmk` or `pdflatex` + `bibtex` to compile the merged thesis and verify zero errors. Ask the user if questions arise.

## Notes

- Each chapter merge task preserves the Current Report content verbatim and adds Old Report content as new sections
- Old Report labels are prefixed with `p1:` to avoid conflicts with Current Report labels
- The merge follows Problem 1 (ICD) / Problem 2 (SA-AKI) framing throughout
- Advisor feedback items (data leakage, 24-hour window, LightGBM justification, Monte Carlo, multi-database framing) are already addressed in the Current Report content and are preserved during merge
- Checkpoints are placed after every 2 chapters to allow incremental verification
