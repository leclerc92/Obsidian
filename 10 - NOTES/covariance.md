---
MOC:
tags:
---
---
***Références :***

---
## Mesure de la covariance 

Elle permet de mettre en évidence le sens de la liaison et son intensité entre deux variables : 
$$ Cov(X,Y)= E(XY)-E(X)E(Y)$$

- $Cov(x,y) > 0$ : relation positive (x augmente, y augmente)
- $Cov(x,y) = 0$ : absence de relation monotone 
- $Cov(x,y) < 0$ : relation négative (x augmente, y diminue)

> [!info]
> Si deux variables sont indépendantes, alors la covariance est égale à 0. 
> Mais ce n'est pas réciproqie 


## Propriétés

- Symétrie : $Cov(x,y) = Cov(y,x)$
- Distibutivité : $Cov(x,y +z) = Cov(x,y) + Cov(x,z)$
- Covariance avec une constant est nulle : $Cov(X,a) = 0$
- Covariance avec variable transformée : $Cov(x,a +by) = bCov(x,y)$

## exemple

Soit X~N(0,1) et $Y=X^2$. 
Sont elles indépendantes ? 

ici on est sur une [[Loi Normale]].
on a donc $Cov(X,Y) = Cov(X,X^2) = E[X.X^2]-E[X].E[X^2] = E[X^3]$
donc $E[X^3]=\int_{\infty}^{-\infty}x^3dx = 0$

## Correlations 

#### Pourquoi normaliser ?

**Problème de la covariance :**

- Dépend des unités de mesure
- Difficile à interpréter : Cov(X,Y) = 150, c'est beaucoup ou peu ? 🤷

**Solution = Corrélation :**

- Division par σXσY "nettoie" les unités
- Ramène toujours entre -1 et +1 → interprétation universelle


> [!tip] Analogie
>
> C'est comme la différence entre :
> 
> - **Covariance** = dire "deux villes sont à 500 km" (valeur absolue)
> - **Corrélation** = dire "deux villes sont à 50% de la distance max du pays" (valeur relative)

Cette normalisation est appliquée grâce à la [[Corrélation de pearson]]