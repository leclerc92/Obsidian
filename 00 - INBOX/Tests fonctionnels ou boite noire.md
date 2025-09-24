---
MOC: "[[PROGRAMMATION]]"
tags:
  - prog/test
---
---
***Références :***

---

Les test fonctionnels permettent de tester la conformité du code par rapport à la spécification. 

- Il ne necessite pas de connaitre la structure interne du code 
- Il ne necessite de connaitre l'interface du code

> [!info] limite des tests fonctionnels
> Ils ne permettent pas de tester finement le code, mais juste une spécification particulière 


#### Domaine d'entrée 

Le domaine d'entrée d'un programme contient toutes ses données/valeurs possible d'entrées possible. 

> [!exemple] 
> - Pour un programme qui calcul la racine carrée d'un nombre : 
> -> Le domaine d'entrée contient tous les réels positifs ou nul

Le problème est que même pour un petit programme, son nombre d'entrée peut etre infinis

#### Analyse du domaine d'entée

En fonction du domaine d'entrée, on peut appliquer plusieurs méthodes :
- [[test combinatoire]]
- [[analyse partitionnelle]] 
- test aux limites
- graphe cause-effet
- test probabiliste
- test à partir d'un modèle formel ou d'un spécification (**model-based-testing)