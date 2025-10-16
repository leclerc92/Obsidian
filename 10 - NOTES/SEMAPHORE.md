---
MOC: "[[NOTIONS DE PROGRAMMATION]]"
tags:
---
---

_**Références :**_

- https://fr.wikipedia.org/wiki/Sémaphore_(informatique)
- https://sites.uclouvain.be/SyllabusC/notes/Theorie/Threads/coordination.html

---

# Définition

Un sémaphore est une variable (ou un type de donnée abstrait) partagée par différents « acteurs », qui garantit que ceux-ci ne peuvent y accéder que de façon séquentielle à travers des opérations atomiques, et constitue la méthode utilisée couramment pour restreindre l'accès à des ressources partagées (par exemple un espace de stockage) et synchroniser les processus dans un environnement de programmation concurrente.

Le sémaphore a été inventé par Edsger Dijkstra et utilisé pour la première fois dans le système d'exploitation THE Operating system. Les sémaphores fournissent la solution la plus courante pour le fameux problème du « dîner des philosophes », bien qu'ils ne permettent pas d'éviter tous les interblocages (ou deadlocks).

Pour pouvoir exister sous forme logicielle, ils nécessitent une implémentation matérielle (au niveau du microprocesseur), permettant de tester et modifier la variable protégée au cours d'un cycle insécable. En effet, dans un contexte de multiprogrammation, on ne peut prendre le risque de voir la variable modifiée par un autre processus juste après que le processus courant vient de la tester et avant qu'il ne la modifie.

---

# Historique

- **Inventeur** : Edsger Dijkstra (1965)
- **Première utilisation** : Système d'exploitation THE (Technische Hogeschool Eindhoven)
- **Contexte** : Solution fondamentale au problème de synchronisation dans les systèmes multiprogrammés
- **Évolution** : Concept étendu et formalisé, devenant un élément central de la programmation concurrente

---

# Types de sémaphores

## Sémaphore binaire

- Peut prendre deux valeurs : 0 ou 1
- Similaire à un verrou (mutex)
- Sert principalement à l'exclusion mutuelle
- Un seul processus peut tenir le sémaphore à la fois

## Sémaphore de comptage (ou sémaphore général)

- Peut prendre n'importe quelle valeur entière non-négative
- Représente le nombre de ressources disponibles
- Permet à plusieurs processus d'accéder à une ressource limitée simultanément
- Exemple : gestion d'un pool de 5 connexions à une base de données

---

# Opérations principales

## Opération P (ou Wait) - Prise

```
P(semaphore) :
  tant que (semaphore == 0) {
    attendre
  }
  semaphore = semaphore - 1
  (opération atomique)
```

- **Effet** : Décrémente le sémaphore
- **Blocage** : Si le sémaphore est 0, le processus est mis en attente
- Le processus entre en section critique

## Opération V (ou Signal) - Libération

```
V(semaphore) :
  semaphore = semaphore + 1
  (opération atomique)
```

- **Effet** : Incrémente le sémaphore
- **Réveil** : Débloque un processus en attente (s'il y en a)
- Le processus sort de la section critique

---

# Mécanismes de synchronisation

## Exclusion mutuelle

Un sémaphore binaire utilisé pour garantir qu'un seul processus accède à une ressource critique à la fois.

```
semaphore mutex = 1

Processus A:        Processus B:
P(mutex)           P(mutex)
section critique   attente...
V(mutex)           P(mutex) - obtenu
                   section critique
                   V(mutex)
```

## Synchronisation productive

Un sémaphore de comptage utilisé pour gérer l'accès à plusieurs instances d'une ressource.

```
semaphore ressources = 3
// Trois processus peuvent accéder simultanément
```

---

# Problèmes résolus

## Problème du dîner des philosophes

Les sémaphores offrent une solution classique où chaque baguette est un sémaphore binaire, et chaque philosophe doit acquérir deux sémaphores pour manger.

## Problème producteur-consommateur

- Sémaphore `vide` : nombre de places libres dans le buffer
- Sémaphore `plein` : nombre de données disponibles
- Synchronisation entre producteurs et consommateurs

## Accès à des ressources limitées

Exemple : imprimante partagée, accès à la base de données, pool de threads

---

# Avantages

- **Atomicité garantie** : Les opérations P et V sont indivisibles
- **Simplicité** : Concept élémentaire et facile à comprendre
- **Performance** : Implémentation matérielle efficace
- **Flexibilité** : Applicable à divers contextes de synchronisation
- **Standard** : Présent dans la plupart des langages et systèmes d'exploitation

---

# Limitations et inconvénients

- **Pas d'évitement de deadlock** : Les sémaphores ne préviennent pas naturellement les interblocages
- **Erreurs de programmation** : Facile d'oublier une opération P ou V, causant des blocages ou des accès concurrents
- **Pas d'ordre de réveil garanti** : Quand plusieurs processus attendent, l'ordre de réveil peut sembler arbitraire
- **Manque de structuration** : Contrairement aux moniteurs ou aux variables de condition, peu de structure syntaxique
- **Inversion de priorité** : Un processus haute priorité peut être bloqué par un processus basse priorité

---

# Implémentation matérielle requise

Pour fonctionner correctement, les sémaphores nécessitent :

- **Instructions atomiques** : Test-and-set (TAS) ou Compare-and-swap (CAS)
- **Cycle insécable** : Garantir qu'on ne peut pas être interrompu pendant P ou V
- **Gestion des files d'attente** : Au niveau du système d'exploitation, pour gérer les processus bloqués

Sans ces garanties, deux processus pourraient concurremment modifier le sémaphore, créant des conditions de course.

---

# Comparaison avec autres mécanismes

|Mécanisme|Avantages|Inconvénients|
|---|---|---|
|**Sémaphore**|Simple, performant, flexible|Erreurs faciles, pas de structure|
|**Mutex**|Plus simple (sémaphore binaire)|Moins flexible que sémaphore général|
|**Moniteur**|Structure, sûreté|Plus lourd, moins performant|
|**Variables de condition**|Contrôle fin, lisibilité|Complexité supplémentaire|
|**Verrous-lecteurs**|Parallélisme pour lectures|Plus complexe à implémenter|

---

# Exemples en pseudo-code

## Producteur-Consommateur avec sémaphores

```
semaphore plein = 0      // Nombre d'éléments en attente
semaphore vide = N       // Places libres dans le buffer
semaphore mutex = 1      // Exclusion mutuelle

Producteur:              Consommateur:
  produire()             P(plein)
  P(vide)                P(mutex)
  P(mutex)               retirer_buffer()
  ajouter_buffer()       V(mutex)
  V(mutex)               V(vide)
  V(plein)               consommer()
```

---

# Points clés à retenir

1. Les sémaphores sont des variables partagées protégeant l'accès aux ressources critiques
2. Les opérations P (wait) et V (signal) sont **atomiques**
3. Sémaphores binaires = exclusion mutuelle ; sémaphores généraux = gestion de ressources multiples
4. Solution fondamentale mais nécessitant une discipline de programmation stricte
5. Problèmes potentiels : deadlocks, livelocks, et erreurs de programmation