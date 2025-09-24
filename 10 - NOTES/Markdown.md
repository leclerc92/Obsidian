---
MOC: "[[PRODUCTIVITE]]"
---

---
***Références :***

---





## 📝 Syntaxe de Base

### Titres

```markdown
# Titre 1
## Titre 2
### Titre 3
#### Titre 4
##### Titre 5
###### Titre 6
```

### Formatage du Texte

```markdown
**Gras** ou __Gras__
*Italique* ou _Italique_
***Gras et italique***
~~Barré~~
`Code inline`
```

### Listes

```markdown
- Liste à puces
  - Sous-élément
- Autre élément

1. Liste numérotée
2. Deuxième élément
   3. Sous-numérotation

- [ ] Case à cocher vide
- [x] Case cochée
```

### Liens et Images

```markdown
[Texte du lien](URL)
![Alt text](chemin/image.png)
[Lien avec titre](URL "Titre au survol")
```

## 🔗 Fonctionnalités Obsidian

### Liens Internes

```markdown
[[Nom de la note]]
[[Nom de la note|Texte affiché]]
[[Note#Section]]
[[Note#^bloc-id]]
```

### Tags

```markdown
#tag
#tag/sous-tag
#tag-avec-tirets
```

### Blocs de Code

````markdown
```python
def hello():
    print("Hello World!")
```
````

### Citations

```markdown
> Citation simple
> Citation sur plusieurs lignes
> continue ici

> Citation imbriquée
>> Citation de niveau 2
```

### Tableaux

```markdown
| Colonne 1 | Colonne 2 | Colonne 3 |
|-----------|-----------|-----------|
| Cellule 1 | Cellule 2 | Cellule 3 |
| Data A    | Data B    | Data C    |
```

### Ligne Horizontale

```markdown
---
***
___
```

### Échappement de Caractères

```markdown
\* Astérisque littéral
\_ Underscore littéral
\# Dièse littéral
\[ Crochet littéral
```

### HTML dans Markdown

```markdown
<strong>Gras en HTML</strong>
<em>Italique en HTML</em>
<u>Souligné</u>
<br> <!-- Saut de ligne -->
```

## 🔧 Syntaxe Avancée

### Tableaux avec Alignement

```markdown
| Gauche | Centré | Droite |
|:-------|:------:|-------:|
| A      |   B    |      C |
| D      |   E    |      F |
```

### Listes de Définition

```markdown
Terme 1
:   Définition 1

Terme 2
:   Définition 2
:   Définition alternative
```

### Références de Liens

```markdown
[Texte du lien][ref]
[Texte avec référence implicite][]

[ref]: https://example.com "Titre"
[Texte avec référence implicite]: https://example.com
```

### Notes de Bas de Page

```markdown
Texte avec note[^1]

[^1]: Contenu de la note de bas de page
```

## 💡 Bonnes Pratiques

### Structure de Document

1. **Un seul H1** par document
2. **Hiérarchie logique** des titres (H1 → H2 → H3)
3. **Lignes vides** autour des éléments de bloc
4. **Cohérence** dans la syntaxe choisie

### Lisibilité

- **Limitez la largeur** des lignes (80-100 caractères)
- **Utilisez des listes** pour organiser l'information
- **Espacez les sections** avec des lignes vides
- **Soyez cohérent** dans l'utilisation des symboles

### Compatibilité

- **Préférez `*` à `_`** pour l'italique et le gras
- **Utilisez les backticks** pour le code inline
- **Échappez les caractères spéciaux** si nécessaire
- **Testez** dans différents parseurs Markdown

---

_Fiche de référence Markdown standard_ 📝