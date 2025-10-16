---
MOC: "[[PROGRAMMATION]]"
tags:
  - prog/bd
---
---
***Références :***

---

## 🚀 Introduction à PostgreSQL

**PostgreSQL** est un **système de gestion de base de données relationnelle et objet (SGBDRO)** libre et open-source, reconnu pour sa robustesse, sa conformité aux normes [[SQL]] et ses fonctionnalités avancées.

### 📌 L'outil psql

**`psql`** est l'utilitaire en ligne de commande de PostgreSQL. Il permet d'interagir directement avec la base de données pour exécuter des requêtes SQL et des **méta-commandes** (qui commencent par `\`). Ces méta-commandes sont spécifiques à `psql` et ne sont pas du SQL standard.

## 🛠️ Connexion et Généralités

| **Commande**                     | **Raccourci** | **Description**                                                                                                                                                         |
| -------------------------------- | ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `psql -U user -d dbname -h host` |               | **Connexion** à la base de données `dbname` en tant que `user` sur le `host`. Omettez `-h` et `-d`pour des valeurs par défaut (utilisateur actuel et base de même nom). |
| `\q`                             |               | **Quitter** l'interface `psql`.                                                                                                                                         |
| `\h`                             |               | Aide sur les commandes SQL (ex: `\h SELECT`).                                                                                                                           |
| `\?`                             |               | **Aide** sur les méta-commandes de `psql`.                                                                                                                              |
| `\c [dbname] [user]`             |               | Se **connecter** à une autre base de données ou en tant qu'un autre utilisateur.                                                                                        |
| `\l` ou `\list`                  |               | **Lister** toutes les bases de données disponibles sur le serveur.                                                                                                      |
| `\l+`                            |               | Lister les bases de données avec plus de détails (taille, description, etc.).                                                                                           |
| `\timing`                        |               | Activer/Désactiver l'affichage du **temps d'exécution** des requêtes.                                                                                                   |
| `\x`                             |               | Activer/Désactiver le mode **affichage étendu** (utile pour les tables larges).                                                                                         |
| `\e`                             |               | **Ouvrir l'éditeur de texte** pour modifier la commande SQL ou psql en cours.                                                                                           |
| `\s`                             |               | Afficher l'**historique** des commandes.                                                                                                                                |

---

## 🔎 Commandes d'Inspection des Objets (`\d...`)

Ces commandes permettent d'inspecter les objets de la base de données (tables, index, vues, etc.). Le format général est `\d[type][+] [pattern]`. Le `+` ajoute des détails.

| **Commande**    | **Raccourci** | **Description**                                                                                    | **Exemple** |
| --------------- | ------------- | -------------------------------------------------------------------------------------------------- | ----------- |
| `\d`            |               | Lister les **tables, vues, séquences, vues matérialisées et tables étrangères** du schéma courant. | `\d`        |
| `\d table_name` |               | Décrire la **structure d'une table** (colonnes, types, contraintes, index, etc.).                  | `\d users`  |
| `\dt`           |               | Lister les **tables** (uniquement).                                                                | `\dt`       |
| `\dv`           |               | Lister les **vues**.                                                                               | `\dv`       |
| `\di`           |               | Lister les **index**.                                                                              | `\di`       |
| `\ds`           |               | Lister les **séquences**.                                                                          | `\ds`       |
| `\dn`           |               | Lister les **schémas** (namespaces).                                                               | `\dn`       |
| `\db`           |               | Lister les **tablespaces** (espaces de stockage).                                                  | `\db`       |
| `\df`           |               | Lister les **fonctions**.                                                                          | `\df`       |
| `\du` ou `\dg`  |               | Lister les **rôles** (utilisateurs et groupes).                                                    | `\du`       |
| `\dp`           |               | Lister les **droits d'accès** (privilèges) pour les tables, vues et séquences.                     | `\dp`       |
| `\dx`           |               | Lister les **extensions** installées.                                                              | `\dx`       |
| `\d+ *`         |               | Lister toutes les contraintes                                                                      |             |
| `\dt+`          |               | Lister la taille des tables & indexs                                                               |             |

### 💡 Note sur les Filtres

Vous pouvez filtrer la sortie des commandes d'inspection en ajoutant un **motif** (pattern) :

- `\dt u*` : Liste les tables dont le nom commence par `u`.
    
- `\d+ users` : Décrit la table `users` avec des informations supplémentaires (taille, description...).
    

---

## ⚙️ Administration et Configuration

|**Commande**|**Description**|
|---|---|
|`\set`|Affiche toutes les variables `psql` actuelles.|
|`\set VAR_NAME value`|Définit une variable `psql` (ex: `\set PAGE_SIZE 50`).|
|`SHOW all;`|Affiche tous les **paramètres de configuration** du serveur PostgreSQL.|
|`SHOW nom_parametre;`|Affiche la valeur d'un paramètre spécifique (ex: `SHOW work_mem;`).|
|`\g` ou `\g;`|Répète la dernière commande SQL exécutée.|
|`\gexec`|Exécute la requête précédente et traite chaque ligne de résultat comme une commande à exécuter. **ATTENTION :** très puissant, à utiliser avec prudence.|

---

## 📂 Commandes Shell et Fichiers

|**Commande**|**Description**|
|---|---|
|`\! [commande]`|Exécute une **commande shell** (système d'exploitation) sans quitter `psql`.|
|`\i filename`|**Exécuter** les commandes contenues dans le fichier `filename` (utile pour les scripts SQL).|
|`\o filename`|Rediriger la **sortie** des prochaines requêtes vers un fichier.|
|`\o`|Arrêter la redirection de sortie.|

---
