---
layout: post
status: publish
published: true
title: '[msdos] La commande ipconfig'
author:
  display_name: Thomas Dutrion
  login: thomas
  email: thomas@engineor.com
  url: http://www.engineor.com
author_login: thomas
author_email: thomas@engineor.com
author_url: http://www.engineor.com
wordpress_id: 78
wordpress_url: http://dev.generation-pc.net/?p=78
date: '2006-08-16 23:11:21 +0100'
date_gmt: '2006-08-16 21:11:21 +0100'
categories:
- Systèmes d'exploitation
- Microsoft
- Windows XP
tags:
- Système
- Microsoft
- XP
- Réseau
- paramètres
- configuration
- ip
- Wifi
comments: []
---
<p>Dans cet article, je vais essayer de vous expliquer la commande msdos ipconfig.</p>
<p>&nbsp;</p>
<p>Pour commencer, on doit ouvrir l'invite de commande msdos (on travaille sous XP).</p>
<p>Deux solutions s'offrent à nous :</p>
<ul style="list-style-type: square;">
<li>Cliquez sur "<em>Démarrer</em>", "<em>Tous les programmes</em>", "<em>Accessoires</em>" puis "<em>Invite de commandes</em>".</li>
<li>Cliquez sur "<em>Démarrer</em>", appuyez sur "<em>Exécuter</em>" et tapez la commande "<em>cmd</em>" suivie de "<em>Entrer</em>".</li>
</ul>
<p>&nbsp;</p>
<p>L'invite de commande s'ouvre alors. On ne s'interesse pas à ce qui s'y affiche.</p>
<p>Tapez la commande :<br />
[sourcecode]ipconfig[/sourcecode]<br />
et appuyez sur "<em>Entrer</em>".</p>
<p>Un texte de ce type s'affiche alors :</p>
<p><a href="http://blog.generation-pc.net/wp-content/uploads/2006/08/ipconfig-windows-XP.jpg"><img class="aligncenter size-full wp-image-80" title="ipconfig windows XP" src="http://blog.generation-pc.net/wp-content/uploads/2006/08/ipconfig-windows-XP.jpg" alt="ipconfig windows XP" width="400" height="96" /></a></p>
<p>Ici l'<strong>adresse IP</strong> du réseau local de l'ordinateur est 192.168.254.1</p>
<p>Le dernier 1 correspond au numéro de l'ordinateur au sein du reseau. Les autres ordinateurs du réseau ont eux aussi une adresse IP en 192.168.254.x (avec x different de 1 car l'adresse IP sert à définir l'ordinateur).</p>
<p>Le <strong>masque de sous-réseau</strong> indique à l'ordinateur sur quel réseau il se connecte (utile surtout dans le cas où l'on crée plusieurs réseaux distincts sur un seul ordinateur).</p>
<p>La <strong>passerelle par défaut</strong> correspond au point de connexion au réseau (hub, routeur). C'est l'adresse ip de celui-ci. Dans le cas d'un réseau direct entre deux ordinateurs, il ne doit rien y avoir de marqué à cet emplacement.</p>
