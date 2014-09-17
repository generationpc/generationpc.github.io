---
layout: post
status: publish
published: true
title: Zend Framework chez OVH
author:
  display_name: Thomas Dutrion
  login: thomas
  email: thomas@engineor.com
  url: http://www.engineor.com
author_login: thomas
author_email: thomas@engineor.com
author_url: http://www.engineor.com
excerpt: "<a href=\"http://blog.generation-pc.net/wp-content/uploads/2011/09/OVH.jpg\"><img
  class=\"alignright  wp-image-370\" title=\"Logo OVH\" src=\"http://blog.generation-pc.net/wp-content/uploads/2011/09/OVH.jpg\"
  alt=\"Logo OVH\" width=\"143\" height=\"139\" /></a>Faire un projet Zend Framework
  c'est super, mais quand on débute et que l'on ne connait pas du tout les configurations
  des logiciels serveurs, ça peut vite devenir compliqué...\r\n\r\n"
wordpress_id: 310
wordpress_url: http://blog.generation-pc.net/?p=310
date: '2011-09-03 09:57:17 +0100'
date_gmt: '2011-09-03 07:57:17 +0100'
categories:
- Non classé
- Développement
- Web
- Zend Framework
- PHP
- Hébergement
tags:
- Zend Framework
- Développement
- Mutualisé
- OVH
- Hébegement
- production
comments:
- id: 83
  author: Dépôt nom domaine
  author_email: aeplink@gmail.com
  author_url: http://www.haisoft.fr/
  date: '2012-09-27 15:13:41 +0100'
  date_gmt: '2012-09-27 13:13:41 +0100'
  content: Merci pour tes conseils et le tuto qui se sont révélés bien utiles.
- id: 125
  author: nikoquattro
  author_email: nikoquattro@gmail.com
  author_url: ''
  date: '2013-05-22 19:15:00 +0100'
  date_gmt: '2013-05-22 17:15:00 +0100'
  content: |-
    Excellent tuto.
    Merci bien pour tes conseils.
    Petite requete toute fois, pourrais tu -à la fin- faire un recap' de l'architecture "sommaire" de ton espace FTP sur ton compte OVH ? Histoire de voir si nous n'avons rien oublié ^^Thx
---
<p><a href="http://blog.generation-pc.net/wp-content/uploads/2011/09/OVH.jpg"><img class="alignright  wp-image-370" title="Logo OVH" src="http://blog.generation-pc.net/wp-content/uploads/2011/09/OVH.jpg" alt="Logo OVH" width="143" height="139" /></a>Faire un projet Zend Framework c'est super, mais quand on débute et que l'on ne connait pas du tout les configurations des logiciels serveurs, ça peut vite devenir compliqué...</p>
<p><a id="more"></a><a id="more-310"></a></p>
<p>Ma proposition : prendre un compte pro chez OVH qui servira :</p>
<ol>
<li>à héberger le projet en développement</li>
<li>à héberger le serveur svn</li>
<li>à héberger le projet en production</li>
</ol>
<p>Notez que d'autres hébergeurs qu'OVH proposent probablement des interfaces similaires, mais pour ma part, je n'ai jamais été déçu par leurs prestations. On peut toute fois noter que l'hébergement mutualisé pro chez OVH vous permet de disposer d'un accès SSH, et du logiciel serveur subversion.</p>
<p>L'hébergement pro d'OVH vous coutera 71,64€ TTC par an, ce qui le place à un niveau très correct parmi les offres de leurs concurrents.</p>
<p><a href="http://blog.generation-pc.net/wp-content/uploads/2011/09/01.png"><img class="aligncenter size-large wp-image-311" title="Hébergement mutualisé pro OVH" src="http://blog.generation-pc.net/wp-content/uploads/2011/09/01-1024x534.png" alt="Hébergement mutualisé pro OVH" width="560" height="292" /></a>Je vous laisse le lien vers la page de l'offre : <a href="http://www.ovh.com/fr/hebergement_mutualise/hebergement_web_mutualise_pro_100go_trafic_illimite.xml">Hébergement mutualisé pro chez OVH</a>.</p>
<p>&nbsp;</p>
<p>Une fois le processus de commande finalisé et le pack livré par OVH, vous aurez accès à votre <a href="https://www.ovh.com/managerv3/">interface de gestion OVH</a>. Là, vous trouverez la liste de tous vos noms de domaines et hébergements, ainsi que vos éventuels autres services.</p>
<p><a href="http://blog.generation-pc.net/wp-content/uploads/2011/09/02.png"><img class="aligncenter size-full wp-image-312" title="OVH - Accueil du manager" src="http://blog.generation-pc.net/wp-content/uploads/2011/09/02.png" alt="OVH - Accueil du manager" width="774" height="778" /></a>En haut de la page, on trouve une liste déroulante dans laquelle il est possible de choisir l'un de nos noms de domaines, ce qui nous amène sur la page de gestion du domaine et des services associés.</p>
<p>Une interface similaire se trouve sur la gauche de la page, sous forme de liste plus classique.</p>
<p>Choisissons le domaine qui nous intéresse (celui qui est associé à l'hébergement pro).</p>
<p><a href="http://blog.generation-pc.net/wp-content/uploads/2011/09/03.png"><img class="aligncenter size-full wp-image-313" title="OVH - Manager : gestion d'un hébergement pro" src="http://blog.generation-pc.net/wp-content/uploads/2011/09/03.png" alt="OVH - Manager : gestion d'un hébergement pro" width="778" height="881" /></a>On retrouve toujours notre liste de produits dans le header de la page. Sur la gauche, cliquez sur hébergement.</p>
<p>Cliquez sur l’icône "sous domaine", car nous allons commencer par ajouter le sous domaine dev.votrenom.com pour la plateforme de développement.</p>
<p style="text-align: center;"><a href="http://blog.generation-pc.net/wp-content/uploads/2011/09/04.png"><img class="size-full wp-image-315 aligncenter" title="OVH - Gestion des sous domaines sur mutualisé pro" src="http://blog.generation-pc.net/wp-content/uploads/2011/09/04.png" alt="OVH - Gestion des sous domaines sur mutualisé pro" width="333" height="186" /></a></p>
<p> Après avoir cliqué sur "Création", il vous faudra remplir un formulaire dont les champs correspondent aux informations minimales requises dans les virtualhosts Apache.</p>
<p><a href="http://blog.generation-pc.net/wp-content/uploads/2011/09/051.png"><img class="alignnone size-full wp-image-329" title="OVH - Ajout de sous domaine - Mutualisé pro" src="http://blog.generation-pc.net/wp-content/uploads/2011/09/051.png" alt="OVH - Ajout de sous domaine - Mutualisé pro" width="562" height="414" /></a></p>
<p>Il faut bien entendu remplir les différents champs avec les valeurs adéquates. Pour l'environnement de développement, nous allons donc mettre comme sous domaine le nom dev, qui pointeras sur /htdocs/dev/public/, et qui gère l'ipv6.</p>
<p>Les fichiers du projet se trouveront donc dans le dossier /htdocs/dev/. Une fois validé, il vous faudra attendre 24h pour que tout soit fonctionnel.</p>
<p>Passons ensuite à l'environnement de production. OVH, propose un hébergement de base qui pointe sur /www, hors nous avons un site pour lequel le virtualhost devrait pointer sur /public... C'est donc un premier problème. Le second problème est que notre site en dev se trouve dans /htdocs, et la logique voudrait que notre site en production de trouve donc dans /htdocs/prod/.</p>
<p>Connectez vous alors en ssh au serveur d'hébergement (sous Windows, utilisez Putty, sur les autres systèmes utilisez votre console). Connectez vous avec les adresse et mot de passe de votre compte FTP.</p>
<p><a href="http://blog.generation-pc.net/wp-content/uploads/2011/09/06.png"><img class="alignnone size-full wp-image-320" title="Putty - Connexion au compte OVH Mutualisé" src="http://blog.generation-pc.net/wp-content/uploads/2011/09/06.png" alt="Putty - Connexion au compte OVH Mutualisé" width="618" height="549" /></a></p>
<p>Lorsque l'on vous demande votre mot de passe, si vous n'êtes pas habitué à l'environnement Linux/Unix, ne vous inquiétez pas, rien ne s'affiche lorsque vous tapez le mot de passe, mais les caractères sur lesquels vous appuyez sont bien pris en compte.</p>
<p><a href="http://blog.generation-pc.net/wp-content/uploads/2011/09/07.png"><img class="alignnone size-full wp-image-321" title="OVH - SSH mutualisé - Login" src="http://blog.generation-pc.net/wp-content/uploads/2011/09/07.png" alt="OVH - SSH mutualisé - Login" width="841" height="527" /></a></p>
<p>Un message d'avertissement s'affiche ensuite, vous indiquant qu'il est possible de vous connecter à une autre adresse dédiée au SSH, plutôt que de passer par le serveur FTP.</p>
<p><a href="http://blog.generation-pc.net/wp-content/uploads/2011/09/08.png"><img class="alignnone size-full wp-image-322" title="OVH - SSH Mutualisé - Avertissement connexion sur FTP" src="http://blog.generation-pc.net/wp-content/uploads/2011/09/08.png" alt="OVH - SSH Mutualisé - Avertissement connexion sur FTP" width="802" height="83" /></a></p>
<p>Là, à l'aide de la commande ls, vous devriez avoir un fichier LISEZ-MOI, un répertoire www et un répertoire cgi-bin.</p>
<p>Commençons par ajouter l'environnement de dev, avec la commande suivante :</p>
<pre>mkdir -p htdocs/dev/public</pre>
<p>Passons ensuite à l'environnement de production, avec la commande :</p>
<pre>mkdir -p htdocs/prod/public</pre>
<p>Reste donc toujours le problème du dossier www... Sur les systèmes de type Unix, donc sur la plateforme d'hébergement mutualisé, il existe un mécanisme appelé lien symbolique, qui permet de faire qu'un fichier n'en soit pas vraiment un, mais juste un lien vers un autre dossier. C'est ce que nous allons utiliser ici.</p>
<p>Dans un premier temps, il va falloir supprimer le dossier www.</p>
<p>rm -r www</p>
<p>A ce moment là, si on essaye d'accéder au site, une erreur 404 s'affichera.</p>
<pre>Not Found</pre>
<pre>The requested URL / was not found on this server.</pre>
<p>Puis il faut mettre en place le lien symbolique en question :</p>
<pre>ln -s htdocs/prod/public/ www</pre>
<p>Ainsi, /www pointera sur /htdocs/prod/public et permettra donc d'utiliser le virtualhost par défaut du compte OVH pour la plateforme de production.</p>
<p>&nbsp;</p>
<p>Bon, on sait où vont aller les fichiers du site pour le développement, pour la production, et on a l'organisation suivante sur le serveur :</p>
<ul>
<li>/</li>
</ul>
<ul>
<li>www (pointe sur htdocs/prod/public)</li>
<li>htdocs</li>
</ul>
<ul>
<li>dev</li>
</ul>
<ul>
<li>public</li>
<li>prod</li>
</ul>
<ul>
<li>public</li>
<li>cgi-bin (facultatif)</li>
<li>LISEZ-MOI (facultatif)</li>
</ul>
<p>&nbsp;</p>
<p>Dernière étape de la mise en place de notre architecture, <a title="Mettre en place un serveur SVN sur OVH en hébergement mutualisé" href="http://guide.ovh.com/SVNMutu" target="_blank">mettre en place le serveur SVN</a>. On va donc rester sur notre console ssh, et créer un nouveau dossier, par exemple "svn", si on est pas très créatif.</p>
<pre>mkdir svn</pre>
<p>Puis entrez la commande suivante en changeant depot par le nom que vous désirez donner à votre dépôt (souvent le nom du projet).</p>
<pre>svnadmin create svn/depot</pre>
<p>Reste à mettre en place une clé SSH autorisée par ordinateur voulant se connecter au dépôt. Cette étape se fait donc sur l'ordinateur client.</p>
<p>Sous Linux ou Mac Os avec Open SSH :</p>
<pre style="padding-left: 30px;">ssh-keygen -t dsa</pre>
<p style="padding-left: 30px;">Récupérez la ligne qui se trouve par défault dans le fichier .ssh/id_dsa.pub .</p>
<p style="padding-left: 30px;">Vous trouverez la clef qui est divisée en trois chaînes de caractères : le type, la clé et un commentaire.</p>
<p>Sous Windows :</p>
<p style="padding-left: 30px;">Téléchargez et exécutez <a href="http://the.earth.li/~sgtatham/putty/latest/x86/puttygen.exe" target="_blank">Putty KeyGen</a>.</p>
<p style="padding-left: 30px;">Choisissez bien DSA en bas, puis générez les clés et sauvez les.</p>
<p style="padding-left: 30px;"><a href="http://blog.generation-pc.net/wp-content/uploads/2011/09/09.png"><img class="alignnone size-full wp-image-325" title="OVH Mutualisé - SVN - Création de clés sous Windows" src="http://blog.generation-pc.net/wp-content/uploads/2011/09/09.png" alt="OVH Mutualisé - SVN - Création de clés sous Windows" width="654" height="585" /></a></p>
<p>&nbsp;</p>
<p>Et voilà !</p>
<p>Il ne nous reste plus qu'à mettre la clé publique sur le serveur. Dans la console SSH, entrez les commandes suivantes :</p>
<pre>mkdir .ssh</pre>
<pre>vi .ssh/authorized_keys2</pre>
<p>Et mettre dans ce fichier la ligne suivante, puis la clé dsa publique.</p>
<pre>command="/usr/bin/svnserve --root=/homez.XXX/loginFTP/svn --tunnel --tunnel-user=marc",no-port-forwarding,no-agent-forwarding,no-X11-forwarding,no-pty</pre>
<p>Remplacez bien entendu /homez.XXX par la valeur rendue par la commande pwd, loginFTP par votre login FTP effectif, et l'utilisateur par la valeur de votre choix.</p>
<p>Puis</p>
<pre>chmod 700 .ssh</pre>
<p>Une fois le projet mis en ligne sur le serveur SVN, vous n'aurez plus qu'à faire un svn checkout dans htdocs/prod/ pour avoir la version courante du site, puis un svn up à chaque fois que c'est requis !</p>
