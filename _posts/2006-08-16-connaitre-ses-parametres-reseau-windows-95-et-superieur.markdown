---
layout: post
status: publish
published: true
title: Connaitre ses paramètres réseau (Windows 95 et supérieur)
author:
  display_name: Thomas Dutrion
  login: thomas
  email: thomas@engineor.com
  url: http://www.engineor.com
author_login: thomas
author_email: thomas@engineor.com
author_url: http://www.engineor.com
wordpress_id: 49
wordpress_url: http://dev.generation-pc.net/?p=49
date: '2006-08-16 16:50:26 +0100'
date_gmt: '2006-08-16 14:50:26 +0100'
categories:
- Systèmes d'exploitation
- Microsoft
- Windows XP
- Windows 95
- Windows Server
tags:
- Système
- Microsoft
- Windows
- XP
- Réseau
- paramètres
- configuration
- ip
comments: []
---
<p>Vous aurez besoin de connaitre un jour ou l'autre ces renseignements que vous pouvez aussi trouver dans vos connexions réseau.</p>
<p>Par exemple l'adresse physique d'une carte ethernet (adresse MAC) lors de la configuration du pare-feu de votre routeur ou tout simplement des infos sur votre configuration réseau actuelle.</p>
<p>Cliquez sur <strong>Démarrer</strong> puis sur <strong>exécuter</strong> et tapez</p>
<pre>cmd</pre>
<p>Dans la fenetre d'invite de commande tapez ensuite tel quel</p>
<pre>ipconfig/all</pre>
<p>puis validez.</p>
<p>Ceci est valable pour windows XP et supérieur, ainsi que pour les versions serveurs.<br />
Si vous etes sous windows 95, 98, ME tapez la commande</p>
<pre>winipcfg /all</pre>
<p>Sur des ordinateurs en réseau avec une connexion partagée ou derriere un routeur votre adresse ip sera celle du réseau.</p>
