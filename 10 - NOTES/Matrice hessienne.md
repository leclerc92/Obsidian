---
tags:
  - maths/algebre
---


---
***Références :***

---
## *Définition :*

La [[matrice]] hessienne d'une fonction f est la matrice carrée de ses [[Dérivée|dérivées]] partielles secondes.

On appelle **forme hessienne** la [[forme quadratique]] associée à la matrice hessienne.

Le **déterminant de la matrice hessienne** peut être utile pour certains tests (notamment en dimension 2).

![[Pasted image 20251001115244.png]]

---

## Caractère défini de la matrice hessienne

### Définie positive
Une matrice hessienne est dite **définie positive** si tous ses **mineurs principaux** sont strictement positifs (> 0).

**Mineurs principaux** = [[determinant]] des sous-matrices principales formées en prenant les k premières lignes et k premières colonnes (k = 1, 2, ..., n).

**Critère de Sylvester** :
- $H_{11} > 0$
- $\begin{vmatrix} H_{11} & H_{12} \\ H_{21} & H_{22} \end{vmatrix} > 0$
- $\begin{vmatrix} H_{11} & H_{12} & H_{13} \\ H_{21} & H_{22} & H_{23} \\ H_{31} & H_{32} & H_{33} \end{vmatrix} > 0$
- etc.

**Lien avec la convexité** :
- Si $\nabla^2 f(x) \succ 0$ pour tout x → f est **strictement [[Convexité|convexe]]**
- Si $\nabla^2 f(x) \succeq 0$ pour tout x → f est **convexe**

### Semi-définie positive
Une matrice hessienne est **semi-définie positive** si tous ses mineurs principaux sont ≥ 0.

→ La fonction f associée est **convexe** (mais pas nécessairement strictement).

### Définie négative
Tous les mineurs principaux alternent en signe : $H_{11} < 0$, $\det(H_2) > 0$, $\det(H_3) < 0$, etc.

→ La fonction f associée est **strictement concave**.

### Semi-définie négative
$\nabla^2 f(x) \preceq 0$ → f est **concave**.