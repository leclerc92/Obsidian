---
tags:
  - maths/algebre
---


---
***Références :***
- https://fr.wikipedia.org/wiki/Formule_de_Leibniz
- https://app.studyraid.com/fr/read/26069/1082517/determinants-de-matrices-formule-de-leibniz

---

La formule de Leibniz est une formule permettant de calculer la dérivée d'ordre n d'un produit de deux fonctions. Elle est analogue à la formule du binôme de Newton pour calculer une puissance d'ordre n d'une somme de deux termes.

$$ fg^{(n)} = \sum_{k=0}^{n}{\begin{pmatrix}
 n \\
k
\end{pmatrix}} f^{(n-k)}g^{k}$$

Cette formule est d'une importance théorique capitale car elle fournit une définition explicite etgénérale du déterminant pour toute dimension nn. Elle est la base de nombreuses démonstrationsen algèbre linéaire, notamment pour prouver que 
$$\det(AB) = \det(A)*\det(B) $$ $$ \det(A^T) = \det(A)$$ 

### Matrices

La formule de Leibniz pour trouver le déterminant d'une matrice carrée convient mieux aux petites matrices, surtout si le calcul est effectué entièrement ou en partie à la main.

*Exemple concret :*

$$ A =  \begin{pmatrix}
2,1,0 \\
1,3,1 \\
0,2,1
\end{pmatrix}
$$
**Étape 1 : Lister toutes les permutations**

Les 6 permutations de (1,2,3) sont :

1. (1,2,3) - permutation identité
2. (1,3,2)
3. (2,1,3)
4. (2,3,1)
5. (3,1,2)
6. (3,2,1)

Permutation (1,2,3) → [2] 1  0     Permutation (1,3,2) → [2] 1  0
                       1 [3] 1                            1  3 [1]
                       0  2 [1]                           0 [2] 1

Permutation (2,1,3) → 2 [1] 0      Permutation (2,3,1) → 2 [1] 0
                     [1] 3  1                            1  3 [1]
                      0  2 [1]                          [0] 2  1

**Etape 2 : Calculer la signature de chaque permutation**

Une inversion = un couple (i,j) où i < j mais σᵢ > σⱼ
*Permutation 1 : (1,2,3)*
- Pas d'inversion (tout est dans l'ordre)
- Nombre d'inversions = 0 (pair) → **signature = +1**

*Permutation 2 : (1,3,2)*
- Position 2 et 3 : 3 > 2 → 1 inversion
- Nombre d'inversions = 1 (impair) → **signature = -1**

| Permutation | Signature | Produit | Contribution |
| ----------- | --------- | ------- | ------------ |
| (1,2,3)     | +1        | 6       | +6           |
| (1,3,2)     | -1        | 4       | -4           |
| (2,1,3)     | -1        | 1       | -1           |
| (2,3,1)     | +1        | 0       | 0            |
| (3,1,2)     | +1        | 0       | 0            |
| (3,2,1)     | -1        | 0       | 0            |
**Etape 3 :Determiner le determinant**

> [!succes] Résulat
> det(A) = 6 - 4 - 1 + 0 + 0 + 0 = 1


## Résumé de la méthode

1. **Lister** les 6 permutations
2. **Sélectionner** les éléments correspondants dans la matrice
3. **Multiplier** ces éléments
4. **Calculer** la signature (compter les inversions)
5. **Appliquer** le signe (+ ou -)
6. **Additionner** tous les termes

