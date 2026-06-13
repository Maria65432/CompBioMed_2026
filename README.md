# CompBioMed_2026

## Overview

This repository contains the code and experiments developed for the prediction of the **Site of Origin (SOO)** of **Idiopathic Ventricular Arrhythmias (IVAs)** using electrocardiogram (ECG) recordings and clinical variables.

The project evaluates both **Deep Learning** and **Classical Machine Learning** approaches for identifying ventricular arrhythmia origins from 12-lead ECG signals. The ultimate goal is to support non-invasive localization of ventricular arrhythmias and improve catheter ablation planning.

Three classification tasks are assessed:

* **Binary classification:** Left Ventricular Outflow Tract (LVOT) vs Right Ventricular Outflow Tract (RVOT)
* **Three-class classification:** LVOT, RVOT, and Commissure (LCC-RCC)
* **Sublocation classification:** Seven anatomical origins:

  * Left Coronary Cusp (LCC)
  * Right Coronary Cusp (RCC)
  * Commissure (LCC-RCC)
  * LVOT Subvalvular
  * LVOT Summit
  * RVOT Septum
  * RVOT Free Wall

---

## Repository Structure

```text
.
├── Notebooks/
│   ├── pre1_teknon_data_cleaning.ipynb
│   ├── pre2_QRSsegmentation.ipynb
│   ├── pre3_DistributionGrafics.ipynb
│   │
│   ├── EXP1_RawDataBased_BinaryClassification.ipynb
│   ├── EXP2_FeatureBased_BinaryClassification.ipynb
│   ├── EXP3_FeatureBased_ThreeClassClassification.ipynb
│   ├── EXP4_FeatureBased_MultilabelClassification.ipynb
│   └── EXP5_UnsupervisedLearning_AllDatasets.ipynb
│
├── data/
│   ├── binary_full_dataset.parquet
│   ├── multiclass_full_dataset.parquet
│   ├── label2.xlsx
│   └── labels_FontiersUnsupervised.xlsx
│
├── models/
│   ├── model.1
│   ├── model.2
│   ├── model.3
│   ├── model.4
│   └── model.5
│
├── outputs/
│   ├── aligned_qrs.pkl
│   ├── qrs_identifiers.pkl
│   └── segmentations.pkl
│
├── requirements.txt
├── CompBioMed_Report.pdf
└── README.md
```

### Folder Description

| Folder                  | Description                                                                                      |
| ----------------------- | ------------------------------------------------------------------------------------------------ |
| `Notebooks/`            | Data preprocessing, feature extraction, model training, evaluation, and visualization notebooks. |
| `data/`                 | Processed datasets used throughout the experiments.                                              |
| `models/`               | Models required for the QRS  Segmentation file
|
| `outputs/`              | Intermediate outputs generated during ECG preprocessing and segmentation.                        |
| `CompBioMed_Report.pdf` | Final project report containing methodology, experiments, and results.                           |

---

## Datasets

The study combines data from four different sources:

* **Teknon:** Clinical dataset from Hospital Teknon (Barcelona)
* **CARTO:** Clinical electroanatomical mapping dataset
* **China:** Publicly available external ECG dataset
* **Sims:** Synthetic ECG dataset generated from electrophysiological simulations

---

## Methodology

### Preprocessing

* Clinical data cleaning and missing value analysis
* ECG signal normalization and filtering
* QRS segmentation and alignment
* PVC transition calculation

### Deep Learning

* Convolutional Neural Networks (CNN)
* CNN + Multilayer Perceptron (MLP) multimodal architecture

### Classical Machine Learning

* Logistic Regression
* Support Vector Machine (SVM)
* Random Forest
* XGBoost

### Unsupervised Learning

* Principal Component Analysis (PCA)
* K-Means Clustering

---

## Requirements

To reproduce the experiments, it is recommended to create a Conda environment using **Python 3.8.20** and install the required dependencies:

```bash
pip install -r requirements.txt
```

---

## Main Results

### Binary Classification (LVOT vs RVOT)

| Model   | Dataset                     | Macro F1 |
| ------- | --------------------------- | -------- |
| XGBoost | Teknon + Clinical Variables | **0.75** |

### Three-Class Classification

| Model               | Dataset               | Macro F1 |
| ------------------- | --------------------- | -------- |
| Logistic Regression | All Datasets Combined | **0.41** |

### Sublocation Classification (7 Classes)

| Model               | Dataset               | Macro F1 |
| ------------------- | --------------------- | -------- |
| Logistic Regression | All Datasets Combined | **0.22** |

---

## Authors

**Irati de Anta Azkarate**
Universitat Pompeu Fabra (UPF)

**Maria Farràs Soldevila**
Universitat Pompeu Fabra (UPF)

---

## License

This repository was developed as part of the CompBioMed 2026 academic project at Universitat Pompeu Fabra.
