# Quick Start Guide: MS Data Analysis Workflow

This guide gets you into analyzing DIA-NN proteomics data using R.

## Prerequisites
* **R**: Download & Install current version from https://cran.r-project.org/
* **RStudio**: Download & install current version from  https://posit.co/download/rstudio-desktop/

## Step 1: Download and Open

1. Download latest repository version by clicking the green "Code" button and selecting "Download ZIP".
2. Unzip to a folder of your choice.
3. Open RStudio -> File -> Open Projects in New Session -> select `MassSpec_ExampleWorkflow.Proj`.

The folder structure is as follows:

```
MassSpec_ExampleWorkflow/
├── MassSpec_ExampleWorkflow.Rproj     # Open this!
├── MS Data Analysis Workflow.Rmd      # Main script
├── InputData/
│   ├── Example_Raw_Data/              # Subset parquet
│   └── Example_Meta_Data/
│       └── Example_meta.csv           # Sample → group mapping
├── OutputData/                        # Generated here (empty initially)
└── .gitignore                         # Ignores large files
```

Why projects? They bundle files, set working directory, save history/settings, and help you stay organized.

## Step 2: Install packages (Run Once)

1. Within RStudio, navigate in your file manager to the Script folder and open `Install_packages.Rmd` by double-clicking.
2. Click on green triangle within {r} line.
3. It might be necessary to restart RStudio after installation is complete. You can do this by clicking on Session -> Restart R.

This installs all required packages, which may take a few minutes. You only need to do this once.

## Step 3: Run the Analysis

This workflow includes loading the data, performing quality control and pre-processing steps like filtering and normalization, and then conducting statistical analyses to identify differentially abundant proteins. Finally, it generates visualizations to help interpret the results. Important outputs, like pre-processed data and statistical results, are saved in the "Output" folder for easy access.

The workflow is organized as R-Markdown file, which combines code and narrative by allowing extensive documentation alongside the code. You can run each code chunk individually by clicking the green triangle next to it, or you can run the entire document by clicking "Run" -> "Run All".

You can also generate a nicely formatted HTML report by clicking "Knit" -> "Knit to HTML". This will execute all code chunks and compile the results into a single, easy-to-read report, which will be saved in the Scripts location.

Almost every line of code is commented to explain what it does, so feel free to read through the comments for a better understanding of each step. This example code should run without any adjustments from your side.

## Step 4: Use your own Data

It's recommended to use a new R project for analysis of your own data:

1. Copy this directory and rename it to something you'd like, e.g. `My_super_awesome_proteomics_data_analysis`.
2. Delete the .Rproj file in the new repository and create a new one by opening RStudio, click on New Project -> Existing Directory -> select your new folder.
3. Replace the example data in `InputData/Example_Raw_Data` with your own DIA-NN parquet files. Make sure to keep the same file structure and naming conventions.
4. Generate a new sample metadata file (e.g. `My_meta.csv`) that maps your samples to their respective groups, and place it in `InputData/Example_Meta_Data/`.
5. Update the file paths in the R-Markdown script to point to your new data files and metadata file.

In the script, it's highlighted where you need to make adjustments to load your own data. Once you've made these changes, you can run the analysis as described in Step 3. This sets you up for your first analysis of your own DIA-NN proteomics data! Feel free to extend the workflow with additional analyses or visualizations as needed.

## Disclaimer

This script is purposely made simple and straightforward to get your started quickly. It is not meant to be a comprehensive or optimized workflow for all types of proteomics data analysis. Depending on your specific research question and data, you may need to adjust the code, add additional steps for data processing verification, like normalization efficiency and imputation bias, or use different statistical methods. Always critically evaluate the results and consider consulting with a statistician or bioinformatician if you're unsure about any aspect of the analysis.