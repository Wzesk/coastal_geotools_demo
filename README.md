# Littoral Shoreline Refinement
<a target="_blank" href="https://colab.research.google.com/github/Wzesk/coastal_geotools_demo/blob/main/sample_shoreline_refinement.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>


## Overview

This module refines approximate/coarse shorelines, typically extracted through image segmentation. It is one step in a larger, modular shoreline extraction pipeline. 

### Core Files

| File | Purpose | Details |
|------|---------|---------|
| `refine_boundary.py` | refines shoreline to match raster image | - builds a spline representation of the shoreline, resamples the image normal to the smoothed shoreline and segments that sampling using slope or kmeans to derive a more accurate shoreline |
| `extract_boundary.py` | extract shoreline from mask | - the initial extraction step, using a mask to and then applying simplication to remove mask artifacts |

## Installation: Conda (Current Method)
```bash
# Create and activate conda environment
conda create --name littoral_pipeline python=3.10
conda activate littoral_pipeline
conda env update --file environment.yml --prune
```
### Usage
To experiment with the shoreline refiner, open the example notebook in colab: 
<a target="_blank" href="https://colab.research.google.com/github/Wzesk/coastal_geotools_demo/blob/main/sample_shoreline_refinement.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

### Interactive Example
To draw your own shorelines, try out the live demo here: [Interactive Shoreline Refinement](https://refine.labs.littor.al/)

## Contributors
This module and the larger project it is a part of has had numerous contributors, including:

Walter Zesk, Tishya Chhabra, Leandra Tejedor, Philip Ndikum

Sarah Dole, Skylar Tibbits, Peter Stempel

## Reference
This project draws extensive inspiration from the [Coastsal Project](https://github.com/kvos/CoastSat) described in detail here:

Vos K., Splinter K.D., Harley M.D., Simmons J.A., Turner I.L. (2019). CoastSat: a Google Earth Engine-enabled Python toolkit to extract shorelines from publicly available satellite imagery. Environmental Modelling and Software. 122, 104528. https://doi.org/10.1016/j.envsoft.2019.104528 (Open Access)
