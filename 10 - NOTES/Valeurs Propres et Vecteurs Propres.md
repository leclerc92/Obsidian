---
tags:
  - maths/algebre
---


---
***Références :***

---
## Définitions fondamentales

### Valeur propre et vecteur propre

Soit $A$ une [[matrice]] carrée $n \times n$. Un **scalaire** $\lambda$ est une **valeur propre** de $A$ s'il existe un **vecteur non nul** $v \in \mathbb{R}^n$ tel que :

$$A v = \lambda v$$

Le vecteur $v$ est appelé **vecteur propre** associé à la valeur propre $\lambda$.

### Interprétation géométrique

- Le vecteur propre $v$ garde **la même direction** après transformation par $A$
- Il est seulement **dilaté** (ou contracté) d'un facteur $\lambda$
- Si $\lambda > 0$ : même sens
- Si $\lambda < 0$ : sens opposé
- Si $|\lambda| > 1$ : dilatation
- Si $|\lambda| < 1$ : contraction

## Calcul des valeurs propres

### Méthode standard

1. **Former** la matrice $(A - \lambda I)$
2. **Calculer** le [[determinant]] : $\det(A - \lambda I) = 0$
3. **Résoudre** l'équation polynomiale obtenue

### Exemple : Matrice $2 \times 2$

$$A = \begin{pmatrix} 3 & 1 \ 0 & 2 \end{pmatrix}$$

**Étape 1 :** Former $A - \lambda I$ $$A - \lambda I = \begin{pmatrix} 3-\lambda & 1 \ 0 & 2-\lambda \end{pmatrix}$$

**Étape 2 :** Calculer le déterminant $$\det(A - \lambda I) = (3-\lambda)(2-\lambda) - 0 = (3-\lambda)(2-\lambda)$$

**Étape 3 :** Résoudre $(3-\lambda)(2-\lambda) = 0 \Rightarrow \lambda_1 = 3, \lambda_2 = 2$

## Calcul des vecteurs propres

### Méthode

Pour chaque valeur propre $\lambda_i$, résoudre le système : $$(A - \lambda_i I) v = 0$$

### Exemple (suite)

**Pour $\lambda_1 = 3$ :** $$\begin{pmatrix} 0 & 1 \ 0 & -1 \end{pmatrix} \begin{pmatrix} v_1 \ v_2 \end{pmatrix} = \begin{pmatrix} 0 \ 0 \end{pmatrix}$$

Système : $v_2 = 0$ et $-v_2 = 0$ Vecteur propre : $v = \begin{pmatrix} 1 \ 0 \end{pmatrix}$ (ou tout multiple non nul)

**Pour $\lambda_2 = 2$ :** $$\begin{pmatrix} 1 & 1 \ 0 & 0 \end{pmatrix} \begin{pmatrix} v_1 \ v_2 \end{pmatrix} = \begin{pmatrix} 0 \ 0 \end{pmatrix}$$

Système : $v_1 + v_2 = 0$ Vecteur propre : $v = \begin{pmatrix} 1 \ -1 \end{pmatrix}$ (ou tout multiple non nul)

## Sous-espace propre

### Définition

Le **sous-espace propre** $E_\lambda$ associé à une valeur propre $\lambda$ est : $$E_\lambda = \ker(A - \lambda I) = {v : (A - \lambda I)v = 0}$$

### Propriétés

- $E_\lambda$ est un sous-espace vectoriel
- $\dim(E_\lambda) \geq 1$ (multiplicité géométrique)
- Tous les vecteurs non nuls de $E_\lambda$ sont des vecteurs propres

## Multiplicités

### Multiplicité algébrique

**Ordre de multiplicité** de $\lambda$ comme racine du [[polynôme caractéristique]].

### Multiplicité géométrique

**Dimension** du sous-espace propre : $\dim(E_\lambda)$.

### Relation importante

$$1 \leq \text{multiplicité géométrique} \leq \text{multiplicité algébrique}$$

## Propriétés fondamentales

### 1. Linéarité des combinaisons

Si $v_1, v_2$ sont vecteurs propres pour la même valeur propre $\lambda$ : $$A(\alpha v_1 + \beta v_2) = \lambda(\alpha v_1 + \beta v_2)$$

### 2. Indépendance linéaire

Les vecteurs propres correspondant à des **valeurs propres distinctes** sont **linéairement indépendants**.

### 3. Somme des valeurs propres

$$\sum_{i=1}^n \lambda_i = \text{tr}(A) \quad \text{(trace de A)}$$

### 4. Produit des valeurs propres

$$\prod_{i=1}^n \lambda_i = \det(A)$$

## Diagonalisation

### Matrice diagonalisable

Une matrice $A$ est **diagonalisable** si elle possède $n$ vecteurs propres linéairement indépendants.

### Condition équivalente

$$A = P D P^{-1}$$ où :

- $D = \text{diag}(\lambda_1, \lambda_2, \ldots, \lambda_n)$ : matrice diagonale des valeurs propres
- $P$ : matrice des vecteurs propres correspondants

### Critère de diagonalisation

$A$ est diagonalisable ⟺ pour toute valeur propre $\lambda$ : $$\text{multiplicité géométrique} = \text{multiplicité algébrique}$$

## Applications importantes

### 1. Systèmes dynamiques

$$x_{k+1} = A x_k \Rightarrow x_k = A^k x_0$$

Les valeurs propres déterminent le comportement asymptotique :

- $|\lambda| < 1$ : convergence vers 0
- $|\lambda| > 1$ : divergence
- $|\lambda| = 1$ : comportement oscillant

### 2. Analyse de stabilité

- Système stable ⟺ toutes les valeurs propres ont partie réelle < 0
- Point critique stable ⟺ toutes les valeurs propres < 0

### 3. Analyse en composantes principales (ACP)

Les vecteurs propres de la matrice de covariance donnent les **directions principales** de variation.

### 4. Google PageRank

L'algorithme utilise le vecteur propre dominant de la matrice de transition du web.

## Cas particuliers

### Matrices triangulaires

Les valeurs propres sont les **éléments diagonaux** : $$A = \begin{pmatrix} a_{11} & \cdots & \cdots \ 0 & a_{22} & \cdots \ \vdots & \ddots & \ddots \end{pmatrix}$$ Valeurs propres : $a_{11}, a_{22}, \ldots, a_{nn}$

### Matrices symétriques

- Toutes les valeurs propres sont **réelles**
- Les vecteurs propres sont **orthogonaux**
- Toujours **diagonalisable**

### Matrices orthogonales

- Toutes les valeurs propres ont **module 1**
- $|\lambda| = 1$ pour tout $\lambda$

## Exemple complet : Matrice $3 \times 3$

$$A = \begin{pmatrix} 2 & 1 & 0 \ 0 & 2 & 1 \ 0 & 0 & 3 \end{pmatrix}$$

**Valeurs propres :** $\lambda_1 = \lambda_2 = 2$ (multiplicité 2), $\lambda_3 = 3$

**Vecteurs propres :**

- Pour $\lambda = 2$ : $E_2 = \text{span}\left{\begin{pmatrix} 1\0\0 \end{pmatrix}, \begin{pmatrix} 1\1\0 \end{pmatrix}\right}$
- Pour $\lambda = 3$ : $E_3 = \text{span}\left{\begin{pmatrix} 1\2\2 \end{pmatrix}\right}$

## Remarques importantes

⚠️ **Attention :** Un vecteur propre n'est jamais le vecteur nul par définition !

💡 **Astuce :** Pour les matrices $2 \times 2$, utilisez la formule : $\lambda = \frac{\text{tr}(A) \pm \sqrt{(\text{tr}(A))^2 - 4\det(A)}}{2}$

🎯 **Vérification :** Toujours vérifier $A v = \lambda v$ après calcul !

⚡ **Unicité :** Les vecteurs propres ne sont définis qu'à un facteur multiplicatif près.