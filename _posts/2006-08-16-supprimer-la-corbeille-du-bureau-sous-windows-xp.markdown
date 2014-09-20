---
layout: post
title: Supprimer la corbeille du bureau sous Windows XP
date: '2006-08-16 17:02:57 +0100'
date_gmt: '2006-08-16 15:02:57 +0100'
categories: astuces
tags: [Systèmes d'exploitation, Microsoft, Windows XP, Paramètres, Corbeille]
comments: true
share: true
---
La corbeille de windows n'est pas un élément comme un autre, elle permet de récuperer des éléments effacés par erreur, elle ne peut donc pas etre renommée ou supprimée d'un simple clic.

Une astuce permet toutefois d'agir sur celle-ci en effectuant quelques modifications de la base de registre.

Modifier la base de registre pouvant facilement "planter" votre système windows en cas de mauvaise manipulation, faites au préalable une sauvegarde de la base de registre pour travailler en toute sécurité.

## Dans Windows XP pro ##
`Démarrer` / `Exécuter` / taper `gpedit.msc` / `Configuration utilisateur` / `Modeles d'administration` / `Bureau` / clic droit - propriétés sur: `Supprimer l'icône de la corbeille du Bureau` / `activer` / `OK`

### Remarques ###

 * ce paramètre supprime toutes les occurrences de l'icône de la corbeille
 * ce paramètre supprime l'icône de la corbeille du Bureau, de l'explorateur Windows, des programmes qui utilisent les fenêtres de l'explorateur Windows, et de la boîte de dialogue `Ouvrir` standard
 * ce paramètre n'empêche pas l'utilisateur d'utiliser d'autres méthodes pour accéder au contenu du dossier de la corbeille
 * pour que les modifications apportées à ce paramètre prennent effet, vous devez fermer puis rouvrir une session.

## Par la base de registre ##
Ouvrir la base de registre: `Démarrer` / `Exécuter` / taper `regedit` / `OK` / `HKLM` / `SOFTWARE` / `Microsoft` / `Windows` / `CurrentVersion` / `Explorer` / `DesktopNameSpace` / `{645FF040-5081-101B-9F08-00AA002F954E}`

Renommer cette clé en `XXX{645FF040-5081-101B-9F08-00AA002F954E}` (pour pouvoir la rétablir facilement en cas de besoin), puis redémarrer le système.