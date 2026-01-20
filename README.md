# MSc Dissertation: Symptom-Based Disease Diagnosis and Medication Recommendation Using BioBERT
**Akshay Margaj**  
Kingston University London, 2025–2026

Fine-tuning **BioBERT** (Biomedical BERT) for disease/symptom diagnosis based on patient-reported symptoms.  
This repository contains the code, preprocessing scripts, and the processed dataset used for model training and evaluation.

## Dataset

- **File**: `medical_dataset.csv` (~32 MB)  
- **Description**:  
  This dataset maps patient symptoms to possible diseases/prognoses.  
  It contains binary/multiclass symptom features (e.g., fever, cough, fatigue, etc.) and a target column indicating the diagnosed condition.  
  Originally designed for classical ML models, here adapted for transformer-based fine-tuning with BioBERT.  
- **Size**: Approximately 32 MB  
- **Columns** (typical structure – adjust if your file differs):  
  - 132+ symptom columns (binary: 0 = absent, 1 = present)  
  - `prognosis` / `disease` column (target label, e.g. 42 possible diseases)

**License note**: The dataset is publicly available on Kaggle under the dataset's original license (usually CC0 or similar – check Kaggle page for details).


## How to Run the Code in Google Colab (Recommended)

1. **Open the notebook in Colab**  
   - Go to your GitHub repo: https://github.com/akshaymargaj/MScDissertation_Symptom_diagnosis_BioBERT  
   - Click on your main notebook file (MScDissertation.ipynb)  
   - Click the **Open in Colab** button (top right)  
   OR  
   Paste this URL in your browser:  
   https://colab.research.google.com/github/akshaymargaj/MScDissertation_Symptom_diagnosis_BioBERT/blob/main/MScDissertation.ipynb

2. **Load the CSV dataset from this GitHub repo** (easiest & reproducible – no manual upload needed)  
   In a Colab code cell, run:

   ```python
   import pandas as pd

   # Replace with your actual raw URL (get it by going to medical_dataset.csv on GitHub → click "Raw" → copy link)
   url = "https://raw.githubusercontent.com/akshaymargaj/MScDissertation_Symptom_diagnosis_BioBERT/main/medical_dataset.csv"

   df = pd.read_csv(url)
   print(df.head())          # quick check
   print(df.shape)           # rows & columns
