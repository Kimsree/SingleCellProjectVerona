# SingleCellProjectVerona (a Multi-Omics Single Cell Analysis Project)

```
Archivage d'un projet que j'ai fait en italie

manque le fichier CHETAH_TME_reference.Rdata pour chetah.
```
A comprehensive single-cell multi-omics analysis workflow for preprocessing, quality control, cell annotation, cell-cell communication analysis, and trajectory inference.

This project provides an end-to-end analysis pipeline for single-cell datasets using state-of-the-art R packages, allowing researchers to explore cellular heterogeneity, identify cell populations, investigate intercellular communication, and reconstruct developmental trajectories.

---

## Overview

The workflow includes:

- Quality control and filtering
- Data normalization
- Dimensionality reduction
- Clustering analysis
- Doublet detection
- Cell type annotation
- Cell-cell communication analysis
- Cell cycle analysis
- Trajectory inference

The pipeline is designed for reproducible and scalable analysis of single-cell multi-omics datasets.

---

## Features

- Comprehensive preprocessing workflow
- Automated cell type annotation
- Doublet identification
- Cell cycle analysis
- Ligand-receptor interaction analysis
- Cell-cell communication inference
- Pseudotime and trajectory reconstruction
- Integration of multiple annotation approaches

---

## Workflow

```
Raw Data
    ↓
Quality Control
    ↓
Normalization
    ↓
Dimensionality Reduction
    ↓
Clustering
    ↓
Doublet Detection
    ↓
Cell Type Annotation
    ↓
Cell-Cell Communication Analysis
    ↓
Trajectory Inference
```

## Analysis Steps
1. Quality Control

Initial filtering is performed to remove:

Low-quality cells
Cells with low feature counts
Potential dead or damaged cells
Technical artifacts

Quality metrics are evaluated before downstream analyses.

2. Normalization

The data are normalized to reduce technical variability and prepare the dataset for downstream analyses.

3. Dimensionality Reduction

Low-dimensional representations are generated to visualize cellular heterogeneity and identify biological structure within the dataset.

Methods commonly include:

PCA
UMAP
t-SNE

4. Clustering

Cells are grouped into clusters according to their transcriptional profiles, enabling the identification of distinct cell populations.

5. Doublet Detection

Potential doublets are identified and removed to improve the accuracy of downstream analyses.

6. Cell Type Annotation

Multiple annotation approaches are used:

SingleR

Reference-based annotation using external reference datasets.

BlueprintEncodeData

Reference atlas used for automated cell identification.

CHETAH

Hierarchical cell type identification for improved annotation accuracy.
need to download it from : https://figshare.com/s/aaf026376912366f81b6

7. Cell Cycle Analysis

Cell cycle phase assignment is performed to identify:

G1 phase cells
S phase cells
G2/M phase cells

This information can be incorporated into downstream analyses.

8. Cell-Cell Communication Analysis

Intercellular communication networks are explored to identify:

Signaling pathways
Ligand-receptor interactions
Sender and receiver cell populations

The analysis particularly investigates signaling interactions involving CD4 T cells and other cellular populations.

9. Trajectory Inference

Developmental trajectories and pseudotime relationships are reconstructed to study dynamic cellular processes.

The workflow uses trajectory inference methods to identify:

Cellular transitions
Developmental pathways
Lineage relationships

---

## Main R Packages

|Package |	Purpose |
| ----------- | ----------- |
|Seurat	Single-cell | data processing and visualization|
|SingleR |	Automated cell annotation|
|CHETAH |	Cell type identification|
|CellChat |	Cell-cell communication analysis|
|Slingshot |	Trajectory inference|
|SingleCellExperiment |	Data structure for single-cell analyses|

---
## Installation

required to have the CHETAH_TME_reference.Rdata file from :  https://figshare.com/s/aaf026376912366f81b6

Install the required packages in R:
```
install.packages(c("Seurat"))

if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

BiocManager::install(c(
    "SingleR",
    "celldex",
    "SingleCellExperiment",
    "slingshot"
))
```

Additional packages may be required depending on the analysis modules.

---

## Example Analyses

Identification of cellular populations
Annotation of immune and stromal cells
Analysis of CD4 T-cell interactions
Detection of significant ligand-receptor pairs
Reconstruction of cellular trajectories
Investigation of differentiation processes

---

## Project Structure

```
project/
│
├── NSCLC_donor_7_count_sample_feature_bc_matrix/sample_feature_bc_matrix/
                                                ├── barcodes.tsv.gz
                                                ├── features.tsv.gz
                                                └── matrix.mtx.gz
├── CHETAH_TME_reference.Rdata (missing download it from: https://figshare.com/s/aaf026376912366f81b6)
├── projetCode.html
├── projetCode.Rmd
└── README.md
```
---

## Authors

Sreevatsa
Akshaya
