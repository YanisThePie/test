# Unreal System

Notre projet consiste en la création d’une application mobile pour les spectateurs du tournoi d’E-Sport « Blast Pro Series ». Cette application, associée à des services et à des partenariats, permettra de **personnaliser l’expérience de chaque spectateur** de la compétition. Elle sera disponible sur Android et iOS, soit 99% du parc de smartphones actuel dans le monde.

# Base de donnée et Serveur

## Comment ça marche?

La base de données sera gérée sous la forme de procédures stockées CRUD en MySQL. Le choix du NoSQL n'a pas été retenu pour des raisons de scalabilité lors de la phase de production.
Un Serveur est déployé en Node.JS sous NGINX pour un muliplexage efficace entre les connexion. La caracteristique asynchrone de NGINX permet d'assurer une grande scalabilité. le Serveur Node.JS Expose la stack réseau en REST, transmet les arguments de la requête à la base de données, puis récupère le retour de la DB et les transmets à la route correspondante.

## Fonctionnalités

* Accès à la Base de donnée
* exposition des méthodes sur le réseau

## Versions et ressources externes

* Node.JS v10.15
* MySQL
* NGINX v1.15

# Application mobile IOS / Android

## Comment ça marche?

L'application mobile est réalisée en React Native, afin de réduire les coûts et le temps de développement multi-plateformes.

Un player vidéo retransmet le flux RTMP de la chaîne Twitch de l'evenement. il est déployé grace au paquet npm "react-native-video".
L'authentification des utilisateurs, la gestion des comptes est réalisée grace à "Passeport-js".
Les resultats des matchs, l'achat des billets se fait grace à des requêtes à l'API de BlastProSeries, déja utilisée par leur site Web.
La boutique en ligne est déployée grace à Cezerin, qui inclus nativement les vues des articles, la gestion du panier et des commandes ainsi que le paiement sécurisé.
Le mini jeu est développé avec Unity3D, puis compilée en APK afin d'être intégrée à une WebView React native avec le projet Open source "react-native-unity".
Le mini-jeu ajoute des points à un compteur de points est tranformé en bons de réductions Cezerin.
La messagerie instantanée est déployée avec le paquet "react-native-gifted-chat".

## Fonctionnalités

* Un player vidéo
* une boutique en ligne
* Un mini-jeu
* un forum participatif
* une gestion des paris sportifs en ligne
* une messagerie instantanée

## Versions et ressources externes

* react-native-video
* Passeport-js
* react-native-unity
* react-native-gifted-chat
* Cezerin


## Schéma d'architecture

![Schéma d'architecture](https://drive.google.com/file/d/13_5RR0af9SJLTVmCZqlPk0nG0_6mLiFy/view?usp=sharing "Schéma d'architecture")


