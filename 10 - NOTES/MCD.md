---
MOC: "[[PROGRAMMATION]]"
tags:
  - prog/bd
---
      ---
***Références :***

---
## Définition

Le **MCD** est le *modèle conceptuel de données*.
C'est un diagramme qui permet de donner une representation shématique d'une [[SGBDR|base de donnée relationnelle]]. 
Les MCD font parti de la methode **MERISE**.

## Syntaxe 
Le MCD possède des **entités** et des **associations**
il peut etre appelé parfois **modèle-entité-association**

- *Entité* : Unité élementaire qui se suffit à elle même. Elle possède des **attributs**. Un attribut souligné est sa **clé primaire**

| CLIENT                                                      |
| ----------------------------------------------------------- |
| <u>N°id</u> : int<br>raison social : char<br>adresse : char |
- *Association :* Elle decrit la **relation d'appartenance** entre des entité. Elle possède un nom decrivant la relation (un verbe) et des **attributs portés**
![[Pasted image 20250927113421 1.png]]

- *Cardinalité :* Permet de préciser les **quantité** maximal et minimal qu'une entité a d'une autre entité

> [!important]
> Lorsque les cardinalités sont de la forme :
> - X,n - Y,n (exemple : 0,n - 1,n) avec X et Y des nombres, on parle de CIM **(contrainte d’intégrité multiple)** = **TABLE**
> 
> - X,1 - Y,n (exemple : 1,1 - 0,n) avec X et Y des nombres, on parle de CIF **(contrainte d’intégrité fonctionnelle)** = **CLE ETRANGERE**

![[Pasted image 20250927113757 1.png]]

![[Capture d’écran 2025-09-27 à 11.48.37 1.png]]

> [!tip]
> On n'evitera de creer des relations 1,1 - 1,1, car cela pourrait etre regroupé dans la même table. On appel cela une **relation fantome**

