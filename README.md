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
│   ├── QRS_Database2.mat
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
├── requirements.txt
├── CompBioMed_Report.pdf
└── README.md
```

### Folder Description

| Folder | Description |
|---------|------------|
| `Notebooks/` | Data preprocessing, feature extraction, model training, evaluation, and visualization notebooks. |
| `data/` | Processed datasets used throughout the experiments. Only Database2 is included, might affect reproductibility|
| `models/` | Pre-trained models required for the ECG segmentation pipeline and experimental analyses. |
| `CompBioMed_Report.pdf` | Final project report containing methodology, experiments, and results. |
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

**Maria Farràs Soldevila**

---

## License

This repository was developed as part of the CompBioMed 2026 academic project at Universitat Pompeu Fabra.
