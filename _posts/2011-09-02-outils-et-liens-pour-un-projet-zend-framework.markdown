---
layout: post
published: true
title: Outils et liens pour un projet Zend Framework
date: '2011-09-02 19:01:36 +0100'
date_gmt: '2011-09-02 17:01:36 +0100'
categories: articles
tags: [Développement, Web, Zend Framework, PHP, Logiciel]
comments: true
share: true
redirect_from: "/2011/09/outils-et-liens-pour-un-projet-zend-framework/"
---
J'entends une question dans le public...

> Hey Thomas, t'utilise quoi quand tu commences un projet avec [Zend Framework](http://framework.zend.com/) ? Je peux créer un site complet sans aucun logiciel payant ?

Bon alors, procédons dans l'ordre. Déjà, si vous développez le projet en local, il vous faudra un serveur *AMP, c'est à dire la combinaison des logiciels serveurs Apache 2, MySql et PHP. L'étoile correspond à la première lettre de votre système d'exploitation (M pour Mac Os, W pour Microsoft Windows et L pour Linux).

Je vous laisse voir ce qui vous correspond, mais je vous propose tout de même [Zend Server community edition](http://www.zend.com/en/products/server-ce/downloads), [Wamp](http://www.wampserver.com/), [Xampp](http://www.apachefriends.org/fr/xampp.html), [EasyPHP](http://www.easyphp.org/fr/)...

Pour ceux qui ne veulent pas se compliquer la vie avec le local, il est possible de développer en synchronisant ses sources sur le serveur directement. Je reviendrais sur ce point un peu plus tard.

Ensuite, il va nous falloir un IDE, je propose donc d'utiliser [Netbeans](http://www.netbeans.com/downloads/index.html), qui nous permettra par la suite d'avoir la "Remote Synchronization" dont je vous parlais, mais aussi l'intégration de logiciels de gestion de versions (notamment SVN, GIT, CVS et Mercurial), ainsi que le support des framework PHP [Zend](http://framework.zend.com/), Symfony et bien d'autres (auto complétion, intégration des outils en ligne de commande...).

En fait, concernant PHP et les environnements, il nous suffira d'utiliser ça. Bien entendu, il va nous falloir un serveur SVN ou GIT, ainsi qu'un serveur FTP/SFTP sur lesquels mettre le projet. On peut aussi envisager d'utiliser [PHPDocumentator](http://www.phpdoc.org/) (documentation de projet), [PHPUnit](https://github.com/sebastianbergmann/phpunit/) (tests unitaires)...

Le reste concernera principalement le design et le côté client.

Ici il nous faudra un peu de javascript pour dynamiser le tout... Pourquoi pas [jQuery](http://jquery.com/), avec certains plugins comme [jQuery UI](http://jqueryui.com/) et [jQuery tools](http://flowplayer.org/tools/) (sans oublier un grand nombre d'autres extensions intéressantes que vous trouverez au besoin à l'aide de votre moteur de recherche favori).

Passons ensuite sur le site de [Twitter Bootstrap](http://twitter.github.com/bootstrap/), qui vous permettra de trouver une UI de base, permettant de monter son design en quelques minutes, tout en ayant quelque chose de très propre.

Pour générer la structure de votre layout, il serait aussi dommage de laisser de côté le [squelettor d'Alsacreations](http://www.alsacreations.com/page/squelettor/), tout en profitant de votre visite sur le site pour [générer des Lorem Ipsum en alsacien](http://www.alsacreations.com/page/schnapsum/), ce qui à l'avantage de changer un peu, mais surtout de proposer différents types de contenu HTML, du paragraphe au formulaire.

Quelques bons liens sur les blogs d'[Akrabat](http://akrabat.com/) et d'[Aurevec](http://blog.aurevec.be/) pour les débutants, et je pense avoir fait le tour.

Petite astuce finale : n'hésitez pas à fréquenter des sites comme [Gnome Look](http://gnome-look.org/) (section icônes et background notamment) où il est possible de trouver un grand nombre de ressources intéressante sous licence libre. Faites toutefois bien attention aux autorisations définies dans la licence, il arrive que ce soit pour un usage non commercial.