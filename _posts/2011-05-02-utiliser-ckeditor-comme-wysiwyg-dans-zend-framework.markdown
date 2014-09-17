---
layout: post
status: publish
published: true
title: Utiliser CKeditor comme WYSIWYG dans Zend Framework
author:
  display_name: Thomas Dutrion
  login: thomas
  email: thomas@engineor.com
  url: http://www.engineor.com
author_login: thomas
author_email: thomas@engineor.com
author_url: http://www.engineor.com
wordpress_id: 186
wordpress_url: http://blog.generation-pc.net/?p=186
date: '2011-05-02 16:03:57 +0100'
date_gmt: '2011-05-02 14:03:57 +0100'
categories:
- Développement
- Web
- Zend Framework
tags:
- ZendX Jquery
- Zend
- Zend Framework
- Développement
- Web
- Installer ZendX Jquery
- configuration
- ckeditor
- wysiwyg
comments: []
---
<p style="text-align: justify;">Lors du développement d'une application web comportant une zone d'administration, une problématique est récurrente : comment vais-je intégrer un éditeur graphique pour que le client puisse personnaliser ses textes ?</p>
<p style="text-align: justify;">Dans cet article, je vous propose ma technique pour intégrer l'éditeur wysiwyg CKeditor au sein de votre application Zend Framework, en partant du principe que la structure des fichiers du site est celle proposée par Zend_Tool, en ajoutant une configuration fonctionnelle de ZendX_JQuery (si vous ne savez pas comment obtenir un tel projet, je vous conseille mon article <a href="http://blog.generation-pc.net/2011/04/zendx-jquery-mise-en-place/">ZendX jQuery – Mise en place dans Zend Framework</a>.</p>
<h3 style="text-align: justify;">Définition de la structure du projet</h3>
<ul style="list-style-type: square;">
<li>sources du site
<ul style="list-style-type: disc;">
<li>application
<ul style="list-style-type: circle;">
<li>config
<ul style="list-style-type: square;">
<li>application.ini</li>
</ul>
</li>
<li>layouts
<ul style="list-style-type: square;">
<li>...</li>
</ul>
</li>
<li>controllers
<ul style="list-style-type: square;">
<li>...</li>
</ul>
</li>
<li>views
<ul style="list-style-type: square;">
<li>...</li>
</ul>
</li>
<li>...</li>
<li>Bootstrap.php</li>
</ul>
</li>
<li>library
<ul style="list-style-type: circle;">
<li>Application</li>
<li>Zend
<ul style="list-style-type: square;">
<li>...</li>
</ul>
</li>
<li>ZendX
<ul style="list-style-type: square;">
<li>...</li>
</ul>
</li>
</ul>
</li>
<li>public
<ul style="list-style-type: circle;">
<li>js</li>
<li>css</li>
<li>...</li>
<li>index.php</li>
</ul>
</li>
</ul>
</li>
</ul>
<p style="text-align: justify;">Les fichiers/dossiers en rouges sont ceux dans lesquels on va modifier des choses.</p>
<p style="text-align: justify;">Premièrement, nous allons ajouter la référence permettant de charger automatiquement les dossiers et fichiers du dossier /library/Application, et pour cela il va falloir éditer le fichier/application/config/application.ini.</p>
<p style="text-align: justify;">Toujours en considérant les fichiers générés par Zend_Tool, il va donc falloir ajouter la ligne suivante dans la catégorie production :</p>
<p>[sourcecode]<br />
[production]<br />
autoloaderNamespaces[] = "Application_"<br />
[/sourcecode]</p>
<div style="text-align: justify;">Maintenant qu'on a chargé le répertoire dans l'include path, il ne nous reste plus qu'à les ajouter. Télécharger les fichiers et installez les dans le dossier /library/Application [<a href="http://www.megaupload.com/?d=X8CKXS0J">Zip des fichiers</a>].</div>
<h3 style="text-align: justify;">Définition de la librairie</h3>
<ul style="list-style-type: square;">
<li>sources du site
<ul style="list-style-type: disc;">
<li>library
<ul style="list-style-type: circle;">
<li>Application
<ul style="list-style-type: square;">
<li>JQuery
<ul style="list-style-type: disc;">
<li>Form
<ul style="list-style-type: circle;">
<li>Element
<ul style="list-style-type: square;">
<li>TextareaCKEditor.php</li>
</ul>
</li>
</ul>
</li>
<li>View
<ul style="list-style-type: circle;">
<li>Helper
<ul style="list-style-type: square;">
<li>CKeditor.php</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
</ul>
<p>&nbsp;</p>
<div style="text-align: justify;">On a presque fini je vous rassure. On ajoute rapidement le dossier de CKEditor [<a href="http://www.megaupload.com/?d=MLW6DPKN">version modifiée fonctionnelle avec ce tutoriel</a>] dans le dossier<strong><em>/public/js/</em></strong>.</div>
<div style="text-align: justify;">On fini le tutoriel en ajoutant les aides de vues dans l'include path pour que Zend les retrouve. Ça se passe dans le Bootstrap de l'application. Etant donné que vous avez déjà ZendX_JQuery de configuré, vous devez avoir une méthode _initView ou similaire dans laquelle vous avez une variable view contenant une Zend_View :</div>
<p>[sourcecode]<br />
$view->addHelperPath('Application/JQuery/View/Helper', 'Application_JQuery_View_Helper');<br />
[/sourcecode]</p>
<div style="text-align: justify;">Et voilà !</p>
<div style="text-align: justify;">Je viens de lire aujourd'hui un article de Rob Allen sur les View Helpers dans Zend Framework, et il propose de les intégrer légèrement différemment. Au lieu de mettre la ligne précédente dans le Bootstrap, il propose d'ajouter la ligne suivante directement dans votre application.ini situé dans le dossier config.<br />
[sourcecode]resources.view.helperPath.Application_View_Helper_ = "Application/View/Helper/"[/sourcecode]</p>
<div style="text-align: justify;">Maintenant pour l'utiliser, il ne vous reste qu'à instancier un objet Application_JQuery_Form_Element_TextareaCKEditor et l'ajouter à un Zend_Form ou faire un $this->ckeditor() sur un objet vue.</div>
<div style="text-align: justify;">Il est par ailleurs possible de passer des paramètres à une instance d'Application_JQuery_Form_Element_TextareaCKEditor en utilisant la méthode setJQueryParam($name, $value). Pour connaitre la liste des paramètres disponibles, rendez vous sur le site de CKEditor.</div>
<div style="text-align: justify;">La principale restriction actuelle de cet élément de formulaire est que le chemin vers la librairie est statique, et que le dossier ckeditor doit donc nécessairement se trouver dans /public/js/.</div>
</div>
</div>
