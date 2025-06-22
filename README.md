
# RNA-seq Differential Expression and Enrichment Analysis Tutorial (Airway Dataset)

This repository contains a comprehensive **RNA-seq analysis pipeline** implemented in R Markdown using the publicly available **airway** dataset. The tutorial demonstrates a full analysis workflow from raw count processing to differential gene expression and functional enrichment.

## Overview

This tutorial guides users through:

- Preparing and exploring RNA-seq data
- Filtering, normalization, and variance stabilization
- Differential gene expression analysis 
- Visualization of results (PCA, MA plots, volcano plot, heatmaps)
- Annotation of differentially expressed genes
- Over-representation analysis (ORA) and Gene Set Enrichment Analysis (GSEA)
- Reducing redundancy in GO terms using semantic similarity (`simplify()`)
- Enrichment analysis for KEGG and Disease Ontology

## Dataset

The tutorial uses the `airway` dataset from Bioconductor, which includes RNA-seq data from human airway smooth muscle cells treated with dexamethasone.

- Source: [Bioconductor airway package](https://bioconductor.org/packages/airway)
- Design: Treated vs. untreated (control) samples
- Organism: Homo sapiens (human)

## Required Packages

- Make sure to install all bioconductor and CRAN packages before running the tutorial

## How to Use

### 1. Clone the Repository

```bash
git clone https://github.com/caparada/RNAseq_airway_tutorial.git
cd RNAseq_airway_tutorial
```
📘 **Or skip to the interactive HTML tutorial here**:  
➡️ [RNA-seq Pipeline – GitHub Pages](https://caparada.github.io/RNAseq/)

### 2. Open and Run the Tutorial

Open `RNAseq_Pipeline_airway.Rmd` in RStudio, then click **Knit** to generate the HTML output. Alternatively, run:

```r
rmarkdown::render("RNAseq_Pipeline_airway.Rmd")
```

### 3. Output Directory

The pipeline creates an output directory (`RNAseq_results/`) in your working dir to save plots and tables, including:

- PCA, MA, volcano, and heatmap plots
- Annotated DE gene tables
- Enrichment results for GO, KEGG, and DO
- GSEA/DO/GO dotplots and simplified outputs

### Project Structure

```
RNAseq_airway_tutorial/
├── RNAseq_Pipeline_airway.Rmd     # Main R Markdown tutorial
├── RNAseq_results/                # Output folder for plots and tables
└── README.md                      # This file
```

## Methods Summary

| Step                            | Method / Package           |
|---------------------------------|----------------------------|
| Data import                     | `airway`, `SummarizedExperiment` |
| Filtering, EDA & normalization  | `edgeR`, `DESeq2`, `vsn` |
| DGE analysis                    | `DESeq2`, `clusterProfiler`, `DOSE` |
| Annotation                      | `AnnotationDbi`, `org.Hs.eg.db` |
| Visualization                   | `ggplot2`, `pheatmap`, `ggrepel`, `clusterProfiler` |
| More Visualization              | `EnhancedVolcano`, `scales`, `viridis` |
| Interactivity                   | `plotly` |
| Enrichment analysis             | `clusterProfiler`, `DOSE`, `GOSemSim`, `enrichplot` |
| Redundancy reduction (GO)       | `simplify()` from `clusterProfiler` |
| Statistics & Data Manipulation  | `stats`, `tidyverse` |


## Acknowledgments

- Data: [airway package](https://bioconductor.org/packages/airway)
- Packages: Bioconductor and CRAN community
- Tutorial created by: Carolina Parada

---

**Feel free to fork this repo and adapt it to your own dataset.**
