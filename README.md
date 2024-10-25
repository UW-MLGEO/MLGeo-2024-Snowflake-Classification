# MLGEO2024_Snowflake_Classification
### Contributors: Valeria Garcia (ESS 569) and Carlos Palma Bernal (ESS 469)

This repository is for the UW-MLGEO 2024 final project.

### **Data Source:**

This project will leverage ice crystal images (in PNG format) photographed by the Particle Habit Imaging and Polar Scattering Probe (PHIPS) during the Investigation of Microphysics and Precipitation in Atlantic Coast-Threatening Snowstorms (IMPACTS) for both the training and testing datasets. IMPACTS was a NASA field campaign focused on studying winter storms during the 2020, 2022, and 2023 winter seasons (January-February), using aircraft to collect microphysical and remote sensing observations across multiple U.S. northeastern and Midwestern winter storms. Along with the ice crystal images, meteorological and navigation data from the P-3 aircraft (on which the PHIPS was onboard) will be used to provide temperature and spatial/geographic information for the ice crystals images. 

<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/IMPACTS_logo.png" alt="IMPACTS logo" width="300"> <img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/PHIPS_instrument.png" alt="PHIPS Instrument" width="425">

For curating the training dataset of this project, ice crystal images from the following flight dates were selected: 2020-02-07 (sample area: Pennslyvannia), 2022-02-17 (sample area: Illinois), 2023-01-23 (sample area: Maine), and 2023-02-14 (sample area: Minnesota). These dates were selected for the unique storm structures sampled. In-cloud sampling of these storms occurred at multiple temperature levels, ensuring a diverse assortment of ice crystal images sampled, which is a requirement for constructing a training dataset representative of many snowflake types. 

### **Data Modalities and Formats:**
* PHIPS ice crystal dataset
  * Consists of ice crystal images in .PNG format, imaged in-cloud
  * Sampling rate: 1 Hz for duration of flight
  * Note: Due to storage constraints in this repository, the raw PHIPS image files were not included in data/raw/
* P-3 aircraft meteorological/navigation dataset
  * Contains time-series numerical data including geographic (e.g. latitude, longitude coordinates), meteorological (e.g. temperature, dewpoint, wind speed) and altitude data (e.g. altitude, pitch, roll, yaw) reported from the P-3 aircraft during each flight
  * Sampling rate: 1 Hz for duration of flight
  * Format: ICARTT (.ict)
    * ICARTT files: an ICARTT file is a text-based format for atmospheric research data, developed to ensure consistency in data sharing. It contains tabular data and headers with information on measurements, units, instruments, and data quality. Lengthy documentation on the ICARTT file format standards can be found [here](https://www.earthdata.nasa.gov/s3fs-public/imported/ESDS-RFC-029v2.pdf)

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
- [download_data_NASA_GHRC.ipynb](https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/notebooks/download_data_NASA_GHRC.ipynb): Instructions for locally downloading from the NASA GHRC website the folders containing the raw PHIPS images (in .PNG format), as well as the .ict files for the P-3 aircraft meteorological/navigational datasets. Due to the large size of the raw PHIPS image data, it is recommended to run the download prompts in the command line. 
- [cleaning_data_P3_nav.ipynb](https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/notebooks/cleaning_data_P3_nav.ipynb): For cleaning the P-3 aircraft met/nav .ict data files using a read routine adapted from the IMPACTS Github repository. Cleaned data is saved as .nc files. Manual inspection/selection of the raw PHIPS images was necessary for cleaning the image dataset, hence why no cleaning notebook for it is provided. Please refer to the README.md under data/clean/ that describes in detail the manual selection process for the images.
- [prepare_AI_ready_data_PHIPS.ipynb](https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/notebooks/prepare_AI_ready_data_PHIPS.ipynb): For reading in the cleaned PHIPS image data and the P-3 aircraft met/nav data and constructing an xarray.Dataset with the images converted to numpy arrays and appropriate meta data attributes included from the P-3 met/nav dataset. This AI-ready dataset is saved as a NetCDF file and manually uploaded to Google Drive as opposed to Github due to repository storage constraints. Please refer to the README.md in data/ai_ready/ for downloading the dataset.
- [EDA_PHIPS.ipynb](https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/notebooks/EDA_PHIPS.ipynb): For exploring the structure and key statistical characteristcs of the "PHIPS_CrystalHabitAI_Dataset.nc" AI-ready dataset. Basic statistics of the pixel intensities across all the PHIPS images are inspected, along with a correlation matrix that explores linear relationshps between image intensity and other data attributes such as habit type and temperature.
