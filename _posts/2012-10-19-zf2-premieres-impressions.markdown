---
layout: post
title: "ZF2, premières impressions !"
date: '2012-10-19 00:41:18 +0100'
date_gmt: '2012-10-18 22:41:18 +0100'
categories: [article]
tags: [Développement, Web, Zend Framework, PHP, Hébergement, Zend, Zend Framework 2, Bootstrap, Phpcloud]
---

[![20121018-113940 PM.jpg](http://blog.generation-pc.net/wp-content/uploads/2012/10/20121018-113940-PM.jpg)](http://blog.generation-pc.net/wp-content/uploads/2012/10/20121018-113940-PM.jpg)

Attendu depuis de nombreux mois, la nouvelle version de Zend Framework est sortie le 7 septembre 2012. Je n'ai pas eu le temps de m'y intéresser jusque là, mais je tiens à vous donner mon avis après quelques jours de tests...

Voilà bien longtemps maintenant que je n'ai pas écrit de post sur ce blog... Ça ne veut bien entendu pas dire que je vais le délaisser, mais simplement que je n'ai pas eu énormément de temps ces derniers mois. Comme certains d'entre vous le savent, [Zend Framework](http://framework.zend.com/) est sorti dans sa version 2 il y a déjà plusieurs semaines, après plusieurs mois de versions bêta publiques. Pour ceux qui ne le savaient pas encore, ou qui se demandent simplement de quoi je parle, je vous laisse faire quelques recherches sur ce sujet car je n'ai malheureusement pas le temps d'en écrire plus.

Pour ma part, j'ai décidé d'utiliser Zend Framework 2 en utilisant le [QuickStart](http://zf2.readthedocs.org/en/latest/index.html#userguide) officiel (réalisé sur la base du tutoriel de [Rob Allen alias Akrabat](http://akrabat.com/), référence pour [débuter sur ZF1](http://akrabat.com/zend-framework-tutorial/), dans sa version réécrite pour la version 2 du Framework). Pour ne pas perdre trop de temps avec la mise en place de mon environnement de test, j'ai aussi choisi d'utiliser [phpcloud](http://www.phpcloud.com), hébergement en ligne de machines virtuelles spécifiquement prévu pour le développement d'application sous Zend Framework. Je pense prendre le temps un peu plus tard d'exprimer mon avis sur cette plateforme.

Côté éditeur, j'ai bien entendu choisi d'utiliser [Netbeans](http://netbeans.org/) (version php) car c'est mon éditeur favori mais aussi celui sur lequel j'ai eu jusqu'ici le plus d'expériences en développement de sites et applications ZF1.


Mes premières impressions sont donc les suivantes :

 * malgré un très bon [QuickStart](http://zf2.readthedocs.org/en/latest/index.html#userguide) comprenant les fonctions de bases et notamment la création d'un module, il devient assez vite difficile de trouver de bonnes ressources en ligne.
 * la prise en mains est extrêmement différente de ce que l'on pouvait trouver en ZF1.
 * l'utilisation des namespaces rend le code beaucoup plus lisible et sympathique, et permettra probablement de limiter réellement le nombre de caractères par ligne, pratique souvent recommandée mais difficilement applicable en ZF1 lorsque des modèles pouvaient s'appeler Module_Models_DbTable_ModelName... (Noms qui à l'époque m'ont ceci dit fait adopter le Framework).
 * on trouve déjà quelques modules assez intéressant tels que ZfcUser qui permet en quelques secondes de mettre en place une gestion assez complète des utilisateurs.


Pour ma part, je retrouve donc toute la flexibilité que j'avais adoré dans ZF1, je regrette cependant le manque de ressources hors lecture du code du Framework, mais celui-ci provient probablement de la jeunesse du Framework.