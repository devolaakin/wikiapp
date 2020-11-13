---
title: About the WBC
description: 
published: true
date: 2020-11-04T12:09:24.131Z
tags: about, contact, funding, usaid, foodforpeace
editor: markdown
---

# Purpose of the WBC Tool
The Water Benefits Calculator (WBC) for Ethiopia (Version 2 and higher) is a desktop-based tool developed by Catholic Relief Services with funding support from the United States Agency for International Development (USAID). The WBC for Ethiopia was originally developed as a spreadsheet-based tool (Version 1) for three demonstration farms (located within or near Obi, Ziway Dugda, and Awale) prior to being adapted to the current, standalone desktop version.

The WBC can be used to compute water infiltration and runoff and sediment washoff for Ethiopian hillsides and agricultural plots and to compare the relative benefits of implementing one or more management interventions on a hillside/plot relative to a pre-management reference condition or other management scenarios. Specific management scenarios (i.e., involving interventions or alternative cropping) can be configured via the use of transects that represent the different crop and landscape configurations and patterns for a field area of interest. The evolution of agricultural activities, including crop planting, growth, and harvest, are represented in the WBC based on the estimated impact of those activities on key hydrologic processes (e.g., water storage in canopy cover). Results reported by the tool include seasonal and annual runoff, evapotranspiration, recharge, and sediment washoff rate at the hillside and plot scales.

The current version of the WBC (Version 2) will eventually be enhanced to incorporate a cost-benefit module (Version 3), which will allow users to compare relative costs and water quantity/quality benefits across various plot management scenarios. Version 4 of the tool will involve calibration of the hydrologic and sediment washoff practices (as represented in Versions 2 and 3) to data collected from literature sources and the field for Ethiopian agricultural areas where CRS has existing relationships.


# What is a Model? 
The WBC is a known as a **systems model**. This systems model (the WBC) is built to simulate watershed hydrology and soil erosion. Models simulate real world conditions using complex mathematical and statistical formulae and techniques. **The real world is extremely complex and varied**, because of this, systems models make assumptions to reduce the complexity of the real world so that people can analyze a simplified reality and computers can compute the simplified conditions. 

>*All models are wrong, but some are useful* - George Box

An example of a simplification is below. In real life, many plots of land are not square or rectangular and may be a combination of any geometric shape, but for the WBC we simplify the goemetry into a rectangle so that the WBC can perform calculations and that people have an easier time using it.  

![plot_rectangle.png](/plot_rectangle.png)

## Mass Balance Model
The WBC is built on the critical physics law, **the law of the conservation of mass**, which states "that for any system closed to all transfers of matter and energy, the mass of the system must remain constant over time, as the system's mass cannot change, so quantity can neither be added nor be removed. Therefore, the quantity of mass is conserved over time." What this means in our context, is that mass and energy that enter the watershed system must go somewhere, it cannot simply disappear. It must go into plants, the soil, runoff as water, go deep into the aquifer, or leave through evapotranspiration. This type of analyis is known as a **mass balance model** because we are "balancing" all the mass and energy that enters the watershed system.[^1]

[^1]: https://en.wikipedia.org/wiki/Mass_balance







# Framework
The WBC tool framework is based on configuration of a **plot** area and an associated set of child **transects** that represent the unique combination of topographic features, land cover, and management interventions for a typical Ethiopian private land area located along a hillslope. A transect defines the representation of topographic features and land use / land cover along the upslope-to-downslope length of the plot (field area) of interest. Within each transect, spatial patterns in land use are segmented as “cells.” Each transect requires specification of appropriate land use segments (i.e., cells), fixed cell width (i.e., the lateral spacing), and the cell length (i.e., the vertical spacing) for each land use segment. Within a transect, the cell length can be varied to configure the vertical spacing of the topographic features. In order to facilitate configuration of spatial patterns, the WBC graphical user interface (GUI) provides a palette of the land cover types that can be added to the transect via basic ‘point-and-click’ action. All transects created within a plot must be specified at the same total length as the prescribed slope length for the plot. A sufficient number of transects must be configured so that the “transect-set” can be reproduced/extrapolated along the cross-slope (lateral) dimension of the plot.

Each WBC plot (field area) is contained within (or a child of) a “hillside” area that is created by a user.  Each hillside belongs to a particular project, which is the highest point of the WBC hierarchy.  The relationships between projects, hillsides, plots, scenarios, transects, and cells are illustrated in Figure 1 and can be summarized as follows:
- **Projects:** A user may create one or more projects within the WBC interface. A project is assumed to represent a general area of interest for evaluating interventions, and it can be represented by a single point location specified on a map or via latitude/longitude coordinates. This location is used by the WBC to determine appropriate meteorological data and soil texture to support the modeling of plots.
- **Hillsides:** Each WBC project may contain one or more hillsides, which represent geographical area(s) with consistent soil and weather characteristics. A hillside does not have to have a steep slope or grade.
- **Plots:** Each hillside may contain one or more plots, with each plot representing a small parcel of land to be specifically analyzed within the WBC. A plot with typically have a surface area of 0.25 to 5 hectares, with a maximum slope length of approximately 400 meters.
- **Scenarios:** One or more scenario(s) may be created within an individual plot. An individual scenario is intended to represent a specific management scenario across one or more transects.
	- **Transects:** Each transect has a fixed width (e.g., 20 meters) and is comprised of multiple cells of varying lengths, which collectively represent the full slope length specified for the parent plot. 
	- **Cells:** Each cell represents a specific land cover condition along the slope represented by the transect. The WBC simulates the movement of water and sediment washoff from upslope to downslope, and therefore each cell imports water/sediment from the ‘upslope’ cell and exports water/sediment to the next cell downslope.

As depicted in the figure below, the quantity and size of plots, scenarios, and transects are flexible and can be specified by the user to best match field conditions for each hillside area.

![wbc_framework.png](/wbc_framework.png)

# Hydrological Simulation Program
The [Hydrologic Simulation Program FORTRAN (HSPF)](https://www.epa.gov/ceam/hydrological-simulation-program-fortran-hspf) model is a U.S. EPA program for simulation of watershed hydrology and water quality. HSPF was been used in watershed modeling practice since the 1970s, and there have been hundreds of applications of HSPF all over the world. The HSPF model uses information such as the time history of rainfall and potential evapotranspiration; land surface characteristics such as land-use patterns; and land management practices to simulate the hydrologic and water quality processes that occur in a watershed drainage area. The result of this simulation is a time history (daily, monthly, and annual) of the quantity and quality of simulated runoff from the pervious and impervious land surfaces represented in the model.

The HSPF model consists of a set of modules arranged in a hierarchical structure that support the continuous simulation of a comprehensive range of hydrologic and water-quality processes. A more detailed description of process representation in HSPF is provided in Bicknell et al. (2005). The “PERLND” (pervious land) module of HSPF simulates the water quantity and quality processes that occur on pervious land areas. The PERLND module is implemented in the WBC tool for hydrology and sediment erosion/washoff (nutrients and pesticides are not included in current versions). The WBC implementation of the PERLND module tracks at an hourly timestep storage of water in various above-surface and subsurface compartments or zones (e.g., canopy and unsaturated soil zones) and the movement of water along three flow output paths: overland flow, interflow, and groundwater flow. A total of six (6) storage zones are used to represent the short- and long-term retention of water in the drainage area, with the total water storage quantities and retention timescales dependent on the parameterization of processes that occur on the land surface and in the soil horizons. A schematic of the hydrologic processes represented in HSPF is shown in the below figure. 

The WBC tool currently generates uncalibrated model simulations of hydrology and sediment loss from Ethiopian hillslope plot (field) areas. Results from the current tool are well suited for evaluating relative changes between alternative management conditions, and therefore the relative benefits of various management approaches; **however, the absolute values should be considered somewhat uncertain and used with caution until the WBC has been calibrated** (Version 4, to be released in spring 2021).

![hspf_graphic.png](/hspf_graphic.png)

# How Accurate is the WBC? 
The question "how accurate is the WBC?" is difficult to answer. The WBC is what is known as a **comparative model**. This means, that the WBC can compare different potential real world scenarios that can help you, the WBC user, make a decision about what you want to do with the plot of land you are modeling. The WBC does not aim to answer the questions "Exactly how much water will runoff from this plot of land?" instead it answers the question, "If I want to build soil bunds instead of terraces, which one will meet my goal ***more or best***?" That goal, depending on your plot and community needs, may be climate resiliency, soil erosion reduction, increased groundwater recharge, etc. There are many goals you may have and the WBC is built to accomodate a large range of them. Even though the WBC may not be accurate enough to say "If you plant 4 rows of chat, your evapotranspiration will improve by X amount" the results from the WBC are replicable. Therefore, the WBC is precise, but not always accurate. This is illustrated in the example below[^2]

---

Precision and accuracy are two ways that scientists think about error. Accuracy refers to how close a measurement is to the true or accepted value. Precision refers to how close measurements of the same item are to each other. Precision is independent of accuracy. That means it is possible to be very precise but not very accurate, and it is also possible to be accurate without being precise. The best quality scientific observations are both accurate and precise.
 
A classic way of demonstrating the difference between precision and accuracy is with a dartboard. Think of the bulls-eye (center) of a dartboard as the true value. The closer darts land to the bulls-eye, the more accurate they are. 
- If the darts are neither close to the bulls-eye, nor close to each other, there is neither accuracy, nor precision (Figure A).  
- If all of the darts land very close together, but far from the bulls-eye, there is precision, but not accuracy (Figure B).   
- If the darts are all about an equal distance from and spaced equally around the bulls-eye there is mathematical accuracy because the average of the darts is in the bulls-eye. This represents data that is accurate, but not precise (Figure C). However, if you were actually playing darts this would not count as a bulls-eye!
- If the darts land close to the bulls-eye and close together, there is both accuracy and precision (Figure D). 
![precision1.png](/precision1.png)

**In the case of the WBC, it is precise, but may not be accurate.**

*The WBC is currently undergoing a level of calibration and this will be released in WBC version 4 in 2021. This will improve the WBC result's accuracy.*

[^2]: https://manoa.hawaii.edu/exploringourfluidearth/physical/world-ocean/map-distortion/practices-science-precision-vs-accuracy#:~:text=Precision%20and%20accuracy%20are%20two,item%20are%20to%20each%20other. 
# Project Background
The WBC was previously developed by [CRS Blue Harvest](http://www.waterbenefitscalculator.com/Home.vbhtml) in 2016 for use in Central America. This tool was developed in collaboration with LimnoTech, an engineering consulting firm, and is being used for planning farm diversification and agroforestry systems on coffee farms in Central America. The tool is designed to compute water quantity and sediment reduction benefits from implementation of management interventions. The WBC allows the user to run a hydrological model that computes specific hydrological parameters (evapotranspiration, surface runoff, basin interflow, groundwater outflow, soil water storage, and sediment loading) before and after implementing management interventions. These interventions take the form of different types of land uses and range from complete coffee renovation to installing infiltration pits. Using the WBC, a farmer or landowner can estimate the expected water and soil benefits from a set of management interventions before installing them and allows the farmer or landowner to make informed decisions on which types of interventions will be best for their application. As the Blue Harvest initiative expands into other landscapes in different regions of the world, this modeling tool must be modified to include different crop types, climate regimes, and agricultural management practices. Therefore, the CRS DFSA operational area has developed this WBC to build on the success of the Blue Harvest WBC in Central America in an effort to implement the tool in another region of the world. 

Community Based Watershed Development Planning (CBWDP) has been implemented in the DFSA operational area for better management of watershed resources. Accordingly, a number of community watersheds were rehabilitated through the labor based Public Work (PW) campaign using different physical and biological soil and water conservation measures. Moreover, the communities witnessed the positive change in land productivity and increased income due to the amount of irrigated land and harvest yield in maize and cash crops. However, tools to aid in strategic planning of PW campaigns and land management have been lacking and CRS DFSA recognizes that the WBC can help decision makers select between potential intervention scenarios based on measureable indicators. Hectares of land reclaimed through soil and water conservation treatments, change on water flow, on ground water table, size of irrigable land, and income before and after the interventions were some of the indicators selected for monitoring. Because of this, the CRS WBC is being developed and tested per previous experience in Central America and to aid in strategic CBWDP to optimize NRM intervention benefits and outcomes. 


# Donors and Funding


# Project Team and Contacts
- Tom Hollywood (CRS): Deputy Director of CRS Ethiopia DFSA
- Negussie Kefeni (CRS): Program Manager II
- Ambachew Worku (CRS): Natural Resource Management Project Manager
	- ambachew.worku@crs.org
- Adam Keough (CRS): Program Manager I
	- adam.keough@crs.org
- Will Garde, P.E. (Garde Engineering): Water Resources Technical Consultant
	- will.garde@crs.org
- Pranesh Selvendiran, Ph.D., P.E. (LimnoTech Engineering): Project Manager
- Todd Redder, P.E. (LimnoTech Engineering): Project Technical Lead
- Derek Schlea, P.E. (LimnoTech Engineering): Project Engineer
- Paul Tomasula, P.E. (LimnoTech Engineering): Project Engineer

