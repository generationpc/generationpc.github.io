---
layout: post
title: '[msdos] La commande ipconfig'
date: '2006-08-16 23:11:21 +0100'
date_gmt: '2006-08-16 21:11:21 +0100'
categories: explications
tags: [Systèmes d'exploitation, Microsoft, Windows XP, Réseau, Paramètres, Configuration, ip, Wifi]
comments: true
redirect_from: "/2006/08/msdos-la-commande-ipconfig/"
---
Dans cet article, je vais essayer de vous expliquer la commande msdos `ipconfig`.

Pour commencer, on doit ouvrir l'invite de commande msdos (on travaille sous XP).

Deux solutions s'offrent à nous :

 * cliquez sur `Démarrer`, `Tous les programmes`, `Accessoires` puis `Invite de commandes`
 * cliquez sur `Démarrer`, appuyez sur `Exécuter` et tapez la commande `cmd`, suivi de `Entrer`

L'invite de commande s'ouvre alors. On ne s'interesse pas à ce qui s'y affiche.

Tapez la commande `ipconfig`, puis appuyez sur `Entrer`.

Un texte de ce type s'affiche alors :

[![ipconfig windows XP](/images/posts/2006-08-16-msdos-la-commande-ipconfig/01.jpg)](/images/posts/2006-08-16-msdos-la-commande-ipconfig/01.jpg)

Ici l'**adresse IP** du réseau local de l'ordinateur est `192.168.254.1`.

Le dernier `1` correspond au numéro de l'ordinateur au sein du réseau. Les autres ordinateurs du réseau ont eux aussi une adresse IP en `192.168.254.x` (avec `x` different de `1` car l'adresse IP est l'identifiant unique de l'ordinateur sur le réseau).

Le **masque de sous-réseau** indique à l'ordinateur sur quel réseau il se connecte (utile surtout dans le cas où l'on crée plusieurs réseaux distincts sur un seul ordinateur).

La **passerelle par défaut** correspond au point de connexion au réseau (hub, routeur). C'est l'adresse ip de celui-ci. Dans le cas d'un réseau direct entre deux ordinateurs, il ne doit rien y avoir de marqué à cet emplacement.
