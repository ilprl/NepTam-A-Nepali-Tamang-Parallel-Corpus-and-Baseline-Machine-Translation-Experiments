# NepTam: Nepali-Tamang Machine Translation Dataset

This repository contains the datasets, benchmarks, and experimental notebooks for **Nepali-Tamang (ne ↔ tam)** Machine Translation, as presented in our paper accepted at **[LREC 2026](https://lrec2026.info/)**.

---

## Overview
Nepali and Tamang are genetically related but structurally distinct languages. This project addresses the resource gap for this language pair by introducing:
* **NepTam20K**: A high-quality supervised dataset for benchmarking.
* **NepTam80K**: An extended dataset for scaled training.

## 📊 Dataset Details

The following table provides the category-wise distribution across our datasets.

| Category | NepTam20K (Train) | NepTam20K (Test) | NepTam80K |
| :--- | :--- | :--- | :--- |
| **Sentence Length** | | | |
| ↳ Short | 5,863 (39.1%) | 1,954 (39.1%) | 15,941 (19.9%) |
| ↳ Medium | 6,793 (45.3%) | 2,266 (45.3%) | 52,122 (65.2%) |
| ↳ Long | 1,552 (10.3%) | 518 (10.4%) | 10,640 (13.3%) |
| ↳ Very Long | 823 (5.5%) | 262 (5.2%) | 1,396 (1.7%) |
| **Tense** | | | |
| ↳ Non-Past | 6,781 (45.2%) | 2,282 (45.6%) | 55,542 (69.4%) |
| ↳ Past | 6,436 (42.9%) | 2,131 (42.6%) | 24,295 (30.3%) |
| **Polarity** | | | |
| ↳ Affirmative | 11,939 (79.6%) | 3,978 (79.6%) | 74,871 (93.6%) |
| ↳ Negative | 1,278 (8.5%) | 435 (8.7%) | 4,966 (6.2%) |
| ↳ Unknown | 1,784 (11.9%) | 587 (11.7%) | 262 (0.3%) |
| **Total Sentences** | **15,000** | **5,000** | **80,099** |

---

## Benchmark Results

### 1. Models Trained on NepTam20K
Evaluated on the **NepTam20K Test Set**.

| Model | Params | Direction | sacreBLEU | chrF++ | METEOR | COMET |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: |
| **NLLB** | 600M | ne → tam | **40.92** | **69.94** | **61.44** | **75.89** |
| | | tam → ne | **45.26** | **70.30** | **62.31** | **80.19** |
| **M2M** | 418M | ne → tam | 40.24 | 69.27 | 60.81 | 75.67 |
| | | tam → ne | 42.73 | 68.74 | 61.07 | 79.13 |
| **mBART** | 610.9M | ne → tam | 40.14 | 68.92 | 60.46 | 75.60 |
| | | tam → ne | 42.96 | 68.25 | 60.43 | 79.04 |
| **Transformer**| 49.07M | ne → tam | 37.71 | 67.74 | 58.20 | 75.00 |
| | | tam → ne | 38.01 | 66.30 | 57.60 | 77.37 |

### 2. Models Trained on NepTam80K
Evaluated on the **NepTam20K Test Set** to show scaling improvements.

| Model | Direction | sacreBLEU | chrF++ | METEOR | COMET |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **NLLB** | ne → tam | **41.79** | **70.60** | **62.19** | **76.12** |
| | tam → ne | **48.28** | **72.31** | **64.25** | **81.26** |
| **mBART** | ne → tam | 41.44 | 70.10 | 61.21 | 75.83 |
| | tam → ne | 46.68 | 71.17 | 61.96 | 80.70 |
| **M2M** | ne → tam | 40.56 | 69.62 | 60.55 | 75.68 |
| | tam → ne | 44.03 | 69.34 | 60.50 | 79.28 |
| **Transformer**| ne → tam | 37.72 | 68.01 | 57.13 | 74.61 |
| | tam → ne | 38.24 | 65.60 | 54.26 | 75.76 |

---


## 📝 Citation
Our paper has been accepted for publication at LREC 2026. If you use this dataset or findings in your research, please cite our work.
