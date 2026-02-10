# bank-marketing-logistic-regression


## 📖 Description
Ce projet construit un **pipeline de machine learning** pour prédire si un client d’une banque souscrira à un dépôt à terme (term deposit) à partir du dataset Bank Marketing (UCI).

Le modèle utilisé est **Logistic Regression** avec gestion du déséquilibre de classes (`class_weight='balanced'`).

---

## 📊 Dataset
- Source : [UCI Bank Marketing Dataset](https://archive.ics.uci.edu/ml/datasets/Bank+Marketing)
- Taille : 45 211 lignes, 17 colonnes
- Target : `y` (1 = yes, 0 = no)

### Colonnes principales
- `age`, `balance`, `day`, `duration`, `campaign`, `pdays`, `previous` → numériques
- `job`, `marital`, `education`, `default`, `housing`, `loan`, `contact`, `poutcome` → catégorielles

---

## ⚙️ Pipeline de traitement

### 1️⃣ Nettoyage
- Détection de doublons
- Encodage binaire de la cible

### 2️⃣ Préprocessing
- **Numerical features** : `RobustScaler` → `StandardScaler` → `SelectKBest (f_classif)`
- **Categorical features** : `OneHotEncoder` → `SelectKBest (mutual_info_classif)`

### 3️⃣ Modèle
- **Logistic Regression**
- Paramètres : `max_iter=1000`, `class_weight='balanced'`
- Évaluation : Accuracy, Classification report, Confusion matrix

---

## 🚀 Instructions pour exécuter

1. Cloner le repository :
```bash
git clone https://github.com/akramzerd0/bank-marketing-logistic-regression.git
cd bank-marketing-logistic-regression
