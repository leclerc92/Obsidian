---
MOC:
tags:
---
---
***Références :***

---
## 📜 Qu'est-ce que le SQL ?

Le **SQL** (Structured Query Language) est le langage standard utilisé pour **gérer et manipuler les bases de données relationnelles** (SGBDR) comme PostgreSQL, MySQL, SQL Server, Oracle, etc.

Le SQL se divise en plusieurs sous-langages :

1. **DDL** (Data Definition Language) : Pour **définir** la structure de la base (créer, modifier, supprimer des tables).
    
2. **DML** (Data Manipulation Language) : Pour **manipuler** les données dans les tables (sélectionner, insérer, mettre à jour, supprimer).
    
3. **DCL** (Data Control Language) : Pour **contrôler** les accès et les permissions (octroyer, révoquer des droits).
    
4. **TCL** (Transaction Control Language) : Pour gérer les **transactions** (valider ou annuler des modifications).
    

---

## 1. DDL : Définition des Données (Structure)

Ces commandes servent à créer et modifier la structure de la base.

|**Commande**|**Objectif**|**Syntaxe Essentielle**|
|---|---|---|
|**`CREATE TABLE`**|Créer une nouvelle table.|`CREATE TABLE NomTable (col1 Type, col2 Type NOT NULL, ...);`|
|**`ALTER TABLE`**|Modifier la structure d'une table existante (ajouter/supprimer colonne, modifier un type, ajouter une contrainte).|`ALTER TABLE NomTable ADD COLUMN nouvelleCol Type;`|
|**`DROP TABLE`**|Supprimer une table et toutes ses données de manière définitive.|`DROP TABLE NomTable;`|

**Exemple de `CREATE TABLE` :**

SQL

```
CREATE TABLE Employes (
    id SERIAL PRIMARY KEY,
    nom VARCHAR(100) NOT NULL,
    departement VARCHAR(50),
    salaire DECIMAL(10, 2),
    date_embauche DATE
);
```

---

## 2. DML : Manipulation des Données (Requêtes Essentielles)

Ces commandes sont les plus utilisées pour interagir avec les données.

### A. Récupération des Données : `SELECT` (La plus importante)

|**Clause**|**Rôle**|**Exemple**|
|---|---|---|
|**`SELECT`**|Spécifie les **colonnes** à retourner.|`SELECT nom, salaire`|
|**`FROM`**|Spécifie la **table** source.|`FROM Employes`|
|**`WHERE`**|Filtre les **lignes** selon une condition.|`WHERE departement = 'IT'`|
|**`GROUP BY`**|Regroupe les lignes ayant les mêmes valeurs pour appliquer des **fonctions d'agrégation**(SUM, COUNT, AVG, MAX, MIN).|`GROUP BY departement`|
|**`HAVING`**|Filtre les **groupes** créés par `GROUP BY` (similaire à `WHERE`, mais pour les groupes).|`HAVING COUNT(*) > 5`|
|**`ORDER BY`**|Trie les résultats. `ASC` (Ascendant, par défaut) ou `DESC` (Descendant).|`ORDER BY salaire DESC`|
|**`LIMIT`**|Limite le nombre de résultats retournés.|`LIMIT 10`|

**Exemple Complet de `SELECT` :**

SQL

```
SELECT
    departement,
    COUNT(*) AS nombre_employes,
    AVG(salaire) AS salaire_moyen
FROM
    Employes
WHERE
    date_embauche > '2020-01-01'
GROUP BY
    departement
HAVING
    AVG(salaire) > 50000.00
ORDER BY
    salaire_moyen DESC;
```

### B. Modification des Données

|**Commande**|**Objectif**|**Syntaxe Essentielle**|
|---|---|---|
|**`INSERT`**|Ajouter de **nouvelles lignes** de données dans une table.|`INSERT INTO NomTable (col1, col2) VALUES (val1, val2);`|
|**`UPDATE`**|**Modifier** les données dans les lignes existantes. **ATTENTION :** Ne jamais oublier la clause `WHERE` pour éviter de mettre à jour toutes les lignes.|`UPDATE NomTable SET col1 = nouv_val WHERE condition;`|
|**`DELETE`**|**Supprimer** des lignes de données. **ATTENTION :** Ne jamais oublier la clause `WHERE`.|`DELETE FROM NomTable WHERE condition;`|

**Exemples :**

SQL

```
-- Insertion
INSERT INTO Employes (nom, departement, salaire)
VALUES ('Jean Dupont', 'RH', 45000.00);

-- Mise à jour
UPDATE Employes
SET salaire = 60000.00
WHERE nom = 'Jean Dupont';

-- Suppression
DELETE FROM Employes
WHERE departement = 'Stagiaire' AND date_embauche < '2024-01-01';
```

---

## 3. `JOIN` : Joindre les Tables

Les bases de données relationnelles stockent les données dans plusieurs tables liées entre elles par des clés (généralement des **clés primaires** et des **clés étrangères**). La clause `JOIN` permet de combiner des lignes de deux tables ou plus.

|**Type de JOIN**|**Résultat**|**Mot-clé**|
|---|---|---|
|**`INNER JOIN`**|Retourne les lignes lorsqu'il y a une **correspondance** dans **les deux tables**.|`JOIN` ou `INNER JOIN`|
|**`LEFT JOIN`**|Retourne **toutes les lignes de la table de gauche** et les lignes correspondantes de la table de droite (met `NULL` si pas de correspondance).|`LEFT JOIN` ou `LEFT OUTER JOIN`|
|**`RIGHT JOIN`**|Retourne **toutes les lignes de la table de droite** et les lignes correspondantes de la table de gauche (met `NULL` si pas de correspondance).|`RIGHT JOIN` ou `RIGHT OUTER JOIN`|
|**`FULL JOIN`**|Retourne **toutes les lignes** des deux tables, avec des valeurs `NULL` pour les colonnes non correspondantes.|`FULL JOIN` ou `FULL OUTER JOIN`|

**Exemple de `JOIN` :**

Supposons une table `Commandes` liée à la table `Employes` par un `employe_id`.

SQL

```
SELECT
    E.nom,
    C.montant,
    C.date_commande
FROM
    Employes AS E  -- Alias de la table Employes
INNER JOIN
    Commandes AS C -- Alias de la table Commandes
ON
    E.id = C.employe_id
WHERE
    C.montant > 1000;
```

---

## 4. Contraintes et Clés

Les contraintes sont des règles appliquées aux colonnes pour maintenir l'intégrité et la qualité des données.

|**Contrainte**|**Description**|
|---|---|
|**`PRIMARY KEY`** (PK)|Identifiant unique pour chaque ligne (une seule par table). **Implique `NOT NULL` et `UNIQUE`**.|
|**`FOREIGN KEY`** (FK)|Crée un lien entre deux tables. Assure que la valeur de la colonne existe dans la table parente.|
|**`NOT NULL`**|Empêche l'insertion de valeurs manquantes (`NULL`).|
|**`UNIQUE`**|Assure que toutes les valeurs d'une colonne sont différentes.|
|**`CHECK`**|Force toutes les valeurs d'une colonne à satisfaire une condition spécifique (ex: âge > 18).|
|**`DEFAULT`**|Fournit une valeur par défaut pour une colonne.|
