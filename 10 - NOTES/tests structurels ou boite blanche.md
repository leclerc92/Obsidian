---
tags:
  - prog/test
MOC: "[[TESTS LOGICIELS]]"
---
---
***Références :***

---






---
***Références :***

---

## 📋 Définition

Les **tests structurels** (ou tests en **boîte blanche**) analysent le **code source** pour créer des cas de test basés sur la **structure interne** du programme.

> **Principe** : Le testeur connaît et utilise la structure du code pour définir ses tests


**Limites de ces tests**
On ne test que ce qui est fait mais pas ce qui aurait du être fait. 

#### **Analyse de flot de contrôle**

- **[[Graphe de flot de controle]]**
    - Représentation visuelle du programme
    - Nœuds = instructions, Arêtes = transitions
    - Base pour toutes les analyses
- **[[Chemins d'exécution]]**
    - Séquences d'instructions possibles
    - Chemins indépendants 
- **[[Expression régulière]]**
    - Notation formelle des chemins
    - Représentation mathématique des parcours
    - Analyse des boucles et répétitions

- **[[Exécution symbolique d'une fonction]]** 
    - Variables symboliques (X, Y, Z...)
    - Contraintes de chemin accumulées
    - Génération automatique de cas de test

#### **Analyse de flot de données**

- **[[Graphe de flot de données]]**
	- Représentation visuelle du programme avec les variables
	- Permet d'identifier les anomalies de flux de données 
		- critère *"toutes les définitions"*
		- critère *"toutes les utilisations"*
		- critère *"tous-les-du-chemins"*
		
		







  







