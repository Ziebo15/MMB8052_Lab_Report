# Assignment 2 – RNA-seq Lab Report  
**MMB8052 – Bioinformatics for Biomedical Scientists**

**Author:** Olaf Adam Zieba  
**Student Number:** 220157214  
**Submission Date:** 23 January 2026  

---

## Overview

This repository contains the code used for Assignment 2 – RNA-seq Lab Report as part of the MMB8052 Bioinformatics for Biomedical Scientists module. The analysis investigates transcriptional changes following reperfusion by comparing RNA-seq profiles at 2 hours and 24 hours post-treatment against naïve control cells.

The workflow performs differential gene expression analysis using DESeq2, with transcript-level quantification imported using tximport. The analysis includes exploratory data analysis, statistical testing, and biological interpretation through multiple visualisation approaches.

---

## Data and Input Files

RNA-seq count data were generated from the GSE116583 dataset. Raw count files are not included in this repository and must be downloaded separately.

The count data can be downloaded from the following URL and unzipped to create a folder called `counts/` in the working directory:

https://github.com/sjcockell/mmb8052/raw/main/practicals/practical_08/results/counts.zip

Once unzipped, the working directory should contain the `counts/` folder before running the analysis script in RStudio.

Sample metadata and transcript-to-gene mapping files are downloaded automatically by the script.

Sample metadata:
https://raw.githubusercontent.com/sjcockell/mmb8052/main/practicals/practical_08/data/sample_table.csv

Transcript-to-gene mapping file:
https://github.com/sjcockell/mmb8052/raw/main/practicals/practical_08/extdata/gene_map.csv

---

## Analysis Performed

Differential expression analysis is performed using DESeq2 for the following comparisons:

- 2 hours vs naïve control cells  
- 24 hours vs naïve control cells  

Data quality and biological signal are explored using dispersion plots and principal component analysis (PCA). Differentially expressed genes are visualised using heatmaps and volcano plots, and Gene Ontology (GO) enrichment analysis is performed to support biological interpretation of transcriptional changes.

All figures are generated interactively within R and displayed in the R plotting window. Figures are not automatically saved to files.

---

## Software and Environment

R version 4.4.1  
Run via RStudio  

---

## Required R Packages

CRAN packages:

install.packages("tidyverse")  
install.packages("ggrepel")  
install.packages("viridis")  
install.packages("BiocManager")  

Bioconductor packages:

BiocManager::install(c(
  "tximport",
  "DESeq2",
  "biomaRt",
  "pheatmap",
  "clusterProfiler",
  "org.Mm.eg.db"
))

---

## How to Run the Analysis

Download and unzip the RNA-seq count data so that a `counts/` directory exists in the working directory.

Install and load all required R packages.

Set the working directory in RStudio to the folder containing the `counts/` directory and analysis script.

Run the analysis script from top to bottom in RStudio.

Running the full script will reproduce all analyses and visualisations included in the accompanying report.

---

## Repository Contents

Assessment2_RNASeq.R – Main RNA-seq analysis script  
README.md – Project documentation  

---

## Notes

Large data files are excluded from version control to avoid unnecessary upload of raw sequencing data. All analyses are fully reproducible using the provided script and publicly available input files.

