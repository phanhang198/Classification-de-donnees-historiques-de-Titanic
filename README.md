## Analyse exploratoire et modélisation prédictive – Dataset Titanic

Cette analyse porte sur le dataset de la compétition Titanic: Machine Learning from Disaster, disponible sur la plateforme Kaggle. L’objectif principal est d’identifier les facteurs influençant la probabilité de survie des passagers lors du naufrage du Titanic et de développer un modèle prédictif capable d’estimer cette probabilité pour de nouveaux passagers.

### 1. Compréhension du dataset

Le dataset contient des informations démographiques et socio-économiques sur les passagers, telles que l’âge, le sexe, la classe du billet ou encore le port d’embarquement. La variable cible est **Survived**, indiquant si le passager a survécu (1) ou non (0). Les variables principales incluent notamment `Pclass`, `Sex`, `Age`, `SibSp`, `Parch`, `Fare`, `Cabin` et `Embarked`. 

Les données sont fournies sous deux fichiers principaux :

* **train.csv** : contient les observations avec la variable cible (survie).
* **test.csv** : contient les passagers pour lesquels la survie doit être prédite.

* ***Concaténer le fichier Train et Test*** 

<img width="576" height="113" alt="image" src="https://github.com/user-attachments/assets/17d21d2b-c899-425e-9f0b-f111d59915cc" />

* ***Renommer les colonnes***
* <img width="1232" height="20" alt="image" src="https://github.com/user-attachments/assets/b4fefbcd-ef58-494b-944b-b24b76a45571" />

* ***Tableau de corélation des colonnes dont les valeurs sont numériques***
<img width="439" height="344" alt="image" src="https://github.com/user-attachments/assets/cc5fbfd1-5d50-4cfd-b0ff-54fa3399fdf1" />


### 2. Nettoyage et préparation des données
Avant le nettoyage, on va faire une copy de dataset pour travailler avec, en gardant le dataset original.

<img width="186" height="31" alt="image" src="https://github.com/user-attachments/assets/1bd07b7c-b71d-4b3b-a5aa-fab0a0a2ea43" />

Une phase de **data preprocessing** a été réalisée afin d’assurer la qualité et l’exploitabilité des données :

* Traitement des **valeurs manquantes**
  
<img width="744" height="118" alt="image" src="https://github.com/user-attachments/assets/f4684f92-d204-4ebb-9d56-11f6ec6797db" />

La plupart des données manquantes se concentrent au colonne "Cabines" qui n'est pâs très important.
On va remplacer les données manquantes, par le valeur médian du colonne comme suivant:

<img width="533" height="148" alt="image" src="https://github.com/user-attachments/assets/713f25b9-8d62-4c6c-b3d2-8f49c834e095" />


### 3. Analyse exploratoire des données (EDA)

L’analyse exploratoire a permis d’identifier plusieurs tendances importantes :

* Les **femmes avaient une probabilité de survie plus élevée que les hommes**.

<img width="1186" height="176" alt="image" src="https://github.com/user-attachments/assets/5eb60512-3a92-4242-8bdd-9ae83f44b8b8" />

* Anamyse en fonction d'âge*
* 
<img width="400" height="128" alt="image" src="https://github.com/user-attachments/assets/a841f62f-0477-42bb-84af-1f8fadddce66" /><br>


<img width="399" height="313" alt="image" src="https://github.com/user-attachments/assets/39ed225e-9246-4c65-85f8-d4b89d00c297" /><br>


* Les passagers de **première classe avaient un taux de survie supérieur** à ceux des classes inférieures.

<img width="1104" height="198" alt="image" src="https://github.com/user-attachments/assets/993f7827-1fcd-4a63-b89c-528d588125a1" />

<img width="386" height="279" alt="image" src="https://github.com/user-attachments/assets/09f6302a-11b8-4fcd-9329-5faa7410bdfc" />

Vu que les hommes ne sont pas les personnes priviligiés, on ca faire une analyse plus profonde.

* Anamyse de probabilité de survie des hommes en fonction de classe*

``` python

Homme_aBord = dt_copy[dt_copy['Sex']== 'male']
Homme_aBord.head()
sns.barplot(x="Classe", y='Survived', data=Homme_surBord[:891].groupby('Classe').mean()['Survived'].reset_index(), palette="Set1").set_title('Moyenne de survie des Hommes en fonction de classe')
plt.savefig("Moyenne de survie Classe_Homme.png")

```
<img width="439" height="307" alt="image" src="https://github.com/user-attachments/assets/42a69407-b1d1-4364-8c0b-f6596c1d30ea" />

Ces observations suggèrent que des facteurs démographiques et socio-économiques ont joué un rôle déterminant dans les chances de survie.


### 4. Conclusion

Cette analyse met en évidence l’importance de la **qualité des données, de l’analyse exploratoire et du feature engineering** dans la construction de modèles prédictifs performants. Le dataset Titanic constitue un cas d’étude classique permettant d’illustrer le processus complet d’un projet de data science, depuis la compréhension des données jusqu’à la création d’un modèle de classification.

