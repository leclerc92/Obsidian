---
MOC: "[[NOTIONS DE PROGRAMMATION]]"
tags:
  - prog/javascript
---
---
***Références :***
- https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/WeakMap
- https://fr.w3docs.com/apprendre-javascript/weakmap-and-weakset.html

---

Les WeakMap est une collection de paires clés-valeur ou *les clé doivent etre des objets*.

Contrairement à une Map, Si l'objet clé n'est plus referencé ailleurs, il pourra etre récuperée par le garbage-collector

**Exemple d'utilisation :**
- Associer des données privées à des objets DOM (index, metadonnées)
- Eviter les fuites de memoire
- Encapsulation (pas de collision avec d'autres proprieté de l'objet)

**Méthodes principales :**
- set(clé,val)
- get(clé)
- has(clé)
- delete(clé)

> [!warning]
> On ne peut pas iterer sur les entrées. Il n'y a donc pas de proprieté size





