---
title: Installing the WBC
description: How to install the WBC on your computer
published: true
date: 2020-09-30T18:02:42.047Z
tags: install, download, installer, package, imagery, aerial, satellite
editor: markdown
---

# Dowload the WBC
You first need to download the WBC installation package from the link below **(link directs to google drive repository)**
> [WBC Download Folder](https://drive.google.com/drive/folders/1oXhB-Jr87M7D4VOErWPvP-p6zWZG2Iud)
{.is-info}


![install2.png](/install2.png)
*WBC Download Folder*

---

This folder has several items of interest:
1. **The WBC install package labeled *WBC_Ethiopia_V2.1.0_installer.zip***
1. WBC Version Release Notes
1. WBC Technical Guidance Document
1. Raster files inside the *Rasters* folder
	4.1 This folder contains zipped raster images that can be downloaded and used within the WBC mapping tab. 
	4.2 Raster images must be downloaded and unzipped to the WBC data directory. By **default** this is `C:\Program Files\WBC_Ethiopia\data\Spatial\Imagery`
	4.3 This folder contains a *Soil Texture* raster that can be used when the soil texture of a site is unknown. For more details on how to use this, click here. 
1. WBC software patches for when new versions come out. 
1. Previous versions folder. 

# Installing the WBC
> [Video on installing the WBC](/1_installing_the_wbc_2.mp4)
{.is-info}


After you have downloaded the installation zip file. Perform the following:
1. Locate your download, this is typically in your downloads folder. 
2. Unzip the *WBC_Ethiopia_V2.1.0_installer.zip* file to a location on your computer. 
3. Click on the file labeled "**install**" that has the file type "**Windows Batch File**"
![install1.png](/install1.png)
> Administrator rights may be required to install the WBC. Contact your Information Technology (IT) department or computer administrator to assist you in installing the software.
{.is-info}

> A popup window may appear that says "Windows protected your PC" and this will prevent you from installing the software. Select ***More Info*** and then ***Run Anyway***
{.is-warning}

4. By default, the WBC will be installed to `C:\Program Files\WBC_Ethiopia` *it is recommended that you do **not** change the installation location*
5. To run the WBC, click on the *WBC_Ethiopia* application file inside `C:\Program Files\WBC_Ethiopia` (see image below)
![wbc_install1_icon.png](/wbc_install1_icon.png)
## Installing Imagery and Soil Rasters
> [Video on installing the WBC raster files](/2_installing_the_wbc_rasters.mp4)
{.is-info}

To install the satellite imagery to be used by the WBC mapping function, download the raster package for the area you are interested in. The following files are available for download:

**General:**
1. Ethiopia, country-wide, low resolution raster
1. Soil Texture (30m)

**Woredas**
1. Arsi Negele
1. Babile
1. Deder
1. Dire Dawa
1. Heben Arsi
1. Melka Belo
1. Midega Tola
1. Shalla
1. Ziway Dugda

> Imagery files are very large, several GBs, so it is recommended you download these on a high speed connection and only download what is necessary for your analysis. 
{.is-warning}

After you have finished downloading the *.7z* imagery file, unzip the file. 

Then, copy and paste (or move) the 3 separate files inside the unzipped folder, these will have the file extensions of **.tif, .mwi, and .mwh** to the **Imagery folder** located in your WBC installation directory. 

By default this is `C:\Program Files\WBC_Ethiopia\data\Spatial\Imagery`
