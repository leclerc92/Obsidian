---
MOC: "[[02 - SOUSDOMAINE/maths/OPTIMISATION|OPTIMISATION]]"
tags:
---

Les problèmes d'optimisation consistent à chercher le minimum ou le maximum d'une fonction (recherche d'optimum)

## **Conditions nécessaires d'optimalité**

### Minimum local
Si x* est un **minimum local** de f, alors **nécessairement** :

1. **Condition du premier ordre** : $\nabla f(x^*) = 0$ ([[Vecteur gradient]])
2. **Condition du second ordre** : $\nabla^2 f(x^*) \succeq 0$ ([[Matrice hessienne]] semi-définie positive)

Les points vérifiant $\nabla f(x^*) = 0$ sont appelés **points critiques** ou **points stationnaires**.

> [!warning]
> Ces conditions sont nécessaires mais **pas suffisantes** ! Un point critique peut être un minimum, un maximum ou un point-selle.

---

## **Conditions suffisantes d'optimalité**

### Minimum local strict
Si les conditions suivantes sont vérifiées, alors x* est **suffisamment** un **minimum local strict** :

1. $\nabla f(x^*) = 0$
2. $\nabla^2 f(x^*) \succ 0$ (Hessienne **définie positive**)

### Maximum local strict
Si les conditions suivantes sont vérifiées, alors x* est **suffisamment** un **maximum local strict** :

1. $\nabla f(x^*) = 0$
2. $\nabla^2 f(x^*) \prec 0$ (Hessienne **définie négative**)

---

## **Récapitulatif**

| Condition | Hessienne | Conclusion |
|-----------|-----------|------------|
| $\nabla f(x^*) = 0$ | $\nabla^2 f(x^*) \succ 0$ | **Minimum local strict** ✓ |
| $\nabla f(x^*) = 0$ | $\nabla^2 f(x^*) \prec 0$ | **Maximum local strict** ✓ |
| $\nabla f(x^*) = 0$ | $\nabla^2 f(x^*) \succeq 0$ | **Peut-être** un minimum (test non concluant) |
| $\nabla f(x^*) = 0$ | Hessienne indéfinie | **Point-selle** |



