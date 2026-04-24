# 🧠 AI-Powered Depression Detection using EEG (MODMA Dataset)

---

### 🔬 Overview
This project presents an **AI-driven system for detecting Major Depressive Disorder (MDD)** using **multimodal EEG signals** from the MODMA dataset.

The system analyzes:
- **128-channel ERP (Event-Related Potentials)**
- **128-channel resting-state EEG**
- **3-channel EEG (low-cost setup)**

> 💡 Focus: **Feature engineering + Machine Learning > Deep Learning** for EEG classification.

---

### 🚀 Highlights
- ⭐ Up to **98% Accuracy**
- 🧠 Multi-modal EEG analysis
- ⚡ **LightGBM best for ERP**
- 🔍 Strong generalization insights (overfitting vs robust models)
- 🏥 Designed for real-world clinical deployment

---

### ⚙️ Pipeline

#### 1. Data Acquisition
- MODMA dataset (EEG + clinical labels)

#### 2. Preprocessing
- Bandpass filtering (0.5–45 Hz)
- Z-score normalization  
- ERP: ICA + epoch extraction (P1, N1, P2, N2, P3)

#### 3. Feature Extraction
***Time-Domain***
- Mean, Variance, RMS, Skewness, Kurtosis  

***Frequency-Domain***
- PSD (Welch)
- Delta, Theta, Alpha, Beta, Gamma bands  

***Non-Linear***
- Hjorth parameters  
- Entropy, Fractal dimensions  

***ERP Features***
- Peak amplitudes & latencies (P1–P3)

***Connectivity***
- Inter-channel correlations  

---

### 🤖 Models Used
***Machine Learning***
- Random Forest  
- XGBoost  
- **LightGBM (Best for ERP)**  
- SVM  
- Logistic Regression  

***Deep Learning***
- CNN (raw EEG)  
- MLP (tabular / VAE features)  

---

### 📊 Results

#### 🧠 128-Channel ERP EEG

| Model | Accuracy | Precision | Recall | F1 Score |
|------|---------|----------|--------|----------|
| **LightGBM** | **93.31%** | 94.36% | 91.53% | **92.92%** |
| XGBoost | 90% | 92% | 87% | 89% |
| Random Forest | 84% | 88% | 78% | 82% |

***Insight:***
- ✔ LightGBM generalizes best  
- ❌ Random Forest overfits (100% train → ~84% test)

---

#### 🧠 128-Channel Resting-State EEG

- ⭐ Random Forest: **~98%**
- ⭐ MLP (VAE Features): **~98%**
- SVM: ~94%  
- CNN: ~92%  

---

#### 🧠 3-Channel EEG

- ⭐ Random Forest: **~97%**
- XGBoost: ~94%  
- MLP: ~79%  

---

### 🧠 Key Insights

***1. Feature Engineering > Deep Learning***  
- ML models outperform CNNs across all modalities  

***2. ERP Features are Highly Discriminative***  
- P3, N2 strongly linked to depression  

***3. Boosting > Bagging (ERP Case)***  
- LightGBM > Random Forest  

***4. Low-Channel EEG Works***  
- 3-channel achieves ~97% → real-world feasibility  

---

### 📈 Evaluation
- Stratified **10-fold Cross Validation**
- **80:20 train-test split**
- Metrics:
  - Accuracy  
  - Precision / Recall / F1  
  - ROC Curve  
  - Confusion Matrix  

---

### 🛠️ Tech Stack
- Python  
- MNE  
- NumPy, Pandas, SciPy  
- Scikit-learn  
- LightGBM, XGBoost  
- TensorFlow / PyTorch  

---

### 📂 Project Structure
```
Data/
Preprocessing/
Feature_Extraction/
Models/
Notebooks/
Results/
README.md
```

---

### ⚠️ Limitations
- Deep learning limited by dataset size  
- Random Forest overfitting (ERP)  
- No real-time deployment yet  

---

### 🔮 Future Work
- EEG + psychometric fusion  
- Transformer-based EEG models  
- Explainable AI (SHAP, LIME)  
- Real-time deployment  

---

### 👩‍💻 Authors
- Sonali  
- Lavanya  
- Disha  
- Raghav  

---

### 💡 Final Insight
> Interpretable, feature-driven ML models can outperform deep learning in EEG-based depression detection while remaining scalable for real-world use.
