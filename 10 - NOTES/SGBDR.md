---
MOC: "[[PROGRAMMATION]]"
tags:
  - prog/bd
---
---
***Références :***

---

## 🎯 Définition

Un **SGBDR** (Système de Gestion de Bases de Données Relationnelles) est un logiciel qui permet de **créer, gérer et interroger** des bases de données fondées sur le **modèle relationnel** (tables, lignes, colonnes, relations).

Il garantit l'intégrité et la cohérence des données, notamment par l'application des principes **ACID**.

## 🏗️ Structure Fondamentale

| **Concept Relationnel** | **Représentation SQL**     | **Description**                                                           |
| ----------------------- | -------------------------- | ------------------------------------------------------------------------- |
| **Relation**            | **Table**                  | Stocke un ensemble d'entités de même type (ex: Clients, Commandes).       |
| **n-uplet**             | **Ligne / Enregistrement** | Un ensemble de valeurs décrivant une seule entité (ex: un client unique). |
| **Attribut**            | **Colonne / Champ**        | Un élément de donnée pour l'entité (ex: Nom, Adresse).                    |

## 🔗 Principes de Base (Clés et Relations)

| **Clé / Relation**    | **Définition**                                                                                    | **Rôle**                                                                           |
| --------------------- | ------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| **Clé Primaire (PK)** | Un attribut (ou ensemble d'attributs) qui identifie de façon **unique** chaque ligne d'une table. | Garantit l'unicité et sert de point d'ancrage.                                     |
| **Clé Étrangère(FK)** | Un attribut dans une table qui fait référence à la **Clé Primaire** d'une autre table.            | Crée des relations entre les tables et assure l'**intégrité référentielle**.       |
| **Relation**          | Le lien logique établi via les clés étrangères (ex: 1 à N, N à N).                                | Permet de lier des informations éparpillées pour éviter la Redondance des données. |

## 🛡️ Les Propriétés ACID

Le SGBDR garantit la fiabilité des transactions grâce aux propriétés **ACID** :

1. **Atomicity (Atomicité)** : Une transaction est traitée comme une unité indivisible. Soit toutes les opérations réussissent, soit aucune n'est effectuée.
    
2. **Consistency (Cohérence)** : Une transaction doit amener la base de données d'un état valide à un autre état valide. Les contraintes (clés, règles) sont respectées.
    
3. **Isolation (Isolation)** : L'exécution simultanée de plusieurs transactions conduit au même résultat qu'une exécution séquentielle. Une transaction ne voit pas les modifications d'une autre transaction en cours.
    
4. **Durability (Durabilité)** : Une fois qu'une transaction est validée (commit), ses modifications sont permanentes et survivent à toute panne du système.
    

## 📝 Langage de Requête

Le langage standard pour interagir avec un SGBDR est le **[[SQL]]** (Structured Query Language).

- **DDL** (Data Definition Language) : `CREATE TABLE`, `ALTER TABLE`, `DROP TABLE`.
    
- **DML** (Data Manipulation Language) : `SELECT`, `INSERT`, `UPDATE`, `DELETE`.
    
- **DCL** (Data Control Language) : `GRANT`, `REVOKE` (gestion des droits).
    

## 💡 Optimisation de Performance

- **Index SQL**: Structures qui accélèrent la recherche de données en fournissant un accès direct (similaire à l'index d'un livre). Très efficaces pour les clauses `WHERE` et `JOIN`.
    
- **Normalisation** : Processus de structuration de la base de données pour minimiser la redondance et améliorer l'intégrité des données (ex: 1NF, 2NF, 3NF).
    

## 🆚 SGBDR vs. NoSQL

| **Caractéristique** | **SGBDR (Relationnel)**                                                             | **NoSQL (Non Relationnel)**                                        |
| ------------------- | ----------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| **Modèle**          | Tabulaire (Lignes/Colonnes)                                                         | Document, Clé-Valeur, Graphe, etc.                                 |
| **Schéma**          | **Strict/Fixe** (Schéma-On-Write)                                                   | **Flexible/Dynamique** (Schéma-On-Read)                            |
| **Scalabilité**     | Principalement **Verticale** (montée en puissance du serveur)                       | Principalement **Horizontale** (ajout de serveurs)                 |
| **Transactions**    | Fortement **ACID**                                                                  | Souvent **BASE** (Compromis pour la performance et la scalabilité) |
| **Cas d'usage**     | Systèmes financiers, ERP, tout système nécessitant une haute intégrité des données. | Big Data, IoT, gestion de contenu, données en temps réel.          |

## 🛠️ Exemples de SGBDR

- **Open Source** :[[PostgreSQL]], MySQL, SQLite
    
- **Commerciaux** : Oracle Database, Microsoft SQL Server, IBM DB2
    

---

`#Database` `#SGBDR` `#SQL` `#ACID` `#ModèleRelationnel`
