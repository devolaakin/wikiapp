---
title: Key Assumptions
description: 
published: true
date: 2020-09-28T15:05:26.576Z
tags: assumptions, development, constraints
editor: markdown
---

# Key Methods and Assumptions
Key methods and assumptions employed in the WBC are summarized below:
-	A daily precipitation time series is required as input, and this series is disaggregated to hourly values by the WBC. The hourly distribution is assumed to follow a SCS type II distribution with peak rainfall occurring at midday.
-	A daily potential evapotranspiration (PET) time series is also required as input, and the daily series is disaggregated to hourly values by the WBC. The hourly distribution is assumed to follow a normal distribution centered on midday. Latitude of the weather station and Julian day are used to calculate the average daylight hours per day, which is in turn used to define the duration of the non-zero PET period within each day. The average daylight hours per day for each month for various locations across the globe is available from http://www.climatemps.com/.
-	Water is assumed to only flow downslope/downstream in the WBC. Therefore, no interaction is assumed between transects (i.e., “cross slope,” along the lateral dimension of the farm). In addition, the WBC currently assumes that no water or sediment are entering the plot from areas located upslope of the plot. 
-	Within each transect, water and sediment fluxes from an upstream cell are linked, as appropriate, to the downstream or receiving cell. The following assumptions apply for upstream to downstream cell linkage:
	-	Surface runoff and interflow from an upstream cell are routed to the receiving cell. The receiving cell, in addition to generating surface runoff from rainfall within its own domain, receives upstream surface runoff as an external input. Similarly, interflow from upstream enters the upper soil zone of the receiving cell.
	-	Water entering the lower soil zone and the resulting groundwater (GW) flows are tracked by individual cells (i.e., there is no linkage of GW flows to other receiving cells). The groundwater flow output reported for the simulated farm or field area reflects the sum of the GW flows generated from each cell.
-	Planting pits, trenches, level bunds, and level Fanya Juus, which are generally referred to as “infiltration features” below, are simulated based on the following methods and assumptions:
	-	Inflows to the infiltration pits/ditches include: 1) direct rainfall to the feature itself, and 2) surface runoff and interflow entering the feature from the upstream cell. 
	-	Overflow occurs when the actual water storage volume in a pit/ditch exceeds the total capture capacity of that pit/ditch.
	-	The volume of water infiltrating into the soil from a pit or ditch is routed to the lower soil zone of the (downstream) receiving cell.
	-	All sediment routed to an infiltration pit/ditch via surface runoff from the adjacent upstream cell (if any) will be assumed to deposit in that pit/ditch. As a result, the pit/ditch will gradually fill in with sediment over time, and the total available water capacity of the pit/ditch will decrease. The rate of in-filling for each pit/ditch feature included in the simulation will be reported in the “Results Dashboard” in a future WBC release (Version 3).
-	The WBC implicitly represents the planting, growth, and harvest cycles for various crop / land cover types through the scaling of key model parameters influencing hydrology and sediment washoff. Further discussion is provided in the “Model Inputs and Parameters” section.
-	The WBC, as currently designed, does not support the evaluation of significant gully areas that may occur between laterally adjacent plots.
-	Deep groundwater losses (inactive groundwater in Figure 2), which represent groundwater lost from the basin due to deep percolation (e.g., to a subsurface aquifer), are assumed to be zero.
