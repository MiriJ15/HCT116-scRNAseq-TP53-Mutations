# Single-Cell RNA-seq Analysis of HCT116 Colorectal Carcinoma Cells

This repository contains the analysis pipeline and results for the study of haploidized HCT116 colorectal carcinoma cells expressing specific TP53 mutations, treated with DMSO or Nutlin. The dataset used in this analysis is publicly available at [E-MTAB-13904](https://www.ebi.ac.uk/biostudies/arrayexpress/studies/E-MTAB-13904).

## Overview

This project investigates the heterogeneity in TP53 mutations by analyzing single-cell RNA sequencing (scRNA-seq) data. Cells were treated with either DMSO or Nutlin, and differential expression and pathway enrichment analyses were conducted to explore genetic variation and associated pathways.

## Dataset

- **Accession**: [E-MTAB-13904](https://www.ebi.ac.uk/biostudies/arrayexpress/studies/E-MTAB-13904)
- **Organism**: *Homo sapiens*
- **Cell Line**: HCT116 (Colorectal carcinoma)
- **Data Type**: scRNA-seq

## Analysis Workflow

### 1. Data Preprocessing
- **Input Data**: Processed `.h5ad` file from E-MTAB-13904.
- Performed quality control using violin plots and scatter plots.
- Filtered cells with high mitochondrial gene content and low gene counts.

### 2. Normalization and Scaling
- Normalized to 10,000 counts per cell.
- Log-transformed data.
- Scaled the data to unit variance.

### 3. Dimensionality Reduction
- Applied PCA and visualized variance ratio.
- Generated UMAP embeddings for clustering and visualization.

### 4. Clustering
- Leiden clustering applied at multiple resolutions to identify cell groups.
- Re-clustering performed for finer resolution.

### 5. Differential Gene Expression
- Identified marker genes for each cluster using the Wilcoxon test.
- Differential expression analysis between DMSO and Nutlin treatments.

### 6. Pathway Enrichment Analysis
- Conducted KEGG pathway enrichment using enriched gene lists.
- Visualized results with bar plots of combined scores for enriched pathways.

## Key Results

### Quality Control
- Retained cells with <5% mitochondrial counts and <6000 genes expressed.

### Clustering
- Identified distinct cell types, including:
  - Cycling Cells
  - Differentiating Progenitors
  - S-phase Cells
  - Stressed Cells
  - Immune Cells

### Differential Expression
- Genes upregulated in Nutlin-treated cells showed enrichment in the p53 signaling pathway.

### Pathway Enrichment
- Top enriched pathways:
  - Bladder Cancer
  - p53 Signaling Pathway
  - Melanoma

## Visualizations

### UMAPs
- Visualized cell clustering and annotations based on Leiden groups and treatments.

### Enrichment Plots
- Highlighted top enriched KEGG pathways with adjusted p-values.

## Reproducibility

### Dependencies
- Python 3.12
- Libraries: `scanpy`, `matplotlib`, `pandas`, `gseapy`

