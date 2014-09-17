---
layout: post
status: publish
published: true
title: 'Outlook : laisser les mails sur le serveur'
author:
  display_name: Thomas Dutrion
  login: thomas
  email: thomas@engineor.com
  url: http://www.engineor.com
author_login: thomas
author_email: thomas@engineor.com
author_url: http://www.engineor.com
excerpt: "Problème, dans le cadre d'une utilisation collaborative d'une même adresse
  email, dont la solution peut paraître simple à nombre d'entre nous informaticiens,
  mais non moins obscur pour les néophytes :\r\n<blockquote>Nous avons une adresse
  email, qui fonctionne, sur laquelle les messages entrant doivent être consultable
  par tous collaborateurs.</blockquote>\r\n&nbsp;\r\n\r\n"
wordpress_id: 286
wordpress_url: http://blog.generation-pc.net/?p=286
date: '2011-08-31 22:28:17 +0100'
date_gmt: '2011-08-31 20:28:17 +0100'
categories:
- Logiciels
- Mails
tags:
- Outlook
- Mail
- pop
comments: []
---
<p>Problème, dans le cadre d'une utilisation collaborative d'une même adresse email, dont la solution peut paraître simple à nombre d'entre nous informaticiens, mais non moins obscur pour les néophytes :</p>
<blockquote><p>Nous avons une adresse email, qui fonctionne, sur laquelle les messages entrant doivent être consultable par tous collaborateurs.</p></blockquote>
<p>&nbsp;</p>
<p><a id="more"></a><a id="more-286"></a></p>
<p>Ah, ça commence mal, dans une telle situation, il aurait fallu l'intervention d'un technicien compétent qui aurait mis en place une liste de diffusion, et non pas une adresse email, de sorte à ce que les mails soient transmis à qui de droit.</p>
<blockquote><p>Le problème de la solution en place est que lorsque j'ouvre Outlook en arrivant le matin, les mails sont récupérés sur mon poste et supprimés du serveur. Les autres collaborateurs n'y ont donc pas accès.</p></blockquote>
<p>Bien, pour cette problématique précise, une solution existe !</p>
<p>Ici, le tutoriel est basé sur Microsoft Outlook, la version complète intégrée à la suite Microsoft Office, dans sa version 2010, mais le principe est le même pour les versions plus anciennes, et aussi pour les versions d'Outlook Express (et probablement Windows Live Mail).</p>
<p>Le principe est simple : il faut que les mails restent sur le serveur, pour un nombre de jour donné, à partir du premier téléchargement.</p>
<p>Premièrement, il faut se rendre dans les paramètres de compte. Cliquer sur "Fichier" en haut à gauche. La page suivante s'ouvre :</p>
<p><a href="http://blog.generation-pc.net/wp-content/uploads/2011/08/01.png"><img class="aligncenter size-large wp-image-288" title="01" src="http://blog.generation-pc.net/wp-content/uploads/2011/08/01-1024x700.png" alt="" width="560" height="382" /></a>Ici il faut choisir le compte que l'on veut paramétrer dans la zone entourée en bleu.</p>
<p><a href="http://blog.generation-pc.net/wp-content/uploads/2011/08/02.png"><img class="aligncenter size-full wp-image-289" title="02" src="http://blog.generation-pc.net/wp-content/uploads/2011/08/02.png" alt="" width="531" height="244" /></a><br />
Une fois le compte sélectionné, cliquer sur paramètre du compte. Une liste déroulante comportant une seule option s'ouvrira, cliquer sur cette option ("Paramètres du compte").<br />
La fenêtre suivante va s'ouvrir. Effectuer un double clic sur l'adresse mail du compte à configurer dans la zone entourée en bleu.</p>
<p><a href="http://blog.generation-pc.net/wp-content/uploads/2011/08/03.png"><img class="aligncenter size-full wp-image-290" title="03" src="http://blog.generation-pc.net/wp-content/uploads/2011/08/03.png" alt="" width="636" height="499" /></a>Une autre fenêtre va s'ouvrir. Cette nouvelle fenêtre contient enfin les informations du compte. Ce tutoriel fait appel à des fonctions avancées, cliquer sur "Paramètres supplémentaires".</p>
<p><a href="http://blog.generation-pc.net/wp-content/uploads/2011/08/04.png"><img class="aligncenter size-full wp-image-291" title="04" src="http://blog.generation-pc.net/wp-content/uploads/2011/08/04.png" alt="" width="713" height="481" /></a>Une fenêtre s'ouvre, c'est la dernière dont on aura besoin. En haut de cette fenêtre, choisir l'onglet "Options avancées".</p>
<p><a href="http://blog.generation-pc.net/wp-content/uploads/2011/08/05.png"><img class="aligncenter size-full wp-image-292" title="05" src="http://blog.generation-pc.net/wp-content/uploads/2011/08/05.png" alt="" width="454" height="432" /></a>Nous voici maintenant sur la page contenant l'option désirée. Dans la section remise, plusieurs choix sont disponibles.</p>
<p><a href="http://blog.generation-pc.net/wp-content/uploads/2011/08/06.png"><img class="aligncenter size-full wp-image-293" title="06" src="http://blog.generation-pc.net/wp-content/uploads/2011/08/06.png" alt="" width="454" height="432" /></a>Ici il faut cocher "Laisser un exemplaire des messages sur le serveur.".</p>
<p>Le problème de ne choisir que cette option est que les comptes mails ne disposent que d'une taille limitée, et ne jamais supprimer les emails peut provoquer une surcharge de la boite mail, et lorsque la boite est pleine, tout nouveau mail sera refusé.</p>
<p>Il est donc possible de choisir de supprimer les mails du compte au bout d'un certain nombre de jours, déterminé approximativement par "taille de la boite &gt; nombre de mails approximatif * taille moyenne des mails", en visant assez large tout de même.</p>
<p>L'autre solution consiste à supprimer les mails du serveur lorsqu'ils sont supprimés des éléments supprimés (vidage de la corbeille outlook). Cette solution ne garanti pas que tous les utilisateurs du compte aient accès à tous les mails, par contre il a l'avantage lorsqu'un mail est traité et supprimé par une personne de ne pas dupliquer ce travail de suppression à tous les collaborateurs. Par contre il faut toujours envisager le cas d'un collaborateur maniaque de la suppression, qui pourrait faire perdre des emails.</p>
<p>Il ne faut pas non plus utiliser la deuxième option seule, car beaucoup d'emails sont conservés sur les Outlook des collaborateurs, et la boite mail sur le serveur sera surchargée rapidement.</p>
