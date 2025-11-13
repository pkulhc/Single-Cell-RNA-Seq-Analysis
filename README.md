
## Description
Single-Cell RNA-Seq Analysis Pipeline is an open-source R package for automated cell type identification and analysis in contact zone tissues. The pipeline performs comprehensive single-cell RNA sequencing data analysis including quality control, normalization, integration, doublet detection, clustering, and cell type annotation, enabling comparative analysis between contact zones and non-contact zones.

1. System Requirements
Software Dependencies and Operating Systems
•	Operating System (OS): No specific restrictions (we used Windows 11)
•	Software Dependencies:
o	R (Version >= 4.0.0)
o	(Optional) RStudio (Version >= 2022.07.0)
Tested Environments
•	This script has been successfully tested on Windows 11 using R 4.2.1 and RStudio 2022.12.0.
Non-Standard Hardware
•	No non-standard hardware is required.
________________________________________
2. Installation Guide
Instructions
1.	Install R: Download and install R (version >= 4.0.0) from the CRAN website.
2.	(Optional) Install RStudio: Download and install RStudio Desktop from the RStudio website (Recommended).
Typical Install Time
•	On a "normal" desktop computer with a good internet connection, downloading and installing R and RStudio takes approximately 5-10 minutes.
________________________________________
3. Demo
Instructions to Run on Data
You can directly modify the file paths in the code to run it on your dataset.
1.	Download or clone this project to your local machine.
2.	Open RStudio, and go to "File" -> "Open File..." to open the [your_script.R] file.
3.	In RStudio, set the working directory to the script's location by navigating to "Session" -> "Set Working Directory" -> "To Source File Location". (This is important so the script can find [demo_data.csv]).
4.	Click the "Source" button in the top-right of the RStudio editor (or type source('[your_script.R]') in the console) to execute the entire script.
Expected Output
•	After the script finishes execution, the console window will display the results.
Expected Run Time
•	On a "normal" desktop computer, running this demo script (including loading data and generating the plot) is expected to take less than 5 minutes.
________________________________________
4. Instructions for Use
How to Run the Software on Your Data
•		No special requirements; a standard dataset can be used.
1.	Prepare your own data file (e.g., my_data.csv).
Important: Ensure your data file has the same column names and data types as [demo_data.csv] for the script to work correctly.
2.	Place your data file (my_data.csv) in the same folder as [your_script.R].
3.	Open [your_script.R] in a text editor or RStudio.
4.	Locate the line of code (around line [XX]) that reads the data:
R
data <- read.csv("[demo_data.csv]")
5.	Modify it to point to your new file:
R
data <- read.csv("my_data.csv")
6.	(If needed) Adjust other parameters, such as the output file name:
R
ggsave("[output_plot.png]")
ggsave("my_custom_plot.png")
7.	Run the script again as described in the "3. Demo" section.



## Installation
This analysis pipeline requires the following R packages:
```{r cars}
CRAN packages
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



