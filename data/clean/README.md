# On cleaning the raw PHIPS image dataset

#### Due to the 1 Hz sampling frequency of the PHIPS data, each data file (one per flight) contains 7,000+ images. Cleaning these files requires manual inspection and grouping of the images for each flight, hence no cleaning notebook is provided for this dataset. This README.md details the criteria used in the manual selection process. 

Below are the ice crystal categories/habit types identified:
* Aggregates
* Bullet rosettes
* Capped columns
* Columns
* Dendrites
* Graupel
* Needles
* Plates
* Polycrystals
* Side-planes
* Tiny
  
For each habit type, all PHIPS images across the four flights of interest (2020-02-07, 2022-02-17, 2023-01-23, and 2023-02-14) were inspected, among which 40 were selected and grouped into each category. Images were selected for each group based on the following descriptions:

## **Aggregates**
Large ice crystals containing smaller single ice crystals (could be a mix of different types) that are stuck/clumped together. 
<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/aggregates_examples.png" alt="aggregates example" width="1000"> 

## **Bullet rosettes**
Column ice crystals resembling bullets joined together at their tips. 
<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/bullet_rosettes_examples.png" alt="bullet rosettes example" width="1000">

## **Capped columns**
Column ice crystals with plates attached at either end. Sometimes the plates exhibit branched growth. 
<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/capped_columns_examples.png" alt="capped columns example" width="1000">

## **Columns**
Single ice crystals shapped like a column or bullet.
<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/columns_examples.png" alt="columns example" width="1000">

## **Dendrites**
Six-sided branched ice crystal. This cateogry includes ice crystals with branched and side-branched growth. 
<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/dendrites_examples.png" alt="dendrites example" width="1000">

## **Graupel**
A heavily rimed ice crystal (i.e. an ice crystal of any type covered completely with frozen water droplets to the point of no recognition). The shape of these ice crystals varies. They tend to look like a fuzzy, opague blob.
<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/graupel_examples.png" alt="graupel example" width="1000">

## **Needles**
As the name suggests, these ice crystals are long and thin, resembling a sewing needle. They oftentimes are found in clusters.
<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/needles_examples.png" alt="needles example" width="1000">

## **Plates**
Single ice crystals shaped like a hexagon. Mildly rimed plates are included in this category as well (i.e. some liquid water accretion on the ice crystal, but not enough to make its shape unrecognizable)
<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/plates_examples.png" alt="plates example" width="1000">

## **Polycrystals**
Complex ice crystals that appear to have branches with plate growth and other ice fragments growing off them. Their centers tend to be opague. This category excludes side-planes, which were identified separately.
<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/polycrystals_examples.png" alt="polycrystals example" width="1000">

## **Side-planes**
A common type of polycrystal that consists of plates joined at their edges, oftentimes looked to be clumped together. 
<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/side_planes_examples.png" alt="side planes example" width="1000">

## **Tiny**
Small fragments of ice crystals, most likely from shattering within the PHIPS probe. Could also be frozen water droplets. These fragments can come in a variety of shapes. Images selected in this category have varied morphologies but their sizes are all tiny relative to the above ice crystals. 
<img src="https://github.com/UW-MLGEO/MLGEO2024_Snowflake_Classification/blob/main/tiny_examples.png" alt="tiny example" width="1000">

Folders were created for each category, in which the images were placed (40 images total per category). To upload to Github, the folders were compressed separately into tar.gz files in the command line.

In this example, the folder "Bullet-rosettes" was compressed into a tar.gz file named "PHIPS_bullet_rosettes"
```bash 
tar -czvf PHIPS_bullet_rosettes.tar.gz Bullet-rosettes
```
