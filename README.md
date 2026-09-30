# PADF-DETR


[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23050051.svg)](https://doi.org/10.5281/zenodo.23050051)

Selected source code and VADD validation/test data accompanying **PADF-DETR: Pose-Aware Directional Feature Learning and Adaptive Fusion for Fine-Grained Volleyball Action Detection in Crowded Scenes**.

**Authors:** Aiming Zeng, Yuan Xu, Weijie Zhong, and Keding Yan.

PADF-DETR studies single-frame volleyball action detection using pose-aware directional feature learning, bi-axial attention, and adaptive multi-scale fusion. VADD contains five action categories: block, defense, serve, set, and spike.

## What is included

| File | Contents |
|---|---|
| [PADF-DETR-source.zip](PADF-DETR-source.zip) | Supplied model source code and configurations |
| [VADD-val-part1.zip](VADD-val-part1.zip), [VADD-val-part2.zip](VADD-val-part2.zip) | 500 validation images and matching labels |
| [VADD-test-part1.zip](VADD-test-part1.zip), [VADD-test-part2.zip](VADD-test-part2.zip) | 500 test images and matching labels |

This is a **partial code and data release**. The full VADD dataset described in the paper contains 5,000 images; the 4,000 training images and trained model weights are not included here.

## Download and use

Download the five ZIP files and extract them into the same directory. Each data ZIP is independently extractable and contains 250 images with corresponding labels.

```text
ultralytics/                   # Source code and model configurations
VADD(minmaldataset)/
  val/images/                  # Validation images
  val/labels/                  # Validation annotations
  test/images/                 # Test images
  test/labels/                 # Test annotations
```

Labels use YOLO format, with one object per line:

```text
class_id x_center y_center width height
```

Coordinates are normalized to image dimensions. Class IDs range from 0 to 4; their mapping to action names still needs to be supplied.

The source snapshot is incomplete, including a missing `ultralytics/nn/tasks.py`, and does not currently support a verified end-to-end training or evaluation workflow. The data check also identified 15 identical image hashes shared across validation and test splits. See [detailed notes](REPRODUCIBILITY_NOTES.md) and [audit results](AUDIT.json) before using the splits for evaluation. Download checksums are in [PACKAGE_CHECKSUMS.json](PACKAGE_CHECKSUMS.json).

## Data source and licensing

VADD was assembled from Japan High School Boys' Volleyball National Tournament footage and annotated with Labelme, then converted to YOLO format. Public redistribution authorization for the footage-derived images and a dataset license are pending clarification; no open license for the images is granted here. Ultralytics source files retain their upstream AGPL-3.0 notices and applicable third-party terms.

## Citation

Author and repository citation metadata are provided in [CITATION.cff](CITATION.cff). The v1.0.0 source code and VADD evaluation data are archived on Zenodo: [10.5281/zenodo.23050051](https://doi.org/10.5281/zenodo.23050051).

For questions about these materials, please use [GitHub Issues](https://github.com/PADF-DETR/PADF-DETR/issues).
