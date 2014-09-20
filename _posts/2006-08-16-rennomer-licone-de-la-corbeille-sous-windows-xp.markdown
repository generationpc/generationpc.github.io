---
layout: post
title: Rennomer l'icone de la corbeille sous windows XP
date: '2006-08-16 16:55:29 +0100'
date_gmt: '2006-08-16 14:55:29 +0100'
categories: astuces
tags: [Systèmes d'exploitation, Microsoft, Windows XP, Renommer, Corbeille]
comments: true
share: true
redirect_from: "/2006/08/rennomer-licone-de-la-corbeille-sous-windows-xp/"
---
La corbeille de windows n'est pas un élément comme un autre, elle permet de récuperer des éléments effacés par erreur, elle ne peut donc pas etre renommée ou supprimée d'un simple clic.

Une astuce permet toutefois d'agir sur celle-ci en effectuant quelques modifications de la base de registre.

Modifier la base de registre pouvant facilement "planter" votre système windows en cas de mauvaise manipulation, faites au préalable une [**sauvegarde de la base de registre**](http://www.pcentraide.com/index.php?showtopic=779) pour travailler en toute sécurité.

Ouvrir la base de registre: `Démarrer` / `Exécuter` / taper `regedit` / `OK`

Rechercher la clé : `HKEY_CLASSES_ROOT\CLSID\{645FF040-5081-101B-9F08-00AA002F954E}\ShellFolder`

Clic droit sur la clé, selectionner `attributes`, pour modifier la valeur : 

 * valeur par défaut : `40 01 00 20`
 * permettre de renommer la corbeille : `50 01 00 20`
 * permettre de supprimer la corbeille : `60 01 00 20`
 * permettre de renommer et de supprimer la corbeille : `70 01 00 20`

Redémarrer le système, l'icone de la corbeille de votre bureau peut maitenant etre renommée: selectionner l'icone / `F2` / `renommer en`....
