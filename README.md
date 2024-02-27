# HLS-SCA(Snow Mapping Project)
Machine learning (ML) techniques are becoming increasingly vital for land cover classification, particularly in mapping snow-covered areas. This repository focuses on evaluating the effectiveness of ML methods compared to traditional index-based methods for snow mapping using the Harmonized Landsat Sentinel-2(HLS) product at 10-m spatial resolution.

# NOTE
This folder structure does not match where the code was developed or executed. Instead, to match the development environment, access cyrocloud and mimic the folder structure (or replace folder paths) as described in the code.

## Objectives
1. Access and visualize airborne and satellite imagery (HLS).
2. Derive preliminary snow maps using index-based methods.
3. Create a random forest model tailored to HLS datasets and evaluate its performance.
4. Explore feature importance and model transferability, including tests on independent datasets.
5. Derive snow-covered areas using existing models, including Google Dynamic World and NASA-IBM geospatial model.

## Tools used in this project
* [Poetry](https://towardsdatascience.com/how-to-effortlessly-publish-your-python-package-to-pypi-using-poetry-44b305362f9f): Dependency management - [article](https://mathdatasimplified.com/2023/06/12/poetry-a-better-way-to-manage-python-dependencies/)
* [hydra](https://hydra.cc/): Manage configuration files - [article](https://mathdatasimplified.com/2023/05/25/stop-hard-coding-in-a-data-science-project-use-configuration-files-instead/)
* [pre-commit plugins](https://pre-commit.com/): Automate code reviewing formatting
* [DVC](https://dvc.org/): Data version control - [article](https://mathdatasimplified.com/2023/02/20/introduction-to-dvc-data-version-control-tool-for-machine-learning-projects-2/)
* [pdoc](https://github.com/pdoc3/pdoc): Automatically create an API documentation for your project
* [crycloud](https://book.cryointhecloud.com/content/Getting_Started.html): Builtin environment to access and manipulate data.
* [2021 Cloud Hackathon](https://nasa-openscapes.github.io/2021-Cloud-Hackathon/tutorials/02_Data_Discovery_CMR-STAC_API.html): Tutorial on data access helps to build baseline model codes.
* [Sentinel Hub](https://apps.sentinel-hub.com/eo-browser/):  Finding an image date/time/location with snow in a place.

## Set up the environment
1. Install [Poetry](https://python-poetry.org/docs/#installation)
2. Set up the environment:
```bash
make env 
```

## Install dependencies
To install all dependencies for this project, run:
```bash
poetry install
```

To install a new package, run:
```bash
poetry add <package-name>
```

## Version your data
To track changes to the "data" directory, type:
```bash
dvc add data
```

This command will create the "data.dvc" file, which contains a unique identifier and the location of the data directory in the file system.

To keep track of the data associated with a particular version, commit the "data.dvc" file to Git:
```bash
git add data.dvc
git commit -m "add data"
```

To push the data to remote storage, type:
```bash
dvc push 
```

## Auto-generate API documentation

To auto-generate API document for your project, run:

```bash
make docs
```
