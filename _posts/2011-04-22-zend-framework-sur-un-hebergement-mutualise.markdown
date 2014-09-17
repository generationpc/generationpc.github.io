---
layout: post
status: publish
published: true
title: Zend Framework sur un hébergement mutualisé
author:
  display_name: Thomas Dutrion
  login: thomas
  email: thomas@engineor.com
  url: http://www.engineor.com
author_login: thomas
author_email: thomas@engineor.com
author_url: http://www.engineor.com
wordpress_id: 122
wordpress_url: http://blog.generation-pc.net/?p=122
date: '2011-04-22 12:33:20 +0100'
date_gmt: '2011-04-22 10:33:20 +0100'
categories:
- Développement
- Web
- Zend Framework
tags:
- Zend
- Zend Framework
- Développement
- configuration
- Hébergement
- Mutualisé
comments:
- id: 37
  author: snoopy
  author_email: preeteeg@gmail.com
  author_url: ''
  date: '2011-06-14 17:05:42 +0100'
  date_gmt: '2011-06-14 15:05:42 +0100'
  content: "Hello ,\r\nAm a newbie to zendframework , i have deployed my zend application
    on a shared host and modified the htaccess file found in the root directory to
    redirect to the public folder of my project named zendproject.\r\n\r\nHere is
    the structure \r\n/Root\r\n.htacess\r\nindex.php\r\n /otherproject\r\n /zendproject\r\n
    \  /application\r\n   /library\r\n   /docs\r\n   /test\r\n   /public\r\n       .htaccess\r\n
    \      index.php\r\n       /skin\r\n         /blues\r\n         /css\r\n           layout.css\r\n
    \          form.css\r\n         /images\r\n       /js\r\n      \r\n\r\nModification
    rewritebase of the  root/.htaccess file a \r\n<code>RewriteEngine on\r\nRewriteBase
    /zendproject/public/\r\nRewriteRule !\\.(js|ico|gif|jpg|png|css)$ index.php\r\nOptions
    -MultiViews\r\n</code>\r\n\r\nIn the public folder i have not modified the default
    .htacess and index.php.\r\nam able to render my default content \"Welcome to the
    Zend Framework!\r\nThis is your project's main page\" on www.site.com however
    am having an issue with the loading of the css files , on firebug /net consol
    i have the following www.site.com/skin/blues/css/layout.css 404 not found.\r\n\r\nif
    i place the absolute path in\r\n<code> </code> the css file is found and it render
    the proper layout style but i dont want the absolute path to be visible..  \r\ni
    want it to be like\r\n<code>\r\n\r\n</code><code>\r\n\r\nCan help me out and if
    wherever this is the right way to deploy a zend project on a shared host.thanks
    you for help</code>"
- id: 38
  author: snoopy
  author_email: preeteeg@gmail.com
  author_url: ''
  date: '2011-06-14 17:10:40 +0100'
  date_gmt: '2011-06-14 15:10:40 +0100'
  content: "Missing comment\r\nif i place the absolute path in\r\n<code></code>\r\nthe
    css file is found and it render the proper layout style but i dont want the absolute
    path to be visible..\r\ni want it to be like\r\n<code></code>\r\nCan help me out
    and if wherever this is the right way to deploy a zend project on a shared host.thanks
    you for help"
- id: 39
  author: Thomas DUTRION
  author_email: thomas@generation-pc.net
  author_url: http://www.prestalyon.com
  date: '2011-06-14 18:34:31 +0100'
  date_gmt: '2011-06-14 16:34:31 +0100'
  content: "Hi,\r\n\r\nActually, you don't have to change anything in your project
    to host it on a shared hosting. You just have to create a .htaccess and an index.php
    on the project root.\r\n\r\nIf you would like to get good support in English,
    you'd better have a look on Akrabat's blog : http://akrabat.com/zend-framework/zend-framework-on-a-shared-host\r\n\r\nAkrabat
    knows Zend Framework very well, and I learned a lot from his website. He is english
    speaking which can be good for you.\r\n\r\nAs your problem seems to be only about
    public files references, you should read again the second point of the tutorial."
- id: 40
  author: snoopy
  author_email: preeteeg@gmail.com
  author_url: ''
  date: '2011-06-14 20:59:43 +0100'
  date_gmt: '2011-06-14 18:59:43 +0100'
  content: "Hi Thomas,\r\nIndeed am having a problem with the files references(css,js)
    in the public folder as they are not found when a request is made to access www.site.com.\r\n\r\nThanks
    you for the english support :) indeed helpful.\r\n\r\nThanks u :)"
- id: 41
  author: Thomas DUTRION
  author_email: thomas@generation-pc.net
  author_url: http://www.prestalyon.com
  date: '2011-06-14 21:14:28 +0100'
  date_gmt: '2011-06-14 19:14:28 +0100'
  content: "Have you succeded to set up a plugin controller for the view ?\r\n\r\nCan
    you send a feedback when you make it work in order to improve this article."
- id: 42
  author: snoopy
  author_email: preeteeg@gmail.com
  author_url: ''
  date: '2011-06-15 15:58:23 +0100'
  date_gmt: '2011-06-15 13:58:23 +0100'
  content: "Hi Thomas,\r\n\r\nAm still having the 404 problem with the loading of
    css files(files not found) despite having set up the view controller plugin .\r\n\r\nHere
    is my set up\r\n:\r\n1.To set up the plugin controller for the view in the boostrap
    file\r\n\r\n<code>\r\n  doctype('XHTML1_STRICT');\r\n            $view-&gt;headTitle('Zend');\r\n
    \            $view-&gt;skin = 'blues';   \r\n            // Add it to the ViewRenderer\r\n
    \           $viewRenderer = Zend_Controller_Action_HelperBroker::getStaticHelper('ViewRenderer');\r\n
    \           $viewRenderer-&gt;setView($view);\r\n            // Return it, so
    that it can be stored by the bootstrap\r\n            return $view;\r\n        }\r\n
    \       \r\n   public function _initAutoload(){\r\n            \r\n            //Add
    autoloader empty namespace\r\n            $autoloader = Zend_Loader_Autoloader::getInstance();\r\n
    \           $resourceLoader= new Zend_Loader_Autoloader_Resource(array(\r\n                'basePath'
    =&gt; APPLICATION_PATH,\r\n                'namespace' =&gt; '',\r\n                'resourceTypes'=&gt;array(\r\n
    \                 'App' =&gt; array(\r\n                        'path' =&gt; 'my/controller/plugin/',\r\n
    \                       'namespace'=&gt;'My_Controller_Plugin_'\r\n                   )\r\n
    \               )\r\n            ));\r\n            // Return it so that it can
    be stored by the bootstrap\r\n            return $autoloader;\r\n        }\r\n\r\n\r\n//register
    the plugin\r\n  protected function _initRegisterControllerPlugins() {\r\n            $this-&gt;bootstrap('frontController')
    ;\r\n            $front = $this-&gt;getResource('frontController') ;\r\n            $front-&gt;registerPlugin(new
    App_Controller_Plugin_View());\r\n    \r\n}\r\n</code>\r\n\r\n2. In the directory
    zendproject/application/app/controller/plugin/view.php\r\n<code>\r\n  getParam('bootstrap')-&gt;getResource('view');
    \      \r\n         $baseUrl = $request-&gt;getBaseUrl();\r\n        if (defined('RUNNING_FROM_ROOT'))
    {\r\n            $baseUrl .= '/public/'; \r\n            $frontController-&gt;setBaseUrl($baseUrl);
    \r\n        }\r\n     \r\n    }   \r\n}\r\n</code>\r\n\r\n3. In the application/config/application.ini
    \r\n<code>\r\nresources.frontController.plugins.view = \"App_Controller_Plugin_View\"\r\n</code>\r\n\r\n4.In
    my zendproject/application/layouts/script/layout.phtml \r\n<code>\r\n  \r\n      loadSkin($this-&gt;skin,$this-&gt;baseUrl);\r\n
    \      ?&gt;\r\n  \r\n  \r\n         layout()-&gt;content?&gt;\r\n  \r\n</code>\r\n\r\nIn
    my zendproject/application/views/helpers/LoadSkin.php\r\n<code>\r\n stylesheets-&gt;stylesheet-&gt;toArray();\r\n//
    append each stylesheet\r\nif (is_array($stylesheets)) {\r\nforeach ($stylesheets
    as $stylesheet) {\r\n  $style=$this-&gt;view-&gt;headLink()-&gt;appendStylesheet($baseUrl.'/skin/'
    . $skin .'/css/' . $stylesheet);\r\n}\r\n}\r\nreturn $style;\r\n}\r\n}\r\n</code>\r\n\r\nIn
    zendproject/public/skin/skin.xml\r\n<code>\r\n \r\n\r\n\r\n    layout.css\r\n
    \   text.css\r\n    forms.css\r\n\r\n\r\n    layout.css\r\n    text.css\r\n    forms.css\r\n\r\n\r\n\r\n</code>\r\n\r\nIn
    zendproject/public/skin/blues/css/layout.css\r\n\r\nIn zendproject/.htaccess\r\n<code>\r\nSetEnv
    APPLICATION_ENV development\r\n\r\nRewriteEngine On\r\nRewriteRule .* index.php\r\n</code>\r\nIn
    zendproject/index.php\r\n<code>\r\n&lt; ?php\r\n    define(&#039;RUNNING_FROM_ROOT&#039;,
    true);\r\n    include &#039;public/index.php&#039;;\r\n</code>\r\n\r\nThe layout
    is rendering properly except the css file is not found.\r\nPutting an absolute
    path on the shared host make the css file to be found but i don't want to use
    an absolute path like that\r\n<code>\r\nlink type=\"text/css\" rel=\"stylesheet\"
    media=\"screen\" href=\"/zendproject/public/skin/blues/css/layout.css\"&gt;\r\n</code>\r\nI
    want the path to be like that:\r\n<code>\r\nlink type=\"text/css\" rel=\"stylesheet\"
    media=\"screen\" href=\"skin/blues/css/layout.css\"&gt;\r\n</code>\r\nAny kind
    help to sort out why the css file is not loading is the most welcome because am
    on this problem since 2 days.. thank u in advance."
- id: 77
  author: iMad
  author_email: belhauss@gmail.com
  author_url: ''
  date: '2012-08-22 03:57:31 +0100'
  date_gmt: '2012-08-22 01:57:31 +0100'
  content: "Bonjour,\r\n\r\nmerci pour l'effort Thomas\r\nJe viens de tester votre
    solution et sa marche nickel, mais je vois qu'on peut accéder à notre application
    via 2 url, avec et sans \"public\", et celà si je me rappel bien pose un problème
    pour SEO.\r\net je me demande est-ce qu'il y a un remède a ce problème et merci"
- id: 78
  author: Thomas DUTRION
  author_email: thomas@generation-pc.net
  author_url: http://blog.generation-pc.net
  date: '2012-08-22 09:13:14 +0100'
  date_gmt: '2012-08-22 07:13:14 +0100'
  content: "Bonjour,\r\n\r\nMerci pour la remarque. Je pense en effet que ça peut
    poser problème.\r\n\r\nPersonnellement je recommande l'utilisation d'un virtualhost
    (pas souvent possible en mutualisé) ou d'un lien symbolique si ton hébergeur propose
    un accès ssh.\r\n\r\nEn terme de SEO, dans le pire des cas le moteur de recherche
    compte un duplicate content et massacre la note du site. Dans le meilleurs des
    cas je pense que chaque url a un rang, et fait concurrence aux autres url (pour
    la même ressource).\r\n\r\nJe pense qu'il est possible d'agir à l'aide du .htaccess
    :\r\n<code>\r\nSetEnv APPLICATION_ENV development\r\n\r\nRewriteEngine On\r\nRewriteRule
    .* index.php\r\n</code>\r\n\r\nSi on arrive à insérer une redirection permanente
    :\r\n<code>\r\nSetEnv APPLICATION_ENV development\r\n\r\nRewriteEngine On\r\nRewriteCond
    %{HTTP_HOST} ^site\\.com$ [NC]\r\nRewriteRule ^\\/public\\/(.*)$ http://site.com/public/$1
    [R=301,L]\r\n\r\nRewriteRule .* index.php\r\n</code>\r\n\r\nEn tout cas je verrais
    bien un truc comme ça, j'ai pas testé donc je compte sur toi pour nous faire un
    retour que je pourrais intégrer à l'article !"
- id: 79
  author: iMad
  author_email: belhauss@gmail.com
  author_url: ''
  date: '2012-08-22 18:26:56 +0100'
  date_gmt: '2012-08-22 16:26:56 +0100'
  content: "Bonjour,\r\n\r\nj'essaie maintenant ta proposition en local, mais je ne
    suis pas un PRO de htaccess, et je ne sais pas quoi faire exactement, c'est ce
    j'ai essayé et ça ne marche pas\r\n\r\nRewriteEngine On\r\nRewriteCond %{HTTP_HOST}
    ^localhost$ [NC]\r\nRewriteRule ^\\/public\\/(.*)$ http://localhost/public/$1
    [R=301,L]\r\nRewriteRule .* index.php\r\n\r\nmais je ne suis pas sur de ma 2iem
    ligne..\r\nen tout cas dans les jours qui viennent, j'aurais accès à un hebergeur
    Pro et je retournerais le résultat."
- id: 80
  author: Thomas DUTRION
  author_email: thomas@generation-pc.net
  author_url: http://blog.generation-pc.net
  date: '2012-08-22 18:40:24 +0100'
  date_gmt: '2012-08-22 16:40:24 +0100'
  content: "Essaye avec le code suivant :\r\n<code>\r\nSetEnv APPLICATION_ENV development\r\nRewriteEngine
    On\r\nRewriteCond %{HTTP_HOST} ^localhost$ [NC]\r\nRewriteRule ^\\/public\\/(.*)$
    http://localhost/$1 [R=301,L]\r\nRewriteRule .* index.php\r\n</code>\r\n\r\nJe
    vois pas pourquoi j'avais remis le /public dans la seconde partie...\r\n\r\nTu
    vas aller chez quel hébergeur ?"
- id: 81
  author: iMad
  author_email: belhauss@gmail.com
  author_url: ''
  date: '2012-08-22 19:21:05 +0100'
  date_gmt: '2012-08-22 17:21:05 +0100'
  content: "ahh je vois ! ça arrive :)\r\n\r\nmais ce code marche pas, je vois toujours
    public sur l'url :/\r\n\r\nmon hébergeur serait www.50dhs.net, je sais j'aurais
    du choisir OVH mais bon ..\r\net merci encore une fois"
- id: 82
  author: Thomas DUTRION
  author_email: thomas@generation-pc.net
  author_url: http://blog.generation-pc.net
  date: '2012-08-22 22:05:26 +0100'
  date_gmt: '2012-08-22 20:05:26 +0100'
  content: |-
    Là j'avoue que je sais pas trop...

    Dans l'idée, essaye quand même d'utiliser au mieux les virtualhost. Je ne connais pas 50dhs (prix attractifs au passage), mais ils ont l'air d'utiliser Cpanel, donc tu pourras peut être avoir une interface pour dire sur quels dossiers doivent pointer les noms de domaine.
---
<p style="text-align: justify;">Cet article fait suite à une question posée sur le forum officiel de la communauté francophone de Zend Framework.</p>
<p style="text-align: justify;">Sujet : <a href="http://www.z-f.fr/forum/viewtopic.php?pid=32238">Arborescence du site en ligne</a>.</p>
<blockquote><p>Bonjour,</p>
<p>voila je veux mettre mon site en ligne, seulement vu que j'ai un serveur mutualisé je ne peux pas mettre certains dossiers comme library ou application à la racine.</p>
<p>Donc je voulais savoir si vous aviez une bonne arborescence a mettre en place au niveau du dossier httpdoc (équivalant de www je crois) sachant que du coup ça va me faire modifier pas mal de chemin dans le site.<br />
merci d'avance ;-)</p>
<p>vince851</p></blockquote>
<p style="text-align: justify;">Ma première réponse fût naturellement de lui proposer une réponse en le dirigeant vers une ressource en anglais que j'ai découvert il y a déjà qu﻿elques années : un article de Rob Allen (akrabat) intitulé "<a href="http://akrabat.com/zend-framework/zend-framework-on-a-shared-host">Zend Framework on a shared host</a>". Malheureusement vince851 ne semble pas très à l'aise avec l'anglais.</p>
<p style="text-align: justify;">Je propose donc dans ce post une traduction (non sans fautes j'imagine) de l'article d'Akrabat, qui respecte sûrement plus le côté technique que le style d'écriture...</p>
<hr />
<p style="text-align: justify;">Lorsque vous déployez un site de Zend Framework sur un hébergement mutualisé, vous ne pouvez généralement pas modifier le DocumentRoot pour pointer vers le public / le dossier du site. Par conséquent l'URL du site Web est http://www.example.com/public/. Ceci ne semble pas très professionnel, donc nous aimerions le supprimer.</p>
<p style="text-align: justify;">[Note personnelle : le chemin public change selon votre architecture]</p>
<p style="text-align: justify;">Le moyen le plus simple pour cette suppression si on considère un projet créé avec Zend_Tool est :</p>
<p><em><strong>Créer le fichier /index.php</strong></em><br />
[sourcecode]< ?php<br />
    define('RUNNING_FROM_ROOT', true);<br />
    include 'public/index.php';[/sourcecode]</p>
<p style="text-align: justify;">Cette instruction va permettre le changement de racine du site web pour utiliser l'index.php déjà créé dans le dossier public par Zend_Tool, et nous n'aurons rien à modifier si on déplace le site sur un VPS ou autre où on peut changer le DocumentRoot directement à public/.</p>
<p><em><strong>Créer le fichier /.htaccess</strong></em><br />
[sourcecode]SetEnv APPLICATION_ENV development</p>
<p>RewriteEngine On<br />
RewriteRule .* index.php[/sourcecode]</p>
<p style="text-align: justify;">On crée un fichier .htaccess qui redirige toutes les requêtes sur l'index.php que l'on vient de créer. Ce que l'on veut faire en faisant grâce à cette technique, c'est empêcher l'accès au fichier application/configs/application.ini [qui peut notamment contenir les informations de connexion à la base de données, etc]. Bien entendu, donner la valeur correcte à la constante APPLICATION_ENV !﻿</p>
<p><em><strong>Références pointant sur les fichiers publics</strong></em></p>
<p style="text-align: justify;">Après avoir créé une règle de réécriture très agressive dans le .htaccess, qu'advient-il des fichiers css, js et images contenus dans le dossier public ? [Sous entendu, le nouveau système ne permettra pas l'affichage de ces fichiers].</p>
<p style="text-align: justify;">Heureusement, nous disposons dans le dossier public d'un fichier .htaccess capable de gérer correctement la situation. Comme Apache exécutera le fichier .htaccess dans le répertoire le plus profond qu'il trouve, toute référence à un dossier ou fichier contenu dans /public/ sera correctement desservie.</p>
<p style="text-align: justify;">Vous devez être au courant de celà lors du référencement des fichiers publics et ajoutez la racine du dossier public à l'url de base (baseUrl) vous-même.</p>
<p style="text-align: justify;">Par exemple, vous pouvez configurer votre fichier CSS et d'autres paramètres d'affichage dans un plugin de contrôleur frontal comme ceci:</p>
<p>[sourcecode]class App_Controller_Plugin_View extends Zend_Controller_Plugin_Abstract<br />
{<br />
    public function dispatchLoopStartup(Zend_Controller_Request_Abstract $request)<br />
    {<br />
        $frontController = Zend_Controller_Front::getInstance();<br />
        $view = $frontController->getParam('bootstrap')->getResource('view'); </p>
<p>        $view->doctype('XHTML1_STRICT');</p>
<p>        $baseUrl = $request->getBaseUrl();<br />
        if (defined('RUNNING_FROM_ROOT')) {<br />
            $baseUrl .= '/public'; <br />
            $frontController->setBaseUrl($baseUrl); <br />
        }<br />
        $view->headLink()->appendStylesheet($baseUrl . '/css/main.css');<br />
        $view->headLink()->appendStylesheet($baseUrl . '/css/screen.css', 'screen');<br />
        $view->headLink()->appendStylesheet($baseUrl . '/css/print.css', 'print');<br />
    }   <br />
}[/sourcecode]</p>
<p style="text-align: justify;">(Pour ce code, on considère que vous avez ajouté resources.view[] = "" au fichier application.ini)</p>
<p style="text-align: justify;">Comme on dispose d'une constante qui nous informe du fait qu'on exécute le script directement depuis la racine ou non, on peut ajouter dynamiquement le /public dans l'url. Si on change d'hébergement pour un où on peut changer le DocumentRoot directement sur le dossier /public/, on n'aura pas besoin de modifier ce code.</p>
<p style="text-align: justify;">C'est tout. Votre application Zend Framework doit normalement fonctionner proprement sur un hébergement mutualisé.</p>
<hr />
<p style="text-align: justify;">Personnellement cette solution me semble assez propre étant donné qu'elle permet une certaine portabilité en fonction de l'hébergement choisi, avec possibilité d'évolution de l'offre d'hébergement.</p>
<p style="text-align: justify;">Pour ceux qui souhaitent ne pas se compliquer la vie avec ça, certains hébergeurs (OVH notamment) propose une structure de dossier permettant la mise en place d'une application Zend Framework avec la structure par défaut proposée par Zend_Tool.</p>
