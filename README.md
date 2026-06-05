# Analyse des sentiments des avis utilisateurs de TaHoma Somfy

## Présentation du projet

Ce projet porte sur l'analyse des sentiments des avis utilisateurs de l'application **TaHoma Somfy** publiés sur l'App Store.

L'objectif est de développer des modèles capables de classifier automatiquement les avis selon leur polarité sentimentale :

- 😊 Positif
- 😐 Neutre
- 😞 Négatif

Plusieurs approches de traitement automatique du langage naturel (NLP) ont été étudiées et comparées, notamment des modèles de Machine Learning, de Deep Learning et des modèles Transformers.

Une application web interactive développée avec Streamlit permet également de réaliser des prédictions de sentiments en temps réel.

---

## Jeu de données

Le dataset est composé de 500 avis utilisateurs collectés depuis l'App Store.

Les principales variables sont :

- Date
- Auteur
- Note
- Version
- Titre
- Commentaire
- Votes

Les sentiments ont été générés à partir des notes utilisateurs selon les règles suivantes :

| Note | Sentiment |
|--------|------------|
| 1 - 2 | Négatif |
| 3 | Neutre |
| 4 - 5 | Positif |

---

## Prétraitement des données

Les principales étapes de prétraitement NLP réalisées sont :

- Conversion des textes en minuscules
- Suppression des emojis
- Suppression des URLs
- Suppression des caractères spéciaux
- Suppression des accents
- Nettoyage des espaces inutiles
- Vectorisation des textes avec TF-IDF

Bibliothèques utilisées :

- Pandas
- SpaCy
- Regex
- Emoji
- Unidecode
- Scikit-Learn

---

## Modèles étudiés

### Machine Learning

- Naive Bayes
- Régression Logistique
- Support Vector Machine (SVM)
- Random Forest
- XGBoost

### Deep Learning

- LSTM
- CNN + LSTM
- BiLSTM

### Transformers

- DistilBERT
- CamemBERT

---

## Résultats

Les modèles ont été évalués à l'aide des métriques suivantes :

- Accuracy
- Precision
- Recall
- F1-score



Cette étude met en évidence l'intérêt des modèles de Deep Learning et des Transformers pour les tâches d'analyse des sentiments en français.

---

## Application de démonstration

Une application web interactive a été développée avec Streamlit afin de permettre la prédiction automatique du sentiment associé à un avis utilisateur.

Fonctionnalités :

- Saisie d'un commentaire utilisateur
- Prédiction instantanée du sentiment
- Affichage du résultat en temps réel

---

## Installation

### 1. Cloner le dépôt

```bash
git clone https://github.com/Nourbenmiled/tahoma-app-store-sentiment-analysis.git
cd tahoma-app-store-sentiment-analysis
```

### 3. Lancer l'application

```bash
streamlit run app.py
```

---

## Structure du projet

```text
PROJET_ANALYSE_DES_SENTIMENTS
│
├── Data/
│
├── Deep Learning/
│   └── LSTM_BiLSTM_CNN.ipynb
│
├── Machine Learning/
│   ├── ML_NaiveBayes.ipynb
│   ├── ML_RandomForest.ipynb
│   ├── ML_Regression_Logistique.ipynb
│   ├── ML_SVM.ipynb
│   └── ML_XGboost.ipynb
│
├── Data_Preprocessing_&_NLP_Pipeline.ipynb
├── CamemBERT.ipynb
├── DistilBERT.ipynb
│
├── app.py
├── bilstm_sentiment_model.h5
├── tokenizer.pkl
├── label_encoder.pkl

```

---

## Technologies utilisées

- Python
- Pandas
- NumPy
- Scikit-Learn
- TensorFlow / Keras
- Hugging Face Transformers
- Streamlit
- Matplotlib
- Seaborn

---

## Modèle déployé

L'application Streamlit utilise le modèle **BiLSTM** entraîné sur les avis utilisateurs de l'application TaHoma Somfy.

Les fichiers utilisés pour l'inférence sont :

- bilstm_sentiment_model.h5
- tokenizer.pkl
- label_encoder.pkl
