---
tags:
  - maths/stats
MOC:
---
---
***Références :***

---

## Propriétés et interprétation

La **variance** ($V$ ou $\sigma^2$) est une mesure de la **dispersion** des données. Comme tu l'as noté, plus les valeurs sont éloignées de la moyenne, plus la variance est grande.

- **Variance nulle :** Une variance égale à zéro signifie que toutes les valeurs de la série sont **identiques à la moyenne**. Il n'y a aucune dispersion.
    
- **Variance positive :** Une variance positive indique que les valeurs sont dispersées. Plus la valeur de la variance est élevée, plus la dispersion est grande.
    

### Unité

L'unité de la variance est le **carré de l'unité** des données d'origine. Par exemple, si tu mesures des poids en kilogrammes, la variance sera exprimée en kilogrammes carrés ($kg^2$). C'est pourquoi elle est souvent moins intuitive à interpréter que l'**[[écart type]]**, qui est la racine carrée de la variance et a la même unité que les données de départ.

---

## Calcul de la variance

La formule que tu as incluse est celle pour une **population entière** ou pour une série statistique complète.

$$ V = \frac{1}{n}\sum_{i=1}^{n}\left(x_{i}-\overline{x}\right)^{2}$$

Pour une **population**, on utilise la notation $\sigma^2$.

### Pour un échantillon

Lorsque tu calcules la variance à partir d'un **échantillon** pour estimer la variance d'une population plus grande, la formule est légèrement différente :

$$ s^2 = \frac{1}{n-1}\sum_{i=1}^{n}\left(x_{i}-\overline{x}\right)^{2}$$

La division par $n-1$ (au lieu de $n$) est appelée la **correction de Bessel**. Elle permet d'obtenir un estimateur **non biaisé** de la variance de la population. Sans cette correction, l'estimation de la variance serait systématiquement sous-estimée.

---

## Théorème de König-Huygens

Ce théorème, aussi connu sous le nom de **formule de Huygens-Steiner** ou simplement formule de la variance, offre une méthode de calcul alternative plus simple. Il énonce que la variance est égale à la **moyenne des carrés moins le carré de la moyenne**.

$$ V = \overline{x^2} - (\overline{x})^2$$

Où :

- $\overline{x^2} = \frac{1}{n}\sum_{i=1}^{n}x_{i}^2$ est la moyenne des carrés des valeurs.
    
- $(\overline{x})^2 = \left(\frac{1}{n}\sum_{i=1}^{n}x_{i}\right)^2$ est le carré de la moyenne des valeurs.
    

Cette formule est souvent plus facile à utiliser pour les calculs manuels, car elle évite de devoir calculer chaque écart par rapport à la moyenne.