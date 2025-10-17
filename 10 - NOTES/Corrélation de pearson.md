---
MOC:
tags:
---


Le **coefficient de corrélation linéaire simple de Pearson**, noté $r$, est une mesure statistique de la **force** et de la **direction** de la **relation linéaire** entre deux variables quantitatives, $X$ et $Y$.

## 1. Formule et Normalisation

Le coefficient de Pearson est une **normalisation** de la [[covariance]] par le produit des [[écart type]] des variables :

$$r = \frac{Cov(X,Y)}{\sigma_X \sigma_Y}$$

- **Rôle de la normalisation :** Contrairement à la covariance, le coefficient $r$ est **borné** (sa valeur est toujours entre $-1$ et $1$). Cette normalisation permet d'avoir une **échelle de mesure standardisée** qui ne dépend pas des unités des variables $X$ et $Y$, rendant la corrélation directement comparable entre différentes études.
    

---

## 2. Propriétés et Interprétation

Les propriétés de $r$ sont essentielles pour comprendre la nature de la relation entre $X$ et $Y$.

- **Plage de valeurs :**
    
    $$-1 \le r \le 1$$
    
    (Il est **sans unité**.)
    

|**Valeur de r**|**Interprétation Concrète**|**Type de Relation**|
|---|---|---|
|**$r = 1$**|**Corrélation linéaire positive parfaite.** Lorsque $X$ augmente, $Y$ augmente **strictement proportionnellement** selon une droite. Tous les points sont **alignés** sur une droite montante.|Forte & Positive 📈|
|**$r \approx 0.8$ à $0.99$**|**Forte liaison linéaire positive.** Lorsque $X$ augmente, $Y$ a une très forte tendance à augmenter.|Forte & Positive|
|**$r \approx 0$**|**Absence de corrélation linéaire.** Il n'y a pas de tendance linéaire claire. Les points sont dispersés.|Nulle 🟰|
|**$r \approx -0.8$ à $-0.99$**|**Forte liaison linéaire négative.** Lorsque $X$ augmente, $Y$ a une très forte tendance à diminuer.|Forte & Négative|
|**$r = -1$**|**Corrélation linéaire négative parfaite.** Lorsque $X$ augmente, $Y$ diminue **strictement proportionnellement** selon une droite. Tous les points sont **alignés** sur une droite descendante.|Forte & Négative 📉|

- **Règle générale :**
    
    - $\vert r \vert$ proche de $1$: **Forte** liaison linéaire.
        
    - $\vert r \vert$ proche de $0$: **Faible** (ou nulle) liaison linéaire.
        
    - Le **signe** de $r$ donne la **direction** (positif ou négatif).
        

---

## 3. Limites et Mise en Garde

Même si $r$ est un outil puissant, il a des limitations cruciales à noter.

- **Ne mesure que la linéarité :** $r$ mesure **uniquement** les relations de type _linéaire_ (en ligne droite).
    
    - _Exemple concret :_ Une relation **parabolique** parfaite ($Y = X^2$) peut avoir un $r$ proche de $0$, car elle n'est pas linéaire. $\Rightarrow$ **Toujours visualiser** les données avec un nuage de points !
        
- **Ne traduit pas la causalité :** Corrélation $\neq$ Causalité. Ce n'est pas parce que deux variables sont corrélées qu'une cause l'autre. Il peut y avoir des variables **confondantes** (ou _lurking variables_).
    
- **Sensibilité aux valeurs extrêmes :** Le coefficient $r$ est **sensible aux valeurs aberrantes** (outliers) qui peuvent artificiellement augmenter ou diminuer sa valeur.
    
- **Ne pas confondre corrélation et pente :** Un $r$ fort signifie que les points sont proches d'une droite, mais la valeur de $r$ **n'indique pas la pente** de cette droite. Une pente raide ou douce peut avoir le même coefficient $r$ si la dispersion autour de la droite est la même.