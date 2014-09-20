---
layout: post
title: Zend Framework chez OVH
date: '2011-09-03 09:57:17 +0100'
date_gmt: '2011-09-03 07:57:17 +0100'
categories: tutoriels
tags: [Développement, Web, Zend Framework, PHP, Hébergement, Mutualisé, OVH, production]
comments: true
share: true
disqus_url: http://www.generation-pc.net/2011/09/zend-framework-chez-ovh/
disqus_identifier: http://www.generation-pc.net/2011/09/zend-framework-chez-ovh/
redirect_from: "/2011/09/zend-framework-chez-ovh/"
---
[![Logo OVH](/images/posts/2011-09-03-zend-framework-chez-ovh/01.jpg)](/images/posts/2011-09-03-zend-framework-chez-ovh/01.jpg)

Faire un projet Zend Framework c'est super, mais quand on débute et que l'on ne connait pas du tout les configurations des logiciels serveurs, ça peut vite devenir compliqué...

Ma proposition : prendre un compte pro chez OVH qui servira :

1. à héberger le projet en développement
2. à héberger le serveur svn
3. à héberger le projet en production

Notez que d'autres hébergeurs qu'OVH proposent probablement des interfaces similaires, mais pour ma part, je n'ai jamais été déçu par leurs prestations. On peut toute fois noter que l'hébergement mutualisé pro chez OVH vous permet de disposer d'un accès SSH, et du logiciel serveur subversion.

L'hébergement pro d'OVH vous coutera 71,64€ TTC par an, ce qui le place à un niveau très correct parmi les offres de leurs concurrents.

[![Hébergement mutualisé pro OVH](/images/posts/2011-09-03-zend-framework-chez-ovh/02.png)](/images/posts/2011-09-03-zend-framework-chez-ovh/02.png)

Je vous laisse le lien vers la page de l'offre : [Hébergement mutualisé pro chez OVH](http://www.ovh.com/fr/hebergement_mutualise/hebergement_web_mutualise_pro_100go_trafic_illimite.xml).

Une fois le processus de commande finalisé et le pack livré par OVH, vous aurez accès à votre [interface de gestion OVH](https://www.ovh.com/managerv3/). Là, vous trouverez la liste de tous vos noms de domaines et hébergements, ainsi que vos éventuels autres services.

[![OVH - Accueil du manager](/images/posts/2011-09-03-zend-framework-chez-ovh/03.png)](/images/posts/2011-09-03-zend-framework-chez-ovh/03.png)

En haut de la page, on trouve une liste déroulante dans laquelle il est possible de choisir l'un de nos noms de domaines, ce qui nous amène sur la page de gestion du domaine et des services associés.

Une interface similaire se trouve sur la gauche de la page, sous forme de liste plus classique.

Choisissons le domaine qui nous intéresse (celui qui est associé à l'hébergement pro).

[![OVH - Manager : gestion d'un hébergement pro](/images/posts/2011-09-03-zend-framework-chez-ovh/04.png)](/images/posts/2011-09-03-zend-framework-chez-ovh/04.png)

On retrouve toujours notre liste de produits dans le header de la page. Sur la gauche, cliquez sur hébergement.


Cliquez sur l’icône "sous domaine", car nous allons commencer par ajouter le sous domaine `dev.votrenom.com` pour la plateforme de développement.

[![OVH - Gestion des sous domaines sur mutualisé pro](/images/posts/2011-09-03-zend-framework-chez-ovh/05.png)](/images/posts/2011-09-03-zend-framework-chez-ovh/05.png)

Après avoir cliqué sur "Création", il vous faudra remplir un formulaire dont les champs correspondent aux informations minimales requises dans les virtualhosts Apache.

[![OVH - Ajout de sous domaine - Mutualisé pro](/images/posts/2011-09-03-zend-framework-chez-ovh/06.png)](/images/posts/2011-09-03-zend-framework-chez-ovh/06.png)

Il faut bien entendu remplir les différents champs avec les valeurs adéquates. Pour l'environnement de développement, nous allons donc mettre comme sous domaine le nom dev, qui pointeras sur `/htdocs/dev/public/`, et qui gère l'ipv6.

Les fichiers du projet se trouveront donc dans le dossier `/htdocs/dev/`. Une fois validé, il vous faudra attendre 24h pour que tout soit fonctionnel.

Passons ensuite à l'environnement de production. OVH, propose un hébergement de base qui pointe sur /www, hors nous avons un site pour lequel le virtualhost devrait pointer sur `/public`... C'est donc un premier problème. Le second problème est que notre site en dev se trouve dans `/htdocs`, et la logique voudrait que notre site en production de trouve donc dans `/htdocs/prod/`.

Connectez vous alors en ssh au serveur d'hébergement (sous Windows, utilisez Putty, sur les autres systèmes utilisez votre console). Connectez vous avec les adresse et mot de passe de votre compte FTP.

[![Putty - Connexion au compte OVH Mutualisé](/images/posts/2011-09-03-zend-framework-chez-ovh/07.png)](/images/posts/2011-09-03-zend-framework-chez-ovh/07.png)

Lorsque l'on vous demande votre mot de passe, si vous n'êtes pas habitué à l'environnement Linux/Unix, ne vous inquiétez pas, rien ne s'affiche lorsque vous tapez le mot de passe, mais les caractères sur lesquels vous appuyez sont bien pris en compte.

[![OVH - SSH mutualisé - Login](/images/posts/2011-09-03-zend-framework-chez-ovh/08.png)](/images/posts/2011-09-03-zend-framework-chez-ovh/08.png)

Un message d'avertissement s'affiche ensuite, vous indiquant qu'il est possible de vous connecter à une autre adresse dédiée au SSH, plutôt que de passer par le serveur FTP.


[![OVH - SSH Mutualisé - Avertissement connexion sur FTP](/images/posts/2011-09-03-zend-framework-chez-ovh/09.png)](/images/posts/2011-09-03-zend-framework-chez-ovh/09.png)

Là, à l'aide de la commande ls, vous devriez avoir un fichier `LISEZ-MOI`, un répertoire `www` et un répertoire `cgi-bin`.

Commençons par ajouter l'environnement de dev, avec la commande suivante : `mkdir -p htdocs/dev/public`

Passons ensuite à l'environnement de production, avec la commande : `mkdir -p htdocs/prod/public`

Reste donc toujours le problème du dossier www... Sur les systèmes de type Unix, donc sur la plateforme d'hébergement mutualisé, il existe un mécanisme appelé lien symbolique, qui permet de faire qu'un fichier n'en soit pas vraiment un, mais juste un lien vers un autre dossier. C'est ce que nous allons utiliser ici.

Dans un premier temps, il va falloir supprimer le dossier `www` : `rm -r www`.

A ce moment là, si on essaye d'accéder au site, une erreur 404 s'affichera.

> Not Found
> 
> The requested URL / was not found on this server.

Puis il faut mettre en place le lien symbolique en question : `ln -s htdocs/prod/public/ www`.

Ainsi, `/www` pointera sur `/htdocs/prod/public` et permettra donc d'utiliser le virtualhost par défaut du compte OVH pour la plateforme de production.

Bon, on sait où vont aller les fichiers du site pour le développement, pour la production, et on a l'organisation suivante sur le serveur :

 * /
     * www (pointe sur htdocs/prod/public)
         * htdocs
     * dev
         * public
     * prod
         * public
     * cgi-bin (facultatif)
     * LISEZ-MOI (facultatif)

Dernière étape de la mise en place de notre architecture, [mettre en place le serveur SVN](http://guide.ovh.com/SVNMutu). On va donc rester sur notre console ssh, et créer un nouveau dossier, par exemple "svn", si on est pas très créatif : `mkdir svn`.

Puis entrez la commande suivante en changeant depot par le nom que vous désirez donner à votre dépôt (souvent le nom du projet) : `svnadmin create svn/depot`.

Reste à mettre en place une clé SSH autorisée par ordinateur voulant se connecter au dépôt. Cette étape se fait donc sur l'ordinateur client.

Sous Linux ou Mac Os avec Open SSH : `ssh-keygen -t dsa`.

Récupérez la ligne qui se trouve par défault dans le fichier `.ssh/id_dsa.pub`.

Vous trouverez la clef qui est divisée en trois chaînes de caractères : le type, la clé et un commentaire.

Sous Windows :

Téléchargez et exécutez [Putty KeyGen](http://the.earth.li/~sgtatham/putty/latest/x86/puttygen.exe).

Choisissez bien DSA en bas, puis générez les clés et sauvez les.

[![OVH Mutualisé - SVN - Création de clés sous Windows](/images/posts/2011-09-03-zend-framework-chez-ovh/10.png)](/images/posts/2011-09-03-zend-framework-chez-ovh/10.png)

Et voilà !

Il ne nous reste plus qu'à mettre la clé publique sur le serveur. Dans la console SSH, entrez les commandes suivantes :

`mkdir .ssh`

`vi .ssh/authorized_keys2`

Et mettre dans ce fichier la ligne suivante, puis la clé dsa publique.

`command="/usr/bin/svnserve --root=/homez.XXX/loginFTP/svn --tunnel --tunnel-user=marc",no-port-forwarding,no-agent-forwarding,no-X11-forwarding,no-pty`

Remplacez bien entendu `/homez.XXX` par la valeur rendue par la commande `pwd`, loginFTP par votre login FTP effectif, et l'utilisateur par la valeur de votre choix.

Puis `chmod 700 .ssh`.

Une fois le projet mis en ligne sur le serveur SVN, vous n'aurez plus qu'à faire un svn checkout dans `htdocs/prod/` pour avoir la version courante du site, puis un svn up à chaque fois que c'est requis !