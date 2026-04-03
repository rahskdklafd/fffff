import requests
import json

API_KEY = "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"
URL = "https://api.groq.com/openai/v1/chat/completions"

SYSTEM_PROMPT = """
You are a Machine Learning and Data Analysis coding assistant.

RESPONSE FORMAT RULES
• Always return ONLY Python code.
• Code must be clean, readable, and properly formatted.
• Preserve indentation and line breaks.
• Add short comments explaining each step.
• The code must run directly in Python or Jupyter Notebook.
• Never compress code into one line.
• Never include explanations outside the code.

BEHAVIOR RULES

1. If the user sends a FULL QUESTION or DATA ANALYSIS TASK:
Return a complete runnable pipeline with comments and an example.

Structure must follow this order:

# Step 1 - Imports
# Step 2 - Example data creation or data loading
# Step 3 - Data preprocessing / cleaning
# Step 4 - Data analysis or transformation
# Step 5 - Result output

2. If the user asks about a SPECIFIC TASK:
Return ONLY the relevant code snippet with a small example dataset.

Example cases:
• scaling features
• groupby operation
• filtering
• numpy slicing
• merging datasets

3. If the user sends BUGGY CODE or an ERROR:
Return the corrected version of the code.

Requirements:
• Fix the bug directly in the code
• Add a comment marking the fix

Example comment:
# FIX: corrected column name

Do NOT explain the error outside the code.

PRIMARY TOPICS (Focus areas)

NUMPY
• Arrays
• Indexing and slicing
• Boolean masking
• Vector operations
• Numerical operations
• Matrix operations

PANDAS / DATA ANALYSIS (DVA Python)
• Data loading
• Data cleaning
    - handling duplicates
    - handling blanks
    - fixing inconsistent data types
• Data filtering
• Data grouping
• Data merging
• Data pivoting
• Data aggregation
"""

def ask(question):
    payload = {
        "model": "openai/gpt-oss-120b",
        "messages": [
            {"role": "system", "content": SYSTEM_PROMPT},
            {"role": "user", "content": question}
        ],
        "temperature": 0
    }

    headers = {
        "Authorization": f"Bearer {API_KEY}",
        "Content-Type": "application/json"
    }

    response = requests.post(URL, headers=headers, data=json.dumps(payload))
    result = response.json()

    return result["choices"][0]["message"]["content"]
to ask any question use this function

print(ask("explain full logistic regression"))

        OR
from IPython.display import Markdown

Markdown(ask("explain full logistic regression"))

api keys:-

lucknow:-

gsk _AF0idVsqN8Of4EUXd9w8WGdyb3FY7XMH59c3q8PqAEjzmincpplt gsk _YAO0UFNe0jA6bJTdCGPXWGdyb3FY52UNm0QD8pM16XawU5lxZtP0 bihar:-

gsk _929p2Xcx2GEgk7Ei3mfSWGdyb3FYlrhO4qOEeolCWY9FGjef5LAr gsk _WrDVVe1xJfByy5wPd0lEWGdyb3FYCKfSL8cJBa5etMvxe0RibOle gsk _FZV9qjwkd7UGUi3JT8h1WGdyb3FY01Ljfjmgdep8hyor2qgzYUld muzafar:-

gsk _PRNGNpPf3V8jC83JGL34WGdyb3FYUqlkcmoO5qHljzNQbgJngsds gsk _tlbP2oGKa6guVQ55e2L1WGdyb3FYijfvxsntUq8zg3IxFxmtabbe ravi:-

gsk _3gEK5dlq63QVsTqf6KJHWGdyb3FYdu3dBNVTJXxuxDfuYy7L0Umb gsk _dmZqtBSrYQpa9lerxcawWGdyb3FYqONboiRU9fbmrXsLhlLGbvFV gsk _FCZYeSiUHJuXk89NI0tNWGdyb3FYSRNT2D2IZmuqK5WklASf67F5 rj18:-

gsk _SeZnfHSDLDKzGI2AONGnWGdyb3FYsyzCQswy7ZzwtJygMgIJ9kLj gsk _aMJcXIQGUskh48AQJy3UWGdyb3FYBNlcMp01VI5KkNpxBf9Qt8io gsk _CrUJuztwGeYCrYGUr6BnWGdyb3FYhKVsaadyUbQt2XcmadQI10Uk gsk _AyIvNjKV3A3VvLAatGgHWGdyb3FY2rG9N0mdhnRrLuBCuXB891cR meerut :-

gsk _W3Vz8vG8FyagTQZCv9E1WGdyb3FYixbjWPKyTVWjKEJ29vmYAIJR gsk _H2XtLooHca8yrhfto70EWGdyb3FYQpJ0i4ghy1eqjWEFGYLMvtUv gsk _Osa4dsWpRdy226YuZJ7BWGdyb3FYD2XSnk68fiaH6Alnl8yrsDq6 gsk _PRGvuTOjnfdT1J38pmN3WGdyb3FYn6cn5DcxOmB5dOgDwRqGo09t gg:-

gsk _a91hAqQemMJAhd5pLo7PWGdyb3FYXiMr7hIglEh8IkwZsvojuqf7 gsk _ctpHZh2ExLGS3YApy0SSWGdyb3FY8b7W8v00aKH3ew0o4SmzKeOg gsk _rkBWZ5OtATuCcrIM5FBgWGdyb3FYWU1bGcwCfLsPiadcxh23iEve gsk _StHQNysPV0fi3sbxF0NbWGdyb3FYQNHERSSNhnkAPpCXcbw72q5s dadri:-

gsk _Fvj9HrCWL8d275AwPnrDWGdyb3FYy1gcNf1Rve8lyFEiwQYe0h1v gsk _W5X9Ajno6LZtkkh18UBfWGdyb3FYtBlJMF13aimdwSlOTT9iOEAL gsk _XPPxnfQzinh4hhbWY7vkWGdyb3FYIQ7ou7kU8uX46c0Kv1PiV0Ms gsk _fAyEpM2GDrxGDDZaYSRaWGdyb3FYkEYNoIi06PfHy0HywGKxwZrN mandi:-

gsk _Cer3BjVGmXpc9nck5WhsWGdyb3FYMgYZbplJ9rLI3YxmZnynQxYR gsk _CVq2n8pjJUDTXQaauyikWGdyb3FYTQXoLaIm1s6UZGtfI5xRLp6C gsk _wSdZpchzW9Ysb9KWteaqWGdyb3FYquPvt3nXnxXX9jcWhvmtjvxl


# Complete ML Cheatsheet: Full Pipeline & Best Practices

**Author:** ML Teacher  
**Topics:** Linear Regression, Logistic Regression, Decision Tree, Neural Networks, Transformers

---

## TABLE OF CONTENTS
1. [General ML Pipeline](#general-ml-pipeline)
2. [Data Cleaning & Preprocessing](#data-cleaning--preprocessing)
3. [Linear Regression](#linear-regression)
4. [Logistic Regression](#logistic-regression)
5. [Decision Tree](#decision-tree)
6. [Neural Networks](#neural-networks)
7. [Transformers](#transformers)
8. [Error Analysis & Evaluation Metrics](#error-analysis--evaluation-metrics)

---

# GENERAL ML PIPELINE

## Universal Steps (All Models)
```
1. Load Data
2. Data Cleaning
3. Exploratory Data Analysis (EDA)
4. Feature Preprocessing & Scaling
5. Train-Test Split
6. Model Training
7. Predictions
8. Evaluation & Metrics
9. Error Analysis
10. Hyperparameter Tuning
11. Final Deployment
```

---

# DATA CLEANING & PREPROCESSING

## 1. Load Data
```python
import pandas as pd
import numpy as np

# Load data
df = pd.read_csv('data.csv')

# Inspect data
print(df.head())           # First 5 rows
print(df.info())           # Data types & missing values
print(df.describe())       # Statistical summary
print(df.isnull().sum())   # Missing values count
```

## 2. Handle Missing Values

### Methods:
| Method | When to Use | Code |
|--------|------------|------|
| **Drop** | <5% missing | `df.dropna()` |
| **Mean/Median Imputation** | Numerical, normally distributed | `df.fillna(df.mean())` |
| **Forward Fill** | Time series data | `df.fillna(method='ffill')` |
| **Interpolation** | Time series | `df.interpolate()` |
| **KNN Imputation** | Preserve relationships | `from sklearn.impute import KNNImputer` |

```python
# Drop rows with missing values
df = df.dropna()

# Fill missing with mean
df['age'] = df['age'].fillna(df['age'].mean())

# KNN Imputation
from sklearn.impute import KNNImputer
imputer = KNNImputer(n_neighbors=5)
df = imputer.fit_transform(df)
```

## 3. Handle Outliers

### Detection Methods:
```python
# IQR Method
Q1 = df['column'].quantile(0.25)
Q3 = df['column'].quantile(0.75)
IQR = Q3 - Q1
lower_bound = Q1 - 1.5 * IQR
upper_bound = Q3 + 1.5 * IQR
df = df[(df['column'] >= lower_bound) & (df['column'] <= upper_bound)]

# Z-Score Method
from scipy import stats
z_scores = np.abs(stats.zscore(df['column']))
df = df[(z_scores < 3)]

# Isolation Forest
from sklearn.ensemble import IsolationForest
iso_forest = IsolationForest(contamination=0.1)
df['outlier'] = iso_forest.fit_predict(df)
df = df[df['outlier'] != -1]
```

## 4. Remove Duplicates
```python
df = df.drop_duplicates()
df = df.drop_duplicates(subset=['column_name'])
```

## 5. Encode Categorical Variables

### Methods:
```python
# One-Hot Encoding (for nominal categories)
df = pd.get_dummies(df, columns=['category'])

# Label Encoding (for ordinal categories)
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
df['category'] = le.fit_transform(df['category'])

# Frequency Encoding
df['category'] = df['category'].map(df['category'].value_counts())

# Target Encoding (for high cardinality)
target_means = df.groupby('category')['target'].mean()
df['category'] = df['category'].map(target_means)
```

## 6. Feature Scaling

### When to Use:
| Algorithm | Scaling Needed? |
|-----------|-----------------|
| Linear Regression | Yes (important) |
| Logistic Regression | Yes (important) |
| Decision Tree | No |
| Random Forest | No |
| Neural Networks | **Yes (critical)** |
| Transformers | Yes |
| KNN | Yes |
| SVM | Yes |

### Scaling Methods:

```python
# Standardization (Z-score normalization)
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)

# Normalization (Min-Max scaling)
from sklearn.preprocessing import MinMaxScaler
scaler = MinMaxScaler()
X_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)

# Robust Scaling (for outliers)
from sklearn.preprocessing import RobustScaler
scaler = RobustScaler()
X_scaled = scaler.fit_transform(X_train)

# Log Scaling (for skewed distributions)
X_log = np.log1p(X)
```

## 7. Feature Engineering

```python
# Create new features
df['new_feature'] = df['feature1'] * df['feature2']
df['ratio'] = df['feature1'] / (df['feature2'] + 1)
df['log_feature'] = np.log1p(df['feature'])

# Polynomial Features
from sklearn.preprocessing import PolynomialFeatures
poly = PolynomialFeatures(degree=2)
X_poly = poly.fit_transform(X)

# Extract date features
df['date'] = pd.to_datetime(df['date'])
df['year'] = df['date'].dt.year
df['month'] = df['date'].dt.month
df['day_of_week'] = df['date'].dt.dayofweek
```

## 8. Train-Test Split

```python
from sklearn.model_selection import train_test_split

# Standard split
X_train, X_test, y_train, y_test = train_test_split(
    X, y, 
    test_size=0.2,           # 80-20 split
    random_state=42,         # For reproducibility
    stratify=y               # For imbalanced data
)

# Time series split
from sklearn.model_selection import TimeSeriesSplit
tscv = TimeSeriesSplit(n_splits=5)
for train_idx, test_idx in tscv.split(X):
    X_train, X_test = X[train_idx], X[test_idx]
    y_train, y_test = y[train_idx], y[test_idx]
```

---

# LINEAR REGRESSION

## When to Use
- Continuous target variable
- Linear relationship between features and target
- Interpretability is important
- Fast inference needed

## Mathematical Formula
```
ŷ = b₀ + b₁x₁ + b₂x₂ + ... + bₙxₙ

Cost Function (MSE):
J(θ) = (1/2m) * Σ(hθ(x) - y)²
```

## Simple Pipeline

```python
import pandas as pd
import numpy as np
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.metrics import mean_squared_error, mean_absolute_error, r2_score

# ===== STEP 1: LOAD & CLEAN =====
df = pd.read_csv('housing.csv')
df = df.dropna()  # Remove missing values

# ===== STEP 2: PREPARE DATA =====
X = df.drop('price', axis=1)
y = df['price']

# Train-test split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Scale features
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)

# ===== STEP 3: TRAIN =====
model = LinearRegression()
model.fit(X_train, y_train)

# ===== STEP 4: PREDICT =====
y_pred = model.predict(X_test)

# Predict on new data
new_data = [[1.5, 3.2, 50.0]]
new_data = scaler.transform(new_data)
prediction = model.predict(new_data)[0]

# ===== STEP 5: EVALUATE =====
print(f"RMSE: {np.sqrt(mean_squared_error(y_test, y_pred)):.2f}")
print(f"MAE:  {mean_absolute_error(y_test, y_pred):.2f}")
print(f"R²:   {r2_score(y_test, y_pred):.4f}")
```

## Key Parameters
| Parameter | Default | Description |
|-----------|---------|-------------|
| `fit_intercept` | True | Include intercept term |
| `normalize` | False | Normalize X (deprecated) |
| `copy_X` | True | Copy X (avoid modifying) |
| `n_jobs` | None | Parallel jobs (-1 = all) |
| `positive` | False | Force positive coefficients |

## Working Example: House Price Prediction
```python
# Complete example
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.metrics import r2_score, mean_squared_error
import pandas as pd
import numpy as np

# Create sample data
np.random.seed(42)
X = np.random.randn(100, 3)
y = 2*X[:, 0] + 3*X[:, 1] - X[:, 2] + np.random.randn(100) * 0.5

# Split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Scale
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)

# Train
model = LinearRegression()
model.fit(X_train, y_train)

# Predict
y_pred = model.predict(X_test)

# Evaluate
print(f"R² Score: {r2_score(y_test, y_pred):.4f}")
print(f"RMSE: {np.sqrt(mean_squared_error(y_test, y_pred)):.4f}")
```

---

# LOGISTIC REGRESSION

## When to Use
- Binary or multi-class classification
- Need probability outputs
- Interpretable model
- Linear decision boundary

## Mathematical Formula
```
Sigmoid Function:
σ(z) = 1 / (1 + e^(-z))

where z = b₀ + b₁x₁ + b₂x₂ + ... + bₙxₙ

Cost Function (Binary Cross-Entropy):
J(θ) = -(1/m) * Σ[y*log(hθ(x)) + (1-y)*log(1-hθ(x))]
```

## Simple Pipeline

```python
import pandas as pd
import numpy as np
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report, roc_auc_score

# ===== STEP 1: LOAD & CLEAN =====
df = pd.read_csv('classification_data.csv')
df = df.dropna()

# ===== STEP 2: PREPARE DATA =====
X = df.drop('target', axis=1)
y = df['target']

# Train-test split (stratify for imbalanced data)
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42, stratify=y
)

# Scale features
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)

# ===== STEP 3: TRAIN =====
model = LogisticRegression(max_iter=1000, random_state=42)
model.fit(X_train, y_train)

# ===== STEP 4: PREDICT =====
y_pred = model.predict(X_test)
y_pred_proba = model.predict_proba(X_test)  # Probabilities

# Predict on new data
new_data = [[1.5, 3.2, 0.5]]
new_data = scaler.transform(new_data)
prediction = model.predict(new_data)[0]

# ===== STEP 5: EVALUATE =====
print(f"Accuracy:  {accuracy_score(y_test, y_pred):.4f}")
print(f"ROC-AUC:   {roc_auc_score(y_test, y_pred_proba[:, 1]):.4f}")
print(f"\nConfusion Matrix:")
print(confusion_matrix(y_test, y_pred))
print(f"\n{classification_report(y_test, y_pred)}")
```

## Key Parameters
| Parameter | Default | Description |
|-----------|---------|-------------|
| `penalty` | 'l2' | 'l1', 'l2', 'elasticnet', 'none' |
| `C` | 1.0 | Inverse regularization (lower = stronger) |
| `solver` | 'lbfgs' | 'lbfgs', 'liblinear', 'newton-cg', 'sag', 'saga' |
| `max_iter` | 100 | Maximum iterations |
| `class_weight` | None | 'balanced' for imbalanced data |
| `multi_class` | 'auto' | 'auto', 'ovr', 'multinomial' |

## Working Example: Iris Classification
```python
from sklearn.linear_model import LogisticRegression
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report

# Load data
iris = load_iris()
X, y = iris.data, iris.target

# Split
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42, stratify=y
)

# Scale
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)

# Train
model = LogisticRegression(max_iter=1000, random_state=42)
model.fit(X_train, y_train)

# Predict
y_pred = model.predict(X_test)

# Evaluate
print(f"Accuracy: {accuracy_score(y_test, y_pred):.4f}")
print("\nConfusion Matrix:")
print(confusion_matrix(y_test, y_pred))
print("\nClassification Report:")
print(classification_report(y_test, y_pred))
```

---

# DECISION TREE

## When to Use
- Non-linear relationships
- Categorical and numerical features
- Feature importance needed
- No scaling required
- Interpretability is critical

## How It Works
```
Splits data recursively based on feature values
Information Gain = Entropy(parent) - Σ(weighted entropy of children)
Gini Impurity = 1 - Σ(p_i²)
```

## Simple Pipeline

```python
import pandas as pd
import numpy as np
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report

# ===== STEP 1: LOAD & CLEAN =====
df = pd.read_csv('data.csv')
df = df.dropna()

# One-hot encode categorical variables (if any)
df = pd.get_dummies(df)

# ===== STEP 2: PREPARE DATA =====
X = df.drop('target', axis=1)
y = df['target']

# Train-test split (NO scaling needed)
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42, stratify=y
)

# ===== STEP 3: TRAIN =====
model = DecisionTreeClassifier(
    max_depth=5,              # Prevent overfitting
    min_samples_split=10,
    min_samples_leaf=5,
    random_state=42
)
model.fit(X_train, y_train)

# ===== STEP 4: PREDICT =====
y_pred = model.predict(X_test)

# Predict on new data
new_data = [[1, 0, 1, 2.5]]
prediction = model.predict(new_data)[0]

# ===== STEP 5: EVALUATE =====
print(f"Accuracy: {accuracy_score(y_test, y_pred):.4f}")
print(f"\nConfusion Matrix:")
print(confusion_matrix(y_test, y_pred))
print(f"\n{classification_report(y_test, y_pred)}")

# Feature importance
for name, importance in zip(X.columns, model.feature_importances_):
    print(f"{name}: {importance:.4f}")

# Visualize tree
from sklearn.tree import plot_tree
import matplotlib.pyplot as plt

plt.figure(figsize=(15, 8))
plot_tree(model, feature_names=X.columns, filled=True, rounded=True)
plt.show()
```

## Key Parameters
| Parameter | Default | Description |
|-----------|---------|-------------|
| `criterion` | 'gini' | 'gini' or 'entropy' |
| `splitter` | 'best' | 'best' or 'random' |
| `max_depth` | None | Limit tree depth (prevents overfitting) |
| `min_samples_split` | 2 | Min samples to split node |
| `min_samples_leaf` | 1 | Min samples in leaf node |
| `min_weight_fraction_leaf` | 0.0 | Fraction of min weight |
| `max_features` | None | 'sqrt', 'log2', or int |
| `random_state` | None | Reproducibility |

## Working Example: Titanic Survival
```python
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report
import pandas as pd
import numpy as np

# Load data
df = pd.read_csv('titanic.csv')
df = df[['Pclass', 'Age', 'Sex', 'Fare', 'Survived']].dropna()

# Encode categorical
df['Sex'] = (df['Sex'] == 'male').astype(int)

# Split
X = df.drop('Survived', axis=1)
y = df['Survived']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Train
model = DecisionTreeClassifier(max_depth=5, min_samples_split=10, random_state=42)
model.fit(X_train, y_train)

# Predict
y_pred = model.predict(X_test)

# Evaluate
print(f"Accuracy: {accuracy_score(y_test, y_pred):.4f}")
print("\nConfusion Matrix:")
print(confusion_matrix(y_test, y_pred))
print("\nFeature Importance:")
for name, imp in zip(X.columns, model.feature_importances_):
    print(f"{name}: {imp:.4f}")
```

---

# NEURAL NETWORKS

## When to Use
- Complex non-linear patterns
- Text/NLP classification tasks
- Structured numerical data (medium-large datasets)
- Fast prototyping

## Complete NLP Pipeline for Text Classification

### Complete Step-by-Step Example: Sentiment Analysis

```python
import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split
from tensorflow import keras
from tensorflow.keras import layers
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report
import re

# ============ STEP 1: RAW TEXT ============
# Load your text data
df = pd.read_csv('reviews.csv')  # columns: 'text', 'label'
texts = df['text'].tolist()      # Reviews/comments
labels = df['label'].values      # 0=negative, 1=positive

print(f"Dataset size: {len(texts)}")
print(f"Sample: {texts[0][:80]}...")

# ============ STEP 2: CLEANING ============
def clean_text(text):
    text = text.lower()                              # Lowercase
    text = re.sub(r'http\S+|www\S+', '', text)      # Remove URLs
    text = re.sub(r'[^a-zA-Z\s]', '', text)         # Keep only letters & spaces
    text = re.sub(r'\s+', ' ', text).strip()        # Remove extra spaces
    return text

texts_cleaned = [clean_text(text) for text in texts]
print(f"Cleaned: {texts_cleaned[0][:80]}...")

# ============ STEP 3: TOKENIZATION ============
from tensorflow.keras.preprocessing.text import Tokenizer

max_words = 5000  # Keep top 5000 words
tokenizer = Tokenizer(num_words=max_words)
tokenizer.fit_on_texts(texts_cleaned)

sequences = tokenizer.texts_to_sequences(texts_cleaned)
print(f"Sequence sample: {sequences[0][:10]}")

# ============ STEP 4: STOP WORDS (Optional) ============
stop_words = {
    'the', 'a', 'an', 'and', 'or', 'but', 'is', 'are', 'was', 'were',
    'in', 'on', 'at', 'to', 'for', 'of', 'with', 'by', 'from', 'be',
    'have', 'has', 'had', 'do', 'does', 'did', 'if', 'while', 'when'
}

def remove_stopwords(text):
    words = text.split()
    return ' '.join([w for w in words if w not in stop_words])

texts_cleaned = [remove_stopwords(text) for text in texts_cleaned]

# ============ STEP 5: STEMMING/LEMMATIZATION ============
from nltk.stem import PorterStemmer
import nltk
nltk.download('punkt', quiet=True)

stemmer = PorterStemmer()

def stem_text(text):
    return ' '.join([stemmer.stem(w) for w in text.split()])

texts_cleaned = [stem_text(text) for text in texts_cleaned]

# Re-tokenize
tokenizer = Tokenizer(num_words=max_words)
tokenizer.fit_on_texts(texts_cleaned)
sequences = tokenizer.texts_to_sequences(texts_cleaned)

# ============ STEP 6: VECTORIZATION / EMBEDDING ============
# Keras Embedding layer handles this - just pad sequences

# ============ STEP 7: PADDING ============
from tensorflow.keras.preprocessing.sequence import pad_sequences

max_length = 100  # Max text length
X = pad_sequences(sequences, maxlen=max_length, padding='post')

print(f"Input shape: {X.shape}")

# ============ TRAIN-TEST SPLIT ============
X_train, X_test, y_train, y_test = train_test_split(
    X, labels, test_size=0.2, random_state=42, stratify=labels
)

# ============ STEP 8: MODEL (LSTM) ============
model = keras.Sequential([
    # Embedding: converts integers to dense vectors
    layers.Embedding(input_dim=max_words, output_dim=128, input_length=max_length),
    
    # LSTM: processes sequences
    layers.LSTM(64, return_sequences=True),
    layers.Dropout(0.2),
    
    layers.LSTM(32),
    layers.Dropout(0.2),
    
    # Classification layers
    layers.Dense(16, activation='relu'),
    layers.Dense(1, activation='sigmoid')  # Binary classification
])

# Compile
model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])

# ============ TRAINING ============
print("\nTraining...")
history = model.fit(
    X_train, y_train,
    epochs=10,
    batch_size=32,
    validation_split=0.2,
    verbose=1
)

# ============ STEP 9: PREDICTION ============
# Predict on test set
y_pred_proba = model.predict(X_test)
y_pred = (y_pred_proba > 0.5).astype(int).flatten()

# Function to predict on new text
def predict_sentiment(text):
    text = clean_text(text)
    text = remove_stopwords(text)
    text = stem_text(text)
    
    seq = tokenizer.texts_to_sequences([text])
    padded = pad_sequences(seq, maxlen=max_length, padding='post')
    
    prediction = model.predict(padded)[0][0]
    return prediction

new_text = "This movie was absolutely amazing!"
score = predict_sentiment(new_text)
print(f"\nText: '{new_text}'")
print(f"Score: {score:.4f} ({'Positive' if score > 0.5 else 'Negative'})")

# ============ EVALUATION ============
print("\n" + "="*50)
accuracy = accuracy_score(y_test, y_pred)
print(f"Accuracy: {accuracy:.4f}")
print("\nConfusion Matrix:")
print(confusion_matrix(y_test, y_pred))
print("\nClassification Report:")
print(classification_report(y_test, y_pred, target_names=['Negative', 'Positive']))

# Save model
model.save('sentiment_model.h5')
```

---

## Simple Architecture for Numerical Data

```python
# For structured data (not text)
model = keras.Sequential([
    layers.Dense(64, activation='relu', input_shape=(num_features,)),
    layers.Dropout(0.2),
    layers.Dense(32, activation='relu'),
    layers.Dropout(0.2),
    layers.Dense(16, activation='relu'),
    layers.Dense(1, activation='sigmoid')
])

model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])
history = model.fit(X_train, y_train, epochs=20, batch_size=32, validation_split=0.2)
```

## Key Parameters

| Parameter | Value | Description |
|-----------|-------|-------------|
| `max_words` | 5000 | Vocabulary size |
| `max_length` | 100 | Sequence length |
| `embedding_dim` | 128 | Embedding dimension |
| `lstm_units` | 64 | LSTM units |
| `epochs` | 10 | Training iterations |
| `batch_size` | 32 | Samples per update |

---

# TRANSFORMERS

## When to Use
- Text classification tasks (NLP)
- Transfer learning with pre-trained models
- When you need state-of-the-art performance

## Simple Pipeline

```python
from transformers import pipeline
import pandas as pd

# ===== SIMPLEST APPROACH: Using Pre-trained Pipeline =====
# This is the easiest - just 2 lines!

classifier = pipeline('sentiment-analysis', 
                     model='distilbert-base-uncased-finetuned-sst-2-english')

texts = [
    "This movie was amazing!",
    "I hated this film",
    "It was okay, nothing special"
]

predictions = classifier(texts)

for text, pred in zip(texts, predictions):
    print(f"Text: {text}")
    print(f"Sentiment: {pred['label']}, Score: {pred['score']:.4f}\n")
```

---

## Manual Fine-tuning (If You Need Custom Model)

```python
import pandas as pd
import torch
from transformers import AutoTokenizer, AutoModelForSequenceClassification, Trainer, TrainingArguments
from datasets import Dataset

# ===== STEP 1: LOAD DATA =====
df = pd.read_csv('reviews.csv')  # columns: 'text', 'label'

# ===== STEP 2: TOKENIZE =====
tokenizer = AutoTokenizer.from_pretrained('distilbert-base-uncased')

def tokenize(examples):
    return tokenizer(examples['text'], padding='max_length', max_length=128, truncation=True)

# Convert to Hugging Face Dataset
dataset = Dataset.from_pandas(df)
tokenized_dataset = dataset.map(tokenize, batched=True)

# Train-test split
train_test = tokenized_dataset.train_test_split(test_size=0.2)
train_dataset = train_test['train']
test_dataset = train_test['test']

# ===== STEP 3: LOAD MODEL =====
model = AutoModelForSequenceClassification.from_pretrained('distilbert-base-uncased', num_labels=2)

# ===== STEP 4: TRAIN =====
training_args = TrainingArguments(
    output_dir='./results',
    num_train_epochs=3,
    per_device_train_batch_size=32,
    per_device_eval_batch_size=64,
    learning_rate=2e-5,
    eval_strategy='epoch'
)

trainer = Trainer(
    model=model,
    args=training_args,
    train_dataset=train_dataset,
    eval_dataset=test_dataset
)

trainer.train()

# ===== STEP 5: PREDICT =====
def predict_text(text):
    pipe = pipeline('sentiment-analysis', model=model, tokenizer=tokenizer)
    return pipe(text)

result = predict_text("This is amazing!")
print(result)

# ===== STEP 6: EVALUATE =====
eval_results = trainer.evaluate(test_dataset)
print(f"Accuracy: {eval_results['eval_accuracy']:.4f}")
```

---

## Quick Reference: Popular Pre-trained Models

```python
from transformers import pipeline

# Text Classification
classifier = pipeline('sentiment-analysis', model='distilbert-base-uncased-finetuned-sst-2-english')

# Zero-shot Classification (no training needed!)
classifier = pipeline('zero-shot-classification', model='facebook/bart-large-mnli')
result = classifier("This movie was great", ["positive", "negative"])

# Named Entity Recognition
ner = pipeline('ner', model='dbmdz/bert-base-cased-finetuned-conll03-english')
result = ner("My name is John and I work at Google")

# Text Generation
generator = pipeline('text-generation', model='gpt2')
result = generator("The future of AI is", max_length=50)

# Question Answering
qa = pipeline('question-answering', model='deepset/roberta-base-squad2')
result = qa(question="What is AI?", context="AI is artificial intelligence")
```

## Key Models

| Model | Size | Use Case | Speed |
|-------|------|----------|-------|
| `distilbert` | Small | Fast sentiment/classification | ⚡⚡⚡ |
| `bert-base` | Medium | General NLP tasks | ⚡⚡ |
| `roberta-base` | Medium | Better BERT alternative | ⚡⚡ |
| `gpt2` | Small | Text generation | ⚡⚡⚡ |
| `t5-small` | Medium | Text-to-text tasks | ⚡⚡ |

---

# ERROR ANALYSIS & EVALUATION METRICS

## Classification Metrics

### Confusion Matrix
```
                Predicted
              Negative  Positive
Actual  Negative   TN       FP
        Positive   FN       TP

TN: True Negative   (Correct negative prediction)
FP: False Positive  (Type I error)
FN: False Negative  (Type II error)
TP: True Positive   (Correct positive prediction)
```

```python
from sklearn.metrics import confusion_matrix
import numpy as np

cm = confusion_matrix(y_true, y_pred)
tn, fp, fn, tp = cm.ravel()

print(f"True Negative:  {tn}")
print(f"False Positive: {fp}")
print(f"False Negative: {fn}")
print(f"True Positive:  {tp}")
```

### Accuracy
```
Formula: (TP + TN) / (TP + TN + FP + FN)
Range: 0 to 1 (higher is better)
Use: When classes are balanced
```

```python
from sklearn.metrics import accuracy_score
accuracy = accuracy_score(y_true, y_pred)
```

### Precision
```
Formula: TP / (TP + FP)
Range: 0 to 1 (higher is better)
Use: When false positives are costly
       (spam detection, fraud detection)
```

```python
from sklearn.metrics import precision_score
precision = precision_score(y_true, y_pred)
# "Of predicted positives, how many were actually positive?"
```

### Recall (Sensitivity/True Positive Rate)
```
Formula: TP / (TP + FN)
Range: 0 to 1 (higher is better)
Use: When false negatives are costly
     (disease detection, missing fraud)
```

```python
from sklearn.metrics import recall_score
recall = recall_score(y_true, y_pred)
# "Of actual positives, how many did we find?"
```

### F1-Score
```
Formula: 2 * (Precision * Recall) / (Precision + Recall)
Range: 0 to 1 (higher is better)
Use: When precision and recall equally important
     Imbalanced datasets
```

```python
from sklearn.metrics import f1_score
f1 = f1_score(y_true, y_pred)
```

### ROC-AUC Score
```
ROC Curve: True Positive Rate vs False Positive Rate
AUC: Area Under the Curve (0 to 1)
0.5 = Random classifier
1.0 = Perfect classifier
```

```python
from sklearn.metrics import roc_auc_score, roc_curve
import matplotlib.pyplot as plt

# Probability predictions needed
roc_auc = roc_auc_score(y_true, y_pred_proba)
fpr, tpr, thresholds = roc_curve(y_true, y_pred_proba)

plt.plot(fpr, tpr, label=f'AUC = {roc_auc:.3f}')
plt.xlabel('False Positive Rate')
plt.ylabel('True Positive Rate')
plt.legend()
plt.show()
```

### Precision-Recall Curve
```python
from sklearn.metrics import precision_recall_curve, average_precision_score
import matplotlib.pyplot as plt

ap = average_precision_score(y_true, y_pred_proba)
precision, recall, thresholds = precision_recall_curve(y_true, y_pred_proba)

plt.plot(recall, precision, label=f'AP = {ap:.3f}')
plt.xlabel('Recall')
plt.ylabel('Precision')
plt.legend()
plt.show()
```

### Classification Report
```python
from sklearn.metrics import classification_report

print(classification_report(y_true, y_pred))
# Output:
#           precision    recall  f1-score   support
# 
#        0       0.95      0.92      0.93       250
#        1       0.91      0.94      0.92       150
#
#     accuracy                       0.93       400
#    macro avg       0.93      0.93      0.93       400
# weighted avg       0.93      0.93      0.93       400
```

## Regression Metrics

### Mean Squared Error (MSE)
```
Formula: (1/n) * Σ(y_actual - y_pred)²
Range: 0 to ∞ (lower is better)
Unit: Squared units of target
```

```python
from sklearn.metrics import mean_squared_error
mse = mean_squared_error(y_true, y_pred)
```

### Root Mean Squared Error (RMSE)
```
Formula: √(MSE)
Range: 0 to ∞ (lower is better)
Unit: Same as target variable
```

```python
rmse = np.sqrt(mean_squared_error(y_true, y_pred))
```

### Mean Absolute Error (MAE)
```
Formula: (1/n) * Σ|y_actual - y_pred|
Range: 0 to ∞ (lower is better)
Unit: Same as target variable
Use: When you want interpretability
```

```python
from sklearn.metrics import mean_absolute_error
mae = mean_absolute_error(y_true, y_pred)
```

### R² Score
```
Formula: 1 - (SS_res / SS_tot)
SS_res = Σ(y_actual - y_pred)²
SS_tot = Σ(y_actual - mean(y))²
Range: -∞ to 1 (higher is better)
1.0 = Perfect fit
0.0 = Model as good as mean
<0.0 = Worse than mean
```

```python
from sklearn.metrics import r2_score
r2 = r2_score(y_true, y_pred)
```

### Mean Absolute Percentage Error (MAPE)
```
Formula: (1/n) * Σ|((y_actual - y_pred) / y_actual)| * 100
Range: 0 to ∞ (lower is better)
Unit: Percentage
Use: When relative error matters
```

```python
def mape(y_true, y_pred):
    return np.mean(np.abs((y_true - y_pred) / y_true)) * 100

mape_value = mape(y_true, y_pred)
```

## Error Types

### Type I Error (False Positive)
```
Definition: Rejecting a true null hypothesis
Example: Detecting disease when patient is healthy
Cost: Medical expenses, patient anxiety
Formula: α (significance level)
```

### Type II Error (False Negative)
```
Definition: Failing to reject a false null hypothesis
Example: Missing disease when patient is sick
Cost: Delayed treatment, serious consequences
Formula: β (usually related to power = 1 - β)
```

## Hyperparameter Tuning

### Grid Search
```python
from sklearn.model_selection import GridSearchCV
from sklearn.linear_model import LogisticRegression

param_grid = {
    'C': [0.001, 0.01, 0.1, 1, 10],
    'penalty': ['l1', 'l2'],
    'solver': ['liblinear', 'saga']
}

grid_search = GridSearchCV(
    LogisticRegression(),
    param_grid,
    cv=5,           # 5-fold cross-validation
    scoring='f1',
    n_jobs=-1
)

grid_search.fit(X_train, y_train)

print(f"Best params: {grid_search.best_params_}")
print(f"Best score: {grid_search.best_score_:.4f}")

best_model = grid_search.best_estimator_
y_pred = best_model.predict(X_test)
```

### Random Search
```python
from sklearn.model_selection import RandomizedSearchCV
import numpy as np

param_dist = {
    'C': np.logspace(-3, 3, 100),
    'penalty': ['l1', 'l2'],
    'solver': ['liblinear', 'saga']
}

random_search = RandomizedSearchCV(
    LogisticRegression(),
    param_dist,
    n_iter=20,      # Try 20 combinations
    cv=5,
    random_state=42,
    n_jobs=-1
)

random_search.fit(X_train, y_train)
```

### Cross-Validation
```python
from sklearn.model_selection import cross_val_score, cross_validate

# Simple cross-validation
scores = cross_val_score(
    LogisticRegression(),
    X_train, y_train,
    cv=5,                    # 5-fold
    scoring='f1'
)
print(f"Scores: {scores}")
print(f"Mean: {scores.mean():.4f} (+/- {scores.std():.4f})")

# Multiple metrics
scores = cross_validate(
    LogisticRegression(),
    X_train, y_train,
    cv=5,
    scoring=['accuracy', 'precision', 'recall', 'f1']
)
```

## Model Selection & Validation

### Training vs Validation vs Test
```
Total Data: 100%
├── Training: 60-70% (used to train model)
├── Validation: 10-20% (used to tune hyperparameters)
└── Test: 20-30% (final evaluation, never seen during training)
```

### Overfitting vs Underfitting
```
Underfitting:  High training error, High test error
               Model too simple
               Solution: Increase model complexity

Good Fit:      Low training error, Low test error
               
Overfitting:   Low training error, High test error
               Model too complex
               Solution: Add regularization, more data, simpler model
```

```python
# Detect overfitting
train_score = model.score(X_train, y_train)
test_score = model.score(X_test, y_test)

if test_score < train_score - 0.1:
    print("⚠️ Overfitting detected!")
elif test_score < train_score - 0.05:
    print("⚠️ Slight overfitting")
else:
    print("✓ Good generalization")
```

### Learning Curves
```python
from sklearn.model_selection import learning_curve
import matplotlib.pyplot as plt

train_sizes, train_scores, val_scores = learning_curve(
    LogisticRegression(),
    X, y,
    cv=5,
    train_sizes=np.linspace(0.1, 1.0, 10),
    scoring='f1'
)

plt.plot(train_sizes, np.mean(train_scores, axis=1), label='Train')
plt.plot(train_sizes, np.mean(val_scores, axis=1), label='Validation')
plt.xlabel('Training Set Size')
plt.ylabel('Score')
plt.legend()
plt.show()
```

## Common Evaluation Mistakes

| ❌ Mistake | ✓ Solution |
|-----------|-----------|
| Using test set for hyperparameter tuning | Use validation set or cross-validation |
| Scaling before train-test split | Always fit scaler on training data only |
| Not handling class imbalance | Use stratified split, class weights, or SMOTE |
| Reporting accuracy on imbalanced data | Use F1, precision-recall, ROC-AUC |
| Training on entire dataset | Always use train-test split |
| Not checking for data leakage | Features shouldn't contain target information |
| Ignoring time dependency in time series | Use time series cross-validation |

---

# QUICK REFERENCE CHEAT SHEET

## Model Selection Guide
```
Continuous Target:
├── Linear relationship → Linear Regression
├── Complex pattern, small data → Linear Regression with regularization
└── Non-linear pattern, large data → Neural Network or Ensemble

Categorical Target (2 classes):
├── Linear boundary → Logistic Regression
├── Non-linear boundary → Decision Tree or SVM
├── Large data → Neural Network
└── Need interpretability → Decision Tree

Categorical Target (3+ classes):
├── Linear boundary → Logistic Regression (softmax)
├── Non-linear boundary → Decision Tree, Random Forest
├── Large data, complex patterns → Neural Network
└── Text/NLP → Transformers

Text Classification:
└── Transformers (BERT, DistilBERT)

Sequence Modeling:
└── LSTM, GRU, or Transformers

Time Series:
└── ARIMA, Prophet, or Neural Networks
```

## When to Scale Features
```
Always Scale:                Scaling Not Needed:
├─ Linear Regression        ├─ Decision Tree
├─ Logistic Regression      ├─ Random Forest
├─ Neural Networks          ├─ Gradient Boosting
├─ KNN                       └─ XGBoost
├─ SVM
├─ K-Means
└─ Transformers
```

## Metric Selection by Problem
```
Classification (Balanced):
└─ Accuracy, Precision, Recall, F1

Classification (Imbalanced):
└─ F1, ROC-AUC, Precision-Recall AUC

Binary Classification (Probabilistic):
└─ ROC-AUC, Log Loss

Multi-Class Classification:
└─ Macro F1, Weighted F1, Accuracy

Regression:
├─ Symmetric errors → RMSE, MSE
├─ Asymmetric errors → MAE
└─ Percentage errors → MAPE, RMSPE
```

## Hyperparameter Ranges (Starting Points)

### Linear Models
```
Learning Rate: [0.0001, 0.001, 0.01, 0.1]
Regularization (C): [0.001, 0.01, 0.1, 1, 10]
Penalty: ['l1', 'l2', 'elasticnet']
```

### Decision Tree
```
max_depth: [3, 5, 7, 10, 15, None]
min_samples_split: [2, 5, 10, 20]
min_samples_leaf: [1, 2, 4, 8]
```

### Neural Network
```
Learning Rate: [0.0001, 0.0005, 0.001, 0.005]
Batch Size: [16, 32, 64, 128]
Hidden Units: [32, 64, 128, 256, 512]
Dropout: [0.1, 0.2, 0.3, 0.5]
```

---

## Final Tips

1. **Always visualize your data** - Understand distributions, relationships, outliers
2. **Baseline model first** - Simple model to compare against
3. **Feature importance** - Understand what drives predictions
4. **Error analysis** - Study where model fails
5. **Class imbalance** - Use stratified split, class weights, or resampling
6. **Reproducibility** - Set random_state/seed everywhere
7. **Cross-validation** - Don't rely on single train-test split
8. **Domain knowledge** - ML is not magic, understand the problem
9. **Document everything** - Future you will thank present you
10. **Monitor in production** - Model performance degrades over time

---

**Happy Learning! 🚀**