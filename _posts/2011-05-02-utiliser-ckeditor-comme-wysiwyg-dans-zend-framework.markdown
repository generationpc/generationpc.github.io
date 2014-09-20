---
layout: post
title: Utiliser CKeditor comme WYSIWYG dans Zend Framework
date: '2011-05-02 16:03:57 +0100'
date_gmt: '2011-05-02 14:03:57 +0100'
categories: tutoriels
tags: [Développement, ZendX Jquery, Zend, Zend Framework, Web, Configuration, ckeditor, wysiwyg]
comments: true
share: true
redirect_from: "/2011/05/utiliser-ckeditor-comme-wysiwyg-dans-zend-framework/"
---

Lors du développement d'une application web comportant une zone d'administration, une problématique est récurrente : comment vais-je intégrer un éditeur graphique pour que le client puisse personnaliser ses textes ?

Dans cet article, je vous propose ma technique pour intégrer l'éditeur wysiwyg CKeditor au sein de votre application Zend Framework, en partant du principe que la structure des fichiers du site est celle proposée par Zend_Tool, en ajoutant une configuration fonctionnelle de ZendX_JQuery (si vous ne savez pas comment obtenir un tel projet, je vous conseille mon article <a href="http://blog.generation-pc.net/2011/04/zendx-jquery-mise-en-place/">ZendX jQuery – Mise en place dans Zend Framework</a>.

## Définition de la structure du projet ##

 * /
     * application
         * config
             * application.ini
         * layouts
             * ...
         * controllers
             * ...
         * views
             * ...
         * ...
         * Bootstrap.php
     * library
         * Application
         * Zend
             * ...
         * ZendX
             * ...
     * public
         * js
         * css
         * ...
         * index.php

Les fichiers/dossiers en rouges sont ceux dans lesquels on va modifier des choses.

Premièrement, nous allons ajouter la référence permettant de charger automatiquement les dossiers et fichiers du dossier `/library/Application`, et pour cela il va falloir éditer le fichier `/application/config/application.ini`.

Toujours en considérant les fichiers générés par Zend_Tool, il va donc falloir ajouter la ligne suivante dans la catégorie production :

{% highlight ini %}
[production]
autoloaderNamespaces[] = "Application_"
{% endhighlight %}

Maintenant qu'on a chargé le répertoire dans l'include path, il ne nous reste plus qu'à les ajouter. Télécharger les fichiers et installez les dans le dossier `/library/Application` [[Zip des fichiers](http://www.megaupload.com/?d=X8CKXS0J)].

## Définition de la librairie ##

 * /
     * library
         * Application
             * JQuery
                 * Form
                     * Element
                         * TextareaCKEditor.php
                 * View
                     * Helper
                         * CKeditor.php

On a presque fini je vous rassure. On ajoute rapidement le dossier de CKEditor [[version modifiée fonctionnelle avec ce tutoriel](http://www.megaupload.com/?d=MLW6DPKN)] dans le dossier `/public/js/`.

On fini le tutoriel en ajoutant les aides de vues dans l'include path pour que Zend les retrouve. Ça se passe dans le Bootstrap de l'application. Etant donné que vous avez déjà `ZendX_JQuery` de configuré, vous devez avoir une méthode \_initView ou similaire dans laquelle vous avez une variable view contenant une `Zend_View` :

{% highlight php %}
$view->addHelperPath('Application/JQuery/View/Helper', 'Application_JQuery_View_Helper');<br />
{% endhighlight %}

Et voilà !


Je viens de lire aujourd'hui un article de Rob Allen sur les View Helpers dans Zend Framework, et il propose de les intégrer légèrement différemment. Au lieu de mettre la ligne précédente dans le Bootstrap, il propose d'ajouter la ligne suivante directement dans votre application.ini situé dans le dossier config.

{% highlight ini %}
resources.view.helperPath.Application_View_Helper_ = "Application/View/Helper/"
{% endhighlight %}

Maintenant pour l'utiliser, il ne vous reste qu'à instancier un objet `Application_JQuery_Form_Element_TextareaCKEditor` et l'ajouter à un `Zend_Form` ou faire un `$this->ckeditor()` sur un objet vue.

Il est par ailleurs possible de passer des paramètres à une instance d'`Application_JQuery_Form_Element_TextareaCKEditor` en utilisant la méthode `setJQueryParam($name, $value)`. Pour connaitre la liste des paramètres disponibles, rendez vous sur le site de CKEditor.

La principale restriction actuelle de cet élément de formulaire est que le chemin vers la librairie est statique, et que le dossier ckeditor doit donc nécessairement se trouver dans `/public/js/`.