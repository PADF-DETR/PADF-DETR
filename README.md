# PADF-DETR

[![DOI](https://zenodo.org/badge/1395611458.svg)](https://doi.org/10.5281/zenodo.23050050)

Selected source code and VADD validation/test data accompanying **PADF-DETR: Pose-Aware Directional Feature Learning and Adaptive Fusion for Fine-Grained Volleyball Action Detection in Crowded Scenes**.

**Authors:** Aiming Zeng, Yuan Xu, Weijie Zhong, and Keding Yan.

PADF-DETR studies single-frame volleyball action detection using pose-aware directional feature learning, bi-axial attention, and adaptive multi-scale fusion. VADD covers five actions: block, defense, serve, set, and spike.

## Release contents

- `PADF-DETR-source.zip`: selected source code and configurations
- `VADD-val-part1.zip`, `VADD-val-part2.zip`: 500 validation images and annotations
- `VADD-test-part1.zip`, `VADD-test-part2.zip`: 500 test images and annotations

This is a partial release. The 4,000 training images and trained model weights are not included. The source snapshot is incomplete and lacks `ultralytics/nn/tasks.py`, so an end-to-end workflow has not been verified. See [REPRODUCIBILITY_NOTES.md](REPRODUCIBILITY_NOTES.md) for dataset contents, setup details, and known limitations.

## Data and licensing

VADD was assembled from Japan High School Boys' Volleyball National Tournament footage. Redistribution rights for footage-derived images and the dataset license are being clarified; no open license is granted for these images. Ultralytics files retain their upstream AGPL-3.0 notices and applicable third-party terms.

## Citation

Zenodo DOI for release v1.0.1: [10.5281/zenodo.23050439](https://doi.org/10.5281/zenodo.23050439). The concept DOI for all versions is [10.5281/zenodo.23050050](https://doi.org/10.5281/zenodo.23050050). The v1.0.0 DOI is [10.5281/zenodo.23050051](https://doi.org/10.5281/zenodo.23050051). Citation metadata are available in [CITATION.cff](CITATION.cff).

Questions about these materials: [GitHub Issues](https://github.com/PADF-DETR/PADF-DETR/issues).
