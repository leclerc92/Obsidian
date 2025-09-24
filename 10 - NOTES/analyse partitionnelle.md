---
tags:
  - prog/test
---


---
***Références :***

---


*Définition :*

Les domaines associées aux parametre d'entrée sont divisés en **région** ou **classe d'équivalence** ou **partition**
Cela correspond à un ensemble de données supposer déclencher le même comportement, et donc le même défaut si il en existe un.

***👍 avantage*** : Il n'y a pas besoin de connaitre l'implementation, seulement **l'espace de donnée d'entrée** pour la spécification.

> [!info ]
> L'objectif est de choisir une valeur dans chacune de ces région. 


#### Conception des partitions 

- *Etape 1* : Determiner les fonctionnalités qui sont testables 
- *Etape 2* : Identifier **les parametres**, **Les domaines d'entrée**, **leurs caracteristiques** 
- *Etape 3* : Concevoir les **Classes d'équivalence** des caracteristiques
- *Etape 4* : Applique un critère de test afin de choisir les combinaison de valeur 

Pour les *Etape 2 et 3* il existe deux méthode : 
- [[Methode syntaxique]] 
- [[Methode comportementale]]

