---
layout: post
status: publish
published: true
title: Supprimer la corbeille du bureau sous Windows XP
author:
  display_name: Thomas Dutrion
  login: thomas
  email: thomas@engineor.com
  url: http://www.engineor.com
author_login: thomas
author_email: thomas@engineor.com
author_url: http://www.engineor.com
wordpress_id: 55
wordpress_url: http://dev.generation-pc.net/?p=55
date: '2006-08-16 17:02:57 +0100'
date_gmt: '2006-08-16 15:02:57 +0100'
categories:
- Systèmes d'exploitation
- Microsoft
- Windows XP
tags:
- Système
- Microsoft
- Windows
- XP
- paramètres
- Corbeille
comments: []
---
<p>La corbeille de windows n'est pas un élément comme un autre, elle permet de récuperer des éléments effacés par erreur, elle ne peut donc pas etre renommée ou supprimée d'un simple clic.</p>
<p>Une astuce permet toutefois d'agir sur celle-ci en effectuant quelques modifications de la base de registre.</p>
<p>Modifier la base de registre pouvant facilement "planter" votre système windows en cas de mauvaise manipulation, faites au préalable une sauvegarde de la base de registre pour travailler en toute sécurité.</p>
<p>&nbsp;</p>
<h3>Dans Windows XP pro :</h3>
<p>Démarrer / Exécuter / taper gpedit.msc / Configuration utilisateur / Modeles d'administration / Bureau / clic droit - propriétés sur: Supprimer l'icône de la corbeille du Bureau / activer / OK</p>
<h4>Remarques:</h4>
<ul style="list-style-type: square;">
<li>Ce paramètre supprime toutes les occurrences de l'icône de la Corbeille.</li>
<li>Ce paramètre supprime l'icône de la Corbeille du Bureau, de l'Explorateur Windows, des programmes qui utilisent les fenêtres de l'Explorateur Windows, et de la boîte de dialogue Ouvrir standard.</li>
<li>Ce paramètre n'empêche pas l'utilisateur d'utiliser d'autres méthodes pour accéder au contenu du dossier de la Corbeille.</li>
<li>Pour que les modifications apportées à ce paramètre prennent effet, vous devez fermer puis rouvrir une session.</li>
</ul>
<p>&nbsp;</p>
<h3>Par la base de registre :</h3>
<p>Ouvrir la base de registre: Démarrer / Exécuter / taper regedit / OK / HKLM / SOFTWARE / Microsoft / Windows / CurrentVersion / Explorer / DesktopNameSpace / {645FF040-5081-101B-9F08-00AA002F954E}</p>
<p>Renommer cette clé en XXX{645FF040-5081-101B-9F08-00AA002F954E} (pour rétablir celle-ci facilement), redémarrer le système.</p>
<p>&nbsp;</p>
