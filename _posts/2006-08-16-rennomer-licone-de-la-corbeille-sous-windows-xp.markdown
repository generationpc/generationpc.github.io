---
layout: post
status: publish
published: true
title: Rennomer l'icone de la corbeille sous windows XP
author:
  display_name: Thomas Dutrion
  login: thomas
  email: thomas@engineor.com
  url: http://www.engineor.com
author_login: thomas
author_email: thomas@engineor.com
author_url: http://www.engineor.com
wordpress_id: 52
wordpress_url: http://dev.generation-pc.net/?p=52
date: '2006-08-16 16:55:29 +0100'
date_gmt: '2006-08-16 14:55:29 +0100'
categories:
- Systèmes d'exploitation
- Microsoft
- Windows XP
tags:
- Système
- Microsoft
- Windows
- XP
- Renommer
- Corbeille
comments: []
---
<p>La corbeille de windows n'est pas un élément comme un autre, elle permet de récuperer des éléments effacés par erreur, elle ne peut donc pas etre renommée ou supprimée d'un simple clic.<br />
Une astuce permet toutefois d'agir sur celle-ci en effectuant quelques modifications de la base de registre.</p>
<p>Modifier la base de registre pouvant facilement "planter" votre système windows en cas de mauvaise manipulation, faites au préalable une <a href="http://www.pcentraide.com/index.php?showtopic=779"><strong>sauvegarde de la base de registre</strong></a> pour travailler en toute sécurité.</p>
<p>Ouvrir la base de registre: <strong>Démarrer</strong> / <strong>Exécuter</strong> / <strong>taper</strong></p>
<pre>regedit</pre>
<p>puis</p>
<pre>OK</pre>
<p>Rechercher la clé:</p>
<pre>HKEY_CLASSES_ROOT\CLSID\{645FF040-5081-101B-9F08-00AA002F954E}\ShellFolder</pre>
<p>Clic droit sur la clé</p>
<pre>attributes</pre>
<p>pour modifier la valeur...</p>
<ul>
<li>Valeur par défaut: <strong>40 01 00 20</strong></li>
<li>Permettre de renommer la Corbeille: <strong>50 01 00 20</strong></li>
<li>Permettre de supprimer la Corbeille: <strong>60 01 00 20</strong></li>
<li>Permettre de renommer et de supprimer la Corbeille: <strong>70 01 00 20</strong></li>
</ul>
<p>Redémarrer le système, l'icone de la corbeille de votre bureau peut maitenant etre renommée: selectionner l'icone / F2 / renommer en....</p>
