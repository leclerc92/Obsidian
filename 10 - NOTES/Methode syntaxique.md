---
tags:
  - prog/test
---


---
***Références :***

---

### méthode syntaxique :

**✅ Étape 1 :** Identifier les caractéristiques syntaxiques
**✅ Étape 2 :** Créer les classes d'équivalence

### Pourquoi "syntaxique" ?

✅ On regarde la **structure** 
✅ On ignore la **logique métier** 
✅ On se base sur les **propriétés** de base


#### Exemple concret  

*Fonction à tester :* `triang(Side1, Side2, Side3)`
- Entrée : 3 entiers (longueurs des côtés)
- Sortie : Type de triangle (Scalene, Isosceles, Equilateral, Invalid)

**Étape 1 : identifier les caracteristiques syntaxiques**

***Paramètres :***
- *Side1, Side2, Side3* (longueurs des côtés)

***Domaine de données :***
- *Type : Valeurs entières

***Caracteristique :***
- *"Relation avec zéro"* --> Car c'est la frontière critique pour les nombres (positif/négatif)

**Étape 2 : Determiner les classes d'équivalence

*Version basique (3 classes)*

| Classe       | Description | Exemples    |
| ------------ | ----------- | ----------- |
| **Positive** | > 0         | 5, 10, 100  |
| **Zéro**     | = 0         | 0           |
| **Négative** | < 0         | -1, -5, -10 |
>[!info] 
> **Nombre de tests :** 3 × 3 × 3 = **27 tests**

*Version raffinée (4 classes)*

| Classe                  | Description | Exemples | Pourquoi cette frontière ?          |
| ----------------------- | ----------- | -------- | ----------------------------------- |
| **b₁ - Greater than 1** | > 1         | 2, 5, 10 | Valeurs "normales"                  |
| **b₂ - Equal to 1**     | = 1         | 1        | Plus petite valeur positive entière |
| **b₃ - Equal to 0**     | = 0         | 0        | Frontière zéro                      |
| **b₄ - Negative**       | < 0         | -1, -5   | Valeurs impossibles                 |
>[!info] 
> **Nombre de tests :** 4 × 4 × 4 = **64 tests**


On a donc le tableau des caracteristiques complet : 

|Caractéristique|b₁ (>1)|b₂ (=1)|b₃ (=0)|b₄ (<0)|
|---|---|---|---|---|
|**q1** = "Relation of Side1 to 0"|Side1 > 1|Side1 = 1|Side1 = 0|Side1 < 0|
|**q2** = "Relation of Side2 to 0"|Side2 > 1|Side2 = 1|Side2 = 0|Side2 < 0|
|**q3** = "Relation of Side3 to 0"|Side3 > 1|Side3 = 1|Side3 = 0|Side3 < 0|

Le tableau des classes d'équivalence est alors : 

| Classe      | Valeur choisie | Justification                       |
| ----------- | -------------- | ----------------------------------- |
| **b₁ (>1)** | **2**          | Valeur de frontière (juste après 1) |
| **b₂ (=1)** | **1**          | Valeur frontière exacte             |
| **b₃ (=0)** | **0**          | Valeur frontière exacte             |
| **b₄ (<0)** | **-1**         | Valeur de frontière (juste avant 0) |
2 et -1 sont les **valeurs de frontières**

--- 
## 🔄 Différence d'approche

### Syntaxique :

- ✅ "Side1 > 0 ?" → Structure des données
- ✅ Frontières numériques (0, 1, >1, <0)
### Comportementale (maintenant) :

- ✅ "Forme un triangle scalène ?" → Logique métier
- ✅ Classifications géométriques et règles de gestion