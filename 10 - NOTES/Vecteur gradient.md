---
tags:
  - maths/algebre
---


---
***Références :***

---
## Définition

Le **gradient** d'une fonction scalaire f : ℝⁿ → ℝ est un **vecteur** qui contient toutes les [[Dérivée]] partielles de f.

### Notation mathématique

```
∇f(x₁, x₂, ..., xₙ) = grad f = [∂f/∂x₁, ∂f/∂x₂, ..., ∂f/∂xₙ]ᵀ
```

### Symboles utilisés

- **∇** (nabla) : opérateur gradient
- **grad f** : notation alternative
- **∂f/∂xᵢ** : dérivée partielle par rapport à xᵢ

## Cas particuliers

### Fonction à 2 variables

```
f(x,y) → ∇f = [∂f/∂x]
              [∂f/∂y]
```

### Fonction à 3 variables

```
f(x,y,z) → ∇f = [∂f/∂x]
                [∂f/∂y]
                [∂f/∂z]
```

## Interprétation géométrique

### 1. Direction de plus forte croissance

- Le gradient **pointe vers** la direction de **plus forte augmentation** de f
- Sa **norme** ||∇f|| donne le **taux de croissance maximal**

### 2. Orthogonalité aux courbes de niveau

- Le gradient est **perpendiculaire** aux courbes de niveau (isolignes)
- En 3D : perpendiculaire aux surfaces de niveau

### 3. Visualisation

```
      ∇f ↗
     /
────●──── courbe de niveau f(x,y) = c
```

## Propriétés fondamentales

### Linéarité

```
∇(αf + βg) = α∇f + β∇g
```

### Règle du produit

```
∇(fg) = f∇g + g∇f
```

### Règle de la chaîne

Si h(x) = f(g(x)), alors :

```
∇h = (∇f ∘ g) · J_g
```

où J_g est la matrice jacobienne de g.

### Gradient d'une composition

```
∇f(g(x)) = (∇f)(g(x)) · ∇g(x)
```

## Calcul pratique

### Exemple 1 : Fonction de [[forme quadratique]]

```
f(x,y) = x² + 3y² - 2xy + 5x

∇f = [∂f/∂x] = [2x - 2y + 5]
     [∂f/∂y]   [6y - 2x]
```

### Exemple 2 : Fonction exponentielle

```
f(x,y) = e^(x²+y²)

∇f = [2xe^(x²+y²)]
     [2ye^(x²+y²)]
```

### Exemple 3 : Fonction à 3 variables

```
f(x,y,z) = xyz + x² - z³

∇f = [yz + 2x ]
     [xz.     ]
     [xy - 3z²]
```

## Applications majeures

### 1. Optimisation

**Condition nécessaire d'optimalité :**

- Point critique : **∇f = 0**
- Maximum local : ∇f = 0 et [[Matrice hessienne]] définie négative
- Minimum local : ∇f = 0 et [[Matrice hessienne]] définie positive

### 2. Algorithmes de descente

**Descente de gradient :**

```
x_{k+1} = x_k - α∇f(x_k)
```

où α > 0 est le pas d'apprentissage.

### 3. Physique

- **Champ de forces** : F = -∇U (potentiel U)
- **Flux de chaleur** : proportionnel à -∇T (température T)
- **Champ électrique** : E = -∇V (potentiel V)

### 4. Apprentissage automatique

- **Rétropropagation** dans les réseaux de neurones
- **Optimisation** des fonctions de coût
- **Régression linéaire** : minimisation par gradient

## Relation avec d'autres concepts

### Dérivée directionnelle

Pour un vecteur unitaire u :

```
D_u f = ∇f · u = ||∇f|| cos θ
```

où θ est l'angle entre ∇f et u.

### Matrice hessienne

```
H_f = ∇(∇f) = [∂²f/∂x₁∂x₁  ∂²f/∂x₁∂x₂  ...]
               [∂²f/∂x₂∂x₁  ∂²f/∂x₂∂x₂  ...]
               [     ⋮           ⋮       ⋱ ]
```

### Jacobienne

Pour f : ℝⁿ → ℝᵐ :

- Si m = 1 : Jacobienne = gradient transposé
- Si m > 1 : Jacobienne = matrice des gradients

## Exemples d'interprétation

### Géographie

- **f(x,y)** = altitude au point (x,y)
- **∇f** = direction de plus forte pente
- **||∇f||** = inclinaison de la pente

### Économie

- **f(x,y)** = profit en fonction de deux variables
- **∇f = 0** = optimum de profit
- **Direction de ∇f** = comment ajuster les variables pour maximiser le profit

### Machine Learning

- **f(θ)** = fonction de coût (erreur)
- **∇f** = direction d'augmentation de l'erreur
- **-∇f** = direction pour réduire l'erreur (descente)

## Cas particuliers utiles

### Fonctions quadratiques

```
f(x) = ½xᵀAx + bᵀx + c
∇f(x) = Ax + b
```

### Norme euclidienne au carré

```
f(x) = ||x||² = xᵀx
∇f(x) = 2x
```

### Fonction log-vraisemblance

```
f(x) = log(g(x))
∇f(x) = ∇g(x)/g(x)
```

## Remarques importantes

⚠️ **Attention :** Le gradient n'existe que si toutes les dérivées partielles existent et sont continues.

💡 **Intuition :** Le gradient "montre le chemin le plus raide vers le haut"

🎯 **Application pratique :** En optimisation, on va dans la direction **opposée** au gradient pour minimiser (descente de gradient)

⚡ **Vitesse :** La norme ||∇f|| indique à quelle vitesse la fonction change dans la direction optimale

## FLASHCARD
TARGET DECK
Mathematics

START
Basic
This is a test 23444.
Back: $\frac{3}{4}$
TEST DE CONTINUITE SUR LIGNE 
<!--ID: 1759786136184-->
END

