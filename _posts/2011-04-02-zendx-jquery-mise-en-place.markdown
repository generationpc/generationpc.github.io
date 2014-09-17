---
layout: post
status: publish
published: true
title: ZendX jQuery - Mise en place dans Zend Framework
author:
  display_name: Thomas Dutrion
  login: thomas
  email: thomas@engineor.com
  url: http://www.engineor.com
author_login: thomas
author_email: thomas@engineor.com
author_url: http://www.engineor.com
wordpress_id: 5
wordpress_url: http://theocrite.wordpress.com/?p=4
date: '2011-04-02 13:54:09 +0100'
date_gmt: '2011-04-02 11:54:09 +0100'
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
comments:
- id: 34
  author: Benjamin Bouvier
  author_email: benjamin.bouvier29@gmail.com
  author_url: http://www.benjaminbouvier.fr
  date: '2011-06-05 20:03:39 +0100'
  date_gmt: '2011-06-05 18:03:39 +0100'
  content: "Tutoriel très clair, très précis. \r\nMerci"
- id: 35
  author: Kurt
  author_email: fwdavy@yahoo.fr
  author_url: ''
  date: '2011-06-13 21:18:33 +0100'
  date_gmt: '2011-06-13 19:18:33 +0100'
  content: "Salut, merci pour le tuto, mais j'arrive à faire fonctionner Jquery.\r\nMon
    code est bien généré dans ma vue :\r\navec JQuery();?&gt;\r\n\r\n\r\n\r\n\r\nPar
    contre si je fais par exemple : \r\ndatePicker('dp','ds',array());?&gt;\r\n\r\n\r\n....et
    bien ça me donne rien  mais si je passe sur le forme mon calendrier n'apparait
    pas, comme ci jquery n'etait pas chargé !?"
- id: 36
  author: Thomas DUTRION
  author_email: thomas@generation-pc.net
  author_url: http://www.prestalyon.com
  date: '2011-06-13 21:33:44 +0100'
  date_gmt: '2011-06-13 19:33:44 +0100'
  content: |-
    Bonjour Kurt,

    Lorsque tu regardes dans le code source généré de ta page, as-tu les trois inclusions nécessaires ? (jquery, jquery Ui et le css de jqueryUI) ?

    Le site sur lequel tu bosses est-il en ligne ?
---
<p style="text-align: justify;"><img class="alignright" title="Logo Zend Framework" src="http://www.throrinstudio.com/images/design/logo_zf.png" alt="Logo Zend Framework" width="100" height="112" /><br />
Bonjour !</p>
<p style="text-align: justify;">Dans cet article, je vais vous expliquer comment mettre en place les aides de vue ZendX_JQuery dans un projet Zend Framework.</p>
<p style="text-align: justify;">Je pars du principe qu'on dispose d'un projet Zend Framework créé avec l'outil Zend Tool.</p>
<p style="text-align: justify;">Pour commencer, on va copier le dossier ZendX dans le dossier library de notre application. Ce dossier est disponible dans "/extras/library/" de votre version de Zend Framework (version complète).</p>
<p style="text-align: justify;">Ensuite, il va falloir modifier le Bootstrap de sorte à ajouter les aides de vues ZendX_JQuery à l'application :</p>
<p>[sourcecode]protected function _initView() {<br />
    $view = new Zend_View();<br />
    //... code de paramétrage de votre vue : titre, doctype ...<br />
    $view->addHelperPath('ZendX/JQuery/View/Helper', 'ZendX_JQuery_View_Helper');<br />
    //... paramètres optionnels pour les helpeurs jQuery ....<br />
    $viewRenderer = Zend_Controller_Action_HelperBroker::getStaticHelper('ViewRenderer');<br />
    $viewRenderer->setView($view);<br />
    return $view;<br />
}[/sourcecode]</p>
<p style="text-align: justify;">Si vous désirez utiliser des versions locales des scripts de jQuery, et un thème au choix que vous pouvez télécharger sur <a href="http://jqueryui.com/themeroller/">jQueryUI ThemeRoller</a>, il vous suffit d'ajouter les instructions suivantes à votre bootstrap, à la place du commentaire "paramètres optionnels..."</p>
<p>[sourcecode]<br />
$view->jQuery()->setLocalPath('/js/jquery-1.5.min.js')<br />
                      ->setUILocalPath('/js/jquery-ui-1.8.9.custom.min.js')<br />
                      ->addStyleSheet('/css/smoothness/jquery-ui-1.8.9.custom.css');<br />
[/sourcecode]</p>
<p style="text-align: justify;">À ce moment là, Zend sait où aller chercher chaque chose, et il ne reste donc qu'à charger jQuery au moment souhaité. Si on désire le lancer sur toute les pages, il faut mettre les instructions suivantes dans le bootstrap :</p>
<p>[sourcecode]<br />
$view->jQuery()->enable();<br />
$view->jQuery()->uiEnable();<br />
[/sourcecode]</p>
<p style="text-align: justify;">Vous pouvez aussi avoir besoin de jQuery et jQueryUI sur une page seulement, en quel cas vous pouvez le charger dans une vue :</p>
<p>[sourcecode]<br />
$this->jQuery()->enable();<br />
$this->jQuery()->uiEnable();<br />
[/sourcecode]</p>
<p style="text-align: justify;">Ou dans une action (contrôleur d'action => action ou contrôleur d'action =>initialisation) :</p>
<p>[sourcecode]<br />
$this->view->jQuery()->enable();<br />
$this->view->jQuery()->uiEnable();<br />
[/sourcecode]</p>
<p style="text-align: justify;">Et pour finir, la petite instruction qui va bien dans la vue ou le layout approprié.</p>
<p>[sourcecode]< ?php echo $this->jQuery(); ?>[/sourcecode]</p>
<p style="text-align: justify;">Pour finir, ZendX Jquery nous propose une méthode permettant d'éviter les conflits avec les autres frameworks JavaScript utilisés, notamment Dojo qui dispose d'une intégration facile au grâce à Zend Framework.</p>
<p>[sourcecode]<br />
// intégrer Dojo à un projet Zend Framework<br />
$view->addHelperPath('Zend/Dojo/View/Helper/', 'Zend_Dojo_View_Helper');</p>
<p>// passer jQuery en mode sans conflit<br />
ZendX_JQuery_View_Helper_JQuery::enableNoConflictMode();<br />
[/sourcecode]</p>
<p style="text-align:justify;">Le mode sans conflit de jQuery permet seulement l'ajout d'un j après les $ utilisés pour la séléction. Par exemple pour séléctionner la div d'id test, on utilisera</p>
<p>[sourcecode]$j('#test');[/sourcecode]</p>
<p style="text-align:justify;">À la place de </p>
<p>[sourcecode]$('#test');[/sourcecode]</p>
