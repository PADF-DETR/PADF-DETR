# PADF-DETR: source code and VADD evaluation data

## Release status

This publication-preparation snapshot was archived as GitHub release [v1.0.0](https://github.com/PADF-DETR/PADF-DETR/releases/tag/v1.0.0) with Zenodo DOI [10.5281/zenodo.23050051](https://doi.org/10.5281/zenodo.23050051). It remains an incomplete reproducibility release: see the limitations below before using it to support a reproducibility claim.

The supplied package contains a modified Ultralytics code tree (its `__version__` is `8.0.201`), RT-DETR model configurations, and VADD validation/test images with object-detection annotations. The supplied manuscript describes single-frame volleyball action detection using VADD: 5,000 tournament images, with 4,000 training, 500 validation, and 500 test images. Only validation and test images are included here. Author metadata are provided below; dataset redistribution permissions remain unconfirmed. No independently reproduced performance claim is made here.

## Download and unpack

Repository: https://github.com/PADF-DETR/PADF-DETR

The source and data are distributed as five independent ZIP archives. Download `PADF-DETR-source.zip`, `VADD-val-part1.zip`, `VADD-val-part2.zip`, `VADD-test-part1.zip`, and `VADD-test-part2.zip`. Extract all five into the same directory; they contain non-overlapping files with the original directory paths. Each data archive contains 250 images and their matching annotations. The numbered files are ordinary ZIP archives, not a multipart ZIP stream. The SHA-256 checksums for the five ZIP downloads are provided in `PACKAGE_CHECKSUMS.json`.

## Repository layout

- `ultralytics/`: supplied Python source, configurations, and supporting files.
- `ultralytics/cfg/models/rtdetr/rtdetr-r18-PADR-Block-BASSA-ASF.yaml`: PADF-DETR architecture configuration.
- `ultralytics/cfg/models/rtdetr/rtdetr-r18.yaml`: supplied reference architecture.
- `ultralytics/nn/modules/block.py`: contains `PADR_Block` and `BASSA` definitions.
- `ultralytics/nn/modules/ASF.py`: contains `Zoom_cat` and `ScalSeq` definitions.
- `VADD(minmaldataset)/val/images/` and `val/labels/`: validation images and annotations.
- `VADD(minmaldataset)/test/images/` and `test/labels/`: test images and annotations.



Original source and data contents are preserved. Python bytecode, notebook checkpoint copies, and runtime caches were excluded from this prepared copy. The original ZIP remains unchanged.

## Dataset contents and format

| Split | JPEG images | Label files | Bounding boxes |
| --- | ---: | ---: | ---: |
| Validation | 500 | 500 | 584 |
| Test | 500 | 500 | 604 |

Each image has a matching text annotation file with the same stem. Nonempty rows have five whitespace-separated fields in YOLO-style detection format:

```text
class_id x_center y_center width height
```

Coordinates are normalized to image dimensions. Observed class IDs are `0` through `4`; the numeric mapping to the five named actions was not supplied. The model YAML retains an `nc: 80` setting, which does not match the five observed label IDs; the original dataset configuration and actual training setup must be recovered before use.

| Class ID | Validation boxes | Test boxes |
| --- | ---: | ---: |
| 0 | 164 | 198 |
| 1 | 9 | 10 |
| 2 | 84 | 73 |
| 3 | 144 | 138 |
| 4 | 183 | 185 |

Checks found no missing image-label pairs and no malformed/out-of-range annotation rows. No images were removed or reassigned.

## Installation and reproduction

A verified installation or reproduction command cannot yet be provided. The archive omits `ultralytics/nn/tasks.py`, although the RT-DETR model and trainer import `RTDETRDetectionModel` from that module. It also omits the project dependency specification, dataset YAML/class mapping, training split, trained checkpoints, study-specific execution scripts, and run settings/results.

Recover these files from the exact experiment version. Do not replace the modified package with a stock Ultralytics installation: that would not establish that the reported PADF-DETR model is reproduced. Record Python, PyTorch, CUDA, dependency versions, hardware, random seeds, optimizer, epochs, input size, split construction, and exact training/evaluation commands in the completed release.

All 139 supplied Python source files passed syntax parsing. No model import, training, inference, or metric reproduction has been verified.

## Provenance and licensing

Many supplied Ultralytics source headers state AGPL-3.0. Preserve upstream attribution and applicable third-party terms. The archive contains no top-level license text or dataset license. This README does not grant new rights over third-party code or images. The authors must identify the VADD source/version, collection and annotation methods, redistribution permissions, class names, and applicable data license. The v1.0.0 Zenodo record is already public; its existence does not establish redistribution rights or grant a data license.

## Citation and persistent access

The v1.0.0 preparation snapshot is archived on Zenodo at [10.5281/zenodo.23050051](https://doi.org/10.5281/zenodo.23050051) and corresponds to the [GitHub v1.0.0 release](https://github.com/PADF-DETR/PADF-DETR/releases/tag/v1.0.0). The documentation update in [GitHub v1.0.1](https://github.com/PADF-DETR/PADF-DETR/releases/tag/v1.0.1) is archived at [10.5281/zenodo.23050439](https://doi.org/10.5281/zenodo.23050439). The concept DOI for all versions is [10.5281/zenodo.23050050](https://doi.org/10.5281/zenodo.23050050). Use the version-specific DOI when citing a particular archived version.

## PLOS ONE data-sharing scope

The deposit must cover the data and metadata needed to reproduce the findings reported in the manuscript, including underlying figure/table values where relevant. A folder called “minimal dataset” does not establish that coverage. Map each manuscript result to the corresponding input data, code, settings, and output. Requirements: [PLOS data availability](https://journals.plos.org/plosone/s/data-availability) and [PLOS materials, software and code sharing](https://journals.plos.org/plosone/s/materials-and-software-sharing).

## Manuscript-reported methods

The supplied PLOS manuscript describes VADD as images from the Japan High School Boys' Volleyball National Tournament, annotated with Labelme and converted to YOLO format. The five action names are block, defense, serve, set, and spike; their numeric ID mapping is still missing. The source-video URL/version and redistribution permissions are not specified.

Reported environment: Ubuntu 20.04, Python 3.8, PyTorch 2.0.0, CUDA 11.8, NVIDIA RTX 4090 (24 GB), and Intel Xeon Gold 6430. Reported training: AdamW, batch size 16, 200 epochs, input 640 x 640, lr0=0.0001, lrf=1.0, weight_decay=0.0001, momentum=0.9, no pretrained weights, and augmentation disabled in the last 10 epochs. These are manuscript-reported settings, not an independently verified execution environment. Exact dependencies, class mapping, scripts, and random seeds remain to be supplied.

## Data-use statement supplied with the dataset

The accompanying dataset documentation describes the intended use as research and academic study and states that copyright and redistribution are subject to the original footage source and applicable permissions. It does not specify a standard data license or document those permissions. No CC BY, CC0, or other new data license is asserted by this repository.

The author-provided README states that these validation/test splits match the paper experiments. This statement has not been verified against original experiment logs. It also states that no additional names, contact details, student IDs, or player IDs are included; that does not establish that visible people in the images are anonymized.

The dataset subset does not enable full retraining from scratch. Repository hosting can accommodate files beyond supplementary-material limits; omitting training data therefore needs a study-specific access explanation and a persistent source where applicable.

## Authors and associated manuscript

Aiming Zeng, Yuan Xu, Weijie Zhong, and Keding Yan, in this order.

- Aiming Zeng and Weijie Zhong: School of General Education, Dongguan City University, Dongguan, China.
- Yuan Xu: School of Artificial Intelligence, Dongguan City University, Dongguan, China.
- Keding Yan: School of Electronics and Information Engineering, Xi'an Technological University, Xi'an, China; corresponding author.

Associated manuscript title: **PADF-DETR: Pose-Aware Directional Feature Learning and Adaptive Fusion for Fine-Grained Volleyball Action Detection in Crowded Scenes**.

These bibliographic details were taken from the author-supplied manuscript source. No publication status, journal acceptance, article DOI, or ORCID is asserted. The manuscript and its figures are not included in this repository. See `CITATION.cff` for repository citation metadata, current version information, and version-specific archive DOI references. No article DOI or publication status is asserted here.

## Archival publication status

The dataset creator has stated that public redistribution authorization for the original match footage and derived images has not been obtained and no dataset license has been selected. The v1.0.0 Zenodo record (DOI `10.5281/zenodo.23050051`) and the documentation-only v1.0.1 record (DOI `10.5281/zenodo.23050439`) are public. The concept DOI covering all versions is `10.5281/zenodo.23050050`. The records and this repository do not grant an open license for the images. Rights and permitted access remain unresolved.


