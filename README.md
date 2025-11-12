---
title: "README"
author: "LinjunZeng"
date: "2025-11-12"
output: html_document
---

## Description
Single-Cell RNA-Seq Analysis Pipeline is an open-source R package for automated cell type identification and analysis in contact zone tissues. The pipeline performs comprehensive single-cell RNA sequencing data analysis including quality control, normalization, integration, doublet detection, clustering, and cell type annotation, enabling comparative analysis between contact zones and non-contact zones.


## Installation
This analysis pipeline requires the following R packages:
```{r cars}
# CRAN packages
install.packages(c("tidyverse", "Seurat", "patchwork", "devtools"))

# Bioconductor packages
if (!require("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
BiocManager::install(c("scDblFinder", "clusterProfiler", "org.Mm.eg.db", 
                      "org.Hs.eg.db", "msigdbr", "enrichplot", 
                      "glmGamPoi", "ComplexHeatmap"))
```

## Examples
The main analysis workflow is contained in the Rmarkdown file Single-Cell RNA-Seq Analysis Pipeline Cell Type Identification in ContactZones.Rmd. Key steps include:
Data loading and quality control
Normalization and integration using SCTransform
Doublet detection with scDblFinder
Cell clustering and marker gene identification
Cell type annotation based on canonical markers

## References
[1] Hao Y, Hao S, Andersen-Nissen E, Mauck WM 3rd, Zheng S, Butler A, Lee MJ, Wilk AJ, Darby C, Zager M, Hoffman P, Stoeckius M, Papalexi E, Mimitou EP, Jain J, Srivastava A, Stuart T, Fleming LM, Yeung B, Rogers AJ, McElrath JM, Blish CA, Gottardo R, Smibert P, Satija R. Integrated analysis of multimodal single-cell data. Cell. 2021 Jun 24;184(13):3573-3587.e29. doi: 10.1016/j.cell.2021.04.048.
[2] Germain PL, Lun A, Garcia Meixide C, Macnair W, Robinson MD. Doublet identification in single-cell sequencing data using scDblFinder. F1000Res. 2021 Sep 28;10:979. doi: 10.12688/f1000research.73600.2.



