# RNA-seq Analysis: NR3C2/MR Expression in Aging Skin Fibroblasts

## Overview
This project analyzes RNA sequencing data from human skin fibroblasts to compare 
the expression of NR3C2 (Mineralocorticoid Receptor / MR) between young and aged donors.

## Dataset
- **GEO Accession:** GSE226189
- **Tissue:** Primary skin fibroblasts
- **Species:** Human
- **Samples:** 61 total (27 Young ≤40 years | 34 Aged ≥60 years)

## Key Finding
NR3C2/MR shows a trend toward higher expression in aged skin fibroblasts 
(log2FC = +0.484, p = 0.012) but does not reach statistical significance 
after multiple testing correction (padj = 0.931), likely due to 
high inter-individual variability.

## Pipeline Steps
1. Data download from NCBI GEO using GEOquery
2. Sample grouping by age (Young ≤40 vs Aged ≥60)
3. Count matrix construction from 82 individual sample files
4. Low-count gene filtering (25,985 genes retained)
5. Differential expression analysis with DESeq2
6. Visualization — boxplot, volcano plot, heatmap

## Tools & Packages
| Package | Purpose |
|---------|---------|
| GEOquery | Download GEO datasets |
| DESeq2 | Differential expression analysis |
| ggplot2 | Visualization |
| ggrepel | Volcano plot labels |
| pheatmap | Heatmap generation |
| tidyverse | Data wrangling |

## Results
| Metric | Value |
|--------|-------|
| baseMean | 467.4 |
| log2FoldChange | +0.484 (higher in Aged) |
| p-value | 0.012 |
| adjusted p-value | 0.931 |

## Plots
### NR3C2 Expression — Boxplot
![boxplot](results/NR3C2_boxplot.png)

### Volcano Plot
![volcano](results/volcano_plot.png)

### Heatmap — Top DE Genes
![heatmap](results/heatmap_top_genes.png)

## Author
Shahrzad Zamani
RNA-seq pipeline built with R 4.6.0 and RStudio
