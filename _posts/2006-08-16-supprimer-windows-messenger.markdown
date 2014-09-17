---
layout: post
status: publish
published: true
title: Supprimer Windows Messenger
author:
  display_name: Thomas Dutrion
  login: thomas
  email: thomas@engineor.com
  url: http://www.engineor.com
author_login: thomas
author_email: thomas@engineor.com
author_url: http://www.engineor.com
wordpress_id: 73
wordpress_url: http://dev.generation-pc.net/?p=73
date: '2006-08-16 20:46:53 +0100'
date_gmt: '2006-08-16 18:46:53 +0100'
categories:
- Logiciels de communication
- Systèmes d'exploitation
- Microsoft
- Windows XP
tags:
- Logiciel
- Windows Live Messenger
- Système
- Microsoft
- Windows
- XP
comments: []
---
<p>Windows Messenger est le programme de messagerie instantannée installée de base dans les differentes versions de Windows XP.</p>
<p>Celui-ci ne dispose pas d'une interface graphique et d'une maniabilité exceptionnelle. Il est donc fort possible que vous désiriez le remplacer par la dernière version d'MSN Messenger, maintenant rebaptisée Windows Live Messenger.</p>
<p>&nbsp;</p>
<h3>Problème :</h3>
<p>Windows Messenger n'apparait pas dans Ajout / Suppression de programmes comme les autres programmes installés par la suite.</p>
<p>&nbsp;</p>
<h3>Solution :</h3>
<p>Allez sur <em><strong>démarrer</strong></em> ensuite sur <em><strong>exécuter</strong></em> et tapez cette ligne de commande:</p>
<pre>RunDll32 advpack.dll,LaunchINFSection %windir%\INF\msmsgs.inf,BLC.Remove</pre>
<p>Ensuite appuyez sur <em><strong>ok</strong></em>.</p>
<p>Une fois Windows Messenger désinstallé, <a href="http://get.live.com/messenger/overview" target="_blank">installez la dernière version de la messagerie Microsoft</a>.</p>
<p>&nbsp;</p>
