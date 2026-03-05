## Analyse exploratoire et modélisation prédictive – Dataset Titanic

Cette analyse porte sur le dataset de la compétition Titanic: Machine Learning from Disaster, disponible sur la plateforme Kaggle. L’objectif principal est d’identifier les facteurs influençant la probabilité de survie des passagers lors du naufrage du Titanic et de développer un modèle prédictif capable d’estimer cette probabilité pour de nouveaux passagers.

### 1. Compréhension du dataset

Le dataset contient des informations démographiques et socio-économiques sur les passagers, telles que l’âge, le sexe, la classe du billet ou encore le port d’embarquement. La variable cible est **Survived**, indiquant si le passager a survécu (1) ou non (0). Les variables principales incluent notamment `Pclass`, `Sex`, `Age`, `SibSp`, `Parch`, `Fare`, `Cabin` et `Embarked`. 

Les données sont fournies sous deux fichiers principaux :

* **train.csv** : contient les observations avec la variable cible (survie).
* **test.csv** : contient les passagers pour lesquels la survie doit être prédite.

* ***Concaténer le fichier Train et Test

<img width="576" height="113" alt="image" src="https://github.com/user-attachments/assets/17d21d2b-c899-425e-9f0b-f111d59915cc" />




### 2. Nettoyage et préparation des données

Une phase de **data preprocessing** a été réalisée afin d’assurer la qualité et l’exploitabilité des données :

* Traitement des **valeurs manquantes**, notamment dans la variable `Age`.
* Suppression ou transformation de certaines variables peu informatives comme `Ticket` ou `Name`.
* Encodage des variables catégorielles (`Sex`, `Embarked`) pour permettre leur utilisation dans les modèles.
* Création de nouvelles variables dérivées (ex : taille de la famille à partir de `SibSp` et `Parch`). ([GitHub][3])

### 3. Analyse exploratoire des données (EDA)

L’analyse exploratoire a permis d’identifier plusieurs tendances importantes :

* Les **femmes avaient une probabilité de survie plus élevée que les hommes**.
* Les passagers de **première classe avaient un taux de survie supérieur** à ceux des classes inférieures.
* Les **enfants et les passagers plus jeunes** avaient globalement de meilleures chances de survie. ([cphaigh.github.io][4])

Ces observations suggèrent que des facteurs démographiques et socio-économiques ont joué un rôle déterminant dans les chances de survie.

### 4. Modélisation prédictive

Le problème est formulé comme un **problème de classification binaire**, visant à prédire la variable `Survived`. Plusieurs algorithmes peuvent être appliqués, notamment :

* Régression logistique
* Decision Tree
* Random Forest
* Naive Bayes
* K-Nearest Neighbors

Ces modèles sont évalués à l’aide de métriques telles que **l’accuracy** ou la validation croisée afin d’estimer leur performance sur des données inconnues. ([Medium][5])

### 5. Conclusion

Cette analyse met en évidence l’importance de la **qualité des données, de l’analyse exploratoire et du feature engineering** dans la construction de modèles prédictifs performants. Le dataset Titanic constitue un cas d’étude classique permettant d’illustrer le processus complet d’un projet de data science, depuis la compréhension des données jusqu’à la création d’un modèle de classification.

