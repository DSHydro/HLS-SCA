# HLS-SCA(Snow Mapping Project)
Machine learning (ML) techniques are becoming increasingly vital for land cover classification, particularly in mapping snow-covered areas. This repository focuses on evaluating the effectiveness of ML methods compared to traditional index-based methods for snow mapping using the Harmonized Landsat Sentinel-2(HLS) product at 10-m spatial resolution.

## Objectives
1. Access and visualize airborne and satellite imagery (HLS).
2. Derive preliminary snow maps using index-based methods.
3. Create a random forest model tailored to HLS datasets and evaluate its performance.
4. Explore feature importance and model transferability, including tests on independent datasets.
5. Derive snow-covered areas using existing models, including Google Dynamic World and NASA-IBM geospatial model.

## Tools used in this Project/References
Environment
* [Cryocloud](https://book.cryointhecloud.com/content/Getting_Started.html): Built-in environment to access and manipulate data.

Tutorials
* [2021 Cloud Hackathon](https://nasa-openscapes.github.io/2021-Cloud-Hackathon/tutorials/): Tutorial on data access helps to build baseline model codes. We primarily used tutorials 2 (to collect relevant links), 4 (to set up NASA Earthdata access), and 5 (extracting .tif files from links collected in tutorial 2).
* [Random Forest Walkthrough](https://geo-smart.github.io/scm_geosmart_use_case/chapters/three.html): A walkthrough on data formatting and general guidelines for creating a random forest model. [Also used the provided function library here](https://github.com/geo-smart/scm_geosmart_use_case/blob/main/book/chapters/functions_book_chapter_SCA.py)

HLS Data Access
* [Sentinel Hub](https://apps.sentinel-hub.com/eo-browser/):  Finding an image date/time/location with snow in a place.
* [Most recent ASO datasets](https://www.airbornesnowobservatories.com/ ): Packages for most recent ASO data.
* [Landsat and Sentinel band reference table](https://lpdaac.usgs.gov/data/get-started-data/collection-overview/missions/harmonized-landsat-sentinel-2-hls-overview/#hls-spectral-bands): The table for HLS Spectral Bands we used to compare and cauculate the NDSI. And we calculated NDSI followed by (https://www.usgs.gov/landsat-missions/normalized-difference-snow-index).
* [Tiling System](https://hls.gsfc.nasa.gov/products-description/tiling-system/): The naming convention used in some parts is based off of the ESA's tiling system. This links to a high resolution image of the system.

Lidar Data
* [Earthdata Search](https://search.earthdata.nasa.gov/search): We used 50m resolution lidar data found via Earthdata Search as our truth values due to it being very precise and accurate. See [here](https://nsidc.org/data/user-resources/help-center/search-order-and-customize-nsidc-daac-data-nasa-earthdata-search): for a tutorial on how to use the tool.
* [ASO](https://data.airbornesnowobservatories.com/) Alternatively, we can look in here for specific regions of lidar data.

## Accessing the working environement
To match the development environment, access cyrocloud.

## Set up a local environment
If you are not able to access cryocloud, then look at the provided [[environment.yml]] file extracted from cryocloud.
From the same directory, run `conda env create --name envname --file=environment.yml` (replacing envname) to generate a conda environment. This will have all libraries at the appropriate versions that we used in this project.

## Model 0
We've generated model 0 based on "ground truth" data, derived from the HLS NDSI product using a threshold of 0.4.
To get model 0, please follow the steps on notebooks:
1. DataDiscovery.ipynb
2. EarthdataLoginSetup.ipynb
3. EarthdataLoginSetup.ipynb

## Random Forest Model
In Process...