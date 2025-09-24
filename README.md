# Histopathologic Cancer Detection

Mini-project for **Kaggle Histopathologic Cancer Detection** (Deliverable Two).

## Project Description
This project is part of a mini Kaggle competition, where the task is to build a binary classifier that detects metastatic cancer in small histopathologic image patches (96×96 pixels).  
The dataset comes from Kaggle and is highly imbalanced (~40% positives).  

We implemented a **ResNet-50** model with weighted sampling, class-weighted BCE loss, and test-time augmentation (TTA).  
The goal is not leaderboard placement but to demonstrate the full ML workflow: data preparation, modeling, evaluation, and discussion.

---

## Results and Validation
- **Best Validation AUC**: 0.9918  
- **Final Validation Loss**: 0.1556  
- **Chosen Threshold**: 0.70  
- **Accuracy**: 0.9611  
- **Precision**: 0.9636  
- **Recall**: 0.9395  
- **F1-score**: 0.9514  
- **Specificity**: 0.973  

External check:  
**Public leaderboard AUC (Kaggle): 0.9557** (Private: 0.9485).  

---

## Key Techniques
- ImageNet pretraining  
- Weighted sampler + `pos_weight` to handle class imbalance  
- Deterministic validation transforms and **4×TTA** at inference  

---

## Limitations
- Only 3 epochs  
- Single backbone/loss  
- No stain normalization or cross-validation  
- Patch-level labels limit slide-level interpretability  

---

## Next Steps
- Try EfficientNet/ResNet101 or ensembles  
- Add stain normalization (e.g., Macenko), MixUp/CutMix  
- Explore Focal/AUCPR losses and threshold calibration via CV  
- Add calibration (EMA/SWA, temperature scaling)  
- Add interpretability (Grad-CAM on FP/FN)  

---

## Repository Structure

- `README.md` — Project overview
- `notebook.ipynb` — Main Jupyter Notebook
- `figures/` — Screenshots (confusion matrix, leaderboard) 

