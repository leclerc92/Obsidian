---
MOC:
tags:
  - maths/stats
---
## C'est quoi concrètement ?

La loi normale est le **modèle de distribution la plus courante** dans la nature et les sciences. Elle décrit la majorité des phénomènes naturels : la taille des gens, les notes aux examens, les erreurs de mesure, etc.

**Représentation** : une courbe en forme de cloche, symétrique.

```
        Plus fréquent
             ▲
             │     ╱╲
             │    ╱  ╲
             │   ╱    ╲
             │  ╱      ╲___
             │_╱____________
                   Valeurs
            μ-3σ   μ   μ+3σ
```

## Les 2 paramètres qui la définissent

### Moyenne (μ) : le centre

- Détermine **où** se situe le pic
- Les données s'agglomèrent autour de cette valeur

### Écart-type (σ) : la largeur
l'[[écart type]]  permet les choses suivantes : 

- Détermine **l'étalement** de la courbe
- σ grand = courbe plate et large
- σ petit = courbe pointue et étroite

**Notation** : X ~ N(μ, σ²)

---

## La règle incontournable : 68-95-99.7

Cela détermine **combien de données se situent dans chaque zone** :

|Zone|Pourcentage|Signification|
|---|---|---|
|μ ± 1σ|68%|Les **deux tiers** des données|
|μ ± 2σ|95%|Presque **tout le monde**|
|μ ± 3σ|99.7%|Quasi-universel|

### Exemple concret : les QI

**QI moyen** = 100, **écart-type** = 15

- 68% des gens ont un QI entre **85 et 115**
- 95% des gens ont un QI entre **70 et 130**
- 99.7% des gens ont un QI entre **55 et 145**

→ Quelqu'un avec un QI de 145+ est dans les **0.15%** les plus brillants

---

## Comment l'utiliser ?

### 1️⃣ Vérifier si vos données suivent une loi normale

Avant de faire des calculs, demandez-vous :

- ✅ L'histogramme a-t-il une forme de cloche ?
- ✅ Moyenne ≈ Médiane ≈ Mode ?
- ✅ Les données sont-elles symétriques ?

**Cas d'usage** : contrôle qualité, tests statistiques, prédictions

### 2️⃣ Calculer une probabilité

**Question** : "Quelle proportion de vis sont défectueuses ?"

1. Standardiser votre valeur : $Z = (X - μ) / σ$
2. Utiliser la table de la loi normale
3. Lire le résultat

**Exemple** : vis de 8.3mm, μ=8mm, σ=0.1mm

- $Z = (8.3 - 8) / 0.1 = 3$
- Probabilité d'être aussi extrême : **< 0.3%** → vis défectueuse

### 3️⃣ Trouver un seuil

**Question** : "À partir de quel score on juge ça 'anormal' ?"

- Fixer un niveau de confiance (ex: 95%)
- Utiliser la table inverse
- Calculer : $x = μ + Z × σ$

**Exemple médical** : Un résultat est "anormal" s'il est au-delà de μ ± 2σ (cas = 5% des gens)

---

## La Table Rapide

Vous n'avez pas besoin de la mémoriser, mais voici les valeurs clés :

|Z|P(Z ≤ z)|Interprétation|
|---|---|---|
|-2|2.28%|Très bas|
|-1|15.87%|Bas|
|0|50%|La moyenne|
|+1|84.13%|Haut|
|+2|97.72%|Très haut|
|+3|99.87%|Extrême|

---

## Cas d'usage réels

### 📊 Contrôle qualité

Vérifier que 95% de la production est conforme (μ ± 2σ)

### 🎓 Éducation

Évaluer les performances : une note est-elle exceptionnelle ?

### 🏥 Médecine

Définir les seuils "normal/anormal" pour les analyses

### 📈 Business

Évaluer les performances commerciales par rapport à la moyenne

---

## Checklist d'utilisation

- [ ] Mes données forment une cloche sur l'histogramme ?
- [ ] J'ai calculé la moyenne (μ) et l'écart-type (σ) ?
- [ ] Je dois trouver une probabilité, un seuil, ou valider une hypothèse ?
- [ ] J'ai standardisé ma valeur en Z-score ?
- [ ] J'ai vérifié le résultat avec la table ou un outil ?