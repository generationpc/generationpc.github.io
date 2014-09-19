---
layout: post
title: Google Web Font dans un projet Zend Framework
date: '2011-04-24 18:27:20 +0100'
date_gmt: '2011-04-24 16:27:20 +0100'
categories: articles
tags: [Développement, Zend, Zend Framework, Google Web Font, Aide de vue, HeadLink]
comments: true
share: true
---
Utiliser [Google Web Font](http://www.google.com/webfonts) est un outil proposé par Google permettant d'utiliser dans un site web une police non standard pour embellir son site, en choisissant dans une liste donnée.

Je ne suis pas ici pour vous expliquer les avantages et inconvénients de cet outil, mais pour faire court, l'intérêt d'utiliser Google Web Font plutôt que `@font-face` notamment est la mise en cache de la police, et donc un chargement plus rapide si l'utilisateur est déjà passé sur un site utilisant cet outil.

Passons à l'intégration proprement dite. Si nous choisissons une police, disons Special Elite qui est la première dans la liste au moment où j'écris ces mots, et que nous voulons l'intégrer ("utiliser cette police"), Google nous fournit la ligne suivante à coller dans notre code HTML.

{% highlight html %}
<link href='http://fonts.googleapis.com/css?family=Special+Elite' rel='stylesheet' type='text/css'>
{% endhighlight %}

Parfait me direz vous ! Quel est le problème encore ?

Le problème ici, c'est que Zend Framework propose une architecture MVC intéressante à ce niveau là, car ça nous permettra d'inclure où l'on a besoin seulement la police voulue.

Ce mécanisme est simplement possible grâce à une [aide de vue](http://framework.zend.com/manual/fr/zend.view.helpers.html). Regardons donc ce qu'on trouve dans la liste des aides de vue par défaut, et arrêtons nous sur... L'[aide de vue HeadLink](http://framework.zend.com/manual/fr/zend.view.helpers.html#zend.view.helpers.initial.headlink).

{% highlight php %}
$this->headLink()->appendStylesheet('http://fonts.googleapis.com/css?family=Special+Elite');
{% endhighlight %}

Cette dernière instruction ajoute la feuille de style donnée (celle fournie par Google) à la pile de l'aide d'action `HeadLink`. Il ne restera alors qu'à afficher tous les liens dans le layout comme il se doit.

{% highlight php %}
echo $this->headLink();
{% endhighlight %}

Bien sûr, nous avons ajouté précédemment une feuille de style à l'aide de vue depuis une vue, mais il est aussi possible d'en ajouter depuis une action d'un contrôleur d'action grâce à l'appel de `$this->view`, ou encore depuis le `Bootstrap`.

N'hésitez pas à poser des questions en commentaires pour les points de détails !
