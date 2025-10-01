---
MOC: "[[DEVOBS]]"
---


---
***Références :***

---

## Définition

SSH est un protocole de communication sécurisé permettant de se connecter à distance à un serveur via une connexion chiffrée. Il remplace les protocoles non sécurisés comme Telnet.

**Utilisations principales :**
- Connexion à distance à un serveur
- Transfert de fichiers sécurisé (SCP, SFTP)
- Authentification auprès de services (GitHub, GitLab)
- Tunneling et redirection de ports

## ==Création d'une clé SSH==

### Générer une paire de clés
```bash
ssh-keygen -t ed25519 -C "ton.email@example.com"
````

**Options :**

- `-t ed25519` : Type de clé (recommandé, plus sûr et rapide que RSA)
- `-t rsa -b 4096` : Alternative RSA si ed25519 non supporté
- `-C "commentaire"` : Commentaire pour identifier la clé

**Processus interactif :**

1. **Nom du fichier** : Appuyer sur Entrée pour `~/.ssh/id_ed25519` (par défaut)
2. **Passphrase** : Mot de passe pour protéger la clé (fortement recommandé !)

### Fichiers générés

Emplacement : `~/.ssh/` (ou `/home/nom_utilisateur/.ssh/`)

|Fichier|Type|Description|
|---|---|---|
|`id_ed25519`|Privée|⚠️ **À NE JAMAIS partager !**|
|`id_ed25519.pub`|Publique|À copier sur les serveurs/services|

---

## Configuration SSH

### Fichier de configuration (`~/.ssh/config`)

Créer ou éditer le fichier pour simplifier les connexions :

bash

```bash
# Serveur de production
Host prod
    HostName 192.168.1.100
    User admin
    Port 22
    IdentityFile ~/.ssh/id_ed25519

# GitHub
Host github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_github

# Serveur avec bastion
Host serveur-interne
    HostName 10.0.0.50
    User user
    ProxyJump bastion.example.com
```

**Avantages** : `ssh prod` au lieu de `ssh admin@192.168.1.100`

### Permissions correctes (important !)

bash

```bash
chmod 700 ~/.ssh              # Dossier
chmod 600 ~/.ssh/id_ed25519   # Clé privée
chmod 644 ~/.ssh/id_ed25519.pub  # Clé publique
chmod 600 ~/.ssh/config       # Fichier de config
```

---

## Utilisation des clés SSH

### Copier la clé publique sur un serveur

**Méthode automatique (recommandée) :**

bash

```bash
ssh-copy-id user@serveur
```

**Méthode manuelle :**

bash

```bash
# 1. Afficher la clé publique
cat ~/.ssh/id_ed25519.pub

# 2. Se connecter au serveur avec mot de passe
ssh user@serveur

# 3. Ajouter la clé dans le fichier authorized_keys
echo "ta_clé_publique" >> ~/.ssh/authorized_keys
chmod 600 ~/.ssh/authorized_keys
```

### Ajouter une clé à GitHub/GitLab

bash

```bash
# Copier la clé publique dans le presse-papier
cat ~/.ssh/id_ed25519.pub

# Puis : GitHub → Settings → SSH and GPG keys → New SSH key
```

**Tester la connexion GitHub :**

bash

```bash
ssh -T git@github.com
# Réponse attendue : "Hi username! You've successfully authenticated..."
```

---

## Agent SSH

L'agent SSH garde les clés en mémoire pour éviter de retaper la passphrase.

### Démarrer l'agent

bash

```bash
# Démarrer l'agent
eval "$(ssh-agent -s)"

# Ajouter ta clé
ssh-add ~/.ssh/id_ed25519
```

### Lister les clés chargées

bash

```bash
ssh-add -l
```

### Supprimer toutes les clés de l'agent

bash

```bash
ssh-add -D
```

### Configuration automatique (Linux)

Ajouter dans `~/.bashrc` ou `~/.zshrc` :

bash

```bash
# Démarrer ssh-agent automatiquement
if [ -z "$SSH_AUTH_SOCK" ]; then
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_ed25519 2>/dev/null
fi
```

---

## Commandes SSH courantes

### Connexion basique

bash

```bash
ssh user@serveur                    # Connexion standard
ssh user@serveur -p 2222           # Port personnalisé
ssh -i ~/.ssh/ma_cle user@serveur  # Clé spécifique
```

### Transfert de fichiers

bash

```bash
# Copier un fichier vers le serveur
scp fichier.txt user@serveur:/chemin/destination/

# Copier un dossier vers le serveur
scp -r dossier/ user@serveur:/chemin/destination/

# Copier depuis le serveur vers local
scp user@serveur:/chemin/fichier.txt ./

# Alternative moderne avec rsync
rsync -avz fichier.txt user@serveur:/destination/
```

### Exécuter une commande à distance

bash

```bash
ssh user@serveur "ls -la /var/log"
ssh user@serveur "df -h && free -m"
```

### Tunnel SSH (Port Forwarding)

bash

```bash
# Forward local → distant
ssh -L 8080:localhost:80 user@serveur
# Accès : localhost:8080 pointe vers serveur:80

# Forward distant → local
ssh -R 9000:localhost:3000 user@serveur
# Le port 9000 du serveur pointe vers ton port 3000 local
```

---

## Gestion des clés

### Lister les clés existantes

bash

```bash
ls -la ~/.ssh/
```

### Afficher l'empreinte d'une clé

bash

```bash
ssh-keygen -lf ~/.ssh/id_ed25519.pub
```

### Changer la passphrase

bash

```bash
ssh-keygen -p -f ~/.ssh/id_ed25519
```

### Créer plusieurs clés (pour différents services)

bash

```bash
# Clé pour GitHub
ssh-keygen -t ed25519 -C "github" -f ~/.ssh/id_ed25519_github

# Clé pour GitLab
ssh-keygen -t ed25519 -C "gitlab" -f ~/.ssh/id_ed25519_gitlab
```

Puis dans `~/.ssh/config` :

```
Host github.com
    IdentityFile ~/.ssh/id_ed25519_github

Host gitlab.com
    IdentityFile ~/.ssh/id_ed25519_gitlab
```

---

## Sécurité et bonnes pratiques

### ✅ À faire

- Utiliser une **passphrase forte** pour protéger la clé privée
- Utiliser **ed25519** (moderne, sûr, rapide)
- Définir les **bonnes permissions** (700/600)
- Utiliser l'**agent SSH** pour ne pas retaper la passphrase
- Créer des **clés différentes** pour des contextes différents (perso/pro)
- **Sauvegarder** tes clés privées dans un endroit sûr (gestionnaire de mots de passe chiffré)

### ❌ À éviter

- Partager ta clé **privée**
- Utiliser SSH sans passphrase (sauf cas spécifiques)
- Laisser des permissions trop ouvertes (777, 644 sur clé privée)
- Utiliser des clés RSA de moins de 2048 bits

### Configuration serveur sécurisée

Dans `/etc/ssh/sshd_config` (côté serveur) :

bash

```bash
# Désactiver l'authentification par mot de passe
PasswordAuthentication no

# Désactiver root login
PermitRootLogin no

# Utiliser seulement SSH v2
Protocol 2

# Limiter les utilisateurs autorisés
AllowUsers user1 user2
```

Puis redémarrer SSH :

bash

```bash
sudo systemctl restart sshd
```

---

## Dépannage

### Problème : Permission denied (publickey)

bash

```bash
# Vérifier que la clé est chargée
ssh-add -l

# Ajouter la clé
ssh-add ~/.ssh/id_ed25519

# Tester avec verbose
ssh -v user@serveur
```

### Problème : Connection refused

bash

```bash
# Vérifier que le serveur SSH tourne
sudo systemctl status sshd

# Vérifier le port (défaut 22)
ssh user@serveur -p 2222

# Tester la connectivité
ping serveur
telnet serveur 22
```

### Problème : Too many authentication failures

Limiter les clés testées :

bash

```bash
ssh -o IdentitiesOnly=yes -i ~/.ssh/id_ed25519 user@serveur
```

### Déboguer avec verbose

bash

```bash
ssh -v user@serveur    # Verbose
ssh -vv user@serveur   # Plus verbose
ssh -vvv user@serveur  # Très verbose
```

### Réinitialiser known_hosts

Si erreur "Host key verification failed" :

bash

```bash
ssh-keygen -R serveur
```

---

## Commandes utiles

bash

```bash
# Afficher toutes les connexions SSH actives
who

# Voir les logs SSH (serveur)
sudo tail -f /var/log/auth.log   # Debian/Ubuntu
sudo tail -f /var/log/secure     # CentOS/RHEL

# Tuer une session SSH bloquée
~.  # (tilde point) dans le terminal

# Garder la connexion SSH active
ssh -o ServerAliveInterval=60 user@serveur
```