---
tags:
---
 

---
***Références :***

---

En mathématiques, l’**écart type** (aussi orthographié **écart-type**) est une mesure de la dispersion des valeurs d'un échantillon statistique ou d'une distribution de probabilité. Il est défini comme la racine de la [[variance]] ou, de manière équivalente, comme la moyenne quadratique des écarts par rapport à la moyenne. 
Il se note en général avec la lettre grecque σ (« sigma »), d’après l’appellation _standard deviation_ en anglais. Il est homogène à la variable mesurée.

## Calcul de l'écart type

L'écart type, noté $\sigma$, se calcule de manière légèrement différente selon que l'on travaille sur une **population entière** ou sur un **échantillon**.

### Pour une population

Si tu as accès à toutes les valeurs de ta population (ce qui est rare en pratique), la formule est :

$$ \sigma = \sqrt{\frac{1}{N}\sum_{i=1}^{N}(x_i - \mu)^2}$$

Où :

- $N$ est la taille totale de la population.
    
- $x_i$ est chaque valeur individuelle.
    
- $\mu$ est la moyenne de la population.
    

### Pour un échantillon

C'est le cas le plus courant. On utilise alors la notation $s$ et la formule est légèrement ajustée pour corriger un biais et obtenir une estimation non biaisée de l'écart type de la population.

$$ s = \sqrt{\frac{1}{n-1}\sum_{i=1}^{n}(x_i - \bar{x})^2}$$

Où :

- $n$ est la taille de l'échantillon.
    
- $x_i$ est chaque valeur de l'échantillon.
    
- $\bar{x}$ est la moyenne de l'échantillon.
    

La division par $n-1$ (au lieu de $n$) est appelée la **correction de Bessel**. Elle permet d'obtenir un estimateur plus précis de la variance et de l'écart type de la population à partir d'un échantillon.

---

## Interprétation et utilité

L'écart type est une mesure concrète de la **dispersion** ou de la **variabilité** des données.

- **Un faible écart type** indique que les valeurs sont peu dispersées et qu'elles sont regroupées près de la moyenne. Les données sont **homogènes**.
    
- **Un grand écart type** indique que les valeurs sont très dispersées par rapport à la moyenne. Les données sont **hétérogènes**.
    

### Analogie

Imagine deux classes d'élèves . Dans la **classe A**, les notes de mathématiques sont toutes comprises entre 10 et 12. Dans la **classe B**, elles s'étalent de 5 à 18.

- La moyenne des notes pourrait être la même pour les deux classes, par exemple 11.
    
- Cependant, la **classe B** aura un écart type beaucoup plus élevé que la **classe A**, car ses notes sont beaucoup plus dispersées.
    

L'écart type te donne une idée de la "typicalité" d'une observation. Dans la classe A, une note de 12 n'est pas surprenante. Dans la classe B, une note de 18 est un écart beaucoup plus significatif par rapport à la moyenne.

---

## Lien avec d'autres notions statistiques

- **Écart type et moyenne :** L'écart type complète la moyenne en donnant une mesure de la fiabilité de celle-ci. Une moyenne seule peut être trompeuse si l'écart type est grand.
    
- **Écart type et [[variance]] :** Comme tu l'as noté, l'écart type est la **racine carrée de la variance**. La variance, de par son unité au carré, est souvent plus difficile à interpréter directement. L'écart type, ayant la même unité que les données d'origine, est beaucoup plus intuitif.
    

---

**_Exemple concret_**

Pour le jeu de données `{2, 4, 4, 4, 5, 5, 7, 9}`, calculons l'écart type :

1. **Moyenne ($\bar{x}$) :** $(2+4+4+4+5+5+7+9) / 8 = 40 / 8 = 5$
    
2. **Écarts par rapport à la moyenne :** $(-3, -1, -1, -1, 0, 0, 2, 4)$
    
3. **Écarts au carré :** $(9, 1, 1, 1, 0, 0, 4, 16)$
    
4. **Somme des carrés :** $9+1+1+1+0+0+4+16 = 32$
    
5. **Variance ($s^2$) :** $32 / (8-1) = 32 / 7 \approx 4.57$
    
6. **Écart type ($s$) :** $\sqrt{4.57} \approx 2.14$
    

L'écart type est d'environ 2,14. Cela nous indique que, en moyenne, les valeurs de cet échantillon s'écartent de la moyenne de 5 d'environ 2,14 unités.