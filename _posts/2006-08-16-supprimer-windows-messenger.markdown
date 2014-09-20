---
layout: post
title: Supprimer Windows Messenger
date: '2006-08-16 20:46:53 +0100'
date_gmt: '2006-08-16 18:46:53 +0100'
categories: astuces
tags: [Logiciels de communication, Systèmes d'exploitation, Microsoft, Windows XP, Logiciel, Windows Live Messenger]
comments: true
share: true
redirect_from: "/2006/08/supprimer-windows-messenger/"
---
Windows Messenger est le programme de messagerie instantannée installée de base dans les differentes versions de Windows XP.

Celui-ci ne dispose pas d'une interface graphique et d'une maniabilité exceptionnelle. Il est donc fort possible que vous désiriez le remplacer par la dernière version d'MSN Messenger, maintenant rebaptisée Windows Live Messenger.

## Problème ##
Windows Messenger n'apparait pas dans `Ajout / Suppression de programmes` comme les autres programmes installés par la suite.

## Solution ##
Allez sur `démarrer`, puis sur `executer` et tapez la commande suivante :

`RunDll32 advpack.dll,LaunchINFSection %windir%\INF\msmsgs.inf,BLC.Remove`

Ensuite appuyez sur `ok`.

Une fois Windows Messenger désinstallé, [installez la dernière version de la messagerie Microsoft](http://get.live.com/messenger/overview).
