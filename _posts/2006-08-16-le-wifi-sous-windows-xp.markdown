---
layout: post
title: Le wifi sous windows XP
date: '2006-08-16 19:04:49 +0100'
date_gmt: '2006-08-16 17:04:49 +0100'
categories: tutoriels
tags: [Systèmes d'exploitation, Microsoft, Windows XP, Réseau, Paramètres, Wifi]
comments: true
share: true
---

 * ouvrir le `menu démarrer`
 * dans `Connexions`, cliquer sur `afficher toutes les connexions`
 * faire un clic droit sur l'icône `connexion réseau sans fil`
 * cliquer sur `propriétés`
 * puis sur le deuxième onglet : `Configuration réseaux sans fils`
 * dans la partie, `Réseaux favoris`, cliquer sur `Ajouter…`
 * dans la case `Nom réseau`, on tape le nom du SSID auquel on veut se connecter
 * pour l'authentification réseau, on se positionne sur `Partagée`
 * pour le `Cryptage de données`, on se positionne sur `WEP`

La clé réseau peut-etre fournie avec la connexion. Il faut la demander au fournisseur qui s’occupe du réseau en question. Vous l'avez peut-etre paramétré vous meme sur le point d'accès ou le routeur.

Si vous n'en utilisez pas, passez cette étape. Ici il s’agit d’une clé WEP 128 bits.

 * dans l’onglet `Authentification`, vérifier que la case `Activer l’authentification IEEE 802.1x pour ce réseau` est décochée
 * dans le troisième onglet, `connexion`, la case `Me connecter à ce réseau lorsqu’il est à portée` devra être cochée si le réseau auquel on essaye de se connecter est le réseau auquel on se connectera par défaut dans la zone où l’on se trouve.

A la suite de toutes ces étapes, l’ordinateur devrait trouver la connexion. Si elle ne fonctionne pas immédiatement, redémarrer l’ordinateur et la connexion devrait alors s’établir.
