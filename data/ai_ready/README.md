# About the PHIPS Ice Crystal Habit AI-ready dataset

### Filename: "PHIPS_CrystalHabitAI_Dataset.nc"

Size: 584.4 MB

Format: NetCDF

Due to the size of the dataset exceeding 100 MB, it was unable to be directly uploaded to Github in `data/ai_ready/`. Instead, the dataset is uploaded and shared on Google Drive. It can be downloaded automatically by clicking [here](https://drive.google.com/uc?id=1gnfZpiBP954-qddiRfEZInfuAoMI7Y__). 

The dataset contains the following variables:

- `image_array`: A 3D array of greyscale images with dimensions `(samples, height, width)`. Each entry represents a 2D array of pixel intensities for an image.
- `timestamp`: The timestamp for each ice crystal image in ISO format (`YYYY-MM-DDTHH:MM:SS`), indicating the time it was captured during a flight.
- `label`: The classified habit type of the ice crystal, with labels in singular form (e.g., 'aggregate', 'column').
- `latitude`: The geographic latitude coordinate where the image was captured.
- `longitude`: The geographic longitude coordinate where the image was captured.
- `temperature`: The air temperature (in degrees Celsius) at the time and location corresponding to each image.
- `altitude`: The flight altitude in kilometers at the time the image was captured.

This dataset contains a total of 440 samples of various ice crystals images imaged during the NASA IMPACTS deployments (on flights 2020-02-07, 2022-02-17, 2023-01-23, or 2023-02-14), each converted to numpy array. All images are in greyscale and equally sized (1024 height x 1360 width pixels). Each image is labeled with one of 11 ice crystal habit categories (aggregate, bullet-rosette, capped column, column, dendrite, graupel, meedle, plate, polycrystal, side-plane, tiny), with 40 images labeled per category.
