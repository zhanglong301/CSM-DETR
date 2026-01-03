# CSM-DETR: Construction Site Monitoring via Mamba-Enhanced Detection Transformer for UAV Aerial Imagery

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)
[![Dataset](https://img.shields.io/badge/Dataset-Baidu%20Pan-blue)](https://pan.baidu.com/s/1fKiM0qmcjHqRwHZwKAhtfA?pwd=vtwu)

## Overview

This repository contains the official implementation of **CSM-DETR**, a novel Mamba-enhanced detection transformer specifically designed for UAV-based construction site monitoring. Our framework achieves state-of-the-art performance with 91.8% mAP@0.5 and 73.6% mAP@0.5:0.95 while maintaining real-time inference at 38 FPS.

### Key Features

- **MobileMamba Backbone**: Achieves linear computational complexity O(n) through selective state space models
- **Dual-Attention Spatial Integration (DASI)**: Captures both local details and global context through parallel attention streams
- **Cross-Scale Deformable Fusion (CSDF)**: Enables flexible cross-scale feature interaction through deformable sampling
- **Hierarchical Local-Aware Fusion (HLAF)**: Preserves fine-grained spatial information during multi-scale feature aggregation

## Code Availability

⚠️ **Note:** The source code is currently being organized and will be released upon paper acceptance. Please star this repository to stay tuned for updates.

---

## UAV-CSM47 Dataset

We also release **UAV-CSM47** (UAV Construction Site Monitoring with 47 categories), a comprehensive benchmark dataset for UAV-based construction site object detection. The dataset contains **15,860 high-resolution aerial images** with **19,498 annotated object instances** across **47 construction-related categories**.

The dataset is designed to facilitate research in:
- UAV-based construction site monitoring
- Aerial object detection
- Multi-scale object detection
- Real-time detection systems

## Dataset Statistics

| Statistic | Value |
|-----------|-------|
| Total Images | 15,860 |
| Total Instances | 19,498 |
| Categories | 47 |
| Image Resolution | 4000×3000 to 5472×3648 |
| Ground Sampling Distance | 1.5-8 cm |
| Flight Altitude | 30-120 meters |

### Category Distribution

The dataset is organized into **5 major groups**:

| Group | Categories | Instances | Percentage |
|-------|------------|-----------|------------|
| **Vehicles** | 8 | 7,966 | 40.9% |
| **Machinery** | 11 | 3,986 | 20.4% |
| **Materials** | 16 | 3,037 | 15.6% |
| **Structures** | 8 | 3,200 | 16.4% |
| **Earthwork** | 4 | 1,309 | 6.7% |

### Detailed Categories

#### Vehicles (8 categories)
| Category | Count | % |
|----------|-------|---|
| Car | 2,244 | 11.51% |
| Big Truck | 1,507 | 7.73% |
| Van | 1,489 | 7.64% |
| Boxcar | 1,109 | 5.69% |
| Small Truck | 952 | 4.88% |
| Concrete Truck | 384 | 1.97% |
| Bus | 173 | 0.89% |
| Watering Cart | 108 | 0.55% |

#### Machinery (11 categories)
| Category | Count | % |
|----------|-------|---|
| Excavator | 1,308 | 6.71% |
| Bulldozer | 753 | 3.86% |
| Crane | 597 | 3.06% |
| Agri. Tricycle | 374 | 1.92% |
| Pickup | 349 | 1.79% |
| Tower Crane | 311 | 1.60% |
| Drill | 290 | 1.49% |
| Closed Crane | 210 | 1.08% |
| Mixer | 105 | 0.54% |
| Road Roller | 46 | 0.24% |
| Leveling Machine | 43 | 0.22% |

#### Materials (16 categories)
| Category | Count | % |
|----------|-------|---|
| Green Cover | 837 | 4.29% |
| Bricks | 318 | 1.63% |
| Brick | 300 | 1.54% |
| Woodpile | 281 | 1.44% |
| Garbage | 261 | 1.34% |
| Concrete House | 230 | 1.18% |
| Fuel Tank | 204 | 1.05% |
| Bar Deposits | 131 | 0.67% |
| Large Cement Pipe | 100 | 0.51% |
| Mid Cement Pipe | 85 | 0.44% |
| Crushed Stones | 84 | 0.43% |
| Thin Steel Pipe | 64 | 0.33% |
| Small Cement Pipe | 53 | 0.27% |
| Slab | 49 | 0.25% |
| Crude Steel Pipe | 22 | 0.11% |
| Big Steel Pipe | 18 | 0.09% |

#### Structures (8 categories)
| Category | Count | % |
|----------|-------|---|
| Building | 712 | 3.65% |
| Scaffold | 605 | 3.10% |
| Grey Enclosure | 390 | 2.00% |
| Greenhouse | 337 | 1.73% |
| Blue Enclosure | 308 | 1.58% |
| Simple House | 304 | 1.56% |
| Building Frame | 287 | 1.47% |
| Big Building | 257 | 1.32% |

#### Earthwork (4 categories)
| Category | Count | % |
|----------|-------|---|
| Earth Vehicles | 558 | 2.86% |
| Soil Mound | 320 | 1.64% |
| Excavation Pit | 245 | 1.26% |
| Backfill Area | 186 | 0.95% |

### Dataset Split

| Split | Images | Percentage |
|-------|--------|------------|
| Training | 11,102 | 70% |
| Validation | 2,379 | 15% |
| Test | 2,379 | 15% |

## Download

**File:** UAV-CSM.zip

**Download Link:** [Baidu Pan](https://pan.baidu.com/s/1fKiM0qmcjHqRwHZwKAhtfA?pwd=vtwu)

- **Link:** https://pan.baidu.com/s/1fKiM0qmcjHqRwHZwKAhtfA?pwd=vtwu
- **Password:** vtwu

## Dataset Structure

```
UAV-CSM47/
├── images/
│   ├── train/
│   ├── val/
│   └── test/
├── labels/
│   ├── train/
│   ├── val/
│   └── test/
└── README.md
```

## Annotation Format

Annotations are provided in YOLO format:
```
<class_id> <x_center> <y_center> <width> <height>
```
All coordinates are normalized to [0, 1].

## Data Collection

- **UAV Platforms:** DJI Phantom 4 Pro, DJI Mavic 3 Enterprise
- **Camera Resolution:** 20MP
- **Collection Sites:** 15 active construction sites
- **Collection Period:** 12 months
- **Flight Altitude:** 30-120 meters
- **Viewing Angles:** Nadir to 45-degree oblique
- **Environmental Conditions:** Clear, cloudy, light rain, haze

## Benchmark Results

Performance comparison on UAV-CSM47 test set:

| Method | mAP@0.5 | mAP@0.5:0.95 | FPS |
|--------|---------|--------------|-----|
| YOLOv5-L | 82.1% | 65.8% | 62 |
| YOLOv8-L | 84.3% | 68.2% | 58 |
| YOLOv10-L | 85.2% | 69.1% | 55 |
| RT-DETR-L | 87.4% | 71.3% | 42 |
| **CSM-DETR (Ours)** | **91.8%** | **73.6%** | 38 |

## Citation

If you use this dataset in your research, please cite our paper:

```bibtex
@article{zhang2025csmdetr,
  title={CSM-DETR: Construction Site Monitoring via Mamba-Enhanced Detection Transformer for UAV Aerial Imagery},
  author={Zhang, Long},
  journal={},
  year={2025}
}
```

## License

This dataset is released under the [CC BY-NC 4.0 License](https://creativecommons.org/licenses/by-nc/4.0/).

- **Attribution** — You must give appropriate credit, provide a link to the license, and indicate if changes were made.
- **NonCommercial** — You may not use the material for commercial purposes.

## Contact

For questions or issues regarding the dataset, please:
- Open an issue on [GitHub](https://github.com/zhanglong301/CSM-DETR)
- Contact: 2024990067@cipuc.edu.cn

## Acknowledgments

We thank all annotators and construction site managers who contributed to this dataset.

---

**GitHub Repository:** [https://github.com/zhanglong301/CSM-DETR](https://github.com/zhanglong301/CSM-DETR)
