---
tags:
  - prog/test
---


---
***Références :***

---

*Objectif :*
Séléctionner les données d'entrée afin de tester au moins une fois chaque valeur parametre 

*👍 avantages :*
- Toute valeur d'un parametre est testé au moins une fois 
- Permet de detecter les oublis et grosses erreurs 

*👎 inconvenient :*
- Ne detecte pas les erreurs lié à une paire de parametre

> [!exemple]
> On veut tester un logiciel qui génère des script pour les serveurs web. Les parametres sont : 
> - Le type d'OS (window,mac,ubuntu)
> - le type de navigateur (firefox,safari,chrome)
> - le type de donnée telechargée : (jpeg,avi,ogg,mp3)
> - connexion sécurisée ou non 
>   
>   --> ==3x3x4x2 = 72 test à réaliser==

> [!tip] avantage des test all single
> le nombre de test correspondra au cardinal le plus grand : 
> 	**ici 4 test (données téléchargées)**
> 

| OS     | NAVIGATEUR | DONNEES | SECURISTATION |
| ------ | ---------- | ------- | ------------- |
| window | firefox    | jpeg    | oui           |
| mac    | safari     | avi     | non           |
| ubuntu | chrome     | ogg     | oui           |
| mac    | safari     | mp3     | non           |
*Chaque valeur de parametre est testée au moins une fois* 