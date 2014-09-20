---
layout: post
title: Connaitre ses paramètres réseau (Windows 95 et supérieur)
date: '2006-08-16 16:50:26 +0100'
date_gmt: '2006-08-16 14:50:26 +0100'
categories: astuces
tags: [Systèmes d'exploitation, Microsoft, Windows XP, Windows 95, Windows Server, Réseau, Paramètres, Configuration, ip]
comments: true
share: true
redirect_from: "/2006/08/connaitre-ses-parametres-reseau-windows-95-et-superieur/"
---
Vous aurez besoin de connaitre un jour ou l'autre ces renseignements que vous pouvez aussi trouver dans vos connexions réseau.

Par exemple l'adresse physique d'une carte ethernet (adresse MAC) lors de la configuration du pare-feu de votre routeur ou tout simplement des infos sur votre configuration réseau actuelle.

Cliquez sur `Démarrer` puis sur `exécuter` et tapez `cmd`.

Dans la fenetre d'invite de commande saisissez `ipconfig/all`, puis validez.

Ceci est valable pour windows XP et supérieur, ainsi que pour les versions serveurs.

Si vous etes sous windows 95, 98, ME tapez la commande `winipcfg /all`.

Sur des ordinateurs en réseau avec une connexion partagée ou derriere un routeur votre adresse ip sera celle du réseau.
