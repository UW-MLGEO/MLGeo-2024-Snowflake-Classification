# MLGEO2024_Snowflake_Classification
## Contributors: Valeria Garcia (ESS 569) and Carlos Palma Bernal (ESS 469)

This repository is for the UW-MLGEO 2024 final project.

### **Data Source:**

This project will leverage ice crystal images (in PNG format) photographed by the Particle Habit Imaging and Polar Scattering Probe (PHIPS) during the Investigation of Microphysics and Precipitation in Atlantic Coast-Threatening Snowstorms (IMPACTS) for both the training and testing datasets. IMPACTS was a NASA field campaign focused on studying winter storms during the 2020, 2022, and 2023 winter seasons (January-February), using aircraft to sample multiple U.S. northeastern and Midwestern winter storms in-cloud. Along with the ice crystal images, meteorological and navigation data from the P-3 aircraft (on which the PHIPS was onboard) will be used to provide temperature and spatial/geographic information for the ice crystals images. 

<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/IMPACTS_logo.png" alt="IMPACTS logo" width="400"> <img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/PHIPS_instrument.png" alt="PHIPS Instrument" width="568">

For curating the training dataset of this project, ice crystal images from the following flight dates were selected: 2020-02-07 (AOI: Pennslyvannia), 2022-02-17 (AOI: Illinois), 2023-01-23 (AOI: Maine), and 2023-02-14 (AOI: Minnesota). These dates were selected for the unique storm structures and locations sampled. In-cloud sampling of these storms occurred at multiple temperature levels, ensuring a diverse assortment of ice crystal images sampled, which is a requirement for constructing a training datset representative of all snowflake types. 

### **Project Objectives:**
To create an AI algorithm (Convolutional Neural Network, CCN) to identify and classify thousands of high-resolution ice crystal images according to snowflake type (i.e. to create an ML-based ice crystal habit classification algorithm). The goal is for this alogorithm to replace manual snowflake classification in research studies, an approach that is unreproducible and subject to human error, providing an objective, faster solution for identifying ice crystals of popular interest in snow microphysics studies, such as dendrites. 



