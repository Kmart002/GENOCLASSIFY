# GenoClassify

Deep learning system for DNA sequence classification using 1D CNN and k-mer feature engineering.

## What It Does

GenoClassify classifies short DNA sequences (100 bp) into one of four species:

| Class | Species | GC Content |
|-------|---------|------------|
| 0 | *Homo sapiens* | ~41% |
| 1 | *Mus musculus* | ~42% |
| 2 | *Plasmodium falciparum* | ~19% |
| 3 | *SARS-CoV-2* | ~38% |

The system uses a structured synthetic genomic dataset with biologically realistic nucleotide compositions.

## Models

Three models are trained and compared:

1. **1D CNN** — operates on one-hot encoded sequences (100x4 matrices), learns spatial motifs
2. **k-mer DNN** — operates on trinucleotide frequency vectors (64-dim), fast and interpretable
3. **Random Forest** — classical ML baseline on k-mer features, provides feature importance

## Project Structure

```
GenoClassify/
├── GenoClassify_Karimat_Abolarinwa.ipynb   # Main notebook (full pipeline)
└── README.md
```

## How to Run

### Google Colab (recommended)
1. Upload `GenoClassify_Karimat_Abolarinwa.ipynb` to Google Colab
2. Run all cells — dependencies install automatically

### Local
```bash
pip install tensorflow scikit-learn pandas numpy matplotlib seaborn
jupyter notebook GenoClassify_Karimat_Abolarinwa.ipynb
```

## Pipeline Overview

1. **Dataset Construction** — generates synthetic DNA sequences with species-specific GC content and motifs
2. **Exploratory Data Analysis** — GC content distributions, nucleotide composition, k-mer heatmaps, PCA
3. **DNA Encoding** — one-hot encoding (for CNN) and k-mer frequency vectors (for DNN/RF)
4. **Model Training** — 1D CNN, Dense NN, and Random Forest
5. **Evaluation** — classification reports, confusion matrices, ROC curves, model comparison
6. **Interpretability** — k-mer importance analysis, CNN filter visualization, embedding space visualization

## Requirements

- Python 3.8+
- TensorFlow 2.x
- scikit-learn
- pandas
- numpy
- matplotlib
- seaborn

## Author

**Karimat Abolarinwa**  
DSHub AI/ML Engineering Programme — Group AI4, Cohort A 2026
