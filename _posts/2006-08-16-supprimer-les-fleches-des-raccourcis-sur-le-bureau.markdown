---
layout: post
status: publish
published: true
title: Supprimer les flèches des raccourcis sur le bureau.
author:
  display_name: Thomas Dutrion
  login: thomas
  email: thomas@engineor.com
  url: http://www.engineor.com
author_login: thomas
author_email: thomas@engineor.com
author_url: http://www.engineor.com
wordpress_id: 76
wordpress_url: http://dev.generation-pc.net/?p=76
date: '2006-08-16 20:59:58 +0100'
date_gmt: '2006-08-16 18:59:58 +0100'
categories:
- Systèmes d'exploitation
- Microsoft
- Windows XP
tags:
- Système
- Microsoft
- Windows
- XP
- Style
- paramètres
- configuration
comments: []
---
<p>Quand vous ajoutez un raccourci sur votre bureau une petite flèche se place sous ce raccourci. Si vous n'aimez pas ces petites flèches qui gâchent vos icones, une petite intervention très simple dans la base de registre vous permet de les supprimer.</p>
<ul style="list-style-type: square;">
<li>Allez sur votre base des registres en cliquant sur :
<ul style="list-style-type: square;">
<li>Démarrer</li>
<li>Exécuter</li>
</ul>
</li>
<li>Tapez
<ul style="list-style-type: square;">
<li>regedit</li>
</ul>
</li>
<li>Validez en cliquant sur :
<ul style="list-style-type: square;">
<li>Ok</li>
</ul>
</li>
</ul>
<p>Vous arriverez sur la fenêtre de l'éditeur de registre.</p>
<p>Faites un double clic sur :</p>
<pre>HKEY_CLASSES_ROOT</pre>
<p>Puis dans la partie gauche de votre fenêtre cherchez :</p>
<pre>lnkfile</pre>
<p>Attention cela s'ecrit "LNKFILE" donc il faut la chercher dans la lettre " <strong>L</strong> " et non dans la lettre " <strong>i</strong> ".</p>
<p>&nbsp;</p>
<p>Une fois que vous aurez trouvé la clé lnkfile cliquez dessus et sur la droite de votre fenêtre vous supprimez (clic droit dessus et ensuite vous cliquez sur supprimer).</p>
<pre>IsShortcut</pre>
<p>Ensuite fermez votre base des registres et redémarrez votre Pc pour que les modifications prennent effet.</p>
