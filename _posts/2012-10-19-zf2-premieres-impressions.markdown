---
layout: post
status: publish
published: true
title: ZF2, premières impressions !
author:
  display_name: Thomas Dutrion
  login: thomas
  email: thomas@engineor.com
  url: http://www.engineor.com
author_login: thomas
author_email: thomas@engineor.com
author_url: http://www.engineor.com
excerpt: "<p style=\"text-align: justify;\"><a href=\"http://blog.generation-pc.net/wp-content/uploads/2012/10/20121018-113940-PM.jpg\"><img
  class=\"size-full alignright\" style=\"margin: 10px;\" src=\"http://blog.generation-pc.net/wp-content/uploads/2012/10/20121018-113940-PM.jpg\"
  alt=\"20121018-113940 PM.jpg\" width=\"200\" height=\"110\" /></a>Attendu depuis
  de nombreux mois, la nouvelle version de Zend Framework est sortie le 7 septembre
  2012. Je n'ai pas eu le temps de m'y intéresser jusque là, mais je tiens à vous
  donner mon avis après quelques jours de tests...</p>\r\n<p style=\"text-align: justify;\">"
wordpress_id: 358
wordpress_url: http://blog.generation-pc.net/?p=358
date: '2012-10-19 00:41:18 +0100'
date_gmt: '2012-10-18 22:41:18 +0100'
categories:
- Développement
- Web
- Zend Framework
- PHP
- Hébergement
tags:
- Zend
- Zend Framework 2
- Bootstrap
- Phpcloud
comments: []
---
<p style="text-align: justify;"><a href="http://blog.generation-pc.net/wp-content/uploads/2012/10/20121018-113940-PM.jpg"><img class="size-full alignright" style="margin: 10px;" src="http://blog.generation-pc.net/wp-content/uploads/2012/10/20121018-113940-PM.jpg" alt="20121018-113940 PM.jpg" width="200" height="110" /></a>Attendu depuis de nombreux mois, la nouvelle version de Zend Framework est sortie le 7 septembre 2012. Je n'ai pas eu le temps de m'y intéresser jusque là, mais je tiens à vous donner mon avis après quelques jours de tests...</p>
<p style="text-align: justify;"><a id="more"></a><a id="more-358"></a></p>
<p style="text-align: justify;">Voilà bien longtemps maintenant que je n'ai pas écrit de post sur ce blog... Ça ne veut bien entendu pas dire que je vais le délaisser, mais simplement que je n'ai pas eu énormément de temps ces derniers mois. Comme certains d'entre vous le savent, <a href="http://framework.zend.com/" target="_blank">Zend Framework</a> est sorti dans sa version 2 il y a déjà plusieurs semaines, après plusieurs mois de versions bêta publiques. Pour ceux qui ne le savaient pas encore, ou qui se demandent simplement de quoi je parle, je vous laisse faire quelques recherches sur ce sujet car je n'ai malheureusement pas le temps d'en écrire plus.</p>
<p style="text-align: justify;">Pour ma part, j'ai décidé d'utiliser Zend Framework 2 en utilisant le <a href="http://zf2.readthedocs.org/en/latest/index.html#userguide" target="_blank">QuickStart</a> officiel (réalisé sur la base du tutoriel de <a href="http://akrabat.com/" target="_blank">Rob Allen alias Akrabat</a>, référence pour <a href="http://akrabat.com/zend-framework-tutorial/" target="_blank">débuter sur ZF1</a>, dans sa version réécrite pour la version 2 du Framework). Pour ne pas perdre trop de temps avec la mise en place de mon environnement de test, j'ai aussi choisi d'utiliser <a href="http://www.phpcloud.com" target="_blank">phpcloud</a>, hébergement en ligne de machines virtuelles spécifiquement prévu pour le développement d'application sous Zend Framework. Je pense prendre le temps un peu plus tard d'exprimer mon avis sur cette plateforme.</p>
<p style="text-align: justify;">Côté éditeur, j'ai bien entendu choisi d'utiliser <a href="http://netbeans.org/" target="_blank">Netbeans</a> (version php) car c'est mon éditeur favori mais aussi celui sur lequel j'ai eu jusqu'ici le plus d'expériences en développement de sites et applications ZF1.</p>
<p style="text-align: justify;">Mes premières impressions sont donc les suivantes :</p>
<ul style="text-align: justify;">
<li>malgré un très bon <a href="http://zf2.readthedocs.org/en/latest/index.html#userguide" target="_blank">QuickStart</a> comprenant les fonctions de bases et notamment la création d'un module, il devient assez vite difficile de trouver de bonnes ressources en ligne.</li>
<li>la prise en mains est extrêmement différente de ce que l'on pouvait trouver en ZF1.</li>
<li>l'utilisation des namespaces rend le code beaucoup plus lisible et sympathique, et permettra probablement de limiter réellement le nombre de caractères par ligne, pratique souvent recommandée mais difficilement applicable en ZF1 lorsque des modèles pouvaient s'appeler Module_Models_DbTable_ModelName... (Noms qui à l'époque m'ont ceci dit fait adopter le Framework).</li>
<li>on trouve déjà quelques modules assez intéressant tels que ZfcUser qui permet en quelques secondes de mettre en place une gestion assez complète des utilisateurs.</li>
</ul>
<p style="text-align: justify;">Pour ma part, je retrouve donc toute la flexibilité que j'avais adoré dans ZF1, je regrette cependant le manque de ressources hors lecture du code du Framework, mais celui-ci provient probablement de la jeunesse du Framework.</p>
<p style="text-align: justify;">Je pense donc essayer de contribuer si j'arrive à trouver le temps pour enrichir les points qui me semblent encore obscurs dans cette documentation.</p>
