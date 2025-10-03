---
MOC: "[[MATHS]]"
tags:
  - maths/stats
---


## L'idée en une phrase

**Tirer des conclusions sur une population entière à partir d'un échantillon limité.**

On ne peut pas tout mesurer → on mesure un échantillon → on généralise avec un niveau de confiance.

---

## Exemple fil rouge : Temps de charge d'une app

**Contexte :** Tu développes une app mobile et veux savoir si le temps de chargement est acceptable.

- **Population** : Tous les utilisateurs potentiels (millions) → μ = ?
- **Échantillon** : 100 utilisateurs testés → $\bar{x} = 2,3$ secondes, $s = 0,8$ sec
- **Question** : Le temps moyen est-il vraiment < 3 secondes ?

**Deux approches possibles :**

### 1️⃣ Estimation : "Quelle est la valeur probable ?"

➜ **Intervalle de confiance à 95%**

- Résultat : [2,1 ; 2,5] secondes
- Interprétation : "On est confiant à 95% que le vrai temps moyen se situe entre 2,1 et 2,5 sec"

### 2️⃣ Test : "Mon hypothèse est-elle crédible ?"

➜ **Test d'hypothèse**

- H₀ : μ = 3 secondes (l'app est trop lente)
- H₁ : μ < 3 secondes (l'app est assez rapide)
- Test t de Student → p-value = 0,001
- Conclusion : On rejette H₀, l'app est significativement plus rapide que 3 sec ✓

---

## Le processus en 4 étapes


1. COLLECTER
   └─ Échantillon représentatif (n observations)

2. DÉCRIRE
   └─ [[STATISTIQUES DESCRIPTIVES]] (x̄, s, médiane...)

3. INFÉRER
   ├─ Estimer → [[Intervalles de confiance]]
   └─ Tester → Tests d'hypothèses

4. CONCLURE
   └─ Interpréter dans le contexte réel


---

## Quel test choisir ? Arbre de décision


Je veux comparer quoi ?
│
├─ UNE MOYENNE
│  ├─ σ connu → Test Z
│  └─ σ inconnu → Test de Student
│
├─ DEUX MOYENNES
│  ├─ Groupes indépendants → Test t indépendant
│  └─ Groupes appariés (avant/après) → Test t apparié
│
├─ 3+ MOYENNES
│  └─ ANOVA
│
├─ UNE PROPORTION
│  └─ Test Z proportion
│
├─ DEUX VARIABLES QUALITATIVES
│  └─ Test du Chi²
│
└─ RELATION ENTRE 2 VARIABLES QUANTITATIVES
   └─ Corrélation et Régression linéaire


> [!tip] Données pas normales ou petit échantillon ? → Utilise les Tests non-paramétriques

---

## Les 3 concepts clés

### 1. Distribution d'échantillonnage

Si je répète mon étude 1000 fois, j'obtiens 1000 $\bar{x}$ différents → ils suivent une distribution.

**Théorème Central Limite :** Pour n ≥ 30, cette distribution est approximativement normale !

### 2. Niveau de confiance (1 - α)

- **95%** = si je répète l'étude 100 fois, 95 intervalles contiendront le vrai paramètre
- Souvent α = 0,05 (5% d'erreur acceptée)

### 3. P-value

Probabilité d'observer nos données (ou plus extrêmes) SI H₀ était vraie.

- p < 0,05 → résultat "significatif" → on rejette H₀
- p ≥ 0,05 → pas assez de preuves → on garde H₀

> [!warning] Attention !
> 
> - Significatif ≠ important dans la pratique
> - Corrélation ≠ causalité
> - p-value ≠ "probabilité que H₀ soit vraie"

---

## Fiches détaillées

### Concepts de base

- Population vs Échantillon
- Théorème Central Limite
- [[Loi Normale]]

### Estimation

- Estimation ponctuelle
- Intervalles de confiance
- Taille d'échantillon

### Tests d'hypothèses

- Tests d'hypothèses - Méthodologie
- Erreurs Type I et II
- Puissance d'un test

### Tests paramétriques

- Test de Student
- Test Z
- Test du Chi²
- ANOVA

### Autres

- Tests non-paramétriques
- Conditions d'application des tests
- Distributions de référence

---


## Formules express

|Besoin|Formule|Conditions|
|---|---|---|
|IC moyenne|$\bar{x} \pm t \times \frac{s}{\sqrt{n}}$|σ inconnu|
|IC proportion|$\hat{p} \pm z \times \sqrt{\frac{\hat{p}(1-\hat{p})}{n}}$|n grand|
|Test t|$t = \frac{\bar{x} - \mu_0}{s/\sqrt{n}}$|σ inconnu|
|Test χ²|$\chi^2 = \sum \frac{(O-E)^2}{E}$|Variables catégorielles|

> Pour les formules détaillées, voir les fiches spécifiques de chaque test.