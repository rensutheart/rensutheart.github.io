---
layout: defaultPage
title: RACC
heading: Regression adjusted colocalisation colour mapping
tag-line: Interactive two-channel colocalisation visualisation for napari
---

**Regression adjusted colocalisation colour mapping (RACC)** is a qualitative visual analysis method for fluorescence microscopy. It maps two-channel colocalisation into an intensity-aware colour representation so that the spatial distribution of correlated signal can be inspected in 2D and 3D.

The maintained implementation is now the **napari-racc** plugin.

[Install the napari plugin](https://pypi.org/project/napari-racc/){: .btn .btn-primary }
[View the source code](https://github.com/rensutheart/napari-racc){: .btn }
[Read the paper](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0225141){: .btn }

## Current implementation: napari-racc

`napari-racc` provides an interactive napari widget for calculating and visualising RACC from two image layers. It supports 2D images and 3D stacks, with the RACC calculation performed on the full volume where possible.

Install it into a Python environment that has napari:

```bash
pip install napari-racc
```

Then open napari and choose:

```text
Plugins > RACC (napari-racc)
```

The plugin includes:

- two input image-layer selectors
- channel thresholds and Costes threshold calculation
- penalisation factor and percentile controls
- live RACC recalculation
- overlay, RACC-only, 3D side-by-side, and MIP side-by-side views
- selectable probe colours and RACC colormaps
- XY/Z display scale controls for anisotropic stacks
- optional bounding boxes for 3D views
- TIFF export of the generated RACC stack

![napari-racc widget controls]({{ '/assets/images/racc-widget-controls.png' | relative_url }})

## Example views

The plugin is intended to let you move quickly between the source-channel overlay and the RACC view.

![3D side-by-side overlay and RACC view]({{ '/assets/images/racc-side-by-side-volume.png' | relative_url }})

Maximum-intensity-projection side-by-side views are also available for fast inspection.

![MIP side-by-side overlay and RACC view]({{ '/assets/images/racc-side-by-side-mip.png' | relative_url }})

## Method and citation

For the full method derivation and biological motivation, cite:

Theart RP, Loos B, Niesler TR (2019) Regression adjusted colocalisation colour mapping (RACC): A novel biological visual analysis method for qualitative colocalisation analysis of 3D fluorescence micrographs. *PLOS ONE* 14(11): e0225141. <https://doi.org/10.1371/journal.pone.0225141>

Patent publication:

- [US20220189129A1](https://patentimages.storage.googleapis.com/f1/10/5d/798b2ae1eea441/US20220189129A1.pdf)

## Legacy Python utility

The original standalone Python utility is preserved here for reproducibility, but it is **not actively maintained**. New users should use the napari plugin unless they specifically need the historical implementation.

- [RACC v0.8.1 ZIP file, including sample files]({{ '/download/RACC_v0.8_1.zip' | relative_url }})
- [Legacy utility notes and formula](RACC.html)

Legacy downloads:

- [RACC v0.8 ZIP file]({{ '/download/RACC_v0.8.zip' | relative_url }})
- [RACC v0.75 ZIP file]({{ '/download/RACC_v0.75.zip' | relative_url }})

## Links

- [napari-racc on PyPI](https://pypi.org/project/napari-racc/)
- [napari-racc on GitHub](https://github.com/rensutheart/napari-racc)
- [RACC paper in PLOS ONE](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0225141)
