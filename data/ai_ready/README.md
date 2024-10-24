# About the PHIPS Ice Crystal Habit AI-ready dataset

### Filename: "PHIPS_CrystalHabitAI_Dataset.nc"

Size: 584.4 MB

Format: NetCDF

Due to the size of the dataset exceeding 100 MB, it was unable to be directly uploaded to Github in data/ai_ready. Instead, the dataset is uploaded and shared on Google Drive. It can be downloaded automatically by clicking [here](https://drive.google.com/uc?id=1gnfZpiBP954-qddiRfEZInfuAoMI7Y__). 

This dataset contains a total of 440 samples of various ice crystals images imaged during the NASA IMPACTS deployments (on flights 2020-02-07, 2022-02-17, 2023-01-23, or 2023-02-14), each converted to numpy array. All images are in greyscale and equally sized (1024 H x 1360 W pixels). Each image is labeled with one of 11 ice crystal habit categories (aggregate, bullet-rosette, capped column, column, dendrite, graupel, meedle, plate, polycrystal, side-plane, tiny), with 40 images labeled per category.
Other data variables include the timestamp (date and time in UTC) at which the image was taken, the image label, the latitude and longitude coordinates of the image (from the P-3 aircraft navigational data) and the temperature (˚C) and altitude (km) reported by the P-3 aircraft at the time the image was taken.
