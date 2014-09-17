---
layout: post
status: publish
published: true
title: Google Web Font dans un projet Zend Framework
author:
  display_name: Thomas Dutrion
  login: thomas
  email: thomas@engineor.com
  url: http://www.engineor.com
author_login: thomas
author_email: thomas@engineor.com
author_url: http://www.engineor.com
wordpress_id: 155
wordpress_url: http://blog.generation-pc.net/?p=155
date: '2011-04-24 18:27:20 +0100'
date_gmt: '2011-04-24 16:27:20 +0100'
categories:
- Développement
- Web
- Zend Framework
tags:
- Zend
- Zend Framework
- Développement
- Google Web Font
- Aide de vue
- HeadLink
comments: []
---
<p style="text-align: justify;">Utiliser <a href="http://www.google.com/webfonts">Google Web Font</a> est un outil proposé par Google permettant d'utiliser dans un site web une police non standard pour embellir son site, en choisissant dans une liste donnée.</p>
<p style="text-align: justify;">Je ne suis pas ici pour vous expliquer les avantages et inconvénients de cet outil, mais pour faire court, l'intérêt d'utiliser Google Web Font plutôt que @font-face notamment est la mise en cache de la police, et donc un chargement plus rapide si l'utilisateur est déjà passé sur un site utilisant cet outil.</p>
<p style="text-align: justify;">&nbsp;</p>
<p style="text-align: justify;">Passons à l'intégration proprement dite. Si nous choisissons une police, disons Special Elite qui est la première dans la liste au moment où j'écris ces mots, et que nous voulons l'intégrer ("utiliser cette police"), Google nous fournit la ligne suivante à coller dans notre code HTML.</p>
<p>[sourcecode]
<link href='http://fonts.googleapis.com/css?family=Special+Elite' rel='stylesheet' type='text/css'>[/sourcecode]</p>
<p style="text-align: justify;">Parfait me direz vous ! Quel est le problème encore ?</p>
<p style="text-align: justify;">Le problème ici, c'est que Zend Framework propose une architecture MVC intéressante à ce niveau là, car ça nous permettra d'inclure où l'on a besoin seulement la police voulue.</p>
<p style="text-align: justify;">Ce mécanisme est simplement possible grâce à une <a href="http://framework.zend.com/manual/fr/zend.view.helpers.html">aide de vue</a>. Regardons donc ce qu'on trouve dans la liste des aides de vue par défaut, et arrêtons nous sur... L'<a href="http://framework.zend.com/manual/fr/zend.view.helpers.html#zend.view.helpers.initial.headlink">aide de vue HeadLink</a>.</p>
<p>[sourcecode]< ?php<br />
    $this->headLink()->appendStylesheet('http://fonts.googleapis.com/css?family=Special+Elite');<br />
?>[/sourcecode]</p>
<p style="text-align: justify;">Cette dernière instruction ajoute la feuille de style donnée (celle fournie par Google) à la pile de l'aide d'action HeadLink. Il ne restera alors qu'à afficher tous les liens dans le layout comme il se doit.</p>
<p>[sourcecode]< ?php<br />
    echo $this->headLink();<br />
?>[/sourcecode]</p>
<p style="text-align: justify;">Bien sûr, nous avons ajouté précédemment une feuille de style à l'aide de vue depuis une vue, mais il est aussi possible d'en ajouter depuis une action d'un contrôleur d'action grâce à l'appel de $this-&gt;view, ou encore depuis le Bootstrap.</p>
<p style="text-align: justify;">N'hésitez pas à poser des questions en commentaires pour les points de détails !</p>
<p>[caption id="attachment_161" align="alignright" width="123" caption="Logo Zend Framework"]<img class="size-full wp-image-161" title="logo_small" src="http://blog.generation-pc.net/wp-content/uploads/2011/04/logo_small.gif" alt="Logo Zend Framework" width="123" height="23" />[/caption]</link>
