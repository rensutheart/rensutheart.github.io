---
layout: defaultPage
title: RACC
heading: Regression adjusted colocalization colour mapping
tag-line: A tool for analyzing the correlation of the colococalization between two fluorescent channels
---

**Regression adjusted colocalization colour mapping (RACC)** is a method to spatially visualize colocalization in fluorescence based micrographs using a colourmap. RACC is designed to meet three objective, firstly to highlight regions within a cell that have strong positive correlation between two fluorescence channels, secondly to highlight colocalized regions that have greater combined fluorescence intensities and lastly to remove outliers in the data while maximizing the utilization of the colourmap's spectrum. These objectives were met using Deming regression along with a penalization factor ($\theta$) to suppress voxels for which the underlying fluorescence intensities are less strongly correlated. Outliers are removed by using automatically calculated thresholds.

## Download and installation

The RACC utility can be downloaded from here (requires [Python 3.5+](https://www.python.org/downloads/)).

It currently has the following dependencies, that can be installed by running the following `pip` commands in the terminal/command prompt.

```
pip install numpy
pip install matplotlib
pip install scikit-image
pip install scipy
pip install mayavi
pip install PyQt5
```

You can then run RACC by typing the following into terminal/command prompt, while you are in the same path as where `RACC.py` is stored.

```
python RACC.py
```

## Using this RACC utility

### Input file types

RACC takes **two single channel** fluorescence images or stacks as input - image can still be RGB, but should not contain more than one fluorescent label. The input type of 2D images or single slices can be any of the common file types (PNG, JPG, TIFF, etc.). 3D image stacks should be provided in TIFF format (separate slices can be combined into a TIFF file using software like [ImageJ/Fiji](https://fiji.sc/)). _Note:_ In the fluorescence channel visualization in 3D the first provided stack will be visualized in Red and the second stack will be visualized in Green, this does not affect the analysis.
