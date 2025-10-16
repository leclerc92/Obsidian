---
MOC: "[[STATISTIQUES]]"
tags:
---

### L'idée en une phrase

**Tirer des conclusions sur une population entière à partir d'un échantillon limité.**

On ne peut pas tout mesurer → on mesure un échantillon → on généralise avec un niveau de confiance.

## Exemple fil rouge : Temps de charge d'une app

**Contexte :** Tu développes une app mobile et veux savoir si le temps de chargement est acceptable.

- **Population** : Tous les utilisateurs potentiels (millions) → $\mu = ?$
    
- **Échantillon** : 100 utilisateurs testés → $\bar{x} = 2,3$ secondes, $s = 0,8$ sec
    
- **Question** : Le temps moyen est-il vraiment < 3 secondes ?
    

**Deux approches possibles :**

### 1️⃣ Estimation : "Quelle est la valeur probable ?"

➜ **[[Intervalles de confiance]]**

- Résultat : [2,1 ; 2,5] secondes
    
- Interprétation : "On est confiant à 95% que le vrai temps moyen se situe entre 2,1 et 2,5 sec"
    

### 2️⃣ Test : "Mon hypothèse est-elle crédible ?"

➜ **Test d'hypothèse**

- $H_0$ : $\mu = 3$ secondes (l'app est trop lente)
    
- $H_1$ : $\mu < 3$ secondes (l'app est assez rapide)
    
- Test t de Student → $p$-value = 0,001
    
- Conclusion : On rejette $H_0$, l'app est significativement plus rapide que 3 sec $\checkmark$
    

---

## Le processus en 4 étapes

1. COLLECTER $\rightarrow$ Échantillon représentatif ($n$ observations)
    
2. DÉCRIRE $\rightarrow$ **[[STATISTIQUES DESCRIPTIVES]]** ($\bar{x}$, $s$, médiane...)
    
3. INFÉRER
    
    - Estimer $\rightarrow$ **[[Intervalles de confiance]]**
        
    - Tester $\rightarrow$ Tests d'hypothèses
        
4. CONCLURE $\rightarrow$ Interpréter dans le contexte réel
    

---

## Quel test choisir ? Arbre de décision

|**Je veux comparer quoi ?**|**Test Paramétrique Recommandé**|
|---|---|
|UNE MOYENNE ($\sigma$ inconnu)|Test de Student|
|DEUX MOYENNES (indépendantes)|Test $t$ indépendant|
|**RELATION entre 2 VARIABLES QUANTITATIVES**|**[[Test de corrélation]]** et Régression linéaire|
|DEUX VARIABLES QUALITATIVES|Test du Chi²|
|3+ MOYENNES|ANOVA|

> [!tip] Données pas normales ou petit échantillon ? $\rightarrow$ Utilise les **Tests non-paramétriques**

---

## Les 3 concepts clés

### 1. Distribution d'échantillonnage

- **Théorème Central Limite :** Pour $n \ge 30$, cette distribution est approximativement **[[Loi Normale]]** !
    

### 2. Niveau de confiance ($1 - \alpha$)

- $95\%$ = si je répète l'étude 100 fois, 95 intervalles contiendront le vrai paramètre.
    
- Souvent $\alpha = 0,05$ ($5\%$ d'erreur acceptée).
    

### 3. P-value

- Probabilité d'observer nos données (ou plus extrêmes) **SI** $H_0$ était vraie.
    
- $p < 0,05 \rightarrow$ résultat "significatif" $\rightarrow$ on rejette $H_0$
    

---

## Fiches détaillées

### Concepts de base

- Population vs Échantillon
    
- Théorème Central Limite
    
- **[[Loi Normale]]**
    

### Estimation

- Estimation ponctuelle
    
- **[[Intervalles de confiance]]**
    
- Taille d'échantillon
    

### Tests d'hypothèses

- Tests d'hypothèses - Méthodologie
    
- Erreurs Type I et II
    
- Puissance d'un test
    
- **[[Test de corrélation]]** _(Nœud clé pour tester la signification des relations)_
    

### Tests paramétriques

- Test de Student
    
- Test Z
    
- Test du Chi²
    
- ANOVA