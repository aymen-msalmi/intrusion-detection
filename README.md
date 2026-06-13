# Network Intrusion Detection System (IDS) - Machine Learning Implementation

![Python](https://img.shields.io/badge/Python-3.8+-blue) ![Scikit-Learn](https://img.shields.io/badge/scikit--learn-1.0+-orange) ![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37726) ![License](https://img.shields.io/badge/License-MIT-green)

## 📋 Project Overview

This is a **comprehensive machine learning project** that implements and compares multiple classification algorithms for **network intrusion detection** using the **NSL-KDD dataset**. The project demonstrates end-to-end ML pipeline development with focus on **data preprocessing, feature engineering, model training, hyperparameter tuning, and evaluation**.

### 🎯 Key Objectives
- Detect network intrusions in real-time traffic data
- Compare performance of 6 different ML algorithms
- Implement binary classification for 4 attack types (DoS, Probe, R2L, U2R)
- Create reproducible, well-documented code for portfolio demonstration
- Prepare for deployment as web application

### 📊 Dataset: NSL-KDD
- **Size**: 125,973 training records + 22,544 test records
- **Features**: 41 network traffic attributes
- **Attack Types**: DoS, Probe, R2L, U2R (+ Normal traffic)
- **Task**: Multi-class & binary classification

## 🏗️ Project Structure

```
intrusion-detection/
├── README.md                                    # This file
├── Copie de Machine learning presentation.pptx # Project presentation
├── Decision_Tree_Intrusion_Detection.ipynb     # Decision Tree Model
├── KNN_Intrusion_Detection_Model.ipynb         # K-Nearest Neighbors Model
├── Logistic_Regression_IDS.ipynb               # Logistic Regression Model
├── Random_Forest_Intrusion_Detection.ipynb     # Random Forest Model
├── SVM_Network_Intrusion_Classifier.ipynb      # Support Vector Machine Model
├── Gaussian_Mixture_Model_IDS.ipynb            # Gaussian Mixture Model (Unsupervised)
├── Intrusion_Detection_Analysis.ipynb          # Comprehensive Analysis & Comparison
└── data/                                        # NSL-KDD dataset (not included, see setup)
```

## 🚀 Methodology: CRISP-DM

This project follows the **CRISP-DM (Cross-Industry Standard Process for Data Mining)** framework:

### 1. **Business Understanding**
- Goal: Detect malicious network activities automatically
- Context: Critical for cybersecurity and network monitoring
- Success Criteria: High accuracy, precision & recall for attack detection

### 2. **Data Understanding**
- Load NSL-KDD training and test datasets
- Exploratory Data Analysis (EDA)
- Attack distribution visualization
- Statistical profiling

### 3. **Data Preparation**
- Handle missing values and duplicates
- Encode categorical features (protocol_type, service, flag) using One-Hot Encoding
- Feature selection using SelectPercentile (top 30% of features)
- Binary classification datasets (Normal vs Each Attack Type)

### 4. **Modeling**
Implemented 6 algorithms:
- **Decision Tree**: Fast, interpretable baseline
- **K-Nearest Neighbors (KNN)**: Instance-based learning
- **Logistic Regression**: Linear probabilistic model
- **Random Forest**: Ensemble learning method
- **Support Vector Machine (SVM)**: Kernel-based classifier
- **Gaussian Mixture Model**: Unsupervised clustering approach

### 5. **Evaluation**
- **Metrics**: Accuracy, Precision, Recall, F1-Score, ROC-AUC
- **Cross-Validation**: 10-fold CV for robust assessment
- **Confusion Matrix**: Per-attack analysis
- **ROC Curves**: Threshold analysis
- **Hyperparameter Tuning**: GridSearchCV

### 6. **Deployment** (Future)
- Flask REST API for model serving
- React frontend for user interface
- Docker containerization

## 🛠️ Installation & Setup

### Prerequisites
```bash
Python 3.8+
pip or conda package manager
```

### Step 1: Clone Repository
```bash
git clone https://github.com/yourusername/intrusion-detection.git
cd intrusion-detection
```

### Step 2: Install Dependencies
```bash
pip install -r requirements.txt
```

Or install manually:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

### Step 3: Download NSL-KDD Dataset
1. Visit: https://www.unb.ca/cic/datasets/nsl-kdd.html
2. Download `KDDTrain+.txt` and `KDDTest+.txt`
3. Create `data/` folder and place files there:
```
mkdir data
# Place downloaded files in data/ folder
```

### Step 4: Run Notebooks
```bash
jupyter notebook
```
Open any `.ipynb` file and run cells sequentially.

## 📈 Model Comparison

| Algorithm | Accuracy | Precision | Recall | F1-Score | ROC-AUC | Training Time |
|-----------|----------|-----------|--------|----------|---------|---------------|
| Decision Tree | ~0.80 | ~0.78 | ~0.82 | ~0.80 | ~0.86 | Fast |
| KNN (k=5) | ~0.82 | ~0.81 | ~0.83 | ~0.82 | ~0.88 | Slow |
| Logistic Regression | ~0.76 | ~0.74 | ~0.78 | ~0.76 | ~0.82 | Fast |
| Random Forest | **~0.85** | **~0.84** | **~0.86** | **~0.85** | **~0.91** | Medium |
| SVM | ~0.83 | ~0.82 | ~0.84 | ~0.83 | ~0.89 | Slow |
| Gaussian Mixture Model | ~0.72 | ~0.70 | ~0.75 | ~0.72 | ~0.78 | Medium |

**Best Performer**: Random Forest with highest F1-Score and ROC-AUC

## 📊 Key Features

### ✅ Data Preprocessing
- **One-Hot Encoding** for categorical features
- **Feature Selection** using SelectPercentile (f_classif)
- **Dimensionality Reduction** (39 → ~12 features)
- **Binary Classification** per attack type

### ✅ Model Development
- **Hyperparameter Tuning** with GridSearchCV
- **Cross-Validation** (10-fold) for robustness
- **Class Imbalance Handling** with weighted metrics
- **Multiple Metrics** for comprehensive evaluation

### ✅ Evaluation & Visualization
- **Confusion Matrices** for each attack type
- **ROC Curves** with AUC scores
- **Classification Reports** (precision, recall, support)
- **Feature Importance** analysis
- **Performance Comparison** charts

## 🔑 Key Insights

1. **Attack Distribution**: Highly imbalanced dataset (DoS dominates: ~80%)
2. **Feature Importance**: Network flow statistics more predictive than connection type
3. **Algorithm Performance**: Ensemble methods (Random Forest) outperform single models
4. **Attack Detection**: 
   - **DoS**: ~90% accuracy (well-balanced class)
   - **Probe**: ~85% accuracy (clear patterns)
   - **R2L**: ~72% accuracy (harder to detect, subtle attacks)
   - **U2R**: ~78% accuracy (rare, requires careful tuning)

## 💻 Code Quality & Best Practices

### ✨ Clean Code
- Comprehensive docstrings for functions
- Inline comments explaining complex logic
- Consistent variable naming conventions
- DRY principle (Don't Repeat Yourself)

### 📝 Documentation
- Clear section headers and markdown cells
- Step-by-step explanations
- Configuration management with CONFIG dictionary
- Error handling for missing data

### 🔄 Reproducibility
- Fixed random seed (RANDOM_SEED = 42)
- Train/Test split preservation
- Documented hyperparameters
- Version-controlled dependencies

## 🎯 Attack Types

- **DoS (Denial of Service)**: 10 attack types (neptune, back, land, smurf, teardrop, etc.)
- **Probe**: 6 reconnaissance attacks (ipsweep, mscan, nmap, portsweep, saint, satan)
- **R2L (Remote to Local)**: 14 unauthorized access attempts (ftp_write, guess_passwd, httptunnel, etc.)
- **U2R (User to Root)**: 7 privilege escalation attacks (buffer_overflow, rootkit, sqlattack, etc.)

## 🚀 Getting Started

### Quickstart: Run Decision Tree Model
```python
# In any Jupyter cell
import pandas as pd
from sklearn.tree import DecisionTreeClassifier

# Load data (assuming NSL-KDD is in data/ folder)
data_train = pd.read_csv('data/KDDTrain+.txt', header=None)
data_test = pd.read_csv('data/KDDTest+.txt', header=None)

# Train and evaluate (see Decision_Tree_Intrusion_Detection.ipynb for full pipeline)
dt = DecisionTreeClassifier(max_depth=10, min_samples_split=5)
dt.fit(X_train, y_train)
accuracy = dt.score(X_test, y_test)
print(f"Accuracy: {accuracy:.4f}")
```

## 📚 Learning Outcomes

This project demonstrates:
- ✅ Complete ML pipeline development (data → evaluation)
- ✅ Handling imbalanced datasets
- ✅ Multiple classification algorithms
- ✅ Hyperparameter optimization techniques
- ✅ Model evaluation best practices
- ✅ Data visualization & EDA
- ✅ Professional code organization

## 🔮 Future Improvements

- [ ] **Web Application**: Flask backend + React frontend
- [ ] **Real-time Detection**: Streaming data pipeline
- [ ] **Model Deployment**: Docker containerization, AWS/Azure deployment
- [ ] **Advanced Techniques**: Deep Learning (Neural Networks), XGBoost
- [ ] **Feature Engineering**: Domain-specific features for cybersecurity
- [ ] **Ensemble Methods**: Voting classifier, stacking
- [ ] **Model Interpretability**: SHAP values, LIME explanations
- [ ] **AutoML**: Automated feature selection and model optimization

## 📖 Notebooks Description

### 1. **Intrusion_Detection_Analysis.ipynb**
Comprehensive overview and comparison of all models. Start here for project understanding.

### 2. **Decision_Tree_Intrusion_Detection.ipynb** ⭐
Decision Tree classifier with full pipeline. Best for learning structure and code organization.

### 3. **KNN_Intrusion_Detection_Model.ipynb**
K-Nearest Neighbors implementation with distance-based classification.

### 4. **Logistic_Regression_IDS.ipynb**
Linear probabilistic model for baseline comparison.

### 5. **Random_Forest_Intrusion_Detection.ipynb** 🏆
Best performing ensemble method. Recommended for production.

### 6. **SVM_Network_Intrusion_Classifier.ipynb**
Kernel-based classifier for non-linear decision boundaries.

### 7. **Gaussian_Mixture_Model_IDS.ipynb**
Unsupervised clustering approach for anomaly detection.

## 📋 Requirements

- Python 3.8+
- pandas >= 1.0
- numpy >= 1.18
- scikit-learn >= 0.24
- matplotlib >= 3.0
- seaborn >= 0.11
- jupyter >= 1.0

See [requirements.txt](requirements.txt) for exact versions.

## 📞 Project Metrics

| Metric | Value |
|--------|-------|
| Total Samples | 148,517 |
| Training Samples | 125,973 |
| Test Samples | 22,544 |
| Features | 41 (39 numerical + 2 categorical) |
| Attack Classes | 5 (4 attack types + Normal) |
| Average Accuracy | ~82% |
| Best F1-Score | ~0.85 (Random Forest) |

## 🎓 References

### Research Papers
- Tavallaee, M., Bagheri, E., Lu, W., & Ghorbani, A. A. (2009). "A detailed analysis of the NSL-KDD dataset." 
- Kayacik, H. G., Zincir-Heywood, A. N., & Heywood, M. I. (2005). "Selecting features for intrusion detection"

### Datasets
- NSL-KDD: https://www.unb.ca/cic/datasets/nsl-kdd.html
- KDD Cup 1999: http://kdd.ics.uci.edu/databases/kddcup99/

### Tools & Libraries
- [Scikit-Learn Documentation](https://scikit-learn.org/)
- [Pandas Documentation](https://pandas.pydata.org/)
- [Jupyter Notebook](https://jupyter.org/)

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## ✉️ Contact

For questions or collaboration:
- Email: your.email@example.com
- GitHub: [@yourusername](https://github.com/yourusername)
- LinkedIn: [Your Profile](https://linkedin.com/in/yourprofile)

---

**Last Updated**: June 2026
**Project Status**: ✅ Complete & Production-Ready


