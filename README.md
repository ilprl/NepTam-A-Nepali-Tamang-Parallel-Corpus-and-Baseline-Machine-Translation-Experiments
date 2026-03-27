# NepTam: Nepali-Tamang Machine Translation Dataset

This repository contains the datasets, benchmarks, and experimental notebooks for **Nepali-Tamang (ne ↔ tam)** Machine Translation, as presented in our paper accepted at **[LREC 2026](https://lrec2026.info/)**.

---

## Overview
Nepali and Tamang are genetically related but structurally distinct languages. This project addresses the resource gap for this language pair by introducing:
* **NepTam20K**: A high-quality supervised dataset for benchmarking.
* **NepTam80K**: An extended dataset for scaled training.

## Datasets

Two parallel corpora are provided for Nepali–Tamang translation:

| Dataset | Split | Sentences |
|---|---|---|
| **NepTam20K** | Train | 15,000 |
| **NepTam20K** | Test | 5,000 |
| **NepTam80K** | — | 80,099 |

### Data Distribution

Sentences are categorised by length, tense, and polarity:

**Sentence Length**

| Length | NepTam20K Train | NepTam20K Test | NepTam80K |
|---|---|---|---|
| Short | 5,863 (39.1%) | 1,954 (39.1%) | 15,941 (19.9%) |
| Medium | 6,793 (45.3%) | 2,266 (45.3%) | 52,122 (65.2%) |
| Long | 1,552 (10.3%) | 518 (10.4%) | 10,640 (13.3%) |
| Very Long | 823 (5.5%) | 262 (5.2%) | 1,396 (1.7%) |

**Tense**

| Tense | NepTam20K Train | NepTam20K Test | NepTam80K |
|---|---|---|---|
| Non-Past | 6,781 (45.2%) | 2,282 (45.6%) | 55,542 (69.4%) |
| Past | 6,436 (42.9%) | 2,131 (42.6%) | 24,295 (30.3%) |

**Polarity**

| Polarity | NepTam20K Train | NepTam20K Test | NepTam80K |
|---|---|---|---|
| Affirmative | 11,939 (79.6%) | 3,978 (79.6%) | 74,871 (93.6%) |
| Negative | 1,278 (8.5%) | 435 (8.7%) | 4,966 (6.2%) |
| Unknown | 1,784 (11.9%) | 587 (11.7%) | 262 (0.3%) |

---

## Models

Four multilingual models were fine-tuned on this dataset:

| Model | Parameters |
|---|---|
| NepTam-M2M (M2M-100) | 418M |
| NepTam-NLLB (NLLB-200) | 600M |
| NepTam-mBART (mBART-50) | 610.9M |
| NepTam-Transformer (vanilla) | 49.07M |

---

## 📈 Results

### Trained on NepTam20K — Evaluated on NepTam20K Test

| Model | Direction | sacreBLEU | chrF | chrF++ | METEOR | COMET |
|---|---|---|---|---|---|---|
| NepTam-M2M | ne→tam | 40.24 | 73.30 | 69.27 | 60.81 | 75.67 |
| | tam→ne | 42.73 | 72.21 | 68.74 | 61.07 | 79.13 |
| **NepTam-NLLB** | **ne→tam** | **40.92** | **73.98** | **69.94** | **61.44** | **75.89** |
| | **tam→ne** | **45.26** | **73.71** | **70.30** | **62.31** | **80.19** |
| NepTam-mBART | ne→tam | 40.14 | 72.91 | 68.92 | 60.46 | 75.60 |
| | tam→ne | 42.96 | 71.65 | 68.25 | 60.43 | 79.04 |
| NepTam-Transformer | ne→tam | 37.71 | 71.71 | 67.74 | 58.20 | 75.00 |
| | tam→ne | 38.01 | 69.89 | 66.30 | 57.60 | 77.37 |

### Trained on NepTam80K — Evaluated on NepTam20K Test

| Model | Direction | sacreBLEU | chrF | chrF++ | METEOR | COMET |
|---|---|---|---|---|---|---|
| NepTam-M2M | ne→tam | 40.56 | 73.70 | 69.62 | 60.55 | 75.68 |
| | tam→ne | 44.03 | 72.83 | 69.34 | 60.50 | 79.28 |
| NepTam-NLLB | ne→tam | 41.79 | 74.58 | 70.60 | 62.19 | 76.12 |
| | tam→ne | 48.28 | 75.57 | 72.31 | 64.25 | 81.26 |
| NepTam-mBART | ne→tam | 41.44 | 74.07 | 70.10 | 61.21 | 75.83 |
| | tam→ne | 46.68 | 74.59 | 71.17 | 61.96 | 80.70 |
| NepTam-Transformer | ne→tam | 37.72 | 72.13 | 68.01 | 57.13 | 74.61 |
| | tam→ne | 38.24 | 69.32 | 65.60 | 54.26 | 75.76 |

> **NepTam-NLLB consistently achieves the best performance** across both dataset sizes and both translation directions.

## Data and Models
Link: https://hf.co/collections/ilprl-docse/neptam-a-nepali-tamang-parallel-corpus-and-baseline-machine

## 📝 Citation
Our paper has been accepted for publication at LREC 2026. If you use this dataset or findings in your research, please cite our work.
Paper Link: https://arxiv.org/abs/2603.14053
