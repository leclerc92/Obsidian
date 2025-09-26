---
tags:
  - maths/algebre
---


---
***Références :***

---
## Définition

Le **polynôme caractéristique** d'une [[matrice]] carrée $A$ de taille $n \times n$ est le polynôme : $$P_A(\lambda) = \det(A - \lambda I)$$

où $I$ est la matrice identité $n \times n$.

### Forme générale

$$P_A(\lambda) = (-1)^n \lambda^n + a_{n-1}\lambda^{n-1} + \cdots + a_1\lambda + a_0$$

## Propriétés fondamentales

### 1. Degré du polynôme

Le polynôme caractéristique est de **degré** $n$ (taille de la matrice).

### 2. Coefficient dominant

Le coefficient de $\lambda^n$ est toujours $(-1)^n$.

### 3. Terme constant

$$a_0 = P_A(0) = \det(A)$$

### 4. Coefficient de $\lambda^{n-1}$

$$a_{n-1} = (-1)^{n-1} \text{tr}(A)$$ où $\text{tr}(A)$ est la trace de $A$ (somme des éléments diagonaux).

### 5. Racines du polynôme

Les **racines** de $P_A(\lambda) = 0$ sont exactement les [[Valeurs Propres et Vecteurs Propres | valeurs propres]] de $A$.

## Calcul pratique

### Cas $2 \times 2$

Pour $A = \begin{pmatrix} a & b \ c & d \end{pmatrix}$ :

$$A - \lambda I = \begin{pmatrix} a-\lambda & b \ c & d-\lambda \end{pmatrix}$$

$$P_A(\lambda) = \det\begin{pmatrix} a-\lambda & b \ c & d-\lambda \end{pmatrix} = (a-\lambda)(d-\lambda) - bc$$

$$P_A(\lambda) = \lambda^2 - (a+d)\lambda + (ad-bc)$$

$$P_A(\lambda) = \lambda^2 - \text{tr}(A)\lambda + \det(A)$$

### Exemple $2 \times 2$

$$A = \begin{pmatrix} 5 & 2 \ 1 & 4 \end{pmatrix}$$

$$P_A(\lambda) = \lambda^2 - 9\lambda + 18 = (\lambda-3)(\lambda-6)$$

Valeurs propres : $\lambda_1 = 3$, $\lambda_2 = 6$

### Cas $3 \times 3$

Pour une matrice $3 \times 3$, le calcul devient plus complexe :

$$P_A(\lambda) = -\lambda^3 + \text{tr}(A)\lambda^2 - \text{(somme des mineurs 2×2)}\lambda + \det(A)$$

### Exemple $3 \times 3$

$$A = \begin{pmatrix} 1 & 2 & 0 \ 0 & 3 & 1 \ 0 & 0 & 2 \end{pmatrix}$$

**Calcul :** $$A - \lambda I = \begin{pmatrix} 1-\lambda & 2 & 0 \ 0 & 3-\lambda & 1 \ 0 & 0 & 2-\lambda \end{pmatrix}$$

Pour une matrice triangulaire : $$P_A(\lambda) = (1-\lambda)(3-\lambda)(2-\lambda)$$

**Développement :** $$P_A(\lambda) = -\lambda^3 + 6\lambda^2 - 11\lambda + 6$$

## Théorèmes importants

### Théorème de Cayley-Hamilton

**Toute matrice carrée satisfait son propre polynôme caractéristique :** $$P_A(A) = 0$$

**Exemple :** Si $P_A(\lambda) = \lambda^2 - 5\lambda + 6$, alors $A^2 - 5A + 6I = 0$.

### Théorème fondamental

Les **valeurs propres** de $A$ sont exactement les **racines** du polynôme caractéristique.

### Multiplicité algébrique

La **multiplicité algébrique** d'une valeur propre $\lambda_0$ est son **ordre de multiplicité** comme racine de $P_A(\lambda)$.

## Relations avec les coefficients

### Formules de Newton (relations de Vieta)

Pour un polynôme $P(\lambda) = \lambda^n - s_1\lambda^{n-1} + s_2\lambda^{n-2} - \cdots + (-1)^n s_n$ :

- $s_1 = \lambda_1 + \lambda_2 + \cdots + \lambda_n = \text{tr}(A)$
- $s_2 = \sum_{i<j} \lambda_i \lambda_j$ (somme des produits 2 à 2)
- $\vdots$
- $s_n = \lambda_1 \lambda_2 \cdots \lambda_n = \det(A)$

### Polynômes élémentaires symétriques

Les coefficients du polynôme caractéristique sont les **polynômes élémentaires symétriques** des valeurs propres.

## Matrices particulières

### Matrice diagonale

Si $A = \text{diag}(\lambda_1, \lambda_2, \ldots, \lambda_n)$ : $$P_A(\lambda) = (\lambda_1 - \lambda)(\lambda_2 - \lambda) \cdots (\lambda_n - \lambda)$$

### Matrice triangulaire

Pour une matrice triangulaire supérieure ou inférieure : $$P_A(\lambda) = \prod_{i=1}^n (a_{ii} - \lambda)$$

Les valeurs propres sont les **éléments diagonaux**.

### Matrice compagnon

La matrice compagnon d'un polynôme $p(\lambda) = \lambda^n + a_{n-1}\lambda^{n-1} + \cdots + a_0$ :

$$C = \begin{pmatrix} 0 & 0 & \cdots & 0 & -a_0 \ 1 & 0 & \cdots & 0 & -a_1 \ 0 & 1 & \cdots & 0 & -a_2 \ \vdots & \vdots & \ddots & \vdots & \vdots \ 0 & 0 & \cdots & 1 & -a_{n-1} \end{pmatrix}$$

**a pour polynôme caractéristique exactement** $p(\lambda)$.

## Applications

### 1. Calcul des puissances de matrices

Grâce au théorème de Cayley-Hamilton, on peut exprimer $A^k$ pour $k \geq n$ comme combinaison linéaire de $I, A, A^2, \ldots, A^{n-1}$.

### 2. Calcul de l'inverse

Si $P_A(\lambda) = \det(A - \lambda I)$ et $\det(A) \neq 0$ : $$A^{-1} = -\frac{1}{\det(A)}(A^{n-1} + a_{n-1}A^{n-2} + \cdots + a_1 I)$$

### 3. Résolution d'équations différentielles

Pour $\frac{dx}{dt} = Ax$, la solution dépend des valeurs propres obtenues via le polynôme caractéristique.

## Invariants

### Similarité

Des matrices **similaires** ont le **même polynôme caractéristique** : Si $B = P^{-1}AP$, alors $P_A(\lambda) = P_B(\lambda)$.

### Trace et déterminant

- $\text{tr}(A) = \sum \lambda_i$ (somme des valeurs propres)
- $\det(A) = \prod \lambda_i$ (produit des valeurs propres)

## Algorithmes de calcul

### Méthode directe

1. Former $A - \lambda I$
2. Calculer $\det(A - \lambda I)$ symboliquement
3. Développer le polynôme obtenu

### Pour grandes matrices

- **Méthode de Hessenberg** : réduction préalable
- **Algorithmes itératifs** : QR, puissance inverse
- **Approximations numériques** des racines

## Exemple complet

### Matrice donnée

$$A = \begin{pmatrix} 0 & 1 & 0 \ 0 & 0 & 1 \ 2 & -5 & 4 \end{pmatrix}$$

### Calcul du polynôme caractéristique

$$A - \lambda I = \begin{pmatrix} -\lambda & 1 & 0 \ 0 & -\lambda & 1 \ 2 & -5 & 4-\lambda \end{pmatrix}$$

**Développement par la première ligne :** $$P_A(\lambda) = -\lambda \det\begin{pmatrix} -\lambda & 1 \ -5 & 4-\lambda \end{pmatrix} - 1 \det\begin{pmatrix} 0 & 1 \ 2 & 4-\lambda \end{pmatrix}$$

$$= -\lambda(-\lambda(4-\lambda) + 5) - 1(0 - 2)$$ $$= -\lambda(-4\lambda + \lambda^2 + 5) + 2$$ $$= \lambda(4\lambda - \lambda^2 - 5) + 2$$ $$= -\lambda^3 + 4\lambda^2 - 5\lambda + 2$$

### Factorisation

$$P_A(\lambda) = -(\lambda - 1)(\lambda - 2)(\lambda - 1) = -(\lambda - 1)^2(\lambda - 2)$$

**Valeurs propres :** $\lambda_1 = 1$ (multiplicité 2), $\lambda_2 = 2$

## Remarques importantes

⚠️ **Complexité :** Le calcul direct du polynôme caractéristique est en $O(n!)$ (via le déterminant).

💡 **Astuce :** Pour les matrices $2 \times 2$, utilisez la formule $\lambda^2 - \text{tr}(A)\lambda + \det(A)$.

🎯 **Vérification :** $\sum \lambda_i = \text{tr}(A)$ et $\prod \lambda_i = \det(A)$.

⚡ **Théorème clé :** Cayley-Hamilton permet d'exprimer les puissances élevées de $A$.