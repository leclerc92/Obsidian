---
MOC: "[[PROGRAMMATION]]"
tags:
  - prog/bd
---
---
***Références :***

---

le MLD permet de valider la conformité du [[MCD]].
Il premet de détaillé l'implementation pour un model spécifique de base de donnée relationnelle.
Il peut est sous forme de diagramme complémentaire au MCD ou sous forme syntaxique.

## traduction du MCD

Les **entités** définies dans le MCD seront traduit syntaxiquement en **table**.
Les **attributs** de chaque entités seront **listés entre parenthese**
**l'identifiant** devient alors la **clé primaire** (premier element souligné)

```
avatars(i̲d̲, path, is_valid)
users(i̲d̲, email, password, registered_at, role)
comments(i̲d̲, content, published_at)
articles(i̲d̲, title, description, content, published_at)
categories(i̲d̲, name
```


## Clé etrangère

> [!information]
> La clé étrangères commence par un # et contient de nom de l'entité référencée suivi de _id : 
> **\#user_id**

### **relation 1:1**

La table qui contient cette clé etrangère est : 
- Au choix si les deux tables on la même cardianlité (0,1 et 0,1 ou 1,1 et 1,1)
- La table pouvant avoir une unicité nulle (0,1 et 1:1) -> la table 0,1 prendra cette clé etrangère

```
avatars(i̲d̲, path, is_valid, #user_id)
users(i̲d̲, email, password, registered_at, role)
comments(i̲d̲, content, published_at)
articles(i̲d̲, title, description, content, published_at)
categories(i̲d̲, name)
```

*Dans cet exemple, un user peut uploader un avatar ou non, donc la clé etrangère est mise dans la table avatars*.

### **relation 1:n**

La table qui contient la clé étrangère est celle qui se situe du coté n de la relation : 

```
avatars(i̲d̲, path, is_valid, #user_id)
users(i̲d̲, email, password, registered_at, role)
comments(i̲d̲, content, published_at, #user_id, #article_id)
articles(i̲d̲, title, description, content, published_at, #user_id)
categories(i̲d̲, name)
```

Dans cet exemple : 
- Un utilisateur publie **0,N** commentaire
- un commenraire est publié par **1,1** users --> contient la clé etrangère

- Un utilisateur oublie **0,N** articles
- Un article est publié par **1,1** users --> contient la clé étrangère 

- Un article contient **0,N** commentaires
- un commentaire est contenu dans **1:1** article --> contient la clé étrangère 

## Table de liaison 

### **Relation n:n**

Une table de liaison est une table contenant seulement les clés étrangères des deux entité. Le couple de clé étrangère constitue la clé primaire de la table 

> [!tip]
> On nomme cette table avec les deux nom des entités séparés par un __
> On peut egalement ajouté un verbe entre les deux : souvent get


```
avatars(i̲d̲, path, is_valid, #user_id)
users(i̲d̲, email, password, registered_at, role)
comments(i̲d̲, content, published_at, #user_id, #article_id)
articles(i̲d̲, title, description, content, published_at, #user_id)
categories(i̲d̲, name)
articles_get_categories(#̲a̲r̲t̲i̲c̲l̲e̲_̲i̲d̲, #̲c̲a̲t̲e̲g̲o̲r̲y̲_̲i̲d̲)
```

*article_id et categori_id sont souligné car ils constituent tous les deux la clé primaire de la table* 

ici on à la création d'un table de laison car : 
- un article possede 0,N catégorie 
- une catégorie possède 0,N articles
Les deux entité sont du coté N, alors on ajoute une table liaison.

