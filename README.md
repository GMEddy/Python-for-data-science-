# Python for data science

 
 >  Devoir maison

**Sommaire**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Introduction](#introduction)
- [Objectif](#Objectif)
- [Analyse](#Analyse)
  - [Liste](#Liste)
  - [Importation](#Importation)
  - [Algorithme](#Algorithme)
- [Etape](#Etape)
- [Interpretation](#Interpretation)
- [Licence](#licence)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Introduction

[https://archive.ics.uci.edu/ml/machine-learning-databases/magic/magic04.names](https://archive.ics.uci.edu/ml/datasets/MAGIC+Gamma+Telescope) 

## Objectif  

MAGIC telescope dataset

**Le jeu de données comprend 10 entités continues pour 19020 observations et une étiquette
soit 'g' pour un événement gamma ou un 'h' pour un événement hadron**

Ma tâche consiste à évaluer et à interpréter l'erreur de classification
sur une classification de particules à l'aide de l'ensemble de données 
du télescope MAGIC Gamma dans les dépôts UCI.

## Analyse ?

En récupérant toutes les données de la base UCI concernant "Magic Gamma Telescope" et interpreter differente classification. 

d'après le dataset : 

La précision de la classification simple n’a pas de sens pour ces données, car classer un événement d'arrière-plan  
en tant que signal est pire que classer un signal événement en arrière-plan. Pour comparer différents classificateurs, 
une courbe ROC doit être utilisé. Les points pertinents sur cette courbe sont ceux où la probabilité d'accepter un événement de fond comme signal est inférieur à l'un des seuils suivants: 0,01, 0,02, 0,05, 0,1, 0,2 en fonction des besoins qualité de l'échantillon des événements acceptés pour différentes expériences.

### Liste 

1. fLongueur:   axe continu majeur de l'ellipse [mm]
2. fWidth:      axe continu mineur de l'ellipse [mm]
3. fSize:       10 de la somme du contenu de tous les pixels [dans #phot]
4. fConc:       ratio continu de la somme des deux pixels les plus élevés sur fSize [ratio]
5. fConc1:      rapport continu  du pixel le plus élevé sur fSize [ratio]
6. fAsym:       distance continue du pixel le plus élevé au centre, projetée sur le grand axe [mm]
7. fM3Long:     continu 3ème racine du troisième moment le long du grand axe [mm]
8. fM3Trans:    3ème racine continue du troisième moment le long d'un axe mineur [mm]
9. fAlpha:      angle continu de l’axe principal avec le vecteur à l’origine [deg]
10. fDist:      distance continue de l'origine au centre de l'ellipse [mm]
11. **classe:     g, h  gamma (signal), hadron (fond)**

### Importation

```
path ="C:\Users\Black Mamba\Documents\Python Scripts\MagicGammaTelescope.csv"
```

### Algorithme ?
 
 Nous allons avoir besoin d'un algorithme pour mener à bien cette analyse , j'ai choisie RandomForestClassifier car cette algorithme me donnais le meilleur résultat.
 
 [https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html] 


## Etape

Les étapes de l'analyse :

Data-visualisation des données 
Data-préparation 
Modélisation 
Optimisation des hyperparamètres 
Visualisation des performance 


### Interpretation 

Les classes que je souhaite distinguer sont Gammas (g) et Hadronic shower background (h). L'ensemble de données contient 19020 échantillons et est un peu déséquilibré (70% g , 30% h).
Dans cet ensemble de données généré par une simulation de Monte Carlo, le nombre d'événements h est fortement sous-estimé. 
Les auteurs de l'ensemble de données ont déclaré que la prédiction d'un arrière-plan (h) en tant que signal (g) était pire que celle d'un g en h, de sorte qu'un ROC doit être utilisé pour valider le modèle au lieu de la précision du classificateur. J'ai abordé ce problème en divisant mon jeu de données en deux.



## Licence

[Uncopyrighted](http://zenhabits.net/uncopyright/)
 
