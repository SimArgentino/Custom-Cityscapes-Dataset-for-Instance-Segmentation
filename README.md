# 🌆 Custom Cityscapes Dataset for Instance Segmentation

## 📌 Overview

This repository provides a curated collection of **10 versions** of the well-known **Cityscapes** dataset, redesigned to support **instance segmentation** tasks. While the original Cityscapes dataset is widely used for semantic segmentation and scene understanding, it lacks proper formatting for instance-level annotation required by modern architectures.

To address this, we used **Roboflow 3.0 Instance Segmentation (Fast)** tools to reprocess the data, applying structured annotations, standardized resizing, and various class definitions. The result is a scalable dataset family tailored to different experimental needs.

---

## 🗃️ Dataset Structure and Purpose

Each version of the dataset was built with a specific use case in mind—from quick prototyping to high-precision segmentation. All datasets share the same preprocessing pipeline (auto-orient, resize to 640×640), and were exported in YOLOv8-compatible format.

The key differences between versions lie in the number of classes and the granularity of annotation.

| Version | # Classes | # Images | Train | Val | Test | Description |
|---------|-----------|----------|-------|-----|------|-------------|
| v1      | 8         | 132      | 86    | 26  | 20   | Minimal setup for debugging and testing |
| v2      | 8         | 132      | 86    | 26  | 20   | Slightly refined version of v1 |
| v3      | 39        | 2641     | 1971  | 599 | 71   | Maximum class coverage, includes all available object groups |
| v4      | 39        | 2641     | 1954  | 478 | 209  | Similar to v3, adjusted for training balance |
| v5      | 26        | 2641     | 2000  | 421 | 220  | Reduced class set to remove noise and ambiguity |
| v6      | 22        | 2641     | 2000  | 421 | 220  | Mid-level complexity, practical class balance |
| v7      | 19        | 2641     | 2000  | 421 | 220  | Further simplified for faster training |
| v8      | 15        | 2641     | 2000  | 421 | 220  | Compact and clean, useful for lightweight models |
| v9      | 10        | 2641     | 2000  | 421 | 220  | Focused dataset with essential urban classes only |
| v10     | 34        | 1994     | 1623  | 371 | 0    | Final refined version used in Mask R-CNN and YOLOv8 experiments |

All datasets were exported with:
- **Resolution**: 640×640 (stretched)
- **Model type**: Roboflow 3.0 Instance Segmentation (Fast)
- **Checkpoint**: COCO

---

## 📦 Why Multiple Versions?

Different segmentation models—and even different training goals—benefit from datasets of varying complexity.  
We created 10 distinct dataset versions to support:

- Fast testing on small datasets (v1–v2)
- High-granularity experimentation (v3–v4)
- Balanced, noise-reduced setups (v5–v7)
- Lightweight or mobile-focused setups (v8–v9)
- Final production-ready model training (v10)

This flexibility enabled structured benchmarking across architectures like **Mask R-CNN** and **YOLOv8**, and helps researchers isolate how class complexity affects model behavior.

---

## 🔍 Use Case Example

These datasets were used in the companion project [Instance Segmentation Benchmark](https://github.com/yourusername/instance-segmentation), where we compared:

- **Mask R-CNN** pretrained on COCO and fine-tuned on Cityscapes v10 (34 classes)
- **YOLOv8** trained from scratch on datasets v3, v4, v9, and v10

The different dataset configurations played a key role in evaluating performance on precision, generalization, and training efficiency.

---

## 📥 Access the Datasets

Each version is hosted and maintained on Roboflow. You can view, explore, or download them directly:

**🔗 [Roboflow Project Page](https://universe.roboflow.com/luigiaworkspace/cityscapes-zz0ur)**

Export format: YOLOv8 (segmentation)

---

## 👤 Authors

This dataset and repository are maintained by:

- **Luigia Costabile**  
- With contributions from Federico Negri, Simone Argentino, Vincenzo Romano, and Francesco Borrelli

---

## 📄 License

The original dataset is licensed under **CC BY 4.0**.  
This repository and its exports are provided under the same license.

---

## 🙏 Acknowledgements

We thank the creators of the original [Cityscapes Dataset](https://www.cityscapes-dataset.com/) and the Roboflow platform for enabling easy conversion and export.

