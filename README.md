# Emotion Classification (NLP)

This repository contains a **supervised emotion classification** project using Python.  
It trains and evaluates models that predict an emotion label from text examples (e.g., *joy, sadness, anger, fear, surprise, neutral*).

## 📂 Dataset

- **File:** `Emotion-Dataset.csv`
- **Typical columns:** 
  - `text` — the input sentence/utterance
  - `label` — the target emotion class (string)
  
> If your column names differ, update the notebook’s data-loading cell accordingly.

## 📒 Notebooks

- `EmotionClassification_KK.ipynb` — end‑to‑end workflow covering:
  - loading & cleaning the data
  - train/validation split with a fixed random seed (e.g., `random_state=1337`)
  - text vectorization (e.g., TF‑IDF)
  - model training (e.g., Linear SVM / Logistic Regression)
  - evaluation (accuracy, macro‑F1, confusion matrix)
  - (optional) export a trained pipeline with `joblib`

## 🚀 Quickstart

### 1) Create & activate a virtual environment
```bash
python3 -m venv .venv
source .venv/bin/activate        # macOS / Linux
.venv\Scripts\Activate.ps1     # Windows PowerShell
```

### 2) Install dependencies
```bash
pip install -r requirements.txt
```

### 3) Run Jupyter and execute the notebook
```bash
jupyter notebook
```
Open **`EmotionClassification_KK.ipynb`** and run all cells.

## 🧪 Optional: Inference script (after exporting a model)

If you export your trained pipeline as `emotion_model.joblib` (from the notebook), you can run quick predictions:

```bash
python predict.py --text "i am feeling awesome today!"
```

`predict.py` (provided) expects a `joblib`-saved pipeline that includes both the vectorizer and classifier.

## 📊 Suggested Metrics to Report
- Accuracy
- Macro‑F1
- Per‑class precision/recall/F1
- Confusion matrix

## 📁 Repository Structure
```
.
├── Emotion-Dataset.csv
├── EmotionClassification_KK.ipynb
├── requirements.txt
└── README.md
```

## 🧷 Reproducibility
- Use a fixed `random_state` (e.g., `1337`) for splits and algorithms where applicable.

## 🧰 Requirements (see `requirements.txt`)
- pandas, numpy
- scikit-learn
- matplotlib
- jupyter
- joblib (for saving/loading trained pipelines)

## 📝 Notes
- Keep raw data under version control if small; otherwise consider a data link or Git LFS.
- If your dataset uses a different schema (e.g., `Sentence`/`Emotion`), edit the notebook/predict script accordingly.
