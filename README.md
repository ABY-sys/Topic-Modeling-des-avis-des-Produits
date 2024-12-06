# **Topic Modeling et Analyse des Sentiments des Avis Clients**

## **Description**
Ce projet vise à analyser les avis clients d’un sous-ensemble du dataset Amazon Review Dataset 2023, spécifiquement pour la catégorie **Cell Phones and Accessories**. Il se divise en trois grandes étapes :
1. Prétraitement des données textuelles.
2. Modélisation thématique à l’aide de techniques de clustering.
3. Analyse des sentiments basée sur des modèles de NLP pré-entraînés.

## **Données**
Les données utilisées proviennent du dataset suivant :
- **Source** : [Amazon Review Dataset 2023](https://amazon-reviews-2023.github.io/)
- **Subset utilisé** : `Cell_Phones_and_Accessories`
- Les fichiers importants sont :
  - `meta.jsonl` : Métadonnées des avis.
  - `reviews.jsonl` : Textes des avis clients.

---

## **Étapes du Projet**

### **Étape 1 : Prétraitement des Données**
- Nettoyage des données textuelles en supprimant la ponctuation, les stop words, et les caractères non pertinents.
- Lemmatisation pour réduire les mots à leur forme de base.
- Résultat : Une liste de tokens prête pour l’analyse.

### **Étape 2 : Modélisation Thématique**
- Utilisation de **SentenceTransformers** pour générer des embeddings vectoriels des avis.
- Application de l’algorithme de clustering **KMeans** pour identifier des topics.
- Visualisation des clusters avec **UMAP**.

### **Étape 3 : Analyse des Sentiments**
- Utilisation d’un modèle pré-entraîné de Hugging Face (`nlptown/bert-base-multilingual-uncased-sentiment`) pour prédire les sentiments des avis.
- Évaluation de la qualité des prédictions par la **corrélation de Pearson** (\(0.82\)) entre les notes réelles et les prédictions.

---

## **Résultats Clés**
1. **Clustering Thématique :**
   - 5 clusters identifiés à partir des embeddings vectoriels.
   - Visualisation des clusters montrant des regroupements thématiques clairs.

2. **Analyse des Sentiments :**
   - Score de corrélation de Pearson entre les notes réelles et prédites : \(0.82\).
   - Les prédictions alignées avec les sentiments exprimés dans les avis clients.

---

## **Technologies Utilisées**
- **Python 3.9**
- **Bibliothèques principales** :
  - NLP : SpaCy, Transformers (Hugging Face), SentenceTransformers
  - Machine Learning : scikit-learn, UMAP
  - Visualisation : Matplotlib
- **Modèle de Sentiment** : `nlptown/bert-base-multilingual-uncased-sentiment`

---

## **Structure du Projet**
```
Topic-Modeling-des-avis-des-Produits/
│
├── data/                   # Contient les fichiers JSON et autres données brutes.
├── notebooks/              # Jupyter Notebooks pour chaque étape.
├── results/                # Résultats sauvegardés (images, fichiers JSON).
├── scripts/                # Scripts Python pour le traitement par étapes.
├── README.md               # Documentation principale.
└── requirements.txt        # Liste des dépendances nécessaires.
```

---

## **Installation**
1. Clonez le dépôt :
   ```bash
   git clone https://github.com/ABY-sys/Topic-Modeling-des-avis-des-Produits.git
   cd Topic-Modeling-des-avis-des-Produits
   ```

2. Installez les dépendances :
   ```bash
   pip install -r requirements.txt
   ```

3. Lancez les scripts ou notebooks dans l’ordre :
   - **Étape 1** : `notebooks/01_preprocessing.ipynb`
   - **Étape 2** : `notebooks/02_clustering.ipynb`
   - **Étape 3** : `notebooks/03_sentiment_analysis.ipynb`

---

## **Résultats**
- Exemple de clustering des avis clients :
  ![Clustering Visualization](results/clustering_visualization.png)

- Distribution des notes réelles vs prédites :
  ![Sentiment Analysis](results/sentiment_analysis_comparison.png)
