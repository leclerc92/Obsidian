---
tags:
  - prog/test
---


---
***Références :***

---

## 📋 Définition

Un **graphe de flot de contrôle** (CFG - Control Flow Graph) est une **représentation graphique** qui montre tous les chemins possibles qu'un programme peut suivre lors de son exécution.

> **Principe** : Chaque instruction = nœud, chaque transition = arête

**🎯 Objectif :** Visualiser la structure du programme pour identifier les chemins de test


**Exemple :**

![[code.png]]  

On peux alors dessiner le graphe correspondant à ce programme comme ceci : 

![[graphe.png]]

> Chaque noeud correspond alors à une ligne du programme ou on s'arrete (condition, boucle,  execution de code)
>  --> Des noeuds peuvent synthétiser plusieurs ligne (noeud 2 = ligne 1 et 2)


on peut alors trouver les [[Chemins d'exécution]] ou traduire ce graphe en [[Expression régulière]]

>Expression régulière de ce graphe :
> 	0.2.3(4(6+&).9.3)*.11.END

> *Chemins d'exécution pour satisfaire tous les arcs :* 
> 
> Ch1 : 0.2.3.4.6.9.3.11.END + 
> Ch2 : 0.2.3.4.9.3.11.END
> Ou 
> Ch3 : 0.2.3.4.6.9.3.4.9.3.11.END