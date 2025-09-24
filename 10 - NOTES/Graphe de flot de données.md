---
tags:
  - prog/test
---


---
***Références :***

---

Ce graphe est similaire au [[Graphe de flot de controle]] mais ajoute des données sur les variables afin de pourvoir verifier certains critères : 
- critère *"toutes les définitions"*
- critère *"toutes les utilisations"*
- critère *"tous-les-du-chemins"* 

## Données ajoutée dans le graphe

Les données ajoutées concernent principalement la délaration et l'utilisation des variables de la fonction : 
- Si une variable voit sa ==valeur changer== --> on note d<sub>nomVariable</sub>
- Si une variable est ==utilisée== --> on note u<sub>nomDeVariable</sub>

> [!important]
> ***Les variables doivent etre écrites exactement dans l'ordre correspondant au programme. 
> Cela permet d'identifier si une variable est utilisée avant d'être déclarée au alerte***

## Représentation du graphe
![[Pasted image 20250918154411.png]]
## Définition des critères

**Critère toutes les définitions**
- Chaque définition de variable doit être exercée au moins une fois par le cas test 

**Critère toutes les utilisations**
- Pour chaque définition d'une variable, tous les chemins qui mènent vers toutes les utilisations possibles de cette variable doivent être testés.

**Critère tous-les-du-chemins**
- Tous les chemins possibles entre chaque définition et chaque utilisation de cette définition doivent être couverts par les tests.
	- Différence avec "toutes les utilisations" :
		- **au moins un** chemin pour chaque paire définition-utilisation dans toutes les utilisations 
		- **tous** les chemins possibles pour chaque paire définition-utilisation dans tous-les-du-chemins
