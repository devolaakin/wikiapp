---
title: Gathering Data
description: Gathering the right inputs for using the WBC
published: true
date: 2020-09-29T18:34:32.086Z
tags: data, soil, slope, weather, plots, land cover
editor: markdown
---

# What data do I need?
By design, the WBC does not require a large quantity of inputs and data. Field obtained data will always be the most accurate, but the WBC will estimate parameters where data is not input or unavailable. 

## Required Inputs

- [ ] Project location (latitude, longitude)
- [ ] Slope of hillsides you wish to model (%)
- [ ] Depth of top soil (cm)
- [ ] Existing plot configuration
- [ ] Soil texture (Per United States Department of Agriculture Classification)*
- [ ] Dry bulk density (g/cm^3)

## Optional Inputs

- [ ] Infiltration rate (mm/hr)
- [ ] Soil organic matter content (%)

> *If you added the *Soil_Texture Raster* to the `C:\Program Files\WBC_Ethiopia\data\Spatial` directory, the USDA Soil Texture will automatically be updated when you place the project location on the WBC Map Tab (your project location is shown with a :star: symbol). 
{.is-info}

# How and where to gather data from
Most of the required inputs are easy to gather in the field or from digital sources. 
## Project location
The project's latitude and longitude can be gathered in the field from a GPS device. Other options for finding a project's location are from Google Earth or [Google Maps](https://www.google.com/maps). 
### Google Earth
1. Navigate to your project location on Google Earth
1. Hover your mouse on the project location
1. The bottom of the screen will display the coordinates for where your mouse is hovering (see red box below), write these down. 
![g_earth_coordinates.png](/g_earth_coordinates.png)

### Google Maps
1. Go to https://www.google.com/maps/
1. Navigate to your project location
1. Click on the map where your project is
1. A popup window on the bottom of the map window will display the coordinates for that location (see below)
![g_maps_coordinates.png](/g_maps_coordinates.png)

## Slope (Plot)
The slope for the plot you will be modeling can be gathered in the field from tools, such as a [clinometer](https://openoregon.pressbooks.pub/forestmeasurements/chapter/1-2-field-technique-tips-for-measuring-slope/), from topographic maps, or from geospatial software, such as Google Earth or ArcGIS. Slope in the WBC is input as a percentage. For general information on calculating slope, click [here](https://en.wikipedia.org/wiki/Grade_(slope))

Below are two videos showing how to measure slope from Google Earth and ESRI ArcGIS Pro. 
> [Using Google Earth to measure slope](/3_ge_measurements.mp4)
{.is-info}

>[Using ArcGIS Pro to measure slope](/4_arcgis_measurements.mp4)
{.is-info}

## Soil Depth
For the WBC, The soil depth represents the depth of the soil profile (from the surface to the parent material, bedrock, or the layer of obstacles for roots) that is readily available for storing infiltrated water. The “Soil Depth” input currently must be specified as a value (e.g., 40 cm), although future versions of the WBC may use a more qualitative approach (e.g., low, medium, or high depth/thickness). The typical range for use with the WBC at this time is 20 to 100 cm, it is not recommended that you input a value higher than 100 cm. 

> The WBC model calculations are very sensitive to this important parameter because soil depth is used to define the maximum storage of the soil upper zone storage (UZS) and lower zone storage (LZS), which in turn influence the rate of water infiltation and runoff. Therefore, it is best to underestimate how deep the soil profile is. **For version 2.X of the WBC, do not exceed 100 cm.**
{.is-warning}


## Existing Plot Configuration
Plots are idealized rectangles composed of **transects** and each transect is composed of **cells**. It is rare that a farm plot in the field will be perfectly rectangular, so you must simplify the plot into a basic geometric shape for the WBC to calculate everything correctly. In order to use the WBC, you need to gather information on what the existing plot looks like and how it is configured. 

![plot_rectangle2.png](/plot_rectangle2.png)

---

This idealized rectangle (**plot**) will then be vertically subdivided into transects. In the example below, aerial imagery is used to draw each **transect** and then measure dimensions. 

---
![plot_input1_1.png](/plot_input1_1.png)

---
![plot_input2_2.png](/plot_input2_2.png)

---

> The easiest two ways to gather the existing plot configuration are to use Google Earth with aerial imagery **or** to measure and record plot information in the field using a worksheet (like this one). See [page on WBC input preparation](/input-preparation) 
{.is-info}

## Soil Texture
The WBC uses the 12 USDA soil texture classifications as inputs for modeling soil hydraulic response and sediment loss. Soil texture is typically determined from soil sampling and lab analysis per the USDA soil texture triangle based on a sample's percent sand, silt, and clay. The texture triangle is explained more in depth [here](https://www.nrcs.usda.gov/wps/portal/nrcs/detail/soils/survey/?cid=nrcs142p2_054167). 

If you do not know the soil texture classification for your project **and** you added the *Soil_Texture* raster to the WBC spatial directory (instructions [here](/Installing-the-wbc)) the soil texture for your project area will automatically be filled in when you enter in the coordinates for your project or place the project on the Map tab. The Soil_Texture raster is from International Soil Reference and Information Centre [(ISRIC)](https://www.isric.org/) [SoilGrids](https://www.isric.org/explore/soilgrids/faq-soilgrids) database. 

## Dry Bulk Density
The WBC automatically estimates **dry bulk density** (g/cm^3^) based on what you enter for **soil texture**. 

However, you may override this value if you know the dry bulk density for the soil at your project location. Dry bulk density is typically determined through soil sampling and lab analysis. For the WBC, it is estimated based on soil texture using average bulk density values for per soil texture and on [ISRIC bulk density data](https://data.isric.org/geonetwork/srv/eng/catalog.search#/metadata/713396f9-1687-11ea-a7c0-a0481ca9e724). 

## Infiltration Rate (optional)
Soil infiltration rate (mm/hour) is measured in the field. The most common method for measuring infiltration rate is to use a cylinder or ring infiltrometer. More details on how to measure soil infiltration rate is available [here](http://www.fao.org/3/S8684E/s8684e0a.htm#:~:text=The%20most%20common%20method%20to,a%20cylinder%20or%20ring%20infiltrometer.&text=Ring%20infiltrometer%20of%2030%20cm,to%20prevent%20lateral%20water%20flow.).


**Basic Infiltration Rates for Various Soil Types**
|Soil Type|Basic Infiltration Rate (mm/hr)|
|:---|:---|
|Sand|less than 30|
|Sandy Loam|20-30|
|Loam|10-20|
|Clay Loam|5-10|
|Clay|1-5|

## Soil Organic Matter Content (optional) 
Soil Organic Matter (SOM) (%) can impact a soil's erodability and increase its water-holding capacity. The WBC allows you to insert your soil's SOM, if you know it, for calculations. If no value is input, the SOM % will be estimated. 

The United States Natural Resource Conservation Service has developed a [SOM datasheet](https://www.nrcs.usda.gov/Internet/FSE_DOCUMENTS/nrcs142p2_053264.pdf) that provides additional information on this parameter and how it can be measured in the field. 