# <em>TitrationAnalysis</em>
A tool for high throughput binding kinetics data analysis
# Notes
The user might experience unexpected glitches with PDF file generation when using the package on Mathematica 13.3, due to changes in how the software handles dynamic updating. In this particular Mathematica version, the page break needs to be calculated for a prolonged period of time and the users are prompted to confirm that they are waiting for the page break calculation to finish every minute or so and they need to manually click a button to proceed.

The script as it stands will not will for Mathematica 14.1. This is being actively investigated.

# Overview
This repository contains the necessary files to install and execute the first version of <em>TitrationAnalysis</em> package (<em>TitrationAnalysis</em> v1.0).

<!-- Please cite the repository as the following: Li K, Dennison SM. <em>TitrationAnalysis</em> tool [Computer Software] (2023). -->
Please cite the repository as the following: Li, Kan, & Dennison, S Moses. (2023). <em>TitrationAnalysis tool</em> (v1.0.0). Zenodo. https://doi.org/10.5281/zenodo.7998652

Alternatively, please cite: Li K, Huntwork RHC, Horn GQ et al. <em>TitrationAnalysis</em>: a tool for high throughput binding kinetics data analysis for multiple label-free platforms [version 1; peer review: awaiting peer review]. Gates Open Res 2023, 7:107 (https://doi.org/10.12688/gatesopenres.14743.1)
# Description
The <em>TitrationAnalysis</em> tool is intended for the high-throughput analysis of binding kinetics data collected on multiple platforms. Currently, the <em>TitrationAnalysis</em> tool supports the analysis of data exported from Carterra LSA (SPRi), Biacore T200 (SPR) and ForteBio Octet Red384 (BLI).

The <em>TitrationAnalysis</em> tool is currently built as a Mathematica<sup>:tm:</sup> package. The package was built on Mathematica 12.0 and adapted for Mathematica 13.0. After the package installation, most of the user interactions will be guided by pop-up windows within Mathematica.

# Getting Started
## Installation
Open the package file (with extension “.m”) in Mathematica<sup>:tm:</sup>. Go to **File → Install**, and install the package as shown in the image below and click “OK”. For Mathematica 13.0 and above, please use the corresponding version contained in this repository. Some of the later updates in Mathematica 12th version, such as Mathematica 12.3, might require package adapted for Mathematica 13.0 as well.

<p align="center">
<img src="Graphics for README/Installation illustration 2023May.png" width="300"/>
</p>

Note 1: For successful installation, please open the package file first in Mathematica and then select the opened package file as “source” during installation. Although the package file can be selected through pop-up file explorer window without first opening the package in Mathematica first, the installation by this method was found not always successful.

Note 2: The version number the package file name ends in refers to the version of Mathematica the corresponding code is suitable for. For example, the package file with name ending in “V12” is suitable to be used in Mathematica V12.0 or similar versions.

## Execution
### Basic command
The command **Get["KineticsToolkit`"]** can be used to call the package. Then the module corresponding to one of the platforms can be called, as shown in the image below.

<p align="center">
<img src="Graphics for README/Package Calling 2023May.PNG" width="450"/>
</p>

Upon executing the command for the desired module, the user will be asked to select the sample information sheet, as shown in the image blow. Click “Open” after selecting. The package will check if there is any necessary correction to be made in the information sheet. If all information appears to be correct, the module will proceed to the next step.

<p align="center">
<img src="Graphics for README/Platform Calling 2023May.PNG" width="450"/>
</p>

### Example files
The example files are provided for each of the platform in the following directories: Example Files – Carterra, Example Files – T200 and Example Files – BLI.

#### Carterra Example Input Files
<em>Sample Information Sheet</em>: Example Data Info Sheet - Carterra.xlsx

<em>Sample Exported Data</em>: Example Exported Data - Carterra.xlsx (Currently in a multi-part zipped file due to the large file size, please use applications such as 7-zip to re-combine the zipped file and extract the excel file inside)
#### Carterra Example Output Files
<em>Sample Fitted Sensorgrams Report</em>: Titration Analysis_Carterra_Sensorgram_Example.pdf

<em>Sample Kinetics Estimates Report</em>: Titration Analysis_Carterra_Report_Example.csv
#### T200 Example Input Files
<em>Sample Information Sheet</em>: Example T200 Data Info Sheet.xlsx

<em>Sample Exported Data</em>: Example T200 Chip 1 Channel 2.txt
#### T200 Example Output Files
<em>Sample Fitted Sensorgrams Report</em>: Titration Analysis_T200_Sensorgram_Example.pdf

<em>Sample Kinetics Estimates Report</em>: Titration Analysis_T200_Report_Example.csv
#### BLI Example Input Files
<em>Sample Information Sheet</em>: Example Data Info Sheet - BLI.xlsx

<em>Sample Exported Data</em>: BLI Example Tray 1 (Folder containing multiple text files, currently contained in a zipped file, please extract the folder inside)
#### BLI Example Output Files
<em>Sample Fitted Sensorgrams Report</em>: Titration Analysis_BLI_Sensorgram_Example.pdf

<em>Sample Kinetics Estimates Report</em>: Titration Analysis_BLI_Report_Example.csv
### Running analysis for Carterra platform
After choosing the sample information sheet, the user will be asked to either keep ordering samples based on the information sheet or order the sample sequentially from A1 to H12 (96 well plate positions), as shown in the image below. Usually information sheet sorting is desired.

<p align="center">
<img src="Graphics for README/Sorting Choice 2023May.PNG" width="300"/>
</p>

Then the user will be asked to select a file containing the exported Carterra data, as shown in the image below. Note that the content of the exported data needs to match what is indicated in the info sheet. Otherwise the module will not proceed.

<p align="center">
<img src="Graphics for README/Choose Carterra Data 2023May.PNG" width="450"/>
</p>

After making a few more selections for global analysis settings, the module will proceed to automatically analyze each sensorgram and generate output files. For the example file, please use default selections for all settings.

### Running analysis for T200 platform
After choosing the sample information sheet, the user will be asked to type in the prefix for all the chip – channel combinations. The prefix for the example data set is shown in the image below (Please type **exactly** as the image shows to match the example input file). The module will attempt to read in the data based on this prefix to find all the chip – channel combinations indicated in the information sheet. Note that the content of the exported data needs to match what is indicated in the info sheet. Otherwise the module will not proceed.

<p align="center">
<img src="Graphics for README/T200 Example Prefix 2023May.PNG" width="250"/>
</p>

Then the user will be asked to provide the data collection frequency for appropriate data thinning. If “10Hz” is chosen, then only one data point per second will be chosen for further analysis. If “1Hz” is chosen, then no data thinning will occur.

<p align="center">
<img src="Graphics for README/T200 Example Frequency 2023May.PNG" width="250"/>
</p>

After making a few more selections for global analysis settings, the module will proceed to automatically analyze each sensorgram and generate output files. For the example file, please use default selections for all settings. As shown in the example information sheet, for the same sensorgram, multiple fitting optimizations can be included in the information sheet and implemented during analysis.

### Running analysis for BLI platform
After choosing the sample information sheet, the user will be asked to type in the prefix for all the tray – sensor combinations. The prefix for the example data set is shown in the image below (Please type **exactly** as the image shows to match the example input file). The module will attempt to read in the data based on this prefix to find all the tray – sensor combinations indicated in the information sheet. Note that the content of the exported data needs to match what is indicated in the info sheet. Otherwise the module will not proceed.

<p align="center">
<img src="Graphics for README/BLI Example Prefix 2023May.PNG" width="250"/>
</p>

Then the user will be asked to provide the data collection frequency for appropriate data thinning. If “5Hz” is chosen, then only one data point per second will be chosen for further analysis. If “1Hz” is chosen, then no data thinning will occur.

<p align="center">
<img src="Graphics for README/BLI Example Frequency 2023May.PNG" width="250"/>
</p>

After making a few more selections for global analysis settings, the module will proceed to automatically analyze each sensorgram and generate output files. For the example file, please use default selections for all settings. As shown in the example information sheet, for the same sensorgram, multiple fitting optimizations can be included in the information sheet and implemented during analysis.

### Stopping analysis
If the analysis needs to be stopped for any reason, go to **Evaluation → Abort Evaluation** to stop code execution.
# Version history
Version 1.0: initial release
# Help
If you need help or have suggestions, feel free to contact Kan Li via email at kl122@duke.edu. You may also communicate through GitHub Discussions.
# Author
Code was developed by Kan Li (kl122@duke.edu).
Other contributors to code development include Georgia D. Tomaras, Gillian Q. Horn and S. Moses Dennison (moses.sekaran@duke.edu).
# License
This project is licensed under the CC-BY-4.0 license. Please see LICENSE.md file for details.

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.7998652.svg)](https://doi.org/10.5281/zenodo.7998652)
