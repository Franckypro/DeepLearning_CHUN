# DeepLearning_CHUN

# Prédiction du Churn des Clients

Ce projet utilise un modèle de Machine Learning pour prédire le churn des clients d'une entreprise, en utilisant un ensemble de données sur les clients (Churn_Modelling.csv). Le modèle prédit si un client quittera ou non l'entreprise en fonction de différentes caractéristiques comme l'âge, le sexe, la géographie, le score de crédit, etc.

## Description du Code

1. **Chargement et Préparation des Données** :
   - Le fichier CSV `Churn_Modelling.csv` est chargé dans un DataFrame pandas.
   - Les colonnes inutiles (`RowNumber`, `CustomerId`, `Surname`) sont supprimées.
   - La colonne `Gender` est encodée en valeurs numériques à l'aide de `LabelEncoder`.

2. **Exploration des Données** :
   - La distribution des classes de la variable cible `Exited` (qui indique si un client a quitté l'entreprise) est affichée, montrant un déséquilibre avec plus de clients restant que de clients quittant.

3. **Séparation des Données** :
   - Les données sont séparées en caractéristiques (`X`) et variable cible (`y`).
   - L'ensemble des données est divisé en ensembles d'entraînement (75%) et de test (25%) à l'aide de `train_test_split`.

4. **Encodage des Catégories** :
   - La colonne `Geography` est encodée à l'aide de `TargetEncoder`, ce qui permet de transformer les variables catégorielles en valeurs numériques en fonction de la variable cible.

5. **Normalisation des Données** :
   - Les données d'entraînement et de test sont normalisées à l'aide de `StandardScaler`.

6. **Modélisation avec un Réseau de Neurones** :
   - Un modèle de réseau de neurones est construit en utilisant Keras. Le modèle est compilé avec l'optimiseur `adam` et la fonction de perte `binary_crossentropy`.
   - Le modèle est entraîné pendant 20 époques avec un lot de taille 16, en utilisant 20% des données pour la validation.

7. **Visualisation des Résultats de l'Entraînement** :
   - Les courbes de perte d'entraînement et de validation sont tracées au fil des époques.

8. **Prédictions et Évaluation du Modèle** :
   - Les prédictions sont effectuées sur l'ensemble de test, et les résultats sont binarisés (valeurs supérieures à 0.5 sont considérées comme positives).
   - Une matrice de confusion est générée pour évaluer les performances du modèle, et un rapport de classification est affiché pour analyser la précision, le rappel, et le score F1 du modèle.

## Dépendances

- `pandas`
- `numpy`
- `matplotlib`
- `sklearn`
- `keras`
- `seaborn`
- `category_encoders`

Vous pouvez installer ces dépendances avec la commande suivante : 

```bash
pip install pandas numpy matplotlib scikit-learn keras seaborn category_encoders

Résultats
Le modèle prédit si un client quittera l'entreprise en fonction des caractéristiques des données. Le rapport de classification montre que le modèle a une précision globale de 84% :

Précision : 0.85 pour les clients qui ne quittent pas, et 0.77 pour ceux qui quittent.

Rappel : 0.98 pour les clients qui ne quittent pas, et 0.31 pour ceux qui quittent.

F1-score : 0.91 pour les clients qui ne quittent pas, et 0.44 pour ceux qui quittent.

Conclusion
Le modèle permet de prédire efficacement si un client quittera l'entreprise, bien que l'équilibre des classes soit un facteur limitant pour la prédiction des clients qui quittent. Des améliorations pourraient inclure l'utilisation d'autres techniques pour traiter le déséquilibre des classes, comme la sur-échantillonnage ou l'ajustement du seuil de classification.

Ce fichier `README.md` fournit une vue d'ensemble du code, de ses objectifs, des étapes suivies et des résultats obtenus.
