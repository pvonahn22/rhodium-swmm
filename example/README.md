

# Rhodium-SWMM Example

This section provides general instructions for installing Rhodium-Swmm and running several analyses on the example model that is provided in the library.  For the steps needed to replicate the exact results and figures presented in [Rhodium-SWMM: An Open-Source Tool for Green Infrastructure Placement Under Deep Uncertainty], please follow **example/teybanian_etal_2022/README_figures.md**.


# Module Summary

* **initialize&#46;py** - Initializes the rhodium-swmm model by setting levers, responses and uncertainties and sets up directory structure for simulation
* **spatial_priorities.py** - creates a dictionary of subcatchments and their spatial priority scores 
* **data** - Directory containing all data needed for simulation
* **spatial_visualization** - Directory containing code to generate visualizations from sample simulation results

# Usage


## Building Python Virtual Environment

Clone the repository by running the following command. 

    `git clone https://github.com/julianneq/rhodium-swmm`

If you are unfamiliar with git, download a zip file of the repository by clicking on the green Code button and then unzip it.

Install Anaconda from https://www.anaconda.com/

From Anaconda Prompt, navigate to the `rhodium-swmm` directory (`cd /path/to/rhodium-swmm`)  
Then create a Python 3.10 virtual environment with:  
    `conda create python310-venv python=3.10`

Then activate this environment with:  
    `conda activate python310-venv`

Next, install the necessary Python packages with:  
    `pip install -r requirements.txt`
    `pip install git+https://github.com/julianneq/rhodium-swmm`

## optimize

Run `cd example\example_module` to move to that directory.
Run `python initialize.py` to optimize the example. Edit line 121 of `initialize.py` to use a different algorithm or NFE.

# Importing your data 

The data folder has three sub folders:

* swwm_data
<br> - swmm_input_template
* cost_benefit
* other_data



<br> 1) For your specific problem, you need to place a swmm input file (.inp) in swmm_input_template folder. 
<br> Replace the name of the swmm input template file in initizle.py with your file name. 

<br> 2) replace the CSV file of cost information for the LID types with your information in the cost_benefit folder.
<br> - Keep the file name or adjust the file name in initilize.py. Keep the column names as example files provided.

<br> 3) replace the CSV file of benefit information for the LID types with your information in the cost_benefit folder. 
<br> - Keep the file name or adjust the file name in initilize.py. Keep the column names as example files provided.

<br> 4) replace the shapefile for the SWMM input file in other_data

<br> 5) after running the optimization, place the Pareto set CSV in *other_data* and adjust the file name in *map_viz.py*


<br>
