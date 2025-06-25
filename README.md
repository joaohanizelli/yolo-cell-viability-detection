# 🔬 YOLOv8 Cell Viability Detection

![Python](https://img.shields.io/badge/python-v3.11+-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-v2.6+-red.svg)
![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-green.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

Automated detection and classification of *Saccharomyces cerevisiae* cells with/without methylene blue staining using YOLOv8 deep learning.

## 🎯 Key Results

- **Performance**: 94.4% mAP@0.5 (validation), 88.7% F1-Score (test)
- **Methodology**: Systematic framework with 5 optimization strategies
- **Key Finding**: Minimal augmentation proved more effective for microscopy
- **Reproducibility**: Complete code with deterministic controls

## 🔬 About This Project

**Bachelor's Thesis (TCC)** - Electronic Engineering, UFSC 2025

**Objective**: Automate cell viability analysis traditionally performed manually, reducing subjectivity and increasing throughput.

**Context**: Specific application for *S. cerevisiae* + methylene blue in brightfield microscopy.

## 🛠️ Technologies

- **Deep Learning**: YOLOv8 (Ultralytics)
- **Framework**: PyTorch, Python 3.11
- **Environment**: Kaggle (Tesla P100)
- **Dataset**: 329 images, 4,930 cellular annotations

## 📊 Dataset Overview

- **Total**: 329 microscopic images (640×640px)
- **Classes**: COM_corante (dead cells) vs SEM_corante (viable cells)
- **Splits**: Train (233), Validation (64), Test (32)
- **Format**: COCO → YOLO conversion
- **Balance**: 46.2% vs 53.8% (adequate)

## 🚀 Quick Start

### Prerequisites
```bash
pip install -r requirements.txt
```

### Run the Complete Notebook
Execute `notebook_completo.ipynb` sequentially:

1. **Block 1**: Dataset loading and analysis
2. **Block 2**: Data preparation (COCO→YOLO)
3. **Block 3**: YOLOv8 baseline
4. **Block 4**: 5 optimization strategies
5. **Block 5**: Threshold optimization
6. **Block 6**: Final validation and results

## 📈 Optimization Strategies Tested

| Strategy | mAP@0.5 | Description |
|----------|---------|-------------|
| Baseline | 90.8% | Standard YOLOv8s |
| Fine-tuning | 93.1% | Reduced LR + regularization |
| High Class Weight | 93.8% | Class balancing |
| High Regularization | 93.9% | Dropout + weight decay |
| **Minimal Augmentation** | **94.4%** ⭐ | **Reduced transformations** |

## 🔍 Key Discoveries

### 💡 Minimal Augmentation Insight
Reduced data augmentation outperformed conventional extensive transformations for microscopy, possibly due to preservation of specific morphological characteristics.

### 🛡️ Anti-Leakage Methodology
Rigorous data leakage prevention protocol:
- Chronological splits respected
- Test set isolated during development
- Deterministic seeds controlled

### 🎯 Threshold Optimization
F1-Score based methodology (threshold=0.55) outperformed arbitrary values.

## ⚠️ Limitations

- **Specific scope**: Only *S. cerevisiae* + methylene blue
- **Small dataset**: 32-image test set (high variance)
- **Single modality**: Brightfield microscopy only
- **Academic context**: Limited undergraduate resources

## 🔮 Future Work

- Validation on larger datasets (>1000 images)
- Extension to other cell species
- Different staining techniques
- Laboratory GUI interface
- Comparison with other architectures

## 📚 Citation

```bibtex
@misc{tcc2025celldetection,
  title={Automated Detection and Classification of S. cerevisiae Cells using YOLOv8},
  author={[João Henrique Anizelli Godoi]},
  year={2025},
  school={Universidade Federal de Santa Catarina},
  url={https://github.com/joaohanizelli/yolo-cell-viability-detection}
}
```

## 📄 Complete Documentation

Full thesis (Portuguese): [Link will be available after defense]

## 🤝 Contributing

This is an academic project, but suggestions and extensions are welcome!

## 📜 License

MIT License - Feel free to use for academic research.

---

**Developed as Bachelor's Thesis - Electronic Engineering, UFSC 2025**
