---
title: Using the WBC
description: How to use the WBC from start to finish
published: true
date: 2020-09-29T18:44:54.113Z
tags: how to, wbc, scenario, transect, hillside, plot
editor: markdown
---

# The WBC Forms
The WBC is setup in a series of fillable forms that the user needs to work through to complete a project. 

![wbc_form1.png](/wbc_form1.png)

>Video of example model running through all forms
{.is-info}

# Project Form
![form_project.png](/form_project.png)

 Your active page is highlighted in **GREEN** on the left navigation panel. On the project form page you can:
- Create a new project
- Delete an existing project
- Name a project after you create a new project
- Add details to the existing project

>You **must** select a project before you can continue to use the WBC
{.is-info}


# Map Form
![form_map_2.png](/form_map_2.png)
Above is a screenshot of the Map form page. On this page, you can navigate the map and place your project location on the map by clicking the "Locate WBC Project" button on the top left of the form. 

Placing your project location on the map is important for two reasons:
1. If you have installed the *Soil_Texture* raster, on the next form page, the soil texture will automatically be filled in based on where your project is. 
1. The coordinates of the project location will automatically be filled in on the next form page based on your project location. 
>Only CRS DFSA Woredas are included in the WBC boundaries and aerial imagery, but the *Soil_Texture* raster is for the entire country. Instructions on how to install the raster files [here](/Installing-the-wbc).
{.is-info}
# Hillside Form
![form_hillside.png](/form_hillside.png)
Above is a screenshot of the Hillside form page. See numbering below for explanation of different sections. 
1. The active project is displayed here and a drop down of available hillsides is available. Once you create a new hillside, the name will not automatically change when area [2] is filled in, but will update if you switch to another form. 
1. Enter hillside name, this will update area [1] after you switch to a different form page. The hillside latitude and longitude will automatically be filled in from the Project location on the map form. *But if you enter your own coordinates, the Project location (Star) will not move locations on the map form.*
1. Enter hillside description. 
1. Soil information is entered here. **USDA soil texture** will be estimated if you installed the Soil_Texture raster file. If not, you may select the soil texture for your hillside from the dropdown menu. **Dry bulk density** is estimated based on soil texture, but you can override the value if you would like. **Soil depth** represents the depth of the soil profile (from the surface to the parent material, bedrock, or the layer of obstacles for roots) that is readily available for storing infiltrated water.
> For now, soil depth input shold range between 20 and 100 cm. In furture WBC versions, this input will be refined per calibrated data sets for Ethiopia soil data. 
{.is-warning}
5. Optional inputs are entered here if you know them for your project location(s). 
1. Select the weather stations and historic weather years to simulate. Currently, there are only 4 weather stations and these are shown on the Map form. Choose all of the weather stations or the weather station closest to your project area. For more information on the weather stations and data in the WBC, click [here](/wbc-overview).

# Plot Form
![form_plot.png](/form_plot.png)
Above is a screenshot of the Plot form page. See numbering below for explanation of different sections. 
1. The active hillside is displayed here. You can create a new plot or delete an existing plot. The plot name changes per input from area [2]. 
1. Here you can enter relevant details on the plot you want to model. **Slope** is the average verticle slope in % over the **length** of the plot. Cross plot width and downslope length are the dimensions of your plot as shown below:
![plot_l_w.png](/plot_l_w.png)
1. Select **Residue** level from the drop down. Residue indicates the amount of crop or plant matter left on the ground after harvest.  
1. Enter a description for your plot, e.g. the family or farmer's name.
1. Several practices (interventions) modeled in the WBC can have their physical parameters adjusted here. See below for what each height corresponds to. 
![intervention_heights.png](/intervention_heights.png)
# Scenario Form
![form_scenario.png](/form_scenario.png)
Above is a screenshot of the Scenario form page. This page is the heart of the WBC and has many pieces to it. There are several critical things to understand:
- Scenarios are the "What-if" cases you want to explore. Typically, you will make one of the scenarios your **baseline** scenario. The baseline is what you want to compare other scenarios (What-if cases) to. For example, your baseline scenario may be a plot where no NRM interventions have been done. The plot is just a plain piece of land with natural vegetation or no vegetation at all. Your baseline scenario would consist of transects that reflect a bare piece of land with minimal vegetation. Then, *you would add a new scenario* in area [1] and begin making transects with the thought, "What if we added bench terraces or planting pits? Maybe we even planted chat?" Then, you have two scenarios to compare, the baseline scenario and the new scenario where you have added several NRM interventions and some crops. 

> **There is no perfect scenario or perfect answer when using the WBC**. What scenarios you decide to model depends on many factors, such as plot location, farmer preferences, climate, soil, what you are hoping to achieve overall, etc. The purpose of the WBC is to allow you to explore many scenarios and choose what one will be best for your project. 
{.is-warning}


- On the Plot form, you entered the cross plot width. The width of the transects in area [2] should sum to the cross plot width. 
	- If the transect widths sum to a number less than the cross plot width, the WBC will use **extropolation** to calculate the missing width. More details on WBC extrapolation are [here](jijew).
	- If the transect widths sum to a number greater than the cross plot width, the WBC will show an **warning** message below area [3]


See numbering below for explanation of different sections. 
1. Here you can add and select scenarios. When you select a scenario, the transects in area [2] will update to be those within the select scenario. Giving scenarios descriptive names and detail descriptions will be helpful later on when comparing the results of the different scenarios.
1. This box allows you to select the transects in your scenario. Select a transect and the width below will be shown and the % of the total cross plot width. In this screenshot, the total cross plot width is 20 meters (shown on plot form) and the transect is 5 meters, so the transect is 25% of the total cross plot width. 
1. Here you can add and delete transects. Below these buttons is a message that displays one of three messages:
3.1 The sum of transects widths is less than plot width (extrapolation will be used)
3.2 Sum of transects width is equal to plot width
3.3 Warning: the sum of transects widths is greater than plot width (% greater than plot width)
1. Here you can edit your transect layout. Each transect is made of cells. These cells represent a unique land cover, such as chat or bare soil, and have the **same width as the transect, but their length can be changed for each cell** depending on what you want to model. By clicking on a land cover option in area [5] you can then click on the cell to make that cell the selected land cover.
4.1 For each transect, cells can have different lengths. For example, Cell 1 in transect 1 may have a length of 1 meter, but for cell 1 in transect 2, it may be 2 meters. *This is not normally the case because most farms and public lands are arranged in rows and patterns,* but it is an option for the WBC. See example below. 
4.2 Each transect does not have to the same number of cells, **but the sum of all cell lengths must be equal to the plot length**. 
![form_scenario_cells.png](/form_scenario_cells.png)
The graphic above shows 4 transects, each with cells and those cell lengths vary. Transect 4 has only 1 cell, but all cells in each transect have lengths that sum to the same total plot length. It it more likely your models will look like the one below.
![form_scenario_cells2.png](/form_scenario_cells2.png)
1. This window shows the different land cover types you can model. Included in the land cover palette are crops, NRM interventions, and general ground cover options. Click on a land cover and then click on the cell you want to make that land cover. You can click on multiple cells and they will each become the land cover type. 
1. Here you can adjust the individual length of each cell. Remember, the sum of all the cell lengths in a transect should equal the total plot length. 

## Extrapolation
The WBC has a built-in feature for extrapolating transects horizontally. This feature can save time if a plot is relatively uniform (the same from left to right) or if it has a specific pattern. 

> The extrapolation feature is only applied horizontally, e.g. from left to right, not vertically.
{.is-warning}

**When would you use this feature?** This feature would be used if, for example, your plot was almost entirely made of rows of crops or similar land uses that follow a pattern from left to right, such as rows of chat. Your total plot width is 50 meters and you define your first transect, transect 1, as 5 meters wide. You will then fill in transect one and then the WBC will repeat that pattern for the remaining 45 meters by duplicating transect 1 nine more times to create 10 transects, each 5 meters wide, for a total width of 50 meters, which is equal to your plot width. See graphic below for what this might look like in practice. 

![form_scenario_extrap.png](/form_scenario_extrap.png)
> You will not be able to see these extra transects on the form interface, but they are calculated. 
{.is-warning}


# Simulation Page
![wbc_simulation1.png](/wbc_simulation1.png)
Above is a screenshot of the Simluation page. This page becomes available after you have filled in everything for at least 1 scenario. This page allows you to select which scenarios from the scenario form that you want to analyze and model. 

See numbering below for explanation of different sections. 
1. Here you can click on which scenarios you want to model. 
1. If you do not want to click on scenarios or have a long list of options in area [1], you can select/deselect all scenarios here. 
1. Once you have selected the scenarios you want to model, click **Run**. 

> Depending on how many transects each scenario has and the processing power of your computer, **it may take several minutes or more for the simulation to complete**. **Do not exit the WBC!**
{.is-warning}


# Results Dashboard
The Results Dashboard has 3 different panels to view WBC results from the simulations you ran. See below for an explanation of each panel. For guidance on how to interpret WBC results, click [here](/wbc-results).

---
![results1.png](/results1.png)
Above is a screenshot of the Scenario Results Panel. Here you can view each scenario individually. As you change scenarios from the drop down in area [2], the graphics will update. 

See numbering below for explanation of different sections. 
1. Click to change between the 3 different results panels. 
1. Click this dropdown menu to select other scenarios that were simulated. 
1. Here several key results are shown on a general hydrology graphic to help the user illustrate the results. 
1. This table lists all the parameters simulated in the WBC and the results of each one. 
1. This graphic illustrates how the water balance (mass balance) is divided. 
---
![results2.png](/results2.png)
Above is a screenshot of the Scenario Comparison Panel. This panel allows you to compare scenarios and then two parameters for each scenario. 

See numbering below for explanation of different sections. 
1. Here your scenarios are listed in a table format with key hydrology parameters.
1. Click on this column to change "False" to "True" in order to turn on the graph and plot the scenario results. 
1. Select two parameters to compare on the graphs for the plotted scenarios from the dropdown menus. 
1. Graph (Plot) area
---
![results3.png](/results3.png)
Above is a screenshot of the Raw Results Panel. This panel allows you to expoort all WBC results for all scenarios and perform additional analysis or further graphing of results. 

See numbering below for explanation of different sections. 
1. Click this button to select which WBC results will be exported. 
1. Click this button to export selected WBC results to an Excel file. 
1. Table of raw results for all scenarios.

## Summary of Key Output Variables
The following are definitions for key terms used in the “Results Dashboard” tabs:
- Evapotranspiration: Quantity of water lost through the combination of evaporation from the soil surface and transpiration through plant respiration. Evaporation + transpiration = evapotranspiration. The WBC breaks down evapotranspiration into Interception ET (leaves) and Soil ET. “Interception ET” represents the contribution of canopy interception storage to total ET, and “Soil ET” represents ET losses from the soil.
- Runoff: Water that immediately runs off the soil surface during a precipitation event and is not used by plants or absorbed into the soil. 
- Interflow: Water that flows downslope within the upper soil zone (usually the top 10 cm or so). 
- Recharge: Represents the quantity of water entering the shallow groundwater storage. 
- Groundwater Outflow: This is water that has percolated into the groundwater storage and then discharged into downstream rivers and springs.
- Change in water storage: Represents the overall change across all water storage compartments (i.e., final storages relative to initial storages at the beginning of the simulation or the start of a user-selected reporting period). 
- Water budget check: It is a diagnostic output and should be reported as zero. It represents the water balance as follows:
	- Precipitation = ET + Runoff + Interflow + Groundwater outflow ± change in storage
- Sediment Load: Represents landscape sediment erosion. 
