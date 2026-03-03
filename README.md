
#  Credit Card Fraud Detection

Projet de Machine Learning pour détecter les transactions frauduleuses à partir d'un dataset réel de transactions par carte bancaire.

---

##  Description

Avec l'essor des paiements en ligne, la fraude bancaire est devenue un problème majeur. Ce projet explore différentes approches de classification pour identifier automatiquement les transactions suspectes.

L'objectif est de comparer plusieurs modèles de ML et d'évaluer leur efficacité dans un contexte de **dataset fortement déséquilibré**.

---

##  Dataset

Le dataset utilisé est le [Credit Card Fraud Detection dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) disponible sur Kaggle.

- **284 807 transactions** effectuées par des cartes bancaires européennes
- **31 variables** au total

| Variable | Description |
|----------|-------------|
| `V1` à `V28` | Variables anonymisées (transformation PCA) |
| `Time` | Temps écoulé entre deux transactions (en secondes) |
| `Amount` | Montant de la transaction |
| `Class` | Variable cible : `0` = normale, `1` = frauduleuse |

>  Le dataset est très déséquilibré : les fraudes représentent seulement ~0.17% des transactions.

---

##  Exploration des données

Avant d'entraîner les modèles, une analyse exploratoire a été réalisée :

- Distribution des classes (visualisation du déséquilibre)
- Distribution des montants selon le type de transaction
- Statistiques descriptives des variables

---

##  Préparation des données

1. Séparation des features `X` et de la cible `y`
2. Split train/test : **80% / 20%**
3. Normalisation avec `StandardScaler` (pour la régression logistique)

---

##  Modèles utilisés

### 1. Logistic Regression
Modèle simple et efficace comme baseline. Utilisation de `class_weight="balanced"` pour compenser le déséquilibre des classes.

### 2. Logistic Regression + Under-Sampling
Équilibrage du dataset en sélectionnant un nombre égal de transactions normales et frauduleuses avant l'entraînement.

### 3. Decision Tree
Modèle permettant de capturer des relations non linéaires entre les variables.

---

##  Évaluation

Les modèles sont évalués avec les métriques suivantes :

- **Accuracy**
- **Confusion Matrix**
- **Classification Report** (Precision, Recall, F1-score)
- **ROC-AUC**
- **PR-AUC** ← particulièrement important pour les datasets déséquilibrés

---

## Structure du projet

```
credit-card-fraud-detection/
│
├── credit_card_fraud_detection.ipynb
├── README.md
└── requirements.txt
```

---

##  Lancer le projet

```bash
# Cloner le repo
git clone https://github.com/ton-username/credit-card-fraud-detection.git
cd credit-card-fraud-detection

# Installer les dépendances
pip install -r requirements.txt

# Lancer le notebook
jupyter notebook notebook/fraud_detection.ipynb
```

---

##  Dépendances

```
pandas
numpy
scikit-learn
matplotlib
jupyter
```

---

##  Conclusion

Ce projet montre comment le Machine Learning peut être appliqué à un problème réel de détection de fraude. Les principales difficultés rencontrées sont liées au **fort déséquilibre des données**, ce qui nous a amené à tester différentes stratégies (class weights, under-sampling).

Ces approches constituent une bonne base pour aller vers des méthodes plus avancées comme Random Forest, XGBoost ou des techniques de sur-échantillonnage (SMOTE).

---

##  Auteur

Projet réalisé par Faiza -L3 info-
