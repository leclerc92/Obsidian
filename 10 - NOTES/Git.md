---
MOC: "[[DEVOBS]]"
tags:
---
---
***Références :***

---





## ⚙️ Configuration Initiale

```bash
# Configuration globale de l'utilisateur
git config --global user.name "Votre Nom"
git config --global user.email "votre.email@example.com"

# Configuration de l'éditeur par défaut
git config --global core.editor "code --wait"  # VS Code
git config --global core.editor "vim"          # Vim

# Voir toutes les configurations
git config --list
git config --global --list

# Voir une configuration spécifique
git config user.name
git config user.email

# Configuration locale (pour un projet spécifique)
git config user.name "Nom pour ce projet"
git config user.email "email@projet.com"
```

## 🚀 Initialisation et Clonage

```bash
# Initialiser un nouveau repository local
git init
git init <nom_dossier>

# Cloner un repository distant
git clone <url_repository>
git clone <url> <nom_dossier>

# Cloner seulement la dernière version (shallow clone)
git clone --depth 1 <url>

# Cloner une branche spécifique
git clone -b <nom_branche> <url>
```

## 📄 État et Suivi des Fichiers

```bash
# Voir l'état du repository
git status
git status -s  # Version courte

# Ajouter des fichiers au staging area
git add <fichier>
git add .              # Tous les fichiers modifiés
git add *.js          # Tous les fichiers .js
git add -A            # Tous les fichiers (même supprimés)

# Retirer des fichiers du staging area
git reset <fichier>
git reset             # Retirer tous les fichiers

# Voir les différences
git diff              # Différences non stagées
git diff --staged     # Différences stagées
git diff --cached     # Alias pour --staged
git diff <fichier>    # Différences pour un fichier spécifique

# Voir l'historique des commits
git log
git log --oneline     # Version condensée
git log --graph       # Avec graphique
git log --all --graph --oneline  # Toutes les branches
git log -p            # Avec les différences
git log -<n>          # Les n derniers commits
git log --author="nom"  # Commits d'un auteur
git log --since="2 weeks ago"  # Depuis une date

# Voir les détails d'un commit
git show <hash_commit>
git show HEAD         # Dernier commit
git show HEAD~1       # Avant-dernier commit
```

## 💾 Commits et Modifications

```bash
# Faire un commit
git commit -m "Message de commit"
git commit -am "Message"  # Add + commit (fichiers trackés)

# Modifier le dernier commit
git commit --amend -m "Nouveau message"
git commit --amend --no-edit  # Garder le même message

# Commits vides (pour déclencher des actions CI/CD)
git commit --allow-empty -m "Commit vide"

# Annuler des modifications
git checkout -- <fichier>    # Annuler modifications non stagées
git checkout .               # Annuler toutes les modifications
git restore <fichier>        # Nouvelle syntaxe (Git 2.23+)
git restore --staged <fichier>  # Retirer du staging area

# Supprimer des fichiers
git rm <fichier>             # Supprimer et stager la suppression
git rm --cached <fichier>    # Supprimer du tracking sans supprimer le fichier
```

## 🌿 Gestion des Branches

```bash
# Lister les branches
git branch                   # Branches locales
git branch -r               # Branches distantes
git branch -a               # Toutes les branches

# Créer une nouvelle branche
git branch <nom_branche>
git checkout -b <nom_branche>  # Créer et basculer
git switch -c <nom_branche>    # Nouvelle syntaxe (Git 2.23+)

# Basculer entre les branches
git checkout <nom_branche>
git switch <nom_branche>      # Nouvelle syntaxe

# Renommer une branche
git branch -m <ancien_nom> <nouveau_nom>
git branch -m <nouveau_nom>   # Renommer la branche courante

# Supprimer une branche
git branch -d <nom_branche>   # Suppression sécurisée
git branch -D <nom_branche>   # Suppression forcée

# Supprimer une branche distante
git push origin --delete <nom_branche>
```

## 🔀 Merge et Rebase

```bash
# Fusionner une branche
git merge <nom_branche>
git merge --no-ff <nom_branche>  # Conserver l'historique de merge

# Annuler un merge en cours
git merge --abort

# Rebase
git rebase <branche_base>
git rebase -i <commit>        # Rebase interactif
git rebase --continue         # Continuer après résolution de conflit
git rebase --abort            # Annuler le rebase

# Cherry-pick (appliquer un commit spécifique)
git cherry-pick <hash_commit>
```

## 🌐 Repositories Distants

```bash
# Voir les repositories distants
git remote -v

# Ajouter un repository distant
git remote add <nom> <url>
git remote add origin <url>

# Modifier l'URL d'un remote
git remote set-url origin <nouvelle_url>

# Supprimer un remote
git remote remove <nom>

# Récupérer les modifications distantes
git fetch                    # Récupérer sans merger
git fetch origin
git fetch --all             # Tous les remotes

# Récupérer et merger
git pull                    # git fetch + git merge
git pull origin <branche>
git pull --rebase          # Utiliser rebase au lieu de merge

# Envoyer les modifications
git push
git push origin <branche>
git push -u origin <branche>  # Définir upstream
git push --all              # Toutes les branches
git push --tags             # Pousser les tags
```

## 🏷️ Tags

```bash
# Lister les tags
git tag
git tag -l "v1.*"          # Tags correspondant à un pattern

# Créer un tag
git tag <nom_tag>          # Tag léger
git tag -a <nom_tag> -m "Message"  # Tag annoté

# Créer un tag sur un commit spécifique
git tag <nom_tag> <hash_commit>

# Supprimer un tag
git tag -d <nom_tag>       # Local
git push origin --delete <nom_tag>  # Distant

# Pousser les tags
git push origin <nom_tag>
git push --tags
```

## 🔍 Recherche et Navigation

```bash
# Rechercher dans les fichiers
git grep "texte_recherché"
git grep -n "texte"        # Avec numéros de ligne
git grep -i "texte"        # Insensible à la casse

# Voir qui a modifié quoi (blame)
git blame <fichier>
git blame -L 10,20 <fichier>  # Lignes 10 à 20

# Trouver quand un bug a été introduit
git bisect start
git bisect bad             # Marquer le commit actuel comme défaillant
git bisect good <commit>   # Marquer un commit comme bon
git bisect reset           # Terminer la recherche

# Navigation dans l'historique
git checkout <hash_commit>  # Se déplacer vers un commit
git checkout HEAD~1        # Commit précédent
git checkout HEAD~5        # 5 commits en arrière
git checkout -            # Retourner à la branche précédente
```

## 🔄 Annulation et Récupération

```bash
# Annuler un commit (crée un nouveau commit inverse)
git revert <hash_commit>
git revert HEAD            # Annuler le dernier commit

# Reset (attention : destructif)
git reset --soft HEAD~1   # Garde les modifications stagées
git reset --mixed HEAD~1  # Garde les modifications (défaut)
git reset --hard HEAD~1   # Supprime tout

# Récupérer des commits "perdus"
git reflog                 # Voir l'historique des références
git checkout <hash_du_reflog>

# Nettoyer le répertoire de travail
git clean -f              # Supprimer fichiers non trackés
git clean -fd             # Supprimer fichiers et dossiers
git clean -n              # Voir ce qui serait supprimé (dry-run)
```

## 📦 Stash (Remisage)

```bash
# Remiser les modifications
git stash                  # Remiser les modifications
git stash push -m "Message"  # Avec message
git stash -u              # Inclure les fichiers non trackés

# Voir les stashes
git stash list

# Appliquer un stash
git stash apply           # Dernier stash (le garde)
git stash pop             # Dernier stash (le supprime)
git stash apply stash@{1} # Stash spécifique

# Supprimer des stashes
git stash drop stash@{1}  # Supprimer un stash spécifique
git stash clear           # Supprimer tous les stashes

# Créer une branche depuis un stash
git stash branch <nom_branche> stash@{1}
```

## 🔧 Outils et Utilitaires

```bash
# Voir les statistiques d'un repository
git shortlog -sn          # Nombre de commits par auteur
git log --stat            # Statistiques des modifications

# Archiver le projet
git archive --format=zip --output=projet.zip HEAD
git archive --format=tar.gz --output=projet.tar.gz HEAD

# Nettoyer le repository
git gc                    # Garbage collection
git fsck                  # Vérifier l'intégrité

# Configurer des alias
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.unstage 'reset HEAD --'
git config --global alias.last 'log -1 HEAD'
git config --global alias.visual '!gitk'
```

## 📂 Fichiers Spéciaux

### .gitignore

```bash
# Exemples de patterns pour .gitignore
*.log                     # Tous les fichiers .log
node_modules/             # Dossier node_modules
.env                      # Fichier d'environnement
temp/                     # Dossier temp
*.tmp                     # Fichiers temporaires
!important.log           # Exception (ne pas ignorer)

# Ajouter un fichier déjà tracké au .gitignore
git rm --cached <fichier>
echo "<fichier>" >> .gitignore
git add .gitignore
git commit -m "Ignore <fichier>"
```

### .gitattributes

```bash
# Exemples pour .gitattributes
*.pdf binary             # Traiter les PDF comme binaires
*.sh text eol=lf         # Forcer les fins de ligne Unix
*.bat text eol=crlf      # Forcer les fins de ligne Windows
```

## 🔀 Workflows Courants

### Feature Branch Workflow

```bash
# Créer une nouvelle feature
git checkout main
git pull origin main
git checkout -b feature/nouvelle-fonctionnalite

# Développer la feature
git add .
git commit -m "Implémenter nouvelle fonctionnalité"
git push -u origin feature/nouvelle-fonctionnalite

# Merger la feature (après code review)
git checkout main
git pull origin main
git merge --no-ff feature/nouvelle-fonctionnalite
git push origin main
git branch -d feature/nouvelle-fonctionnalite
```

### Hotfix Workflow

```bash
# Créer un hotfix depuis main
git checkout main
git pull origin main
git checkout -b hotfix/correction-critique

# Corriger le bug
git add .
git commit -m "Corriger bug critique"
git push -u origin hotfix/correction-critique

# Merger vers main et develop
git checkout main
git merge --no-ff hotfix/correction-critique
git push origin main

git checkout develop
git merge --no-ff hotfix/correction-critique
git push origin develop

git branch -d hotfix/correction-critique
```

## 💡 Tips et Bonnes Pratiques

### Messages de Commit

```bash
# Format recommandé pour les messages de commit
git commit -m "type(scope): description courte

Description plus détaillée si nécessaire.

- Point important 1
- Point important 2

Fixes #123"

# Types courants :
# feat: nouvelle fonctionnalité
# fix: correction de bug
# docs: documentation
# style: formatage, point-virgules manquants, etc.
# refactor: restructuration du code
# test: ajout de tests
# chore: maintenance, mise à jour de dépendances
```

### Aliases Utiles

```bash
# Ajouter ces alias à votre ~/.gitconfig
[alias]
    st = status
    co = checkout
    br = branch
    ci = commit
    df = diff
    lg = log --oneline --graph --decorate --all
    unstage = reset HEAD --
    last = log -1 HEAD
    amend = commit --amend --no-edit
    pushf = push --force-with-lease
    cleanup = "!git branch --merged | grep -v '\\*\\|main\\|develop' | xargs -n 1 git branch -d"
```

### Commandes d'Urgence

```bash
# J'ai committé sur la mauvaise branche
git reset --soft HEAD~1   # Annuler le commit, garder les changements
git checkout <bonne_branche>
git add .
git commit -m "Bon message"

# J'ai pushé des credentials par erreur
git reset --hard HEAD~1   # Supprimer le commit localement
git push --force-with-lease origin <branche>  # Forcer le push

# Récupérer un fichier supprimé
git checkout HEAD~1 -- <fichier_supprimé>

# Synchroniser une fork avec l'upstream
git remote add upstream <url_original>
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```