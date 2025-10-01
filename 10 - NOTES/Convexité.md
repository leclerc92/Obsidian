---
MOC: "[[MATHS]]"
tags:
---

## Convexité et optimisation

### Convexité d'une fonction

**Définition :**
Une fonction f est **convexe** sur un domaine D si pour tous points x, y ∈ D et tout λ ∈ [0,1] :
$$f(\lambda x + (1-\lambda)y) \leq \lambda f(x) + (1-\lambda)f(y)$$

Elle est **strictement convexe** si l'inégalité est stricte pour λ ∈ ]0,1[.

**Test de convexité :**
- **Dimension 1** : f est convexe si $f''(x) \geq 0$ pour tout x
- **Dimension n** : f est convexe si la [[Matrice hessienne]] est semi-définie positive : $\nabla^2 f(x) \succeq 0$ pour tout x

**Pour l'optimisation :**

| Type de fonction | Point critique ($\nabla f(x^*) = 0$) | Conclusion |
|------------------|--------------------------------------|------------|
| Strictement convexe | Si existe | **Minimum global unique** ✓ |
| Convexe | Si existe | **Minimum global** (peut ne pas être unique) |
| Fonction générale | Si existe | Peut être min, max ou point-selle ⚠️ |

⚠️ **Important** : Une fonction strictement convexe ne garantit pas l'existence d'un minimum ! 
- Exemple : $f(x) = e^x$ sur $\mathbb{R}$ est strictement convexe mais n'a pas de minimum.
- Pour garantir l'existence : domaine compact OU fonction → +∞ aux bords.

---

### Convexité d'un ensemble (domaine)

Un ensemble D est **convexe** si pour tous points x, y ∈ D, le segment [x,y] est entièrement dans D :
$$\forall x, y \in D, \forall \lambda \in [0,1] : \lambda x + (1-\lambda)y \in D$$

**Visuellement** : si je trace une droite entre deux points du domaine, elle reste entièrement dans le domaine.

---

## Exemples

> [!example] Fonctions convexes
> - $f(x) = ax + b$ (affine, convexe mais pas strictement)
> - $f(x) = x^2$ (strictement convexe)
> - $f(x) = e^x$ (strictement convexe)
> - $f(x) = |x|$ (convexe mais pas strictement, car non différentiable en 0)
> - $f(x) = -\ln(x)$ pour x > 0 (strictement convexe)

> [!example] Ensembles convexes
> - Un disque
> - Un demi-plan
> - Un polyèdre
> - L'intersection de deux ensembles convexes
> 
> **Non convexes** : étoile, croissant de lune

---

## Propriété clé pour l'optimisation

**Théorème** : Pour une fonction convexe sur un ensemble convexe :
- Tout **minimum local** est un **minimum global**
- Si la fonction est strictement convexe, le minimum global est **unique** (s'il existe)