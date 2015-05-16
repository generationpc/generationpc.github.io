---
layout: post
title: PhpBB erreur Trailing paths not supported
description: "Comment héberger un site web gratuitement lorsque l'on démarre."
modified: 2015-05-16
category: tutoriels
tags: [Développement, Internet, Mutualisé, Hébèrgement, PHPBB, Erreur]
comments: true
share: true
---

Suite à une mise à jour du forum de l'un de mes clients, lié à un site et hébergé chez OVH en mutualisé, nous avons rencontré l'erreur `Trailing paths and PATH_INFO is not supported by phpBB 3.0` de PhpBB lors de l'accès aux pages ayant une url commençant par index.

## L'erreur
PhpBB3 n'autorise pas l'accès aux pages en utilisant la variable `$_SERVER['PATH_INFO']`. Le site utilise une redirection pour toutes les urls ne correspondant pas à un fichier physique, envoyant toutes les requêtes sur le fichier `index.php`.

## La correction
Il suffit en fait d'ajouter l'option `-MultiViews` dans le fichier `.htaccess` pour indiquer au [mod_negociation](http://httpd.apache.org/docs/2.2/mod/mod_negotiation.html) d'Apache, activé par défaut chez OVH, que l'on ne veut pas que le serveur cherche un fichier avec le même nom et n'importe quelle extension dans le dossier cible.
