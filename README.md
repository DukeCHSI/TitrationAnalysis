# <em>TitrationAnalysis</em>
Tools for high throughput binding kinetics data analysis
# Overview
This repository contains the necessary files to install and execute the first version of <em>TitrationAnalysis</em> package (<em>TitrationAnalysis</em> v1.0).
# Description
# Getting Started
## Installation
Open the package file (with extension “.m”) in Mathematica. Go to **File → Install**, and install the package as shown in the image below and click “OK”. For Mathematica 13.0 and above, please use the corresponding version contained in this repository.

<p align="center">
<img src="Graphics for README/Installation illustration 2023May.png" width="300"/>
</p>

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
After choosing the sample information sheet, the user will be asked to type in the prefix for all the chip – channel combinations. The prefix for the example data set is shown in the image below. The module will attempt to read in the data based on this prefix to find all the chip – channel combinations indicated in the information sheet. Note that the content of the exported data needs to match what is indicated in the info sheet. Otherwise the module will not proceed.

<p align="center">
<img src="Graphics for README/T200 Example Prefix 2023May.PNG" width="250"/>
</p>

Then the user will be asked to provide the data collection frequency for appropriate data thinning. If “10Hz” is chosen, then only one data point per second will be chosen for further analysis. If “1Hz” is chosen, then no data thinning will occur.

<p align="center">
<img src="Graphics for README/T200 Example Frequency 2023May.PNG" width="250"/>
</p>

After making a few more selections for global analysis settings, the module will proceed to automatically analyze each sensorgram and generate output files. For the example file, please use default selections for all settings. As shown in the example information sheet, for the same sensorgram, multiple fitting optimizations can be included in the information sheet and implemented during analysis.

### Running analysis for BLI platform
After choosing the sample information sheet, the user will be asked to type in the prefix for all the tray – sensor combinations. The prefix for the example data set is shown in the image below. The module will attempt to read in the data based on this prefix to find all the tray – sensor combinations indicated in the information sheet. Note that the content of the exported data needs to match what is indicated in the info sheet. Otherwise the module will not proceed.

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
This project is licensed under the GNU GPLv3 license. Please see LICENSE.md file for details.
