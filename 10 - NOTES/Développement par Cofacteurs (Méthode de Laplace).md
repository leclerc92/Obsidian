---
tags:
  - maths/algebre
---


---
***Références :***

---

*Principe :*

Le développement par cofacteurs permet de calculer le déterminant d'une matrice n×n en le ramenant à des déterminants de matrices (n-1)×(n-1).

*Vocabulaire :*

**Le Mineur Mᵢⱼ**

- C'est le déterminant de la sous-matrice obtenue en **supprimant** la ligne i et la colonne j
- Pour une matrice 3×3, chaque mineur est le déterminant d'une matrice 2×2

**Le Cofacteur Cᵢⱼ**

- Cᵢⱼ = (-1)^(i+j) × Mᵢⱼ
- Le signe alterne selon un damier :$$\begin{pmatrix}
+,-,+,-,\dots \\
-,+,-,+,\dots \\
+,-,+,-,\dots \\
\end{pmatrix}
$$


#### Exemple concret :
$$A = \begin{pmatrix}
2,1,0 \\
1,3,1 \\
0,2,1
\end{pmatrix}$$
**Étape 1 : Choisir une ligne ou colonne**

> [!tip]
> On choisit la ligne ou la colonne avec le plus de 0, ici [2,1,0]

**Étape 2 : Calculer chaque cofacteur**

*Pour A(1,1) :*

[2  1  0]     [3  1]
[1  3  1] --> [2  1]
[0  2  1]

Calculer le mineur : 
$$ M_{1,1} = \det(\begin{pmatrix}
3,1\\
2,1
\end{pmatrix}
 = 3*1-2*1 = 1

$$
Déterminer le cofacteur :  $$C_{1,1} = +1 * M_{1,1} = 1$$
*Pour A(1,2) :*

[2  1  0]     [1  1]
[1  3  1] --> [0  1]
[0  2  1]

Calculer le mineur : 
$$M_{1,2} = \det(\begin{pmatrix}
1,1\\
0,1
\end{pmatrix}
=1*1-0*1 = 1
$$
Calculer le cofacteur : 
$$C_{1,2} = -1 * M_{1,2} = -1$$*Pour A(1,3) :*

[2  1  0]     [1  3]
[1  3  1] --> [0  2]
[0  2  1]

Calculer le mineur : 
$$M_{1,3} = \det(\begin{pmatrix}
1,3 \\
0,2
\end{pmatrix}
= 1*2-0*3 = 2
$$
Calculer le cofacteur : 
$$C_{1,3} = 1*M_{1,3} = 2$$


**Étape 2 : Calculer le déterminant**

$$\det(A) = A_{1?1}*C_{1,1} + A_{1,2}*C_{1,2} + A_{1,3}*C_{1,3} = 1$$