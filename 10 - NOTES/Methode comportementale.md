---
tags:
  - prog/test
---


---
***Références :***

---


*Principe :*

On découpe les données selon leur SENS MÉTIER/LOGIQUE, pas selon leur format

#### Exemple concret  

*Fonction à tester :* `triang(Side1, Side2, Side3)`
- Entrée : 3 entiers (longueurs des côtés)
- Sortie : Type de triangle (Scalene, Isosceles, Equilateral, Invalid)

**Étape 1 : identifier les caracteristiques syntaxiques**

***Paramètres :***
- *Side1, Side2, Side3* (longueurs des côtés)

***Domaine de données :***
- *Type : Valeurs entières*

***Caracteristique :***
- *"Classification géometrique"* --> comportement attendu


**Étape 2 : Determiner les classes d'équivalence

*Version basique*

| Classe          | Description              | Exemple (Side1, Side2, Side3) |
| --------------- | ------------------------ | ----------------------------- |
| **Scalène**     | 3 côtés différents       | (4, 5, 6)                     |
| **Isocèle**     | 2 côtés égaux            | (3, 3, 4)                     |
| **Équilatéral** | 3 côtés égaux            | (3, 3, 3)                     |
| **Invalide**    | Ne forme pas un triangle | (3, 4, 8)                     |

--- 
## 🔄 Différence d'approche

### Syntaxique :

- ✅ "Side1 > 0 ?" → Structure des données
- ✅ Frontières numériques (0, 1, >1, <0)

### Comportementale (maintenant) :

- ✅ "Forme un triangle scalène ?" → Logique métier
- ✅ Classifications géométriques et règles de gestion