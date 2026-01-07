# 🎬 Système de Recommandation de Films - MovieLens

![Python](https://img.shields.io/badge/Python-3.13-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.6-orange)
![Pandas](https://img.shields.io/badge/Pandas-2.3-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

> Projet académique de création d'un système de recommandation de films basé sur le **filtrage collaboratif** utilisant l'algorithme **K-Nearest Neighbors (KNN)**.

## 📋 Table des matières
- [À propos](#-à-propos)
- [Objectifs](#-objectifs)
- [Technologies](#-technologies)
- [Dataset](#-dataset)
- [Installation](#-installation)
- [Utilisation](#-utilisation)
- [Résultats](#-résultats)
- [Structure du projet](#-structure-du-projet)
- [Améliorations futures](#-améliorations-futures)
- [Auteur](#-auteur)

---

## 🎯 À propos

Ce projet implémente un **système de recommandation de films** utilisant la technique de **filtrage collaboratif** et l'algorithme **K-Nearest Neighbors (KNN)**. Le système analyse les préférences des utilisateurs pour recommander des films similaires basés sur les notations d'utilisateurs ayant des goûts similaires.

### Principe de fonctionnement

1. **Analyse des données** : Exploration du dataset MovieLens (100 000 notations)
2. **Nettoyage** : Filtrage des films et utilisateurs peu actifs
3. **Modélisation** : Création d'une matrice utilisateurs-films
4. **Recommandation** : Utilisation de KNN avec similarité cosine pour trouver des films similaires

---

## 🎓 Objectifs

- ✅ Comprendre les systèmes de recommandation
- ✅ Maîtriser le filtrage collaboratif
- ✅ Implémenter l'algorithme KNN pour la recommandation
- ✅ Manipuler et visualiser des données avec Pandas et Matplotlib
- ✅ Créer un projet complet pour portfolio GitHub

---

## 🛠️ Technologies

| Technologie | Version | Utilisation |
|------------|---------|-------------|
| **Python** | 3.13.5 | Langage principal |
| **Pandas** | 2.3.3 | Manipulation de données |
| **NumPy** | 2.4.0 | Calculs matriciels |
| **scikit-learn** | 1.6+ | Algorithme KNN |
| **Matplotlib** | 3.10.8 | Visualisations |
| **Seaborn** | 0.13.2 | Visualisations avancées |
| **Jupyter Notebook** | - | Développement interactif |

---

## 📊 Dataset

**MovieLens 100K Dataset**
- 📦 **100 000 notations** de films
- 👥 **943 utilisateurs** uniques
- 🎬 **1 682 films** au catalogue
- ⭐ Notes de **1 à 5 étoiles**
- 🎭 **19 genres** de films

### Fichiers utilisés
- `ratings.csv` : Notations des utilisateurs (user_id, movie_id, rating, timestamp)
- `movies.csv` : Informations sur les films (movie_id, title, genres)

---

## 📥 Installation

### Prérequis
- Python 3.13+
- pip

### Étapes d'installation

1. **Cloner le repository**
```bash
git clone https://github.com/votre-username/Recommendation_Produit.git
cd Recommendation_Produit
```

2. **Créer un environnement virtuel**
```bash
python -m venv .venv
```

3. **Activer l'environnement virtuel**
- Windows :
```bash
.venv\Scripts\activate
```
- Linux/Mac :
```bash
source .venv/bin/activate
```

4. **Installer les dépendances**
```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

5. **Lancer Jupyter Notebook**
```bash
jupyter notebook
```

6. **Ouvrir le fichier**
```
jupiter/01_exploration.ipynb
```

---

## 🚀 Utilisation

### Exemple 1 : Rechercher des films
```python
rechercher_films("Star Wars")
```
**Sortie :**
```
🔍 Films trouvés contenant 'Star Wars' :
   • Star Wars (1977)
   • Empire Strikes Back, The (1980)
   • Return of the Jedi (1983)
```

### Exemple 2 : Obtenir des recommandations
```python
recommander_films("Toy Story", n_recommendations=5)
```
**Sortie :**
```
🎬 Film trouvé : Toy Story (1995)
🔍 Recherche de films similaires...

🎯 Recommandations :

1. Aladdin (1992)
   📊 Score de similarité : 94.32%

2. Lion King, The (1994)
   📊 Score de similarité : 92.15%

3. Beauty and the Beast (1991)
   📊 Score de similarité : 89.76%
   
...
```

---

## 📈 Résultats

### Statistiques du dataset après nettoyage
- 🎬 **603 films** conservés (minimum 50 notations)
- 👥 **728 utilisateurs** actifs (minimum 20 notations)
- 📊 **Densité de la matrice** : ~10% (sparse matrix)
- ⭐ **Note moyenne** : 3.53 / 5

### Performance du modèle
- **Algorithme** : K-Nearest Neighbors (k=10)
- **Métrique de similarité** : Cosine Similarity
- **Temps d'entraînement** : < 1 seconde
- **Temps de prédiction** : < 0.1 seconde par film

### Visualisations incluses
- Distribution des notes par utilisateur
- Top 10 des films les plus notés
- Distribution des genres de films
- Heatmap de la matrice utilisateurs-films
- Statistiques d'activité des utilisateurs

---

## 📂 Structure du projet

```
Recommendation_Produit/
│
├── data/
│   ├── ratings.csv          # Notations des utilisateurs
│   └── movies.csv            # Informations sur les films
│
├── jupiter/
│   └── 01_exploration.ipynb  # Notebook principal
│
├── .venv/                    # Environnement virtuel (non versionné)
│
├── README.md                 # Documentation du projet
└── .gitignore                # Fichiers à ignorer
```

---

## 🔮 Améliorations futures

### Court terme
- [ ] Ajouter une interface utilisateur (Streamlit)
- [ ] Exporter le modèle entraîné (pickle)
- [ ] Créer des tests unitaires

### Moyen terme
- [ ] Implémenter d'autres algorithmes (SVD, ALS)
- [ ] Ajouter le filtrage par contenu (genres, acteurs)
- [ ] Système hybride (collaboratif + contenu)

### Long terme
- [ ] Déploiement web (Flask/FastAPI)
- [ ] Utilisation de Deep Learning (Neural Collaborative Filtering)
- [ ] Recommandations en temps réel

---

## 📝 Méthodologie

### Étape 1 : Exploration des données
- Chargement et analyse des datasets
- Statistiques descriptives
- Visualisations (distributions, top films, genres)

### Étape 2 : Préparation des données
- Filtrage des films peu notés (< 50 notations)
- Filtrage des utilisateurs peu actifs (< 20 notations)
- Création de la matrice utilisateurs-films (sparse matrix)

### Étape 3 : Modélisation
- Configuration du modèle KNN (k=10, metric='cosine')
- Entraînement sur la matrice transposée
- Fonction de recommandation avec scores de similarité

---

## 🎓 Concepts clés appliqués

### Filtrage collaboratif
Technique basée sur l'idée que les utilisateurs ayant des goûts similaires dans le passé auront des goûts similaires dans le futur.

### K-Nearest Neighbors (KNN)
Algorithme qui trouve les k éléments les plus proches d'un élément donné selon une métrique de distance.

### Similarité cosine
Mesure l'angle entre deux vecteurs pour déterminer leur similarité (0 = différent, 1 = identique).

### Matrice sparse
Matrice contenant principalement des zéros, optimisée pour économiser la mémoire.

---

## 🤝 Contributions

Les contributions sont les bienvenues ! N'hésitez pas à :
- Ouvrir une issue pour signaler un bug
- Proposer des améliorations
- Soumettre une pull request

---

## 📄 Licence

Ce projet est développé dans un cadre académique pour apprentissage et portfolio.

---

## 👤 Auteur

DIALLO FATOUMATA DIALLO
- 🎓 Étudiante en L3 a EFREI PARIS
- 💼 [LinkedIn] www.linkedin.com/in/fatoumata-diaraye-diallo-3a2258390
- 🐙 [GitHub](https://github.com/votre-username)

---

## 🙏 Remerciements

- **MovieLens** pour la mise à disposition du dataset
- **GroupLens Research** pour leurs travaux sur les systèmes de recommandation
- La communauté **scikit-learn** pour l'excellent framework de Machine Learning

---

<p align="center">
  ⭐ Si ce projet vous a été utile, n'hésitez pas à lui donner une étoile ! ⭐
</p>

<p align="center">
  Développé avec ❤️ pour l'apprentissage du Machine Learning
</p>
