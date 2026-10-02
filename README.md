<div align="center">

# 🌷 Predictive Learning Gap Analyzer

### AI-Powered Student Risk Prediction & Personalized Learning Support

<p>
  <em>
    A machine-learning driven educational analytics system that combines
    student performance, homework, assessment, and interaction data to
    identify learning risk patterns and generate personalized academic
    recommendations.
  </em>
</p>

<br>

<img src="https://img.shields.io/badge/AI%20%26%20Machine%20Learning-DFA7C7?style=for-the-badge&labelColor=FFFDF9" />
<img src="https://img.shields.io/badge/Deep%20Learning-E8A0BF?style=for-the-badge&labelColor=FFFDF9" />
<img src="https://img.shields.io/badge/Random%20Forest-8B6F61?style=for-the-badge&labelColor=F7F3EE" />
<img src="https://img.shields.io/badge/XGBoost-DFA7C7?style=for-the-badge" />
<img src="https://img.shields.io/badge/TensorFlow-FFB6C1?style=for-the-badge&logo=tensorflow&logoColor=6D564A" />
<img src="https://img.shields.io/badge/Python-6D564A?style=for-the-badge&logo=python&logoColor=FFFDF9" />
<img src="https://img.shields.io/badge/License-MIT-6D564A?style=for-the-badge" />

<br><br>

**♡ Early identification · Data-driven intervention · Personalized learning ♡**

</div>

---

<div align="center">

> ### 🌸 *Understand the learning pattern before the learning gap becomes a barrier.*

</div>

---

# 🌷 About the Project

The **Predictive Learning Gap Analyzer** is an educational analytics and machine-learning project designed to identify students who may require additional academic support.

Instead of evaluating students using examination scores alone, the project combines multiple dimensions of learner activity, including:

```text
Student Information
        +
Homework Performance
        +
Test Performance
        +
Learning Interactions
        ↓
Feature Engineering
        ↓
Risk Prediction
        ↓
Learning-Gap Analysis
        ↓
Personalized Recommendations
````

The system is designed to move from **prediction to intervention** by not only identifying students classified as at-risk, but also generating structured recommendations and action plans based on their predicted status and academic performance.

---

# 🎀 The Core Idea

Traditional academic analysis often looks backward:

```text
Exam Result
     ↓
Student Performance
     ↓
Intervention
```

This project explores a more proactive approach:

```text
Learning Behaviour
        ↓
Performance Signals
        ↓
Machine Learning
        ↓
Risk Prediction
        ↓
Early Intervention
        ↓
Personalized Learning Support
```

The objective is to help educators identify potential learning difficulties earlier and provide more targeted academic support.

---

# ✦ What the System Analyzes

The notebook is designed around eight CSV datasets covering two academic cohorts.

### Class 11

```text
class11_students.csv
class11_homework.csv
class11_tests.csv
class11_interactions.csv
```

### Class 12

```text
class12_students.csv
class12_homework.csv
class12_tests.csv
class12_interactions.csv
```

These data sources provide the foundation for constructing the student-level feature representation used by the models.

---

# 📊 Project Pipeline

```text
┌─────────────────────────────────────┐
│          Raw Student Data           │
│                                     │
│ Students · Homework · Tests        │
│ Interactions                        │
└──────────────────┬──────────────────┘
                   │
                   ▼
┌─────────────────────────────────────┐
│        Data Preprocessing            │
│                                     │
│ Cleaning · Aggregation              │
│ Feature Preparation                 │
└──────────────────┬──────────────────┘
                   │
                   ▼
┌─────────────────────────────────────┐
│       Feature Engineering            │
│                                     │
│       71 Student Features           │
└──────────────────┬──────────────────┘
                   │
                   ▼
┌─────────────────────────────────────┐
│        Target Creation              │
│                                     │
│       At-Risk / Not At-Risk         │
└──────────────────┬──────────────────┘
                   │
                   ▼
┌─────────────────────────────────────┐
│         Data Preparation            │
│                                     │
│ Train / Validation / Test           │
│ Standardization                     │
│ SMOTE Class Balancing               │
└──────────────────┬──────────────────┘
                   │
                   ▼
        ┌──────────┼──────────┐
        │          │          │
        ▼          ▼          ▼
      🧠 DL       🌲 RF      ⚡ XGBoost
        │          │          │
        └──────────┼──────────┘
                   │
                   ▼
┌─────────────────────────────────────┐
│          Ensemble Prediction        │
│                                     │
│ Weighted Model Combination          │
└──────────────────┬──────────────────┘
                   │
                   ▼
┌─────────────────────────────────────┐
│        Learning-Gap Analysis        │
│                                     │
│ Performance · Risk · Recommendations│
└──────────────────┬──────────────────┘
                   │
                   ▼
┌─────────────────────────────────────┐
│       Personalized Action Plan      │
└─────────────────────────────────────┘
```

---

# 🩷 Key Features

## 01 · Multi-Source Student Analytics

The system combines information from multiple dimensions of student activity rather than relying on a single performance indicator.

### Data dimensions

* Student information
* Homework performance
* Test performance
* Interaction activity

This produces a broader student representation for predictive modeling.

---

## 02 · 71-Feature Student Representation

The final feature matrix used in the modeling pipeline contains:

```text
100 students
71 features
```

The feature space is constructed from the available student, homework, test, and interaction information.

This enables the models to capture multiple aspects of academic behaviour simultaneously.

---

## 03 · At-Risk Student Identification

The project formulates the prediction task as a binary classification problem:

```text
0 → Not At-Risk
1 → At-Risk
```

The notebook includes a target-generation component that calculates a risk-oriented score using homework and test performance.

The recorded dataset used in the final run contains:

```text
100 students
67 Not At-Risk
33 At-Risk
```

---

## 04 · Class Imbalance Handling

The project incorporates **SMOTE (Synthetic Minority Over-sampling Technique)** during model training to address class imbalance in the training data.

The modeling workflow therefore includes:

```text
Training Data
      ↓
Feature Scaling
      ↓
SMOTE
      ↓
Balanced Training Set
      ↓
Model Training
```

This is applied to the training data before fitting the traditional machine-learning models and within the deep-learning training pipeline.

---

# 🧠 Machine Learning Models

The project combines three predictive approaches.

## 🧠 Deep Learning

A TensorFlow/Keras feed-forward neural network is constructed using:

```text
Input Layer
    ↓
Dense(128, ReLU)
    ↓
Batch Normalization
    ↓
Dropout(0.30)
    ↓
Dense(64, ReLU)
    ↓
Batch Normalization
    ↓
Dropout(0.30)
    ↓
Dense(32, ReLU)
    ↓
Batch Normalization
    ↓
Dropout(0.20)
    ↓
Dense(16, ReLU)
    ↓
Dropout(0.20)
    ↓
Dense(1, Sigmoid)
```

Training uses:

* Adam optimizer
* Binary cross-entropy
* Accuracy
* Precision
* Recall
* AUC
* Early stopping
* Learning-rate reduction

---

## 🌲 Random Forest

A Random Forest classifier is used as one of the ensemble components.

Configuration in the notebook:

```python
RandomForestClassifier(
    n_estimators=100,
    random_state=42
)
```

---

## ⚡ XGBoost

The second tree-based model is an XGBoost classifier:

```python
XGBClassifier(
    random_state=42,
    eval_metric="logloss"
)
```

---

# 🎀 Ensemble Learning

The project combines predictions from:

```text
40%  Deep Learning
40%  Random Forest
20%  XGBoost
```

The ensemble probability is calculated as:

```text
Ensemble Probability
=
0.4 × DL Probability
+
0.4 × RF Probability
+
0.2 × XGBoost Probability
```

The final classification is:

```text
Ensemble Probability > 0.5
            ↓
        At-Risk
```

Otherwise:

```text
        Not At-Risk
```

---

# 📈 Data Splitting

The recorded final modeling pipeline uses:

```text
Total samples       → 100
Training samples    → 64
Validation samples  → 16
Test samples        → 20
```

The training/validation split uses stratification to preserve the class distribution.

---

# 🌸 Model Evaluation

The project evaluates predictions using:

* Accuracy
* Precision
* Recall
* AUC
* Confusion Matrix
* Classification Report
* Precision-Recall analysis

The notebook also generates visual evaluation outputs including:

```text
Training / Validation Loss
Training / Validation Accuracy
Training / Validation AUC
Confusion Matrix
Precision-Recall Curves
```

---

# 📊 Recorded Final Run

The repository's executed notebook records the following final summary:

| Metric                         | Recorded Value |
| :----------------------------- | -------------: |
| 👩🏻‍🎓 Students analyzed      |        **100** |
| 🎯 Features used               |         **71** |
| 🚨 At-Risk labels              |         **33** |
| 🌷 Not At-Risk labels          |         **67** |
| 🧠 Deep Learning test accuracy |      **0.600** |
| 🤖 Ensemble test accuracy      |      **0.550** |

> These values correspond to the executed notebook run stored in the repository and should be interpreted as results from this particular dataset split, feature construction, target-generation procedure, and training configuration.

---

# ✦ Learning-Gap Analysis

Prediction is followed by an additional **GapAnalyzer** stage.

For each student, the system creates a report containing:

```text
Student ID
Risk Prediction
Risk Probability
Homework Performance
Test Performance
Recommendations
Action Plan
```

---

# 🩷 Student Performance Analysis

The reporting component analyzes:

## Homework

The analyzer calculates:

```text
Average score
Total assignments
Performance level
```

Performance levels are categorized as:

```text
≥ 85%  → Excellent
≥ 70%  → Good
< 70%  → Needs Improvement
```

---

## Tests

The test-analysis component similarly calculates:

```text
Average score
Number of tests taken
Performance level
```

using the same performance-level thresholds.

---

# 💌 Personalized Recommendations

For students predicted as **At-Risk**, the current rule-based reporting layer provides recommendations such as:

```text
• Schedule one-on-one tutoring sessions
• Focus on foundational concepts
• Increase practice frequency
• Monitor progress weekly
```

The associated action plan includes:

```text
Weekly study time → 8–10 hours
Focus areas       → Basic concepts
                     Problem solving
Assessment        → Weekly quizzes
```

For students predicted as **Not At-Risk**, the current system provides recommendations such as:

```text
• Maintain current study routine
• Challenge with advanced problems
• Participate in peer teaching
• Set higher goals
```

with an action plan emphasizing:

```text
Weekly study time → 5–7 hours
Focus areas       → Advanced topics
                     Applications
Assessment        → Monthly reviews
```

---

# 🌷 Example Student Report

A generated report follows this structure:

```text
==================================================
STUDENT REPORT
==================================================

Student ID:
STD0002

Risk Level:
At-Risk

Risk Probability:
60.0%

Homework Performance:
75.7%
30 assignments
Good

Test Performance:
74.6%
6 tests
Good

Recommendations:
1. Schedule one-on-one tutoring sessions
2. Focus on foundational concepts
3. Increase practice frequency
4. Monitor progress weekly

Action Plan:
Weekly Hours → 8–10 hours
Focus Areas  → Basic concepts
               Problem solving
Assessment   → Weekly quizzes
```

---

# 🧮 Target Creation

The notebook contains a `TargetCreator` class responsible for constructing the binary target.

The risk score incorporates:

```text
Test Performance
        +
Homework Performance
        +
Small Random Variability Component
```

The project then maps the resulting score into:

```text
At-Risk
Not At-Risk
```

A safeguard is also included to create a balanced class distribution when only one class is produced by the initial target-generation process.

> Because the current target-generation implementation includes synthetic balancing/variability logic, the generated labels should be regarded as a project-specific modeling target rather than externally validated educational outcomes.

---

# 🛠️ Technology Stack

<div align="center">

| Technology                | Purpose                               |
| :------------------------ | :------------------------------------ |
| 🐍 **Python**             | Core analytics and modeling           |
| 🐼 **Pandas**             | Data manipulation                     |
| 🔢 **NumPy**              | Numerical computation                 |
| 🧠 **TensorFlow / Keras** | Deep learning                         |
| 🌲 **Scikit-learn**       | Preprocessing, Random Forest, metrics |
| ⚡ **XGBoost**             | Gradient-boosted tree classification  |
| ⚖️ **imbalanced-learn**   | SMOTE oversampling                    |
| 📊 **Matplotlib**         | Static visualization                  |
| 🌷 **Seaborn**            | Statistical visualization             |
| ✨ **Plotly**              | Interactive visualization             |
| ☁️ **Google Colab**       | Notebook execution environment        |

</div>

---

# 📂 Repository Structure

```text
Predictive_Learning_Gap_Analyzer-/
│
├── 🌷 Predictive_Learning_Gap_Analyzer.ipynb
│
├── 🧠 deep_learning.h5
├── 🌲 random_forest.pkl
├── ⚡ xgboost.pkl
│
├── 📏 scaler.pkl
├── 🏷️ feature_names.pkl
│
├── 📄 README.md
└── 📜 LICENSE
```

---

# 🧠 Saved Model Artifacts

The repository includes trained model components so the modeling workflow does not have to begin from scratch.

### Deep Learning Model

```text
deep_learning.h5
```

TensorFlow/Keras neural-network model.

### Random Forest

```text
random_forest.pkl
```

Serialized Random Forest classifier.

### XGBoost

```text
xgboost.pkl
```

Serialized XGBoost classifier.

### Feature Scaler

```text
scaler.pkl
```

Stores the scaling transformation used by the ensemble pipeline.

### Feature Names

```text
feature_names.pkl
```

Stores the feature names corresponding to the trained model input representation.

---

# 🚀 Getting Started

## 01 · Clone the Repository

```bash
git clone https://github.com/ViivianREINE/Predictive_Learning_Gap_Analyzer-.git
```

```bash
cd Predictive_Learning_Gap_Analyzer-
```

---

# 🌸 Run the Notebook

The primary implementation is contained in:

```text
Predictive_Learning_Gap_Analyzer.ipynb
```

The notebook is compatible with a Python / Google Colab workflow.

Open the notebook in Google Colab or Jupyter Notebook.

---

# 📦 Install Dependencies

The notebook installs the required packages using:

```bash
pip install tensorflow scikit-learn pandas numpy matplotlib seaborn plotly xgboost imbalanced-learn
```

Or install them manually:

```bash
pip install tensorflow scikit-learn pandas numpy matplotlib seaborn plotly xgboost imbalanced-learn
```

---

# 📥 Dataset Requirements

The notebook expects the following eight CSV files:

```text
class11_students.csv
class11_homework.csv
class11_tests.csv
class11_interactions.csv

class12_students.csv
class12_homework.csv
class12_tests.csv
class12_interactions.csv
```

The notebook includes a Google Colab upload workflow for loading these datasets.

---

# 🧪 Reproducing the Pipeline

The notebook is organized as a sequential analytical workflow:

```text
STEP 1
Install Packages
      ↓
STEP 2
Import Libraries
      ↓
STEP 3
Upload Dataset Files
      ↓
Data Cleaning
      ↓
Feature Engineering
      ↓
Target Variable Creation
      ↓
Train / Validation / Test Split
      ↓
Deep Learning Model
      ↓
Ensemble Model
      ↓
Gap Analysis & Reporting
      ↓
Evaluation
      ↓
Model Export
```

---

# 📈 Visual Analytics

The notebook uses both static and interactive visualization tools.

Potential outputs include:

```text
📊 Distribution Analysis
📈 Performance Trends
🧩 Confusion Matrices
🎯 Precision-Recall Curves
🧠 Learning Curves
📉 Validation Curves
✨ Interactive Plotly Visualizations
```

These visualizations support both model evaluation and exploratory understanding of student behaviour.

---

# 🌼 Educational Use Cases

The project can support educational analytics scenarios such as:

### Early Academic Support

Identify students who may benefit from intervention.

### Performance Monitoring

Track homework and assessment patterns.

### Personalized Learning

Generate targeted academic recommendations.

### Teacher Decision Support

Provide structured learner-level summaries.

### Academic Analytics

Combine multiple educational signals into a predictive framework.

---

# 💗 Human-Centered Philosophy

The project is built around a simple progression:

```text
Observe
   ↓
Understand
   ↓
Predict
   ↓
Intervene
   ↓
Support
```

The purpose of predictive educational analytics should not be to label students permanently.

Instead, prediction can serve as a signal for:

```text
More attention
More support
Better resources
Personalized interventions
```

---

# 🔐 Ethics, Privacy & Fairness

Educational data can contain highly sensitive information.

A production implementation should therefore incorporate:

* Strong access controls
* Encryption
* Consent-aware data collection
* Secure storage
* Data minimization
* Transparent model explanations
* Bias and fairness evaluation
* Human oversight
* Appropriate retention policies

Predictions should be used as **decision-support signals**, not as irreversible judgments about a student's ability or future.

---

# ⚠️ Important Limitations

The current project is a **machine-learning prototype** and has several methodological considerations.

### Synthetic / Project-Specific Target Construction

The notebook's target-generation logic includes a fallback class-balancing mechanism and a small random variability component.

### Limited Dataset Size

The recorded final experiment uses:

```text
100 students
71 features
```

which is small for drawing broad conclusions about educational populations.

### Exploratory Model Evaluation

The recorded test accuracies are specific to the stored experimental run and should not be interpreted as universal model performance.

### No External Validation

The repository does not establish performance on an independent external educational cohort.

### Human Oversight

Predictions should be interpreted alongside teacher expertise, student context, and actual educational evidence.

---

# 🌱 Future Roadmap

## 🌷 Phase I — Current System

* [x] Multi-source student analytics
* [x] Feature engineering
* [x] 71-feature student matrix
* [x] Risk classification
* [x] SMOTE balancing
* [x] Deep learning model
* [x] Random Forest
* [x] XGBoost
* [x] Ensemble prediction
* [x] Gap analysis
* [x] Personalized recommendations
* [x] Model serialization

---

## 🎀 Phase II — Explainable Learning Analytics

* [ ] SHAP-based explanations
* [ ] Feature importance dashboards
* [ ] Individual prediction explanations
* [ ] Student learning profiles
* [ ] Teacher-facing visualization layer

---

## 🧠 Phase III — Advanced Personalization

```text
Prediction
    ↓
Weak-area detection
    ↓
Topic recommendation
    ↓
Adaptive learning pathway
    ↓
Targeted practice
    ↓
Progress monitoring
```

Future recommendations could incorporate:

* topic-level weaknesses
* assignment patterns
* test-domain performance
* learning consistency
* engagement signals

---

## 🌸 Phase IV — Production Educational Platform

Potential architecture:

```text
              Student Data
                   │
                   ▼
              Data Pipeline
                   │
                   ▼
            Feature Store
                   │
                   ▼
          ML Prediction Layer
                   │
        ┌──────────┼──────────┐
        ▼          ▼          ▼
     Risk       Weak Areas   Trends
        │          │          │
        └──────────┼──────────┘
                   ▼
        Personalized Support
                   │
                   ▼
        Teacher / Student UI
```

---

# 💡 Possible Future Technologies

```text
FastAPI
React / Next.js
PostgreSQL
MLflow
SHAP
TensorFlow Serving
Docker
Cloud Storage
Feature Stores
MLOps Pipelines
```

---

# 🎨 Visual Identity

For project documentation and presentation, the recommended aesthetic is:

<div align="center">

### 🌷 Soft Rose · Beige · Off White · Mocha · Rose Gold

</div>

### Color Palette

| Color         |    Hex    |
| :------------ | :-------: |
| 🌸 Blush Pink | `#F7D6E6` |
| 🌹 Dusty Rose | `#DFA7C7` |
| 🎀 Soft Rose  | `#E8A0BF` |
| 🥐 Warm Beige | `#F7F3EE` |
| 🤍 Off White  | `#FFFDF9` |
| ☕ Mocha       | `#8B6F61` |
| 🤎 Dark Brown | `#6D564A` |

### Typography Direction

```text
Elegant Headings → Playfair Display
Soft Editorial   → Cormorant Garamond
Readable Body    → Inter
Technical Data   → JetBrains Mono
```

GitHub controls README font rendering, so the visual identity is created through spacing, hierarchy, HTML alignment, badges, tables, and restrained use of emojis.

---

# 🏆 Project Highlights

<div align="center">

### 🧠 AI-Powered Prediction

### 📊 71-Feature Student Modeling

### 🌲 Random Forest + XGBoost

### 🧬 Deep Learning

### ⚖️ SMOTE Class Balancing

### 📈 Model Evaluation

### 🎯 Risk Prediction

### 💌 Personalized Recommendations

### 📚 Learning-Gap Analysis

### 🌷 Educational Data Science

</div>

---

# 📌 Project Summary

|                              |                                                      |
| :--------------------------- | :--------------------------------------------------- |
| **Project**                  | Predictive Learning Gap Analyzer                     |
| **Domain**                   | Educational Data Science                             |
| **Primary Task**             | Student Risk Classification                          |
| **Students in Recorded Run** | 100                                                  |
| **Features**                 | 71                                                   |
| **Models**                   | Deep Learning, Random Forest, XGBoost                |
| **Ensemble Weights**         | 40% DL · 40% RF · 20% XGBoost                        |
| **Class Balancing**          | SMOTE                                                |
| **Evaluation**               | Accuracy, Precision, Recall, AUC, Confusion Matrix   |
| **Reporting**                | Learning-gap analysis & personalized recommendations |
| **Primary Environment**      | Google Colab / Jupyter                               |
| **Language**                 | Python                                               |
| **License**                  | MIT                                                  |

---

# 👩🏻‍💻 Author

<div align="center">

## Priyam Parashar

**AI/ML · Data Science · Bioinformatics · Healthcare & Educational Technology**

<br>

<a href="https://github.com/ViivianREINE">
<img src="https://img.shields.io/badge/GitHub-ViivianREINE-6D564A?style=for-the-badge&logo=github&logoColor=FFFDF9" />
</a>

</div>

---

# 📜 License

This project is licensed under the **MIT License**.

See [`LICENSE`](./LICENSE) for the complete license text.

---

<div align="center">

# 🌷 Predictive Learning Gap Analyzer

### *Predict early. Understand deeply. Support personally.*

<br>

**♡ Data · Intelligence · Education · Impact ♡**

<br>

<sub>
Built at the intersection of machine learning, educational analytics, and personalized learning.
</sub>

</div>
```
