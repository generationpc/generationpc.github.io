---
layout: post
title: ZendX jQuery - Mise en place dans Zend Framework
date: '2011-04-02 13:54:09 +0100'
date_gmt: '2011-04-02 11:54:09 +0100'
categories: articles
tags: [Développement, Zend Framework, ZendX Jquery, Zend Framework]
comments: true
---
![Logo Zend Framework](/images/posts/2011-04-02-zendx-jquery-mise-en-place/01.png)

Bonjour !

Dans cet article, je vais vous expliquer comment mettre en place les aides de vue `ZendX_JQuery` dans un projet Zend Framework.

Je pars du principe qu'on dispose d'un projet Zend Framework créé avec l'outil `Zend_Tool`.

Pour commencer, on va copier le dossier `ZendX` dans le dossier library de notre application. Ce dossier est disponible dans `/extras/library/` de votre version de Zend Framework (version complète).

Ensuite, il va falloir modifier le Bootstrap de sorte à ajouter les aides de vues `ZendX_JQuery` à l'application :

{% highlight php %}
protected function _initView()
{
    $view = new Zend_View();
    //...code de paramétrage de votre vue : titre, doctype...
    $view->addHelperPath('ZendX/JQuery/View/Helper', 'ZendX_JQuery_View_Helper');
    //...paramètres optionnels pour les helpeurs jQuery...
    $viewRenderer = Zend_Controller_Action_HelperBroker::getStaticHelper('ViewRenderer');
    $viewRenderer->setView($view);
    return $view;
}
{% endhighlight %}

Si vous désirez utiliser des versions locales des scripts de jQuery, et un thème au choix que vous pouvez télécharger sur [jQueryUI ThemeRoller](http://jqueryui.com/themeroller/), il vous suffit d'ajouter les instructions suivantes à votre bootstrap, à la place du commentaire "paramètres optionnels..."

{% highlight php %}
$view->jQuery()->setLocalPath('/js/jquery-1.5.min.js')
               ->setUILocalPath('/js/jquery-ui-1.8.9.custom.min.js')
               ->addStyleSheet('/css/smoothness/jquery-ui-1.8.9.custom.css');
{% endhighlight %}

À ce moment là, Zend sait où aller chercher chaque chose, et il ne reste donc qu'à charger jQuery au moment souhaité. Si on désire le lancer sur toute les pages, il faut mettre les instructions suivantes dans le bootstrap :

{% highlight php %}
$view->jQuery()->enable();
$view->jQuery()->uiEnable();
{% endhighlight %}

Vous pouvez aussi avoir besoin de jQuery et jQueryUI sur une page seulement, en quel cas vous pouvez le charger dans une vue :

{% highlight php %}
$this->jQuery()->enable();
$this->jQuery()->uiEnable();
{% endhighlight %}

Ou dans une action (contrôleur d'action => action ou contrôleur d'action => initialisation) :

{% highlight php %}
$this->view->jQuery()->enable();
$this->view->jQuery()->uiEnable();
{% endhighlight %}

Et pour finir, la petite instruction qui va bien dans la vue ou le layout approprié.
`<?php echo $this->jQuery(); ?>`

Pour finir, `ZendX_Jquery` nous propose une méthode permettant d'éviter les conflits avec les autres frameworks JavaScript utilisés, notamment Dojo qui dispose d'une intégration facile au grâce à Zend Framework.

{% highlight php %}
// intégrer Dojo à un projet Zend Framework
$view->addHelperPath('Zend/Dojo/View/Helper/', 'Zend_Dojo_View_Helper');
// passer jQuery en mode sans conflit
ZendX_JQuery_View_Helper_JQuery::enableNoConflictMode();
{% endhighlight %}

Le mode sans conflit de jQuery permet seulement l'ajout d'un `j` après les `$` utilisés pour la séléction. Par exemple pour séléctionner la div d'id test, on utilisera `$j('#test');` à la place de `$('#test');`.

