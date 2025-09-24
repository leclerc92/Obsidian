---
tags:
  - prog/test
---

---
***Références :***

---

## 📋 Définition

L'**exécution symbolique** est une technique d'analyse qui exécute un programme avec des **variables symboliques** (X, Y, Z...) plutôt que des valeurs concrètes.

> **Objectif** : Explorer tous les chemins d'exécution possibles pour générer des cas de test

## 🎯 Méthode pas à pas

### 1. **Identifier les noeud**

- Chaque `if`, `while`, `for` crée un noeud
- Noter les conditions de noeud

### 2. **Créer le tableau**

```
Colonnes essentielles :
- Chemin/Étape
- Variables symboliques  
- Contraintes accumulées
- Sortie symbolique
```

## 📊 Tableau d'exécution symbolique

|Étape|Instruction|Variables|Contraintes de chemin|Condition|Sortie|
|---|---|---|---|---|---|
|1|`if x > 0`|x, y|-|x > 0|-|
|2a|`if y < 10`|x, y|{x > 0}|y < 10|-|
|3a|`return x+y`|x, y|{x > 0, y < 10}|-|x + y|
|2b|`else`|x, y|{x > 0}|y ≥ 10|-|
|3b|`return x-y`|x, y|{x > 0, y ≥ 10}|-|x - y|
|2c|`else`|x, y|{x ≤ 0}|-|-|
|3c|`return 0`|x, y|{x ≤ 0}|-|0|
