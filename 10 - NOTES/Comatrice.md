---
tags:
---


---
***Références :***

---

## Définition

La **comatrice** (ou [[matrice]] adjointe classique) d'une matrice carrée $A$ est la **transposée** de la matrice des cofacteurs.

### Notation

$$\text{Com}(A) = (C_{ij})^T$$ où $C_{ij}$ est le cofacteur de l'élément $a_{ij}$.

### Rappel : Cofacteur

Le cofacteur $C_{ij}$ de l'élément $a_{ij}$ est : $$C_{ij} = (-1)^{i+j} \times M_{ij}$$ où $M_{ij}$ est le **mineur**(déterminant de la sous-matrice obtenue en supprimant la ligne $i$ et la colonne $j$).

## Construction étape par étape

### Étape 1 : Calculer les mineurs $M_{ij}$

Pour chaque élément $a_{ij}$, calculer le [[determinant]] de la matrice $(n-1) \times (n-1)$ obtenue en supprimant la ligne $i$ et la colonne $j$.

### Étape 2 : Calculer les cofacteurs $C_{ij}$

$$C_{ij} = (-1)^{i+j} \times M_{ij}$$

### Étape 3 : Former la matrice des cofacteurs

$$\text{Cof}(A) = \begin{pmatrix} C_{11} & C_{12} & \cdots & C_{1n} \ C_{21} & C_{22} & \cdots & C_{2n} \ \vdots & \vdots & \ddots & \vdots \ C_{n1} & C_{n2} & \cdots & C_{nn} \end{pmatrix}$$

### Étape 4 : Transposer

$$\text{Com}(A) = \text{Cof}(A)^T$$

## Exemple détaillé : Matrice $2 \times 2$

### Matrice donnée

$$A = \begin{pmatrix} a & b \ c & d \end{pmatrix}$$

### Calcul des cofacteurs

- $C_{11} = (-1)^{1+1} \times d = d$
- $C_{12} = (-1)^{1+2} \times c = -c$
- $C_{21} = (-1)^{2+1} \times b = -b$
- $C_{22} = (-1)^{2+2} \times a = a$

### Matrice des cofacteurs

$$\text{Cof}(A) = \begin{pmatrix} d & -c \ -b & a \end{pmatrix}$$

### Comatrice

$$\text{Com}(A) = \begin{pmatrix} d & -b \ -c & a \end{pmatrix}$$

## Exemple : Matrice $3 \times 3$

### Matrice donnée

$$A = \begin{pmatrix} 1 & 2 & 3 \ 0 & 1 & 4 \  
5 & 6 & 0 \end{pmatrix}$$

### Calcul des mineurs

- $M_{11} = \det\begin{pmatrix} 1 & 4 \ 6 & 0 \end{pmatrix} = 0 - 24 = -24$
- $M_{12} = \det\begin{pmatrix} 0 & 4 \ 5 & 0 \end{pmatrix} = 0 - 20 = -20$
- $M_{13} = \det\begin{pmatrix} 0 & 1 \ 5 & 6 \end{pmatrix} = 0 - 5 = -5$
- $M_{21} = \det\begin{pmatrix} 2 & 3 \ 6 & 0 \end{pmatrix} = 0 - 18 = -18$
- $M_{22} = \det\begin{pmatrix} 1 & 3 \ 5 & 0 \end{pmatrix} = 0 - 15 = -15$
- $M_{23} = \det\begin{pmatrix} 1 & 2 \ 5 & 6 \end{pmatrix} = 6 - 10 = -4$
- $M_{31} = \det\begin{pmatrix} 2 & 3 \ 1 & 4 \end{pmatrix} = 8 - 3 = 5$
- $M_{32} = \det\begin{pmatrix} 1 & 3 \ 0 & 4 \end{pmatrix} = 4 - 0 = 4$
- $M_{33} = \det\begin{pmatrix} 1 & 2 \ 0 & 1 \end{pmatrix} = 1 - 0 = 1$

### Matrice des cofacteurs

$$\text{Cof}(A) = \begin{pmatrix} -24 & 20 & -5 \ 18 & -15 & 4 \ 5 & -4 & 1 \end{pmatrix}$$

### Comatrice

$$\text{Com}(A) = \begin{pmatrix} -24 & 18 & 5 \ 20 & -15 & -4 \ -5 & 4 & 1 \end{pmatrix}$$

## Propriété fondamentale

### Relation avec l'inverse

Pour une matrice inversible $A$ : $$A^{-1} = \frac{\text{Com}(A)}{\det(A)}$$

### Vérification

$$A \times \text{Com}(A) = \det(A) \times I$$ $$\text{Com}(A) \times A = \det(A) \times I$$

## Applications principales

### 1. Calcul de l'inverse

**Méthode par comatrice :** Si $\det(A) \neq 0$, alors : $$A^{-1} = \frac{1}{\det(A)} \text{Com}(A)$$

### 2. Règle de Cramer

Pour résoudre le système $Ax = b$ : $$x_i = \frac{\det(A_i)}{\det(A)}$$ où $A_i$ est la matrice $A$ avec la colonne $i$ remplacée par $b$.

### 3. Développement du déterminant

Le déterminant peut s'écrire : $$\det(A) = \sum_{j=1}^n a_{ij} C_{ij} \quad \text{(développement selon la ligne } i\text{)}$$ $$\det(A) = \sum_{i=1}^n a_{ij} C_{ij} \quad \text{(développement selon la colonne } j\text{)}$$

## Propriétés importantes

### 1. Déterminant de la comatrice

$$\det(\text{Com}(A)) = (\det(A))^{n-1}$$ où $n$ est la taille de la matrice.

### 2. Comatrice du produit

$$\text{Com}(AB) = \text{Com}(B) \times \text{Com}(A)$$

### 3. Comatrice de la transposée

$$\text{Com}(A^T) = (\text{Com}(A))^T$$

### 4. Comatrice de l'inverse

Si $A$ est inversible : $$\text{Com}(A^{-1}) = \frac{(\text{Com}(A))^{-1}}{(\det(A))^{n-2}}$$

## Cas particuliers

### Matrice $1 \times 1$

$$A = (a) \Rightarrow \text{Com}(A) = (1)$$

### Matrice diagonale

Si $A = \text{diag}(d_1, d_2, \ldots, d_n)$, alors : $$\text{Com}(A) = \text{diag}\left(\frac{\det(A)}{d_1}, \frac{\det(A)}{d_2}, \ldots, \frac{\det(A)}{d_n}\right)$$

### Matrice singulière

Si $\det(A) = 0$, alors $A \times \text{Com}(A) = 0$.

## Algorithme de calcul

### Pour une matrice $n \times n$ :

1. **Pour chaque élément** $(i,j)$ :
    
    - Supprimer la ligne $i$ et la colonne $j$
    - Calculer le mineur $M_{ij}$
    - Calculer le cofacteur $C_{ij} = (-1)^{i+j} M_{ij}$
2. **Former la matrice des cofacteurs** $\text{Cof}(A)$
    
3. **Transposer** : $\text{Com}(A) = \text{Cof}(A)^T$
    

## Remarques importantes

⚠️ **Complexité :** Le calcul de la comatrice a une complexité en $O(n!)$, donc impraticable pour de grandes matrices.

💡 **Usage pratique :** Principalement utilisée pour les matrices de petite taille (2×2, 3×3).

🎯 **Alternative moderne :** Pour l'inversion, préférer la décomposition LU ou QR pour les grandes matrices.

⚡ **Propriété clé :** $A \times \text{Com}(A) = \det(A) \times I$ même si $A$ n'est pas inversible !