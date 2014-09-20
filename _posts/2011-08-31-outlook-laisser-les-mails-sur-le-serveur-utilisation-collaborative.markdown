---
layout: post
title: 'Outlook : laisser les mails sur le serveur'
date: '2011-08-31 22:28:17 +0100'
date_gmt: '2011-08-31 20:28:17 +0100'
categories: tutoriels
tags: [Logiciels, Mails, Outlook, Mail, POP]
comments: true
share: true
---

Problème, dans le cadre d'une utilisation collaborative d'une même adresse email, dont la solution peut paraître simple à nombre d'entre nous informaticiens, mais non moins obscur pour les néophytes :

> Nous avons une adresse email, qui fonctionne, sur laquelle les messages entrant doivent être consultable par tous collaborateurs.

Ah, ça commence mal, dans une telle situation, il aurait fallu l'intervention d'un technicien compétent qui aurait mis en place une liste de diffusion, et non pas une adresse email, de sorte à ce que les mails soient transmis à qui de droit.

> Le problème de la solution en place est que lorsque j'ouvre Outlook en arrivant le matin, les mails sont récupérés sur mon poste et supprimés du serveur. Les autres collaborateurs n'y ont donc pas accès.

Bien, pour cette problématique précise, une solution existe !

Ici, le tutoriel est basé sur Microsoft Outlook, la version complète intégrée à la suite Microsoft Office, dans sa version 2010, mais le principe est le même pour les versions plus anciennes, et aussi pour les versions d'Outlook Express (et probablement Windows Live Mail).

Le principe est simple : il faut que les mails restent sur le serveur, pour un nombre de jour donné, à partir du premier téléchargement.

Premièrement, il faut se rendre dans les paramètres de compte. Cliquer sur "Fichier" en haut à gauche. La page suivante s'ouvre :

[![Outlook: informations sur le compte](/images/posts/2011-08-31-outlook-laisser-les-mails-sur-le-serveur-utilisation-collaborative/01.png)](/images/posts/2011-08-31-outlook-laisser-les-mails-sur-le-serveur-utilisation-collaborative/01.png)

Ici il faut choisir le compte que l'on veut paramétrer dans la zone entourée en bleu.

[![Outlook: Paramètres du compte](/images/posts/2011-08-31-outlook-laisser-les-mails-sur-le-serveur-utilisation-collaborative/02.png)](/images/posts/2011-08-31-outlook-laisser-les-mails-sur-le-serveur-utilisation-collaborative/02.png)

Une fois le compte sélectionné, cliquer sur paramètre du compte. Une liste déroulante comportant une seule option s'ouvrira, cliquer sur cette option ("Paramètres du compte").

La fenêtre suivante va s'ouvrir. Effectuer un double clic sur l'adresse mail du compte à configurer dans la zone entourée en bleu.

[![Outlook: Paramètres, liste des comptes](/images/posts/2011-08-31-outlook-laisser-les-mails-sur-le-serveur-utilisation-collaborative/03.png)](/images/posts/2011-08-31-outlook-laisser-les-mails-sur-le-serveur-utilisation-collaborative/03.png)

Une autre fenêtre va s'ouvrir. Cette nouvelle fenêtre contient enfin les informations du compte. Ce tutoriel fait appel à des fonctions avancées, cliquer sur "Paramètres supplémentaires".

[![Outlook: Paramètres supplémentaires de gestion de compte](/images/posts/2011-08-31-outlook-laisser-les-mails-sur-le-serveur-utilisation-collaborative/04.png)](/images/posts/2011-08-31-outlook-laisser-les-mails-sur-le-serveur-utilisation-collaborative/04.png)

Une fenêtre s'ouvre, c'est la dernière dont on aura besoin. En haut de cette fenêtre, choisir l'onglet "Options avancées".

[![Outlook: Options avancées de gestion de compte](/images/posts/2011-08-31-outlook-laisser-les-mails-sur-le-serveur-utilisation-collaborative/05.png)](/images/posts/2011-08-31-outlook-laisser-les-mails-sur-le-serveur-utilisation-collaborative/05.png)

Nous voici maintenant sur la page contenant l'option désirée. Dans la section remise, plusieurs choix sont disponibles.

[![Outlook: Laisser un exemplaire des messages sur le serveur](/images/posts/2011-08-31-outlook-laisser-les-mails-sur-le-serveur-utilisation-collaborative/06.png)](/images/posts/2011-08-31-outlook-laisser-les-mails-sur-le-serveur-utilisation-collaborative/06.png)

Ici il faut cocher "Laisser un exemplaire des messages sur le serveur.".

Le problème de ne choisir que cette option est que les comptes mails ne disposent que d'une taille limitée, et ne jamais supprimer les emails peut provoquer une surcharge de la boite mail, et lorsque la boite est pleine, tout nouveau mail sera refusé.

Il est donc possible de choisir de supprimer les mails du compte au bout d'un certain nombre de jours, déterminé approximativement par "taille de la boite &gt; nombre de mails approximatif * taille moyenne des mails", en visant assez large tout de même.

L'autre solution consiste à supprimer les mails du serveur lorsqu'ils sont supprimés des éléments supprimés (vidage de la corbeille outlook). Cette solution ne garanti pas que tous les utilisateurs du compte aient accès à tous les mails, par contre il a l'avantage lorsqu'un mail est traité et supprimé par une personne de ne pas dupliquer ce travail de suppression à tous les collaborateurs. Par contre il faut toujours envisager le cas d'un collaborateur maniaque de la suppression, qui pourrait faire perdre des emails.

Il ne faut pas non plus utiliser la deuxième option seule, car beaucoup d'emails sont conservés sur les Outlook des collaborateurs, et la boite mail sur le serveur sera surchargée rapidement.
