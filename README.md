Code for my MSc thesis: **"Extending Differentially Private Fine-Tuning of
Wearable Foundation Models with Heart Rate Signals."**

This project studies privacy-preserving multimodal Human Activity Recognition
(HAR), fusing heart rate (HR) and IMU data on the PAMAP2 dataset

## Contents

| File | Description |
|------|-------------|
| `HR_models.ipynb` | Heart-rate classification models (MLP / LSTM / GRU / BiLSTM, with and without feature engineering) and the LOSO evaluation pipeline. |
| `Experiments.ipynb` | Main experiments, fusion, and result analysis (confusion matrices, per-subject accuracy summaries). |

## Data

This project uses the **PAMAP2 Physical Activity Monitoring** dataset from the
UCI Machine Learning Repository:

- Dataset: https://archive-beta.ics.uci.edu/dataset/231/pamap2+physical+activity+monitoring

The dataset contains recordings from 3 IMUs (hand, chest, ankle), a heart-rate
monitor, and activity labels for a range of daily and sport activities.

**Notes on the data used here:**
- Only the files in the **`Protocol`** folder are used.
- **Subject 9 (`subject109.dat`) is excluded** (very little / incomplete data),
  so experiments run on subjects **101–108**.
- The raw data is **not included in this repository** because it is too large.

### Getting the data

1. Download the PAMAP2 dataset from the UCI link above.
2. Extract it and place the `Protocol` `subjectXXX.dat` files where the notebooks
   expect them (the loaders use the pattern `subject{}.dat`).
3. Each file is whitespace-separated with 54 columns (timestamp, activity ID,
   heart rate, and the three IMUs).
