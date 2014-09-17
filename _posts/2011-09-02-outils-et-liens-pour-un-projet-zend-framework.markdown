---
layout: post
status: publish
published: true
title: Outils et liens pour un projet Zend Framework
author:
  display_name: Thomas Dutrion
  login: thomas
  email: thomas@engineor.com
  url: http://www.engineor.com
author_login: thomas
author_email: thomas@engineor.com
author_url: http://www.engineor.com
excerpt: "J'entends une question dans le public...\r\n<blockquote>Hey Thomas, t'utilise
  quoi quand tu commences un projet avec <a href=\"http://framework.zend.com/\">Zend
  Framework </a>? Je peux créer un site complet sans aucun logiciel payant ?</blockquote>"
wordpress_id: 302
wordpress_url: http://blog.generation-pc.net/?p=302
date: '2011-09-02 19:01:36 +0100'
date_gmt: '2011-09-02 17:01:36 +0100'
categories:
- Développement
- Web
- Zend Framework
- PHP
- Logiciels
tags:
- Zend
- Zend Framework
- Développement
- Logiciel
- php
comments: []
---
<p>J'entends une question dans le public...</p>
<blockquote><p>Hey Thomas, t'utilise quoi quand tu commences un projet avec <a href="http://framework.zend.com/">Zend Framework </a>? Je peux créer un site complet sans aucun logiciel payant ?</p></blockquote>
<p><a id="more"></a><a id="more-302"></a><br />
Bon alors, procédons dans l'ordre. Déjà, si vous développez le projet en local, il vous faudra un serveur *AMP, c'est à dire la combinaison des logiciels serveurs Apache 2, MySql et PHP. L'étoile correspond à la première lettre de votre système d'exploitation (M pour Mac Os, W pour Microsoft Windows et L pour Linux).</p>
<p>Je vous laisse voir ce qui vous correspond, mais je vous propose tout de même <a href="http://www.zend.com/en/products/server-ce/downloads">Zend Server community edition</a>, <a href="http://www.wampserver.com/">Wamp</a>, <a href="http://www.apachefriends.org/fr/xampp.html">Xampp</a>, <a href="http://www.easyphp.org/fr/">EasyPHP</a>...</p>
<p>Pour ceux qui ne veulent pas se compliquer la vie avec le local, il est possible de développer en synchronisant ses sources sur le serveur directement. Je reviendrais sur ce point un peu plus tard.</p>
<p>&nbsp;</p>
<p>Ensuite, il va nous falloir un IDE, je propose donc d'utiliser <a href="http://www.netbeans.com/downloads/index.html">Netbeans</a>, qui nous permettra par la suite d'avoir la "Remote Synchronization" dont je vous parlais, mais aussi l'intégration de logiciels de gestion de versions (notamment SVN, GIT, CVS et Mercurial), ainsi que le support des framework PHP <a href="http://framework.zend.com/">Zend</a>, Symfony et bien d'autres (auto complétion, intégration des outils en ligne de commande...).</p>
<p>&nbsp;</p>
<p>En fait, concernant PHP et les environnements, il nous suffira d'utiliser ça. Bien entendu, il va nous falloir un serveur SVN ou GIT, ainsi qu'un serveur FTP/SFTP sur lesquels mettre le projet. On peut aussi envisager d'utiliser <a href="http://www.phpdoc.org/">PHPDocumentator</a> (documentation de projet), <a href="https://github.com/sebastianbergmann/phpunit/">PHPUnit </a>(tests unitaires)...</p>
<p>&nbsp;</p>
<p>Le reste concernera principalement le design et le côté client.</p>
<p>Ici il nous faudra un peu de javascript pour dynamiser le tout... Pourquoi pas <a href="http://jquery.com/">jQuery</a>, avec certains plugins comme <a href="http://jqueryui.com/">jQuery UI</a> et <a href="http://flowplayer.org/tools/">jQuery tools</a> (sans oublier un grand nombre d'autres extensions intéressantes que vous trouverez au besoin à l'aide de votre moteur de recherche favori).</p>
<p>Passons ensuite sur le site de <a href="http://twitter.github.com/bootstrap/">Twitter Bootstrap</a>, qui vous permettra de trouver une UI de base, permettant de monter son design en quelques minutes, tout en ayant quelque chose de très propre.</p>
<p>Pour générer la structure de votre layout, il serait aussi dommage de laisser de côté le <a href="http://www.alsacreations.com/page/squelettor/">squelettor d'Alsacreations</a>, tout en profitant de votre visite sur le site pour <a href="http://www.alsacreations.com/page/schnapsum/">générer des Lorem Ipsum en alsacien</a>, ce qui à l'avantage de changer un peu, mais surtout de proposer différents types de contenu HTML, du paragraphe au formulaire.</p>
<p>&nbsp;</p>
<p>Quelques bons liens sur les blogs d'<a href="http://akrabat.com/zend-framework-tutorial/">Akrabat </a>et d'<a href="http://blog.aurevec.be/">Aurevec </a>pour les débutants, et je pense avoir fait le tour.</p>
<p>Petite astuce finale : n'hésitez pas à fréquenter des sites comme <a href="http://gnome-look.org/">Gnome Look</a> (section icônes et background notamment) où il est possible de trouver un grand nombre de ressources intéressante sous licence libre. Faites toutefois bien attention aux autorisations définies dans la licence, il arrive que ce soit pour un usage non commercial.</p>
