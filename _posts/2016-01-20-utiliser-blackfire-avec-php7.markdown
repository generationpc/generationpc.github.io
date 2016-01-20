---
layout: post
title: Utiliser Blackfire avec PHP 7
description: "Blackfire n'étant pas encore compatible php 7, voici une solution pour continuer à l'utiliser."
modified: 2016-01-20
category: tutoriels
tags: [Développement, PHP, Performances, PHP 7]
comments: true
share: true
---

[Blackfire](https://blackfire.io/) est un service proposé par Sensiolabs, permettant de faire un profil de consommation d'une application PHP dans le but de l'optimiser. Rendu public bien avant la sortie de PHP 7, ce service ne propose malheureusement pas de clients à jour à l'heure où j'écris ces lignes, d'où ce tutoriel.

## La solution

Au lieu de se reposer sur les services proposés, c'est à dire le `probe` -- la sonde -- pour récupérer les profils de performance bruts, et l'`agent` -- service à mettre sur le serveur web --  chargé d'envoyer les données aux serveurs de Blackfire, nous allons simplement récupérer les données depuis `XDebug` au format `cachegrind` puis les uploader "manuellement" en utilisant le client fourni par Blackfire.

### Configurer XDebug

Je vais considérer qu'XDebug est installé sur votre machine (testable à l'aide de la commande `php -i | grep "xdebug support"` si vous êtes sur Mac OS X ou Linux).

Pour profiler une page, nous allons donc changer le fichier de configuration d'XDebug. La commande suivante vous permettra de trouver le fichier à éditer :

```
php -i | grep xdebug.ini
```

Ajouter les lignes suivante à ce fichier (ou éditer la valeur actuelle si la ligne existe déjà) :

```
xdebug.profiler_output_dir = /tmp/cachegrind/files
xdebug.profiler_enable_trigger = 1
```

La première ligne doit correspondre à un répertoire existant sur la machine. Vérifiez son existance ou créez le avant tout (`mkdir -p /tmp/cachegrind/files `).

La seconde ligne permet d'activer la collection de données uniquement lors de l'utilisation du paramètre `XDEBUG_PROFILE=1` (passable par cookie, en GET ou en POST).

### Uploader sur Blackfire

Après avoir executé votre première requête avec `XDEBUG_PROFILE=1` activé, vous trouverez un fichier `cachegrind` dans le dossier spécifié.

```
$ ls /tmp/cachegrind/files/                   
cachegrind.out.697
```

Il faut donc maintenant avoir le client Blackfire installé. Vous pouvez utiliser `which blackfire` pour vérifier si le client existe, et si cette commande retourne `blackfire not found`, vous devez alors suivre la [procédure d'installation](https://blackfire.io/docs/up-and-running/installation) (installez uniquement l'agent en suivant les instructions intitulées `Installing the Blackfire CLI tool`).

Enfin, uploadez le fichier cachegrind à l'aide de l'agent :

```
blackfire upload /tmp/cachegrind/files/cachegrind.out.697
```

Voilà, le profil sera alors disponible sur blackfire.io comme vous avez l'habitude avec PHP 5.x sans intervention de votre part.