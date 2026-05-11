# Projet Dashbord Excel
# Analyse Offres Emploi Data dans le Monde

![1_Salary_Dashboard.png](images/Final_Dashboard.gif)

## Introduction

> Ce projet consiste en la création d'un dashbord interactif sous Microsoft Excel permettant d'analyser les offres d'emploi dans le domaine de la data dans le monde.
> Ce projet peut aider à avoir un apperçu des salaires des metiers de la data à travers le monde. Le tableau de bord fournit les informations sur les salaires médians selon les métiers, les types de contrats les plus proposés, les pays offrant le plus d'opportunités, les plateformes de recrutement les plus utilisé, le nombre total d'offres d'emploi.
> L'Objectif principal de ce projet est de transformer des données brutes en informations visuelles facilles à comprendre afin d'aider à la prise de décision et à l'analyse du marché de l'emploi data dans le monde.

### Objectifs du Projet
Pratiquer l'analyse de données avec Excel, Concevoir un dashbord interactif et lisible, explorer le marché des métiers de la data dans le monde, presenter des indicateurs clés (KPI), developper des compétences en visualisation de données.

### Outils Utilisé
Microsoft Excel (Power Query, Tableaux croisés dynamiques, Graphiques dynamiques, Segments/Slicers, validation des données, fonctions et formules), Github pour le partage du projet.

### Dashboard Final
Le fichier final ![(Data_Science_Salary_Dashbord.xlsx](Data_Science_Salary_Dashbord.xlsx).

### Ensemble de Données

Les données utilisé pour ce projet proviennent des informations du monde reel des metiers de la science de données.
 Les données qui ont servi à l'elaboration de ce projet provienne du tutoriel de Luke Barousse. Ils contiennent des information detaillés sur les different job, a savoir, le nom, le salaires, la localité, etc...

## Structure du Dashbord

### 📉 Graphes

#### 📊 Data Science Job Salaries - Bar Chart

<img src="images/Chart1.png" width="850" height="550" alt="Salary Dashboard Chart1">

- 🛠️ **Fonctionnalités Excel:**Utilisation de la fonctionnalité de graphique à barres (avec des valeurs de salaires formatées) et optimisation de la mise en page pour une meilleure clarté.
- 🎨 **Choix de conception:** Utilisation d’un graphique à barres horizontales pour faciliter la comparaison visuelle des salaires médians.
- 📉 **Organisation de données:** Tri des intitulés de postes par salaire décroissant afin d’améliorer la lisibilité.
- 💡 **Enseignement tirés:** Cela permet d’identifier rapidement les tendances salariales, en montrant que les postes Senior et les postes d’Ingénieurs sont généralement mieux rémunérés que les postes d’Analystes.

#### 🗺️ Country Median Salaries - Map Chart

![1_Salary_Dashboard_Chart2.png](images/Country_Map.gif)

- 🛠️ **Fonctionnalités Excel:** Utilisation de la fonctionnalité de carte géographique d’Excel pour représenter les salaires médians à l’échelle mondiale.
- 🎨 **Choix de conception :** Utilisation d’une carte codée par couleurs afin de différencier visuellement les niveaux de salaires selon les régions.
- 📊 **Représentation des données :** Affichage du salaire médian pour chaque pays disposant de données disponibles.
- 👁️ **Amélioration visuelle :** Optimisation de la lisibilité et de la compréhension immédiate des tendances salariales géographiques.
- 💡 **Enseignements tirés :** Permet de comprendre rapidement les disparités salariales mondiales et de mettre en évidence les régions aux salaires élevés ou faibles.

### 🧮 Formules et Fonctions

#### 💰 Salaire median par metier

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

- 🔍 **Filtrage multicritère :** Vérifie l’intitulé du poste, le pays, le type d’horaire et exclut les salaires vides.
- 📊 **Formule matricielle :** Utilisation de la fonction `MEDIAN()` avec une instruction `IF()` imbriquée pour analyser un tableau de données.
- 🎯 **Analyses personnalisées :** Fournit des informations salariales spécifiques selon le poste, la région et le type d’horaire.
- 🔢 **Objectif de la formule :** Cette formule alimente le tableau ci-dessous en renvoyant le salaire médian en fonction de l’intitulé du poste, du pays et du type spécifiés.

🍽️ Background Table

![1_Salary_Dashboard_Screenshot1.png](images/Screenshot1.png)

📉 Dashboard Implementation

<img src="images/Job_Title.png" width="400" height="500" alt="Salary Dashboard Title">

#### ⏰ Count of Job Schedule Type/ Nombre de types d'horaires de travail

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```



- 🔍 **Génération d’une liste unique :** La formule Excel ci-dessous utilise la fonction FILTER() pour exclure les entrées contenant « and » ou des virgules, ainsi que les valeurs nulles.
- 🔢 **Objectif de la formule :** Cette formule alimente le tableau ci-dessous, qui fournit une liste unique des types d’horaires de travail.
🍽️ Background Table

![1_Salary_Dashboard_Type.png](images/Screenshot2.png)

📉 Dashboard Implementation:

<img src="images/Type.png" width="350" height="500" alt="Salary Dashboard Type">

### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Validation améliorée des données :** L’implémentation de la liste filtrée comme règle de validation des données dans les options `Job Title`, `Country` et `Type` de l’onglet Données garantit:
    - 🎯 que les saisies utilisateur soient limitées à des types d’horaires prédéfinis et validés
    - 🚫 la prévention des entrées incorrectes ou incohérentes
    - 👥 une amélioration globale de l’utilisabilité du tableau de bord

<img src="images/Data_Validation.gif" width="425" height="400" alt="Salary Dashboard Data Validation">

## Résultat et observation
Quelques observations obtenues à partir du dashbord:
   - Les postes de Senior Data Scientist et Machine Learnig Engineer présentent generalement les salaires les plus élévés.
   - Les Contrats Full-Time sont les plus fréquents.
   - Indeed apparaît comme la plateforme de recrutement dominante.
   - Les Etats-Unis représentent une forte concentration des offres analysées

## Compétences Développées
Grâce à ce projet, j'ai renforcé mes compétences en:
   - Nettoyage de données,
   - Analyse de données,
   - Visualisation de données,
   - création de dashbords,
   - Utilisatio avancée d'Excel,
   - Communication des resultats

## Fichier du Projet
📦 Data-Jobs-Dashboard
 ┣ 📊 Dashboard.xlsx
 ┣ 📷 dashboard.png
 ┗ 📄 README.md
