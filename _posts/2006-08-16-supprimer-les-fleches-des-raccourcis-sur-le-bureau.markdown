---
layout: post
title: Supprimer les flèches des raccourcis sur le bureau.
date: '2006-08-16 20:59:58 +0100'
date_gmt: '2006-08-16 18:59:58 +0100'
categories: astuces
tags: [Systèmes d'exploitation, Microsoft, Windows XP, Style, Paramètres, Configuration]
comments: true
share: true
---
Quand vous ajoutez un raccourci sur votre bureau une petite flèche se place sous ce raccourci. Si vous n'aimez pas ces petites flèches qui gâchent vos icones, une petite intervention très simple dans la base de registre vous permet de les supprimer.

 * allez sur votre base des registres en cliquant sur :
     * `démarrer`
     * `executer`
 * tapez :
     * `regedit`
 * validez en cliquant sur :
     * `ok`

Vous arriverez sur la fenêtre de l'éditeur de registre.

Faites un double clic sur `HKEY_CLASSES_ROOT`, puis dans la partie gauche de votre fenêtre cherchez `lnkfile`.

Attention cela s'ecrit `LNKFILE` donc il faut la chercher dans la lettre **L** et non dans la lettre **i**.

Une fois que vous aurez trouvé la clé `lnkfile` cliquez dessus et sur la droite de votre fenêtre vous supprimez (clic droit dessus et ensuite vous cliquez sur supprimer).

`IsShortcut`

Ensuite fermez votre base des registres et redémarrez votre PC pour que les modifications prennent effet.
