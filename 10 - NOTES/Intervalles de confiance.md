---
MOC:
tags:
---
---
***Références :***

---

## Principe général

Un intervalle de confiance (IC) estime un **paramètre inconnu** de la population avec une **marge d'erreur**.

**Formule générale :** $$\text{Estimation} \pm \text{Valeur critique} \times \text{Erreur standard}$$

**Interprétation (95%)** : Si on répète l'étude 100 fois, environ 95 intervalles contiendront le vrai paramètre.

> [!warning] Attention L'IC ne dit PAS "il y a 95% de chances que le paramètre soit dans l'intervalle". Le paramètre est fixe, c'est l'intervalle qui varie !

---

## IC pour une moyenne

### Cas 1 : σ connu (rare en pratique)

$$\bar{x} \pm z_{\alpha/2} \times \frac{\sigma}{\sqrt{n}}$$

**Exemple :** Taille moyenne d'étudiants

- $\bar{x} = 170$ cm, σ = 10 cm, n = 50, niveau 95%
- $z_{0.025} = 1.96$
- IC : $170 \pm 1.96 \times \frac{10}{\sqrt{50}} = [167.2 ; 172.8]$ cm

### Cas 2 : σ inconnu (cas usuel)

$$\bar{x} \pm t_{\alpha/2, n-1} \times \frac{s}{\sqrt{n}}$$

**Conditions :**

- Distribution normale OU n ≥ 30
- Échantillon aléatoire

**Exemple :** Temps de livraison

- $\bar{x} = 2.3$ jours, s = 0.8 jour, n = 25, niveau 95%
- $t_{0.025, 24} = 2.064$
- IC : $2.3 \pm 2.064 \times \frac{0.8}{\sqrt{25}} = [1.97 ; 2.63]$ jours

---

## IC pour une proportion

$$\hat{p} \pm z_{\alpha/2} \times \sqrt{\frac{\hat{p}(1-\hat{p})}{n}}$$

**Conditions :**

- $n\hat{p} \geq 10$ et $n(1-\hat{p}) \geq 10$

**Exemple :** Taux de satisfaction

- 75 clients satisfaits sur 100 → $\hat{p} = 0.75$
- Niveau 95%, $z_{0.025} = 1.96$
- IC : $0.75 \pm 1.96 \times \sqrt{\frac{0.75 \times 0.25}{100}} = [0.665 ; 0.835]$
- Interprétation : entre 66.5% et 83.5% de satisfaction

---

## IC pour une différence de moyennes

### Groupes indépendants (variances égales)

$$(\bar{x}_1 - \bar{x}_2) \pm t_{\alpha/2, n_1+n_2-2} \times s_p \sqrt{\frac{1}{n_1} + \frac{1}{n_2}}$$

où $s_p = \sqrt{\frac{(n_1-1)s_1^2 + (n_2-1)s_2^2}{n_1+n_2-2}}$ (écart-type poolé)

**Interprétation :** Si l'IC contient 0, pas de différence significative entre les groupes.

---

## IC pour un coefficient de corrélation ⚠️

### Problème avec r directement

Le coefficient de corrélation r :

- Est borné : $-1 \leq r \leq 1$
- N'est pas normalement distribué (surtout si r proche de ±1)
- Distribution asymétrique

❌ On ne peut pas utiliser : $r \pm z \times SE_r$

### Solution : Transformation de Fisher

**Étape 1 - Transformer r en z :**

$$z = \frac{1}{2}\ln\left(\frac{1+r}{1-r}\right) = \text{arctanh}(r)$$

Cette transformation "linéarise" r :

- z suit approximativement une loi normale
- Variance stable : $Var(z) \approx \frac{1}{n-3}$

**Étape 2 - IC sur z :**

$$z \pm z_{\alpha/2} \times \frac{1}{\sqrt{n-3}}$$

**Étape 3 - Retransformer en r :**

$$r = \frac{e^{2z} - 1}{e^{2z} + 1} = \tanh(z)$$

### Exemple complet

**Données :** Corrélation entre heures d'étude et notes

- r = 0.65 (sur n = 30 étudiants)
- Niveau 95%

**Calcul :**

1. Transformation : $$z = \frac{1}{2}\ln\left(\frac{1+0.65}{1-0.65}\right) = 0.775$$
    
2. Erreur standard : $$SE_z = \frac{1}{\sqrt{30-3}} = \frac{1}{\sqrt{27}} = 0.192$$
    
3. IC sur z : $$0.775 \pm 1.96 \times 0.192 = [0.399 ; 1.151]$$
    
4. Retransformation :
    
    - Borne inf : $r = \tanh(0.399) = 0.38$
    - Borne sup : $r = \tanh(1.151) = 0.82$

**IC final :** $r \in [0.38 ; 0.82]$

**Interprétation :** On est confiant à 95% que la vraie corrélation entre heures d'étude et notes se situe entre 0.38 et 0.82 (corrélation positive modérée à forte).

> [!tip] Lien avec d'autres fiches La transformation de Fisher est aussi utilisée pour tester H₀: ρ = 0 → voir [[Test de corrélation]]

---

## Facteurs influençant la largeur de l'IC

**L'IC devient plus étroit si :**

- ✅ n augmente (plus de données = plus de précision)
- ✅ s diminue (moins de variabilité)
- ✅ Niveau de confiance diminue (90% vs 99%)

**Trade-off :** Précision vs Confiance

- IC 99% : plus large mais plus sûr
- IC 90% : plus étroit mais moins sûr

---

## Tableau récapitulatif

|Paramètre|Conditions|Formule|Distribution|
|---|---|---|---|
|Moyenne (σ connu)|n grand|$\bar{x} \pm z \frac{\sigma}{\sqrt{n}}$|Normale|
|Moyenne (σ inconnu)|Normale ou n≥30|$\bar{x} \pm t \frac{s}{\sqrt{n}}$|Student|
|Proportion|n grand|$\hat{p} \pm z\sqrt{\frac{\hat{p}(1-\hat{p})}{n}}$|Normale|
|Corrélation|n≥10|Via transformation de Fisher|Normale (sur z)|
