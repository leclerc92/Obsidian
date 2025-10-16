---
MOC: "[[MATHS]]"
tags:
  - maths/stats
---

---
***Références :***

---

## Principe général

**Question centrale :** La corrélation observée dans mon échantillon reflète-t-elle une vraie corrélation dans la population, ou est-ce juste du hasard ?

**Hypothèses :**

- **H₀** : ρ = 0 (pas de corrélation dans la population)
- **H₁** : ρ ≠ 0 (corrélation existe)

> [!tip] Rappel Une corrélation significative ne prouve PAS la causalité !

---

## Quel test choisir ?

```
Mes données sont :
│
├─ Quantitatives continues
│  ├─ Relation LINÉAIRE + Distribution normale
│  │  └─ ✅ Test de Pearson (r)
│  │
│  └─ Relation NON linéaire OU données non normales
│     └─ ✅ Test de Spearman (ρ_s)
│
└─ Ordinales (rangs)
   ├─ Échantillon grand (n > 30)
   │  └─ ✅ Test de Spearman
   │
   └─ Échantillon petit + nombreux ex-aequo
      └─ ✅ Test de Kendall (τ)
```

---

## Test de Pearson (paramétrique)

### Conditions d'application

✅ Variables **quantitatives continues** 
✅ Relation **linéaire** entre X et Y 
✅ Distribution **bivariée normale** (ou n ≥ 30) 
✅ Absence de **valeurs extrêmes**

### Méthode 1 : Via statistique t (H₀: ρ = 0)

**Formule :**

$$t = r\sqrt{\frac{n-2}{1-r^2}}$$

Distribution : Student avec **ddl = n - 2**

**Processus :**

1. Calculer r sur l'échantillon -> [[Corrélation de pearson]]
2. Calculer la statistique t
3. Comparer à $t_{\alpha/2, n-2}$ ou calculer la p-value
4. Décision : si |t| > valeur critique → rejeter H₀

### Exemple : Heures d'étude vs Notes

**Données :**

- n = 30 étudiants
- r = 0.65
- α = 0.05

**Calcul :**

$$t = 0.65\sqrt{\frac{30-2}{1-0.65^2}} = 0.65\sqrt{\frac{28}{0.5775}} = 0.65 \times 6.98 = 4.54$$

**Décision :**

- ddl = 28
- Valeur critique : $t_{0.025, 28} = 2.048$
- |4.54| > 2.048 → **On rejette H₀**
- p-value < 0.001

**Conclusion :** La corrélation entre heures d'étude et notes est statistiquement significative (r = 0.65, p < 0.001). Plus on étudie, plus les notes tendent à augmenter.

### Méthode 2 : Via transformation de Fisher (H₀: ρ = ρ₀)

**Utile pour :**

- Tester ρ = 0.5 (valeur spécifique ≠ 0)
- Comparer deux corrélations

**Processus :**

1. **Transformer r :** $$z = \frac{1}{2}\ln\left(\frac{1+r}{1-r}\right) = \text{arctanh}(r)$$
    
2. **Transformer ρ₀ :** $$z_0 = \text{arctanh}(\rho_0)$$
    
3. **Statistique de test :** $$Z = \frac{z - z_0}{\frac{1}{\sqrt{n-3}}}$$
    
    Distribution : N(0,1)
    
4. **Décision :** Si |Z| > $z_{\alpha/2}$ → rejeter H₀
    

### Exemple : Test ρ = 0.5

**Données :** r = 0.65, n = 30, tester H₀: ρ = 0.5

**Calcul :**

1. $z = \text{arctanh}(0.65) = 0.775$
2. $z_0 = \text{arctanh}(0.5) = 0.549$
3. $Z = \frac{0.775 - 0.549}{\frac{1}{\sqrt{27}}} = \frac{0.226}{0.192} = 1.18$

**Décision :**

- $z_{0.025} = 1.96$
- |1.18| < 1.96 → **On ne rejette pas H₀**

**Conclusion :** On ne peut pas conclure que ρ ≠ 0.5. La corrélation observée (0.65) est compatible avec ρ = 0.5.

---

## Test de Spearman (non-paramétrique)

### Quand l'utiliser ?

✅ Relation **monotone** (pas forcément linéaire) 
✅ Variables **ordinales** ou quantitatives 
✅ Données **non normales** 
✅ Présence de **valeurs extrêmes**

### Principe

Mesure la [[Corrélation de spearman]] entre les **rangs** des observations.

**Coefficient de Spearman :**

$$\rho_s = 1 - \frac{6\sum d_i^2}{n(n^2-1)}$$

où $d_i$ = différence entre les rangs de X et Y pour l'observation i

### Statistique de test

Pour n > 30 :

$$t = \rho_s\sqrt{\frac{n-2}{1-\rho_s^2}}$$

Distribution : Student avec ddl = n - 2

### Exemple : Satisfaction client vs Temps d'attente

**Données :** 15 clients

|Client|Temps attente (min)|Satisfaction (/10)|
|---|---|---|
|1|5|9|
|2|12|6|
|3|8|7|
|...|...|...|

**Pourquoi Spearman ?**

- Relation non linéaire (satisfaction décroît rapidement, puis plateau)
- Petit échantillon avec données ordinales (échelle /10)

**Étapes :**

1. Classer les temps d'attente (rangs pour X)
2. Classer les satisfactions (rangs pour Y)
3. Calculer $\rho_s$

**Résultat :** ρₛ = -0.72, p = 0.002

**Conclusion :** Corrélation négative forte et significative. Plus le temps d'attente augmente, plus la satisfaction diminue (relation monotone).

> [!info] Différence Pearson vs Spearman
> 
> - Pearson mesure la force de la relation **linéaire**
> - Spearman mesure la force de la relation **monotone**
> 
> Si la relation est linéaire, les deux donneront des résultats similaires !

---

## Test de Kendall (non-paramétrique)

### Quand l'utiliser ?

✅ **Petits échantillons** (n < 30) ✅ Nombreux **ex-aequo** dans les données ✅ Interprétation en termes de **probabilité de concordance**

### Principe

Mesure la concordance entre paires d'observations.

**Coefficient de Kendall (τ) :**

$$\tau = \frac{C - D}{C + D}$$

- C = nombre de paires concordantes
- D = nombre de paires discordantes

**Paire concordante :** Si X₁ < X₂ et Y₁ < Y₂ (ou inversement)

### Statistique de test

Pour n ≥ 10 :

$$Z = \frac{\tau}{\sqrt{\frac{2(2n+5)}{9n(n-1)}}}$$

Distribution : N(0,1)

### Exemple : Classement de 10 étudiants

**Données :**

|Étudiant|Rang Math|Rang Physique|
|---|---|---|
|A|1|2|
|B|2|1|
|C|3|4|
|...|...|...|

**Calcul :**

- Paires concordantes : 35
- Paires discordantes : 10
- τ = (35-10)/(35+10) = 0.56

**Test :**

- Z = 2.84
- p-value = 0.005

**Conclusion :** Les classements en maths et physique sont significativement concordants (τ = 0.56, p < 0.01).

**Interprétation pratique :** Un étudiant pris au hasard a 56% de chances d'avoir un meilleur classement en physique qu'un autre s'il a aussi un meilleur classement en maths.

---

## Comparaison des trois tests

| Caractéristique    | [[Corrélation de pearson \| Pearson]] (r) | Spearman (ρₛ)     | Kendall (τ)       |
| ------------------ | ----------------------------------------- | ----------------- | ----------------- |
| **Type**           | Paramétrique                              | Non-param.        | Non-param.        |
| **Mesure**         | Linéarité                                 | Monotonie         | Concordance       |
| **Échelle**        | Quantitative                              | Ordinale/Quant.   | Ordinale          |
| **Conditions**     | Normalité                                 | Aucune            | Aucune            |
| **Robustesse**     | Faible                                    | Moyenne           | Forte             |
| **Interprétation** | % variance expliquée                      | Corrélation rangs | Prob. concordance |
| **Ex-aequo**       | Sensible                                  | Gérable           | Bien géré         |
| **Valeur**         | -1 à 1                                    | -1 à 1            | -1 à 1            |

---

## Tableau de décision rapide

|Situation|Test recommandé|
|---|---|
|Relation linéaire, données normales|✅ Pearson|
|Relation non-linéaire mais monotone|✅ Spearman|
|Données ordinales (Likert, classements)|✅ Spearman ou Kendall|
|Petit échantillon (n < 30) + ex-aequo|✅ Kendall|
|Présence de valeurs extrêmes|✅ Spearman ou Kendall|
|Besoin de variance expliquée (R²)|✅ Pearson uniquement|

---

## Exemples de relations

### Pearson détecte, pas Spearman

```
Relation en U (non monotone)
Y = X² centré autour de 0
→ r ≈ 0, ρₛ ≈ 0 ✓
```

### Spearman détecte, Pearson sous-estime

```
Relation exponentielle : Y = e^X
→ r = 0.85, ρₛ = 0.99
(Spearman capture mieux la monotonie)
```

### Les deux détectent pareil

```
Relation linéaire parfaite : Y = 2X + 3
→ r = 1, ρₛ = 1 ✓
```

---

## Lien avec d'autres concepts

### Avec [[covariance]]

$$r = \frac{Cov(X,Y)}{\sigma_X \sigma_Y}$$

Le test de Pearson teste si cette covariance standardisée est significativement différente de 0.

### Avec [[Intervalles de confiance]]

Après un test significatif, construire un IC pour quantifier la force de la relation :

- Via transformation de Fisher pour r
- Bootstrap pour ρₛ et τ

### Avec Régression linéaire

- r² = coefficient de détermination
- Un test de corrélation significatif justifie une régression

---

## Formules récapitulatives

### Test de Pearson (H₀: ρ = 0)

$$t = r\sqrt{\frac{n-2}{1-r^2}} \sim t(n-2)$$

### Test de Spearman (n > 30)

$$t = \rho_s\sqrt{\frac{n-2}{1-\rho_s^2}} \sim t(n-2)$$

### Test de Kendall (n ≥ 10)

$$Z = \frac{\tau}{\sqrt{\frac{2(2n+5)}{9n(n-1)}}} \sim N(0,1)$$

### Transformation de Fisher (H₀: ρ = ρ₀)

$$Z = \frac{\text{arctanh}(r) - \text{arctanh}(\rho_0)}{\frac{1}{\sqrt{n-3}}} \sim N(0,1)$$
