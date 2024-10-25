# MLGEO2024_Snowflake_Classification
#### Contributors: Valeria Garcia (ESS 569) and Carlos Palma Bernal (ESS 469)

## Project Overview
The "MLGEO2024_Snowflake_Classification" project aims to develop a robust AI algorithm utilizing Convolutional Neural Networks (CNNs) to identify and classify high-resolution ice crystal images according to snowflake type. This initiative seeks to automate the classification process, which is traditionally carried out manually—a method that is often time-consuming, prone to human error, and lacks reproducibility.

### **Importance of Snowflake Classification**
Snowflake classification is vital for understanding microphysical processes occurring within winter storms, which has implications for snowfall accumulation. By providing a reliable, objective classification system, this project will enhance the scientific community's ability to study and interpret snow microphysics, which plays a crucial role in winter weather systems.

### **Objectives**
The primary objectives of this project include:
* **Automating Classification**: Replace manual snowflake classification with a machine learning-based algorithm to improve efficiency and accuracy.
* **Data-Driven Insights**: Leverage statistical analyses and visualizations to gain insights into the characteristics and distributions of different ice crystal types.

## **Snowflake classes**

To better understand the aim of the project, it is necessary to be familiar with some of the  main types of snowflakes included in the data. These are, accompanied by brief desciptions:

**Plates**

Ice crystals shaped like a hexagon.

<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/plates_examples.png" alt="Plate" width="700">

**Columns**

Ice crystals shaped like a column, some having a thinner shape closer to a needle.

<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/columns_examples.png" alt="Column" width="700">

<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/capped_columns_examples.png" alt="Capped column" width="700">

<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/needles_examples.png" alt="Needle" width="700">

**Side-planes**

Multiple plates joined together.

<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/side_planes_examples.png" alt="Side plane" width="700">

**Bullet rosettes**

Multiple columns joined together.

<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/bullet_rosettes_examples.png" alt="Bullet rosette" width="700">

**Dendrites**

Six-sided branched ice crystals.

<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/dendrites_examples.png" alt="Dendrite" width="700">


**Graupels**

Ice crystals covered completely with frozen water droplets such that they look like fuzzy blobs.

<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/graupel_examples.png" alt="Graupel" width="700">

**Aggregates**

Large ice crystals composed of many smaller crystals.

<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/aggregates_examples.png" alt="Aggregate" width="700">

**Irregulars**

Crystals that do not fit any of the above categories, for example, tiny cristals.

<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/tiny_examples.png" alt="Tiny" width="700">

## **Data Source:**

This project will utilize ice crystal images (in PNG format) photographed by the Particle Habit Imaging and Polar Scattering Probe (PHIPS) during the Investigation of Microphysics and Precipitation in Atlantic Coast-Threatening Snowstorms (IMPACTS) for both the training and testing datasets. IMPACTS was a NASA field campaign focused on studying winter storms during the 2020, 2022, and 2023 winter seasons (January-February), using aircraft to collect microphysical and remote sensing observations across multiple U.S. northeastern and Midwestern winter storms. Along with the ice crystal images, meteorological and navigation data from the P-3 aircraft (on which the PHIPS was onboard) will be used to provide temperature and spatial/geographic information for the ice crystals images. 

<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/IMPACTS_logo.png" alt="IMPACTS logo" width="300"> <img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/PHIPS_instrument.png" alt="PHIPS Instrument" width="425">

For curating the training dataset of this project, ice crystal images from the following flight dates were selected: 2020-02-07 (sample area: Pennslyvannia), 2022-02-17 (sample area: Illinois), 2023-01-23 (sample area: Maine), and 2023-02-14 (sample area: Minnesota). These dates were selected for the unique storm structures sampled. In-cloud sampling of these storms occurred at multiple temperature levels, ensuring a diverse assortment of ice crystal images sampled, which is a requirement for constructing a training dataset representative of many snowflake types. 

### **Data Modalities and Formats:**
* PHIPS ice crystal dataset
  * Consists of ice crystal images in .PNG format, imaged in-cloud
  * Sampling rate: 1 Hz for duration of flight
  * Note: Due to storage constraints in this repository, the raw PHIPS image files were not included in `data/raw/`
* P-3 aircraft meteorological/navigation dataset
  * Contains time-series numerical data including geographic (e.g. latitude, longitude coordinates), meteorological (e.g. temperature, dewpoint, wind speed) and altitude data (e.g. altitude, pitch, roll, yaw) reported from the P-3 aircraft during each flight
  * Sampling rate: 1 Hz for duration of flight
  * Format: ICARTT (.ict)
    * ICARTT files: an ICARTT file is a text-based format for atmospheric research data, developed to ensure consistency in data sharing. It contains tabular data and headers with information on measurements, units, instruments, and data quality. Lengthy documentation on the ICARTT file format standards can be found [here](https://www.earthdata.nasa.gov/s3fs-public/imported/ESDS-RFC-029v2.pdf)


## Getting Started 

To get started with the "MLGEO2024_Snowflake_Classification" project, follow these steps:

### **Prerequisites:**
* `Python 3.9.12` or later
* Conda for managing dependencies (recommended)
* Git cloning the repository
* An NASA Earthdata Login Profile (for downloading data)

### **1. Clone the repository**
Start by cloning the repository to your local machine:
```bash 
git clone https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification.git
cd MLGEO2024_Snowflake_Classification
```
### **2. Set Up the Environment**
Create a conda environment with the necessary dependencies using the `snow_classification_env.yml` file:
```bash 
conda env create -n snow_classification_env -f snow_classification_env.yml
conda activate snow_classification_env
```
This will install all required packages, including libraries for data processing, machine learning, and visualization.

### **3. Register for a NASA Earthdata Login Profile**

To download the IMPACTS P-3 met/nav data on the NASA Global Hydrometeorology Resource (GCHR) website, an Earthdata Login profile is needed. Registering is free and can be done [here](https://urs.earthdata.nasa.gov/users/new?client_id=OLpAZlE4HqIOMr0TYqg7UQ&redirect_uri=https%3A%2F%2Fd53njncz5taqi.cloudfront.net%2Furs_callback&response_type=code&state=https%3A%2F%2Fsearch.earthdata.nasa.gov%2Fsearch%3Fq%3Dp3metnavimpacts%26ee%3Dprod)


## Descriptions of the Python notebooks in this repository

- [download_data_NASA_GHRC.ipynb](https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/notebooks/download_data_NASA_GHRC.ipynb): Instructions for locally downloading from the NASA GHRC website the folders containing the raw PHIPS images (in .PNG format), as well as the .ict files for the P-3 aircraft meteorological/navigational datasets. Due to the large size of the raw PHIPS image data, it is recommended to run the download prompts in the command line.
  
- [cleaning_data_P3_nav.ipynb](https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/notebooks/cleaning_data_P3_nav.ipynb): For cleaning the P-3 aircraft met/nav .ict data files using a read routine adapted from the [IMPACTS Github repository](https://github.com/joefinlon/impacts_tools.git). Cleaned data is saved as NetCDF files. Manual inspection/selection of the raw PHIPS images was necessary for cleaning the image dataset, hence why no cleaning notebook for it is provided. Please refer to the README.md under `data/clean/` that describes in detail the manual selection process for the images.
  
- [prepare_AI_ready_data_PHIPS.ipynb](https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/notebooks/prepare_AI_ready_data_PHIPS.ipynb): For reading in the cleaned PHIPS image data and the P-3 aircraft met/nav data and constructing an xarray.Dataset with the images converted to numpy arrays and appropriate meta data attributes included from the P-3 met/nav dataset. This AI-ready dataset is saved as a NetCDF file and manually uploaded to Google Drive (file name: `PHIPS_CrystalHabitAI_Dataset.nc`) as opposed to Github due to repository storage constraints. Please refer to the README.md in `data/ai_ready/` for downloading the dataset.
  
- [EDA_PHIPS.ipynb](https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/notebooks/EDA_PHIPS.ipynb): For exploring the structure and key statistical characteristcs of the `PHIPS_CrystalHabitAI_Dataset.nc` AI-ready dataset. Basic statistics of the pixel intensities across all the PHIPS images are inspected, along with a correlation matrix that explores linear relationshps between image intensity and other data attributes such as habit type and temperature.
  
- [dimensionality_reduction_PHIPS.ipynb](https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/notebooks/dimensionality_reduction_PHIPS.ipynb): For analyzing the dimensions of the `PHIPS_CrystalHabitAI_Dataset.nc` AI-ready dataset and implementing linear (Principle Component Analysis, PCA) and non-linear (t-Distributed Stochastic Neighbor Embedding, t-SNE) dimension reduction techniques to tease out linear and non-linear relationships, respectively, in the data.
