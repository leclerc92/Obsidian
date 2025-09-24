---
tags:
  - prog/test
---


---
***Références :***

---

Un **chemin d'exécution** est une séquence d'instructions qui peuvent être exécutées depuis le début d'un programme (ou d'une fonction) jusqu'à sa fin. Dans le contexte des tests en boîte blanche, l'analyse des chemins d'exécution permet de s'assurer qu'un maximum de code est testé.

###### ***Critères de couverture***

- *Tous les arcs*
	- Chaque arête du graphe doit être parcourue au moins une fois
	- **Faisable** : Ensemble fini d'arêtes
	
- *Tous les chemins*
	- Exécuter tous les chemins possibles
	- **Problème avec boucles** : Nombre potentiellement infini
	- **Généralement impossible** en pratique



> [!info] notion de N-chemins (pour les boucles)
> - **0-chemin** : Aucune itération de boucle
> - **1-chemin** : Une itération de boucle
> - **2-chemin** : Deux itérations de boucle
> - **k-chemin** : k itérations de boucle

> [!tip]
> L'ensembles de chemins possibles d'un programme sont donnés par leurs [[Expression régulière]]