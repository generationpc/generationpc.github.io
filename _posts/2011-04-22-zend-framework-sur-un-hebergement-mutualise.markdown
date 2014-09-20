---
layout: post
title: Zend Framework sur un hébergement mutualisé
date: '2011-04-22 12:33:20 +0100'
date_gmt: '2011-04-22 10:33:20 +0100'
categories: tutoriels
tags: [Zend, Zend Framework, Développement, Configuration, Hébergement, Mutualisé]
comments: true
---

Cet article fait suite à une question posée sur le forum officiel de la communauté francophone de Zend Framework.

**Sujet :** [Arborescence du site en ligne](http://www.z-f.fr/forum/viewtopic.php?pid=32238)

> Bonjour,
> 
> voila je veux mettre mon site en ligne, seulement vu que j'ai un serveur mutualisé je ne peux pas mettre certains dossiers comme library ou application à la racine.
> 
> Donc je voulais savoir si vous aviez une bonne arborescence a mettre en place au niveau du dossier httpdoc (équivalant de www je crois) sachant que du coup ça va me faire modifier pas mal de chemin dans le site.
> 
> merci d'avance ;-)
> 
> vince851
 
Ma première réponse fût naturellement de lui proposer une réponse en le dirigeant vers une ressource en anglais que j'ai découvert il y a déjà qu﻿elques années : un article de Rob Allen (akrabat) intitulé "[Zend Framework on a shared host](http://akrabat.com/zend-framework/zend-framework-on-a-shared-host)". Malheureusement vince851 ne semble pas très à l'aise avec l'anglais.

Je propose donc dans ce post une traduction (non sans fautes j'imagine) de l'article d'Akrabat, qui respecte sûrement plus le côté technique que le style d'écriture...


Lorsque vous déployez un site de Zend Framework sur un hébergement mutualisé, vous ne pouvez généralement pas modifier le `DocumentRoot` pour pointer vers le dossier `/public/` du site. Par conséquent l'URL du site Web est `http://www.example.com/public/`. Ceci ne semble pas très professionnel, donc nous aimerions le supprimer.

[Note personnelle : le chemin public change selon votre architecture]

Le moyen le plus simple pour cette suppression si on considère un projet créé avec `Zend_Tool` est :

## Créer le fichier `/index.php` ##

{% highlight php %}
define('RUNNING_FROM_ROOT', true);
include 'public/index.php';
{% endhighlight %}

Cette instruction va permettre le changement de racine du site web pour utiliser l'`index.php` déjà créé dans le dossier public par `Zend_Tool`, et nous n'aurons rien à modifier si on déplace le site sur un VPS ou autre où on peut changer le `DocumentRoot` directement à `/public`.

## Créer le fichier `/.htaccess` ##
{% highlight ApacheConf %}
SetEnv APPLICATION_ENV development

RewriteEngine On
RewriteRule .* index.php
{% endhighlight %}

On crée un fichier `.htaccess` qui redirige toutes les requêtes sur l'`index.php` que l'on vient de créer. Ce que l'on veut faire en faisant grâce à cette technique, c'est empêcher l'accès au fichier `application/configs/application.ini` [qui peut notamment contenir les informations de connexion à la base de données, etc]. Bien entendu, donner la valeur correcte à la constante `APPLICATION_ENV` !﻿

## Références pointant sur les fichiers publics ##
Après avoir créé une règle de réécriture très agressive dans le .htaccess, qu'advient-il des fichiers css, js et images contenus dans le dossier public ? [Sous entendu, le nouveau système ne permettra pas l'affichage de ces fichiers].

Heureusement, nous disposons dans le dossier public d'un fichier `.htaccess` capable de gérer correctement la situation. Comme Apache exécutera le fichier `.htaccess` dans le répertoire le plus profond qu'il trouve, toute référence à un dossier ou fichier contenu dans `/public/` sera correctement servit.

Vous devez être au courant de celà lors du référencement des fichiers publics et ajoutez la racine du dossier public à l'url de base (`baseUrl`) vous-même.

Par exemple, vous pouvez configurer votre fichier CSS et d'autres paramètres d'affichage dans un plugin de contrôleur frontal comme ceci :

{% highlight php %}
class App_Controller_Plugin_View extends Zend_Controller_Plugin_Abstract
{
    public function dispatchLoopStartup(Zend_Controller_Request_Abstract $request)
    {
        $frontController = Zend_Controller_Front::getInstance();
        $view = $frontController->getParam('bootstrap')->getResource('view');
        $view->doctype('XHTML1_STRICT');
        $baseUrl = $request->getBaseUrl();
        if (defined('RUNNING_FROM_ROOT')) {
            $baseUrl .= '/public';
            $frontController->setBaseUrl($baseUrl);
        }
        $view->headLink()->appendStylesheet($baseUrl . '/css/main.css');
        $view->headLink()->appendStylesheet($baseUrl . '/css/screen.css', 'screen');
        $view->headLink()->appendStylesheet($baseUrl . '/css/print.css', 'print');
    }
}
{% endhighlight %}

(Pour ce code, on considère que vous avez ajouté `resources.view[] = "" au fichier application.ini`)

Comme on dispose d'une constante qui nous informe du fait qu'on exécute le script directement depuis la racine ou non, on peut ajouter dynamiquement le `/public` dans l'url. Si on change d'hébergement pour un où on peut changer le `DocumentRoot` directement sur le dossier `/public`, on n'aura pas besoin de modifier ce code.

C'est tout. Votre application Zend Framework doit normalement fonctionner proprement sur un hébergement mutualisé.

Personnellement cette solution me semble assez propre étant donné qu'elle permet une certaine portabilité en fonction de l'hébergement choisi, avec possibilité d'évolution de l'offre d'hébergement.

Pour ceux qui souhaitent ne pas se compliquer la vie avec ça, certains hébergeurs (OVH notamment) propose une structure de dossier permettant la mise en place d'une application Zend Framework avec la structure par défaut proposée par `Zend_Tool`.