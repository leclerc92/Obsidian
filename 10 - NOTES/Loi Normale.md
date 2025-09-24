---
MOC:
tags:
  - maths/stats
---


---
***Références :***

---
---
***Références :***

---

## Définition

La **loi normale** (ou gaussienne) est une distribution de probabilité continue caractérisée par sa **courbe en forme de cloche**, symétrique autour de sa moyenne.

**Notation** : X ~ N(μ, σ²)

- μ = moyenne
- σ² = variance
- σ = écart-type

## Caractéristiques Visuelles

```
           Fréquence
               |
               |     /\
               |    /  \
               |   /    \
               |  /      \
               | /        \
               |/          \____
               |________________
                      X
               μ-3σ  μ  μ+3σ
```

### Propriétés de la Courbe

- **Symétrique** autour de la moyenne μ
- **Unimodale** : un seul pic au centre
- **Asymptotique** : les queues s'approchent de 0 sans jamais l'atteindre
- **Aire totale** sous la courbe = 1

## Paramètres

### Moyenne (μ)

- **Position** du centre de la courbe
- **Médiane** = **Mode** = **Moyenne** = μ

### Écart-type (σ)

- **Largeur** de la courbe
- Plus σ est grand → courbe plus étalée
- Plus σ est petit → courbe plus pointue

## Règle Empirique (68-95-99.7)

Dans une distribution normale :

|Intervalle|Pourcentage des données|
|---|---|
|μ ± 1σ|**68%**|
|μ ± 2σ|**95%**|
|μ ± 3σ|**99.7%**|

### Exemple Pratique

**QI** : μ = 100, σ = 15

- 68% des gens ont un QI entre **85 et 115**
- 95% des gens ont un QI entre **70 et 130**
- 99.7% des gens ont un QI entre **55 et 145**

## Loi Normale Centrée Réduite

**Transformation** : Z = (X - μ) / σ

**Propriétés** :

- Z ~ N(0, 1)
- Moyenne = 0
- Écart-type = 1
- Permet de **standardiser** toute loi normale

## Table de la Loi Normale

|Valeur Z|P(Z ≤ z)|Interprétation|
|---|---|---|
|-3|0.0013|0.13% à gauche|
|-2|0.0228|2.28% à gauche|
|-1|0.1587|15.87% à gauche|
|0|0.5000|50% à gauche|
|1|0.8413|84.13% à gauche|
|2|0.9772|97.72% à gauche|
|3|0.9987|99.87% à gauche|

## Applications Courantes

### Phénomènes Naturels

- **Taille, poids** des individus
- **QI, notes** scolaires
- **Erreurs de mesure**
- **Temps de réaction**

### En Statistiques

- **Théorème Central Limite** : moyennes d'échantillons
- **Tests d'hypothèses** : test Z, test t
- **Intervalles de confiance**
- **Contrôle qualité**

## Vérification de la Normalité

### Tests Statistiques

- **Shapiro-Wilk** (n ≤ 50)
- **Kolmogorov-Smirnov**
- **Jarque-Bera**

### Méthodes Graphiques

- **Histogramme** : forme de cloche
- **Q-Q plot** : points alignés
- **Boîte à moustaches** : symétrique

### Critères Numériques

- **Asymétrie** ≈ 0 (skewness)
- **Aplatissement** ≈ 3 (kurtosis)
- **Moyenne ≈ Médiane ≈ Mode**

## Calculs Pratiques

### Probabilité P(a < X < b)

1. Standardiser : z₁ = (a-μ)/σ, z₂ = (b-μ)/σ
2. Utiliser la table : P(z₁ < Z < z₂) = Φ(z₂) - Φ(z₁)

### Quantiles

Pour trouver x tel que P(X ≤ x) = p :

1. Trouver z dans la table tel que Φ(z) = p
2. Calculer : x = μ + z×σ

## Formules Essentielles

### Fonction de Densité

f(x) = (1/(σ√(2π))) × e^(-½((x-μ)/σ)²)

### Fonction de Répartition

F(x) = P(X ≤ x) = Φ((x-μ)/σ)

### Standardisation

Z = (X - μ) / σ

## Points Clés à Retenir

✅ **La normale n'est qu'un modèle** - vérifier l'adéquation aux données réelles

✅ **68-95-99.7** : règle fondamentale à mémoriser

✅ **Symétrie parfaite** : P(X < μ) = P(X > μ) = 0.5

✅ **Valeurs extrêmes rares** : |z| > 3 représente moins de 0.3% des cas

✅ **Standardisation universelle** : toute normale devient N(0,1)

## Exemples d'Application

### Contrôle Qualité

- Diamètre vis : μ = 8mm, σ = 0.1mm
- 95% des vis entre 7.8mm et 8.2mm
- Si diamètre = 8.3mm → défaut (probabilité < 0.3%)

### Seuils de Décision

- Test médical : valeur normale si -2σ < résultat < +2σ
- Résultat "anormal" si |z| > 2 (probabilité < 5%)