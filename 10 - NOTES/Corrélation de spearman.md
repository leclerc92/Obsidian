---
MOC:
tags:
---
---
***Références :***

---

## Principe

La corrélation de Spearman mesure **l'intensité de la relation monotone**entre deux variables en analysant leurs **rangs** plutôt que leurs valeurs brutes.

**Différence clé avec Pearson :**

- **Pearson (r)** : mesure la relation **linéaire** entre valeurs
- **Spearman (ρₛ)** : mesure la relation **monotone** entre rangs

> [!info] Relation monotone Une relation est monotone si quand X augmente, Y augmente toujours (ou diminue toujours), sans forcément être linéaire.
> 
> Exemples : Y = X², Y = log(X), Y = e^X

---

## Quand utiliser Spearman ?

### ✅ Situations idéales

1. **Relation non linéaire mais monotone**
    - Exemple : salaire vs années d'expérience (croissance logarithmique)
2. **Variables ordinales**
    - Échelles de Likert (1 à 5)
    - Classements, rangs
3. **Présence de valeurs extrêmes**
    - Spearman est robuste aux outliers
    - Les rangs "lissent" l'effet des valeurs aberrantes
4. **Distributions non normales**
    - Pas d'hypothèse de normalité requise
5. **Petit échantillon**
    - Fonctionne dès n ≥ 5 (mais test significatif nécessite n ≥ 10)

### ❌ Quand préférer Pearson

- Relation clairement **linéaire**
- Données **quantitatives continues** et **normales**
- Besoin de **R²** (variance expliquée) pour régression

---

## Formule

### Formule générale (toujours valable)

Spearman = Pearson appliqué aux rangs :

$ρs=\frac{∑(RXi−\bar{RX})(RYi−\bar{RY})}{∑(RXi−\bar{RX})^2∑(RYi−\bar{RY})^2}$


où :

- $RXi$​​ = rang de la i-ème observation de X
- $RYi​​$ = rang de la i-ème observation de Y

### Formule simplifiée (sans ex-aequo)

$ρs=1-\frac{6∑di^2}{n(n^2−1)}$

où :

- $di=RXi−RYi$​​ = différence entre les rangs
- $n$ = nombre d'observations

> [!warning] Attention La formule simplifiée n'est valable **QUE s'il n'y a AUCUN ex-aequo** dans les données !

---

## Exemple complet pas à pas

### Contexte : Notes de 6 étudiants

On veut savoir si les performances en Maths et Physique sont corrélées.

**Données brutes :**

|Étudiant|Note Maths (X)|Note Physique (Y)|
|---|---|---|
|Alice|15|14|
|Bob|12|10|
|Clara|18|17|
|David|10|12|
|Emma|14|15|
|Farid|16|16|

### Étape 1 : Attribuer les rangs

**Pour les Maths :** on classe de la plus petite à la plus grande note

|Note Maths|10|12|14|15|16|18|
|---|---|---|---|---|---|---|
|**Rang**|1|2|3|4|5|6|

**Pour la Physique :**

|Note Physique|10|12|14|15|16|17|
|---|---|---|---|---|---|---|
|**Rang**|1|2|3|4|5|6|

### Étape 2 : Tableau de travail

| Étudiant  | X   | RX​ | Y   | RY​ | di=RX−RY​  | di2​  |
| --------- | --- | --- | --- | --- | ---------- | ----- |
| Alice     | 15  | 4   | 14  | 3   | 4 - 3 = 1  | 1     |
| Bob       | 12  | 2   | 10  | 1   | 2 - 1 = 1  | 1     |
| Clara     | 18  | 6   | 17  | 6   | 6 - 6 = 0  | 0     |
| David     | 10  | 1   | 12  | 2   | 1 - 2 = -1 | 1     |
| Emma      | 14  | 3   | 15  | 4   | 3 - 4 = -1 | 1     |
| Farid     | 16  | 5   | 16  | 5   | 5 - 5 = 0  | 0     |
| **Total** |     |     |     |     |            | **4** |

ici on alors $ρs=0.886$

### Interprétation

**ρₛ = 0.886** : Corrélation **très forte et positive** entre les rangs en Maths et Physique.

→ Les étudiants qui performent bien en Maths tendent fortement à bien performer en Physique (et vice-versa).