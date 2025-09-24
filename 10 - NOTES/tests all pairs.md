---
tags:
  - prog/test
---


---
***Références :***

---

*Objectif :*
Tester les erreurs du à une combinaison de 2 paramètres afin de couvrir toute paire de valeurs

*👍 avantages :*
- Efficace
- Simple à mettre en oeuvre
- peut servir conjointement à d'autres méthodes

*👎 inconvenient :*
- Ne convient que pour un petit ensemble de données 

> [!exemple]
> On veut tester un logiciel qui génère des script pour les serveurs web. Les parametres sont : 
> - Le type d'OS (window,mac,ubuntu)
> - le type de navigateur (firefox,safari,chrome)
> - le type de donnée telechargée : (jpeg,avi,ogg,mp3)
> - connexion sécurisée ou non 
>   
>   --> ==3x3x4x2 = 72 test à réaliser==

>[!tip] avantage des test all single
> 
> On peut reduire ce nombre de test a 12

| Test | OS      | Navigateur | Type fichier | Connexion sécurisée |
| ---- | ------- | ---------- | ------------ | ------------------- |
| 1    | Windows | Firefox    | JPEG         | Oui                 |
| 2    | Windows | Safari     | AVI          | Non                 |
| 3    | Windows | Chrome     | OGG          | Non                 |
| 4    | Mac     | Firefox    | AVI          | Oui                 |
| 5    | Mac     | Safari     | OGG          | Oui                 |
| 6    | Mac     | Chrome     | MP3          | Non                 |
| 7    | Ubuntu  | Firefox    | MP3          | Oui                 |
| 8    | Ubuntu  | Safari     | JPEG         | Non                 |
| 9    | Ubuntu  | Chrome     | AVI          | Non                 |
| 10   | Windows | Firefox    | MP3          | Non                 |
| 11   | Mac     | Firefox    | JPEG         | Non                 |
| 12   | Ubuntu  | Chrome     | JPEG         | Oui                 |
