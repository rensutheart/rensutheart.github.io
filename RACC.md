---
layout: defaultPage
title: RACC
heading: Regression adjusted colocalization colour mapping
tag-line: A tool for analyzing the correlation of the colococalization between two fluorescent channels
---

**Regression adjusted colocalization colour mapping (RACC)** is a method to spatially visualize colocalization in fluorescence based micrographs using a colourmap. RACC is designed to meet three objective, firstly to highlight regions within a cell that have strong positive correlation between two fluorescence channels, secondly to highlight colocalized regions that have greater combined fluorescence intensities and lastly to remove outliers in the data while maximizing the utilization of the colourmap's spectrum. These objectives were met using Deming regression along with a penalization factor ($\theta$) to suppress voxels for which the underlying fluorescence intensities are less strongly correlated. Outliers are removed by using automatically calculated thresholds.

After regression has been calcualted the colourmap value can be determined with the following formula:

$$
    C_i=
    \begin{cases}
      0, & \text{if}\ \ \  x_{p_i} \leq d(x_{p_{max}}-x_{p_0}) \mathrm{tan} (\theta) + x_{p_0} \ \ \text{or}\ \ d > d_t \\ 
      \frac{x_{p_i}-x_{p_0}}{x_{p_{max}}-x_{p_0}} - d ~ \mathrm{tan} (\theta),  & \text{if}\ \ \ d(x_{p_{max}}-x_{p_0})\mathrm{tan}(\theta) + x_{p_0} < x_{p_i} < x_{p_{max}} \\
      1 - d ~ \mathrm{tan}(\theta), & \text{if}\ \ \  x_{p_i} \geq x_{p_{max}} \\
    \end{cases}
$$

For a full derivation and explanation please refer to the [paper](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0225141). 

## Download and installation

The RACC utility can be downloaded from here (requires [Python 3.5+](https://www.python.org/downloads/)):

- [RACC v0.8.1 ZIP file (includes sample files)]({{ site.url }}/download/RACC_v0.8_1.zip)

### Quick installation (Windows only)
Simply run the included .bat files to install all the packages as well as run RACC.


### Manual installation (Windows, Linux, MacOS)
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

### Utility settings

In the RACC utility you select the two input files (both must be either 2D or 3D). You can optionally view the input images which will be displayed as soon as you click "Process". 

Under the parameters group, you can set the background filtering thresholds for the individual channels. The penelization factor, which diminishes voxels that are far from the regression line. The precentage to include is used to automatically calculate both a distance threshold away from the regression line, and a maximum combined intensity (all voxels beyond these thresholds are excluded from the resulting visualization).

In the output settings, you can select the file type, whether it should use the built in colourmap or output the image as grayscale. You can also optionally visualize the output within the utility.

After all the settings are as desired, click on "Process" to calculate the RACC output for the given input.

## Citation
If you used this method or tool in your research please cite it as follows:

Theart RP, Loos B, Niesler TR (2019) Regression adjusted colocalisation colour mapping (RACC): A novel biological visual analysis method for qualitative colocalisation analysis of 3D fluorescence micrographs. PLoS ONE 14(11): e0225141. https://doi.org/10.1371/journal.pone.0225141

## Report errors

Please note that this utility is not in active development, however, please report any problems with the utility to rensutheart22 (at) gmail.com
