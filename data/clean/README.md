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
Large ice crystals containing smaller single ice crystals (could be a mixed of different types) that are stuck/clumped together. 

## **Bullet rosettes**
Column ice crystals resembling bullets joined together at their tips. 

## **Plates**
Single ice crystals shaped like a hexagon. 

## **Capped columns**
Column ice crystals with plates attached at either end.

## **Columns**
Single ice crystals shapped like a column or bullet.

## **Dendrites**
Six-sided branched ice crystal.

## **Graupel**
A heavily rimed ice crystal (i.e. an ice crystal of any type covered completely with frozen water droplets to the point of no recognition). The shape of these ice crystals varies. They tend to look like a fuzzy, opague blob.



