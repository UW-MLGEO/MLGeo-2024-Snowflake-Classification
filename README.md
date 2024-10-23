# MLGEO2024_Snowflake_Classification
## Contributors: Valeria Garcia (ESS 569) and Carlos Palma Bernal (ESS 469)

This repository is for the UW-MLGEO 2024 final project.

### **Data Source:**

This project will leverage ice crystal images (in PNG format) photographed by the Particle Habit Imaging and Polar Scattering Probe (PHIPS) during the Investigation of Microphysics and Precipitation in Atlantic Coast-Threatening Snowstorms (IMPACTS) for both the training and testing datasets. IMPACTS was a NASA field campaign focused on studying winter storms during the 2020, 2022, and 2023 winter seasons (January-February), using aircraft to collect microphysical and remote sensing observations across multiple U.S. northeastern and Midwestern winter storms. Along with the ice crystal images, meteorological and navigation data from the P-3 aircraft (on which the PHIPS was onboard) will be used to provide temperature and spatial/geographic information for the ice crystals images. 

<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/IMPACTS_logo.png" alt="IMPACTS logo" width="300"> <img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/PHIPS_instrument.png" alt="PHIPS Instrument" width="425">

For curating the training dataset of this project, ice crystal images from the following flight dates were selected: 2020-02-07 (sample area: Pennslyvannia), 2022-02-17 (sample area: Illinois), 2023-01-23 (sample area: Maine), and 2023-02-14 (sample area: Minnesota). These dates were selected for the unique storm structures sampled. In-cloud sampling of these storms occurred at multiple temperature levels, ensuring a diverse assortment of ice crystal images sampled, which is a requirement for constructing a training dataset representative of many snowflake types. 

### **Registering for a NASA Earthdata Login Profile:**

To download the IMPACTS P-3 met/nav data on the NASA Global Hydrometeorology Resource (GCHR) website, an Earthdata Login profile is needed. Registering is free and can be done [here](https://urs.earthdata.nasa.gov/users/new?client_id=OLpAZlE4HqIOMr0TYqg7UQ&redirect_uri=https%3A%2F%2Fd53njncz5taqi.cloudfront.net%2Furs_callback&response_type=code&state=https%3A%2F%2Fsearch.earthdata.nasa.gov%2Fsearch%3Fq%3Dp3metnavimpacts%26ee%3Dprod)

### **Project Objectives:**
To create an AI algorithm (Convolutional Neural Network, CCN) to identify and classify thousands of high-resolution ice crystal images according to snowflake type (i.e. to create an ML-based ice crystal habit classification algorithm). The goal is for this alogorithm to replace manual snowflake classification in research studies, a tedious approach that is unreproducible and subject to human error, in order to provide an objective, reliable solution for identifying ice crystals of popular interest in snow microphysics studies, such as dendrites. 

### **Creating the snow_classfication_env environment:**
The required packages and dependencies are given in the [snow_classification_env.yml](https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/snow_classification_env.yml) file. 
Download this file and run the following prompt in the command line to create a Conda environment compatible with running scripts and notebooks in this repository.
```bash 
conda env create -n snow_classification_env -f snow_classification_env.yml
```
Activate this environment before running notebooks and scripts
```bash 
conda activate snow_classification_env
```
### **About the Python notebooks in this repository:**
<insert "High-level description of each script/notebook" >
