---
MOC: "[[MATHS]]"
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

Les statistiques inférentielles permettent de **généraliser** les résultats d'un échantillon à une population entière et de **prendre des décisions** sous incertitude.

## Concepts Fondamentaux

### Population vs Échantillon

- **Population** : ensemble complet étudié (paramètres : μ, σ, π)
- **Échantillon** : sous-ensemble de la population (statistiques : x̄, s, p̂)

### Distribution d'Échantillonnage

- Distribution théorique d'une statistique calculée sur tous les échantillons possibles
- **Théorème Central Limite** : pour n ≥ 30, x̄ suit approximativement une loi normale

## Estimation

### Estimation Ponctuelle

- **Estimateur** : règle de calcul (x̄ pour μ)
- **Estimation** : valeur numérique obtenue
- **Propriétés** : sans biais, convergent, efficace

### Estimation par Intervalle (Intervalle de Confiance)

- **Formule générale** : estimation ± marge d'erreur
- **Niveau de confiance** : 1 - α (souvent 95% ou 99%)

#### IC pour une moyenne (σ connu)

x̄ ± z_{α/2} × (σ/√n)

#### IC pour une moyenne (σ inconnu)

x̄ ± t_{α/2} × (s/√n)

#### IC pour une proportion

p̂ ± z_{α/2} × √(p̂(1-p̂)/n)

## Tests d'Hypothèses

### Étapes du Test

1. **Hypothèses** : H₀ (nulle) vs H₁ (alternative)
2. **Seuil de signification** : α (souvent 0,05)
3. **Statistique de test** et sa distribution sous H₀
4. **Valeur critique** ou **p-value**
5. **Décision** : rejeter ou ne pas rejeter H₀
6. **Conclusion** en contexte

### Types d'Erreurs

- **Erreur Type I (α)** : rejeter H₀ vraie
- **Erreur Type II (β)** : accepter H₀ fausse
- **Puissance** : 1 - β (probabilité de rejeter H₀ fausse)

### P-value

Probabilité d'observer une valeur au moins aussi extrême que celle observée, sous H₀.

- **p < α** : résultat significatif → rejeter H₀
- **p ≥ α** : résultat non significatif → ne pas rejeter H₀

## Tests Paramétriques

### Test de Student (t)

#### Une moyenne (σ inconnu)

- **H₀** : μ = μ₀
- **Statistique** : t = (x̄ - μ₀)/(s/√n)
- **ddl** : n - 1

#### Deux moyennes indépendantes

- **H₀** : μ₁ = μ₂
- **Statistique** : t = (x̄₁ - x̄₂)/s_pooled × √(1/n₁ + 1/n₂)

#### Deux moyennes appariées

- **H₀** : μ_d = 0
- **Statistique** : t = x̄_d/(s_d/√n)

### Test de la Normale (Z)

#### Une moyenne (σ connu)

- **Statistique** : z = (x̄ - μ₀)/(σ/√n)

#### Une proportion

- **H₀** : π = π₀
- **Statistique** : z = (p̂ - π₀)/√(π₀(1-π₀)/n)

### Test du χ² (Chi-deux)

#### Indépendance

- **H₀** : variables indépendantes
- **Statistique** : χ² = Σ(O_i - E_i)²/E_i
- **ddl** : (r-1)(c-1)

#### Adéquation

- **H₀** : distribution suit le modèle théorique

### ANOVA (Analyse de Variance)

#### À un facteur

- **H₀** : μ₁ = μ₂ = ... = μₖ
- **Statistique** : F = VCE/VCR
- Compare la variance entre groupes / dans les groupes

## Tests Non-Paramétriques

### Conditions d'Utilisation

- Échantillons petits (n < 30)
- Données non normales
- Variables ordinales
- Conditions des tests paramétriques non respectées

### Principaux Tests

- **Mann-Whitney** : comparer deux groupes indépendants
- **Wilcoxon** : comparer deux groupes appariés
- **Kruskal-Wallis** : comparer k groupes indépendants
- **χ² d'indépendance** : association entre variables qualitatives

## Distributions de Référence

### [[Loi Normale]] N(μ,σ²)

- **Centrée réduite** : Z ~ N(0,1)
- **Règle empirique** : 68%-95%-99.7%

### Loi de Student t(ν)

- **ddl** : ν = n - 1
- Plus aplatie que la normale
- Converge vers N(0,1) quand ν → ∞

### Loi du χ² (ν)

- **ddl** : ν
- Asymétrique positive
- Variance = 2ν

### Loi de Fisher F(ν₁,ν₂)

- **ddl** : ν₁ (numérateur), ν₂ (dénominateur)
- Rapport de deux χ²

## Conditions d'Application

### Tests Paramétriques

1. **Normalité** des données ou grands échantillons
2. **Indépendance** des observations
3. **Homoscédasticité** (égalité des variances)

### Vérifications

- **Test de Shapiro-Wilk** : normalité
- **Test de Levene** : égalité des variances
- **Graphiques Q-Q** : normalité visuelle

## Taille d'Échantillon

### Estimation

n = (z_{α/2} × σ / E)² où E = marge d'erreur souhaitée

### Test d'hypothèses

Dépend de α, β, et taille d'effet attendue

## Points Clés à Retenir

1. **Toujours vérifier** les conditions d'application
2. **p-value ≠ probabilité que H₀ soit vraie**
3. **Significatif ≠ important** (différence pratique vs statistique)
4. **Corrélation ≠ causalité**
5. **Interpréter** les IC autant que les tests
6. **Tests multiples** : ajuster le seuil α (Bonferroni)

## Formules Essentielles

|Test|Statistique|Distribution|
|---|---|---|
|t (1 moy.)|t = (x̄-μ₀)/(s/√n)|t(n-1)|
|z (1 moy.)|z = (x̄-μ₀)/(σ/√n)|N(0,1)|
|z (1 prop.)|z = (p̂-π₀)/√(π₀(1-π₀)/n)|N(0,1)|
|χ² indép.|χ² = Σ(O-E)²/E|χ²((r-1)(c-1))|
|F (ANOVA)|F = VCE/VCR|F(k-1,n-k)|
