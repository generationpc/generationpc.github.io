---
layout: post
title: Installer un thème de bureau sous Windows XP
date: '2006-08-16 11:39:15 +0100'
date_gmt: '2006-08-16 09:39:15 +0100'
categories: tutoriels
tags: [Systèmes d'exploitation, Microsoft, Windows XP, Thèmes, Style, Patch]
comments: true
share: true
redirect_from: "/2006/08/installer-un-theme-de-bureau-sous-windows-xp/"
---
Pour installer un nouveau thème, il suffit de patcher un [DLL](http://www.pcentraide.com/index.php?showtopic=1328) de Windows avec le patch join à l'article, puis de choisir le thème téléchargé.

## Le patch ##
Vous devez déjà télécharger le [patch permettant l'installation de thèmes sous Windows XP](http://thomas.dutrion.free.fr/patch-theme.exe).

Double-cliquer sur l'executable que vous venez de télécharger, il s'appelle `patch-theme.exe`, une fenêtre s'ouvre. Cliquer sur `patch`.

Il faut attendre quelques secondes (ou quelques minutes selon votre configuration). Une fenêtre de protection des fichiers Windows s'ouvre.

Cliquer sur annuler.

Cliquer sur OK sur la fenêtre qui reste.

On fini par redémarrer l'ordinateur à la demande du programme.

## Les thèmes ##
La première partie de ce tutoriel servait uniquement à modifier les fichiers systemes dans le but d'installer les themes en question.

Je vais donc vous proposer de télécharger un [pack de deux thèmes](http://thomas.dutrion.free.fr/pack%202%20themes.rar) (un thème mac et le thème de windows vista).

Décompresser l'archive, puis cliquer sur l'un des deux fichiers `.msstyle`. Une fenêtre va s'ouvrir (je prends l'exemple avec `vista.msstyle`).

En cliquant sur ok on applique le thème avec ses paramètres de base.

Pour modifier certains paramètres du thème (notamment la position de la barre dans l'explorateur, modifiez la ligne "vista aero" en "vista xp" qui est disposé comme le thème de windows classique).

Pour trouver d'autres thèmes, rendez-vous sur [themexp.org](http://www.themexp.org/). Si le patch ne marche pas, [testez celui-ci](http://thomas.dutrion.free.fr/Theme_Multipatcher_Fr.exe) ou [celui-là](http://thomas.dutrion.free.fr/PatchXP_pour_UXTheme_SP1.exe).
