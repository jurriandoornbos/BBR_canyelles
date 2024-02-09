
<div align="center">
  <p>
    <a href="https://icaerus.eu" target="_blank">
      <img width="50%" src="https://icaerus.eu/wp-content/uploads/2022/09/ICAERUS-logo-white.svg"></a>
    <h3 align="center">BBR Canyelles implementation</h3>
    
   <p align="center">
    Using the Canyelles orthomosaic dataset from 06092023, implemented Botrytis Bunch Rot prediction.    
    <br/>
    <br/>
    <br/>
    <br/>
    <a href="https://github.com/icaerus-eu/repo-title/issues">Report Bug</a>
    -
    <a href="https://github.com/icaerus-eu/repo-title/issues">Request Feature</a>
  </p>
</p>
</div>

![Downloads](https://img.shields.io/github/downloads/icaerus-eu/repo-title/total) ![Contributors](https://img.shields.io/github/contributors/icaerus-eu/repo-title?color=dark-green) ![Forks](https://img.shields.io/github/forks/icaerus-eu/repo-titlee?style=social) ![Stargazers](https://img.shields.io/github/stars/icaerus-eu/repo-title?style=social) ![Issues](https://img.shields.io/github/issues/icaerus-eu/repo-title) ![License](https://img.shields.io/github/license/icaerus-eu/repo-title) 

## Table Of Contents
- [Summary](#summary)
- [Installation](#installation)
- [Usage](#usage)
- [Authors](#authors)
- [Acknowledgments](#acknowledgments)

## Summary

Based on the orthomosaics processed for the June 2023 [Canyelles dataset](https://zenodo.org/records/10171243), a Botrytis Bunch Rot risk implementation is made, based on the work from [Ariza et al. (2023)](https://github.com/mararizasentis/BBR), [full text for BBR also available](https://www.softxjournal.com/article/S2352-7110(23)00238-8/fulltext). BBR is an open-source standard workflow based on biophysical parameters for automatic Botrytis cinerea assessment in vineyards using UAV images.
![Botrytis map](https://github.com/jurriandoornbos/bbr_canyelles/blob/main/notebooks/can2023_bot_risk.png?height=150)

## Installation
Please install `uavgeo>0.2.1` and your preferred jupyter notebook editor in your python environment: 
```
pip install uavgeo jupyterlab
```
Then open the notebooks, and run the various code cells to explore the BBR implementation.

## Usage
It is assumed that the raw datasets are stored in the `data` folder. 

### Required input datasets are:
- Plant geometries: a regularly spaced grid with the centerpoints in the middel of the vineyard row.
- DSM: surface model which is  the default output from many photogrammetry tools, residual things geometries like CHM and DEM are calculated in the notebooks
- RGB/Multispectral orthomosaic: the input for NDVI and shadows map, calculated in the notebooks
- input_train_randomForest.csv: the processed dataset from [Ariza et al. 2023](https://www.softxjournal.com/article/S2352-7110(23)00238-8/fulltext)
- mask/shape of the vineyard for cutting out the shape.

### Code structure:
- `1_preprocessing.ipynb`: preprocesses all the datasets above ready for data extraction and stores them in `/data/preprocessed`. 
- `2_bbr_data_extraction_prediction.ipynb`: extracts all the values from the rasters using the plants geometries, and predicts the disease. 


## Authors
* **Jurrian Doornbos** - *Wageningen University* - [Jurrian Doornbos](https://github.com/jurriandoornbos)
* **Mar Ariza Sentis** - *Wageningen University* - [Mar Ariza Sentis](https://github.com/mararizasentis)
* **Esther Vera** - *Noumena* - [Esther Vera](https://github.com/esthernoumena)

## Acknowledgments
This project is funded by the European Union, grant ID 101060643.

<img src="https://rea.ec.europa.eu/sites/default/files/styles/oe_theme_medium_no_crop/public/2021-04/EN-Funded%20by%20the%20EU-POS.jpg" alt="https://cordis.europa.eu/project/id/101060643" width="200"/>
