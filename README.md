# 🔬 Metastatic Breast Cancer Detection from Histopathology Images

Deep-learning pipeline that detects metastatic tissue in lymph-node histopathology patches using the **PatchCamelyon (PCam)** dataset, a baseline CNN, and **ResNet18 transfer learning**, with **Grad-CAM** explainability.

> **Course:** Healthcare Analytics (21CSE428T) · **Domain:** Biomedical Image Analysis / Digital Pathology

## 📌 Overview

| | |
|---|---|
| **Task** | Binary classification of 96×96 RGB patches |
| **Classes** | `0` Non-metastatic · `1` Metastatic |
| **Dataset** | [PatchCamelyon](https://patchcamelyon.grand-challenge.org/): 327,680 patches from lymph-node scans |
| **Models** | Baseline CNN, ResNet18 (ImageNet pretrained, fine-tuned) |
| **Metrics** | Accuracy, Precision, Recall, F1, ROC-AUC, confusion matrix |
| **Explainability** | Grad-CAM heatmaps, misclassified-sample analysis |

## ✨ Features

- Automatic PCam download via `torchvision.datasets.PCAM` (with an alternative download option)
- Subset sampling for fast training on limited hardware (e.g. Google Colab)
- Healthcare-data preprocessing walkthrough (EHR-style cleaning, standardization) and image normalization/augmentation
- Baseline CNN vs. ResNet18 transfer learning comparison
- Evaluation with ROC curves, confusion matrices, and classification reports
- Misclassification analysis and Grad-CAM visual explanations
- Discussion of clinical limitations, ethics, and bias, plus viva Q&A

## 🗂️ Repository Structure

```
MetaStatic_BreastCancer_Detection/
├── PCam_Healthcare_Analytics_Complete_Project.ipynb   # Full project notebook
└── README.md
```

## 📓 Notebook Contents

1. Dataset and project justification
2. Healthcare data / EHR concepts
3. Preprocessing of healthcare data
4. Biomedical image analysis
5. Download and load PCam
6. Train/validation/test strategy
7. Baseline CNN
8. Transfer learning with ResNet18
9. Results and discussion
10. Misclassified-image analysis
11. Grad-CAM explainability
12. Innovation component
13. Limitations and ethics
14. Conclusion, viva questions, references

## 🚀 Getting Started

### Requirements

- Python 3.9+
- PyTorch, torchvision
- numpy, pandas, matplotlib, scikit-learn, Pillow
- Jupyter or Google Colab (a GPU is recommended)
- `h5py` (needed by torchvision's PCAM loader)

```bash
pip install torch torchvision numpy pandas matplotlib scikit-learn pillow h5py jupyter
```

### Run

```bash
git clone <your-repo-url>
cd MetaStatic_BreastCancer_Detection
jupyter notebook PCam_Healthcare_Analytics_Complete_Project.ipynb
```

Or upload the notebook to Google Colab, select a GPU runtime, and run all cells.

> [!NOTE]
> The PCam download is several GB. The notebook trains on subsets with a small number of epochs by default. Increase `EPOCHS` and the subset sizes for better results.

## ⚙️ Default Configuration

| Parameter | Value |
|---|---|
| Batch size | 64 |
| Baseline CNN learning rate | 1e-3 |
| ResNet18 fine-tuning learning rate | 1e-4 |
| Epochs | 1–3 (adjustable) |

## ⚠️ Disclaimer

This is an **educational project**. It is not a medical device and must not be used for clinical diagnosis or treatment decisions. Real deployment would require external validation, bias assessment, and regulatory approval.

## 📚 References

- Veeling et al., *Rotation Equivariant CNNs for Digital Pathology* (2018): PatchCamelyon
- He et al., *Deep Residual Learning for Image Recognition* (2016)
- Selvaraju et al., *Grad-CAM* (2017)

