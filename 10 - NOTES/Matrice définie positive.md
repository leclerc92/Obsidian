---
tags:
  - maths/algebre
---


---
***Références :***

---

## Définition

Une [[matrice]] carrée **A** de taille n×n est dite **définie positive** si pour tout vecteur **x** ∈ ℝⁿ non nul :

```
x^T A x > 0
```

### Notation

- On note souvent **A ≻ 0** pour indiquer qu'une matrice A est définie positive
- **A ⪰ 0** signifie que A est semi-définie positive (x^T A x ≥ 0)

## Propriétés essentielles

### 1. Symétrie nécessaire

- Une matrice définie positive doit être **symétrique** : $$A = A^T$$
- Si A n'est pas symétrique, on considère souvent $$(A + A^T)/2$$

### 2. Inversibilité

- Toute matrice définie positive est **inversible**
- Son [[determinant|déterminant]] est **strictement positif**

### 3. Valeurs propres

- **Toutes les [[valeurs propres]] sont strictement positives**
- C'est équivalent à la définition par la [[forme quadratique]]

## Critères de reconnaissance

### Critère 1 : Valeurs propres

A est définie positive ⟺ toutes ses valeurs propres λᵢ > 0

### Critère 2 : Mineurs principaux (critère de Sylvester)

A est définie positive ⟺ tous ses **mineurs principaux** sont positifs

Pour une matrice 3×3 :

```
det(a₁₁) > 0
det([a₁₁ a₁₂]) > 0
    [a₂₁ a₂₂]
det(A) > 0
```

### Critère 3 : Décomposition de Cholesky

A est définie positive ⟺ elle admet une **décomposition de Cholesky** :

$$A = L L^T$$

où L est une matrice triangulaire inférieure à coefficients diagonaux positifs.

## Exemples

### Exemple 1 : Matrice 2×2

```
A = [4  1]
    [1  3]
```

**Vérification :**

- Mineurs : det(4) = 4 > 0, det(A) = 12-1 = 11 > 0 ✓
- Valeurs propres : λ₁ ≈ 4.56, λ₂ ≈ 2.44 (toutes > 0) ✓

### Exemple 2 : Matrice identité

```
I = [1  0]
    [0  1]
```

Toujours définie positive (valeurs propres = 1)

### Contre-exemple

```
B = [1  2]
    [2  1]
```

det(B) = 1-4 = -3 < 0, donc B n'est pas définie positive.

## Applications importantes

### 1. Optimisation

- Les **fonctions convexes** ont une hessienne semi-définie positive
- Minimum global ⟺ hessienne définie positive au point critique

### 2. Méthodes numériques

- **Méthode du gradient conjugué** pour résoudre Ax = b
- Convergence garantie si A est définie positive

### 3. Statistiques

- **Matrices de covariance** sont semi-définies positives
- **Corrélations** : matrices de corrélation sont semi-définies positives

### 4. Géométrie

- Définit des **ellipsoïdes** dans ℝⁿ
- Les courbes de niveau de x^T A x = c sont des ellipses

## Propriétés de calcul

### Somme

Si A ≻ 0 et B ≻ 0, alors A + B ≻ 0

### Produit scalaire

Si A ≻ 0 et α > 0, alors αA ≻ 0

### Congruence

Si A ≻ 0 et P inversible, alors P^T A P ≻ 0

### Inverse

Si A ≻ 0, alors A⁻¹ ≻ 0

## Remarques importantes

⚠️ **Attention :** Une matrice peut avoir tous ses coefficients positifs sans être définie positive !

💡 **Astuce mnémotechnique :** "Définie positive" = "énergie toujours positive" pour la forme quadratique :$$x^T A x$$

🔍 **Test rapide :** Si tous les coefficients diagonaux sont positifs ET que la matrice est à diagonale dominante, elle est souvent définie positive.