# NMA_PKU
# Network Meta-Analysis of Interventions for Phenylketonuria (PKU)

## Overview
This repository contains the data and R scripts used to perform a **frequentist network meta-analysis (NMA)** evaluating the effectiveness of dietary, pharmacological, and adjunctive interventions for reducing blood phenylalanine (Phe) levels in individuals with phenylketonuria (PKU).

The analysis was conducted using the **`netmeta`** package in R and follows methodological standards consistent with **Cochrane Handbook guidance** for network meta-analysis.

---

## Objectives
To compare and rank the effectiveness of:
- Dietary interventions (e.g., phenylalanine-restricted diet, CGMP, LNAA)
- Pharmacological therapies (e.g., sapropterin, sepiapterin, pegvaliase)
- Adjunctive strategies (e.g., adherence optimization)

on blood phenylalanine levels in patients with PKU.

---

## Repository Structure

#Under construction


---

## Data Description

The dataset (`NMA_PKU.xlsx`) includes:

- `study`: Study identifier  
- `design`: Study design (RCT or crossover)  
- `treat1`, `treat2`: Interventions compared  
- `TE`: Treatment effect (mean difference)  
- `seTE`: Standard error of the effect  
- `n.trts`: Total number of participants per study  

### Notes on Study Designs
- **Crossover trials** were included using **paired effect estimates (TE and seTE)**.
- For descriptive summaries, participants in crossover and multi-arm trials were counted **once per treatment exposure**, but **only once globally**.
- Multi-arm studies (e.g., Yano_2016) were handled to avoid double counting of participants.

---

## Methods

### Statistical Approach
- **Frequentist network meta-analysis**
- Package: `netmeta` (R)
- Effect measure: Mean Difference (MD)
- Model: Random-effects
- Between-study variance estimator: REML

### Reference Comparator
- Phenylalanine-restricted diet

### Assumptions Assessed
- **Transitivity**: Evaluated based on study and population characteristics
- **Consistency/Inconsistency**:
  - Local: SIDE (back-calculation method)
  - Global: SIDDE approach

### Outputs Generated
- Network graph
- League table
- Forest plots
- Inconsistency assessment
- Treatment ranking (SUCRA, rankograms)

---

## Reproducibility

### Requirements
- R (≥ 4.0 recommended)
- Packages:
  - `netmeta`
  - `readxl`
  - `writexl`

### How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/NMA-PKU.git
   cd NMA-PKU
