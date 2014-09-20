---
layout: post
title: Héberger un site gratuitement (ou presque)
description: "Comment héberger un site web gratuitement lorsque l'on démarre."
modified: 2013-05-31
category: tutoriels
tags: [Développement, Internet, Mutualisé, Hébèrgement gratuit, Site web, CDN]
comments: true
share: true
---

> Thomas, saurais-tu comment héberger gratuitement mon portfolio ?

Une question qui revient très régulièrement... Normal, me direz-vous, quand on commence, après les études notamment, on n'a pas forcement d'argent a investir dans l'hébergement d'un portfolio.

![Portfolio example](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/01.png)

Je vais commencer cet article par un avertissement pour vous aider a choisir quel investissement faire pour maximiser le rendu. Cet article va traiter de solutions avec le fournisseur de nom de domaine OVH, que j'ai testé et approuvé pour vous, mais gardez en tête que de nombreux autres proposent des services plus ou moins equivalents pour un prix relativement similaire. A vous donc de choisir. Bien entendu, utiliser un hébergeur gratuit ne vous garantie aucune qualité de service, c'est pourquoi la solution expliquée ci-dessous contient des niveaux de sécurité concernant l'accès au site, qui ici sont utilisés entre autre en secours, mais les memes techniques s'appliquent sur vos futurs sites professionnels dans un soucis de qualité de service.

## Etape 1 : le nom de domaine ##
Le nom de domaine représente une étape importante de votre personal marketing. C'est le point d'entré de votre site, il doit être a la fois court et plein de sens, pour un portfolio probablement votre nom, ou votre pseudo en ligne. Le problème des noms de domaines, c'est que ce n'est pas gratuit, mais ce n'est pas non plus excessivement cher.

Vous pouvez cependant prendre un nom de domaine gratuit, soit en passant par un fournisseur comme [Dot TK](http://www.dot.tk/fr/index.html), ce que je vous déconseille car si les recruteurs que vous croisez sont un minimum branché web, ils vont trouver ca pas terrible, ou encore prendre un sous domaine court, et pratiquement impossible a retenir pour les personnes a qui vous parlez du site, du style .fr.nf chez [Azote.org](http://www.azote.org/) (qui reste un très bon service pour des sites personnels ou des plateformes de dev).

Mon conseil personnel, vous l'aurez compris, est de payer le nom de domaine chez un vrai fournisseur, comme OVH ou Godaddy (au pire).

Quel que soit votre fournisseur, il vous donnera accès a une interface de gestion sur laquelle vous pourrez retrouver les memes concepts que ceux que j'explique pour OVH dans le reste du document.

## Etape 2 : l'hébergement ##
Malheureusement pour vous, j'ai en partie failli a mon objectif dans le premier point, vous demandant de payer (d'ou le presque gratuit dans le titre). Le domaine étant acheté, le reste sera réellement totalement gratuit.

L'hébergement, pour les vraiment novices, c'est la ou vous aller déposer les fichiers de votre site web. Il contient généralement un accès FTP/SFTP pour déposer les fichiers, une base Mysql pour les données dynamiques, et il sera accessible en utilisant votre nom de domaine a condition que vous fassiez pointer votre domaine sur son adresse IP.

OVH, ainsi que de nombreux autres fournisseurs, vous proposent des packs comprenant l'hébergement et le nom de domaine, préconfigurés, ce qui vous permet de ne pas vous soucier de la configuration. Cependant, ces packs sont plus cher que d'acheter un domaine et prendre un hébergement gratuit, simplement parce qu'ils incluent une qualité de service, avec pourcentage garantie de disponibilité en ligne notamment, ce que ne font pas les gratuits. Opter pour la solution gratuite vous permettra aussi de comprendre les rouages qui se passent de manière transparente pour vous lorsque vous achetez un pack hébergement, et meme un peu plus, ce qui fera de vous un meilleur professionnel du web !

Je vais donc vous recommander un héberger gratuit, proposant a l'heure ou j'écris ces lignes 500mo d'espace disque, une base mysql et l'utilisation d'un domaine personnalise, c'est a dire tout ce dont vous avez besoin. Cet hébergeur est un hébergeur associatif français, [Olympe.in](https://www.olympe.in/?lang=FR), n'hésitez pas a leur faire des dons des que vous en aurez l'opportunité.

[![Logo Olympe Hosting](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/02.png)](https://www.olympe.in/?lang=FR)

Je me permets de me dispenser des étapes d'inscription et de connection au panel de gestion, demandez en commentaire si vous désirez que je les ajoutes.

Je nous considère donc connecté au panel de gestion d'Olympe.in. Pour des raisons de disponibilité des domaines que je possèdes deja, la demo sera faite a l'aide du domaine theocrite.eu.

La capture ci-dessous va nous permettre d'avoir une vue d'ensemble de l'interface de gestion d'Olympe.in, puis de créer l'espace d'hébergement de fichier pour le site. On voit sur le point 1 le menu, plus précisément l'onglet courant ("Sites" pour les actions que nous désirons effectuer). Le point 2 nous prouve que nous sommes bien connecté, avec le bon compte.

[![Olympe panel screen capture](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/03.png)](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/03.png)

Le point 3 représente l'action que nous allons effectuer : créer un nouveau site. Celui-ci aura un sous domaine de la forme vous.olympe.in, et nous changerons ce domaine plus tard. 

L'illustration ci-dessous montre la creation du site test.olympe.in (test étant deja occupé, le nom sera theocrite dans les captures suivantes). Apres avoir renseigné le nom du site et le mot de passe que vous désirez pour la connection SFTP, cliquez sur le bouton "créer".

[![Olympe panel script capture - add a new site](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/04.png)](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/04.png)

Vous disposez dès lors d'un acces au site et a sa configuration.

[![Olympe panel screen capture website button](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/05.png)](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/05.png)

Cliquer sur le bouton vous amènera sur la page de configuration du site en question.

[![Olympe panel site management screen capture](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/06.png)](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/06.png)

Les informations importantes sont disponibles dans l'encadré rouge. En utilisant les données des points 1 et 2, ainsi que le mot de passe renseigné dans le formulaire de création du compte sur la plateforme (étape précédente), vous pouvez maintenant envoyer vos données sur l'espace disque qui vous est alloué. Je vais utiliser Filezilla dans les captures suivantes, car c'est un logiciel disponible sur tous les systèmes d'exploitation, mais sachez que vous pouvez en utiliser d'autres tel WinSCP. Notez qu'Olympe est un hébergeur un peu special, qui fournis un accès SFTP et non pas FTP, ce qui fait d'un point de vue sécurité que votre mot de passe ne transite pas en clair sur le réseau, contrairement a de nombreux autres hébergeurs.

[![Olympe.in upload using Filezilla](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/07.png)](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/07.png)

Dans Filezilla, on va rentrer les données fournies par l'hébergeur (1, 2, 3, 4). Il est important de noter que nous allons utiliser le port 22 (SFTP) (4), alors que la configuration par défaut de Filezilla aurait été d'utiliser le port 21 (FTP). L'utilisation de ce champ de formulaire pour le port est très importante, sinon vous n'arriverez pas a vous connecter. Un fois connecté (5, 6), vous pouvez envoyer vos fichiers (7), puis consulter le site en utilisant votre adresse .olympe.in.

Si vous avez besoin de bases de données, c'est le moment de la créer et de la remplir sur le panel de gestion d'Olympe, puis de changer votre configuration de connexion dans vos fichiers PHP. Je ne vais pas détailler ce processus ici, mais toute demande d'aide en commentaire sera traitée.

Votre site est maintenant fonctionnel, mais il n'est pas rattaché au nom de domaine que vous avez acheté. Si votre site ne marche pas a cette étape, allez mettre en commentaire en bas de page ! On va maintenant attacher votre domaine a votre site sur l'hébergement, ce qui signifie que le domaine ne sera pas réellement rattaché, mais si vous envoyez une requête au serveur d'hébergement avec le domaine en cible, ca marchera. Si vous désirez approfondir le problème de pointage du domaine, regardez du cote des fichiers hosts de votre système, mais ce n'est pas le sujet du jour.

Allez maintenant dans l'onglet "Domaines" du panel Olympe, puis cliquez sur "Ajouter un domaine".

[![Add a domain on Olympe.in panel](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/08.png)](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/08.png)

Il faut ensuite completer un formulaire dans lequel on va entrer les informations du domaine. Le premier champ est simplement votre nom de domaine seul. Le second champ est simplement le site a associer au domaine. Comme vous disposez d'un seul site avec le compte de base d'Olympe, vous n'aurez de toutes façons pas le choix ! Pour le troisième champ, nous allons simplement entrer www, ainsi le dossier www sera crée a la racine de votre espace web. et deviendra le DOCUMENT_ROOT de votre espace web, c'est a dire la ou votre domaine pointera. Cliquez ensuite sur le bouton "Créer".

[![Olympe - Domain configuration](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/09.png)](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/09.png)

Voila pour la configuration sur Olympe, on va maintenant copier l'adresse IP fournie par Olympe pour faire pointer le domaine dessus.

[![Olympe - Domain information](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/10.png)](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/10.png)

Copiez cette adresse, nous allons l'utiliser dans la section suivante. Je vous laisse découvrir par vous meme les autres fonctions d'Olympe, notamment si vous désirez mettre en place une base SQL ou encore vous désirez avoir une adresse email personnalisée. Vos questions sont bien entendu les bienvenues dans les commentaires.

## Modifier le pointage de votre domaine OVH ##
Nous allons maintenant modifier l'adresse sur laquelle votre domaine OVH va pointer. Je vais profiter de cette section pour vous faire un bref rappel théorique sur les DNS.

Lorsque qu'un client, vous par exemple dans votre navigateur web, entre une adresse, une requête est envoyée sur le réseau, et va "demander" a des serveurs DNS l'adresse IP associée au domaine demandé, de sorte a pouvoir ensuite se diriger. Pour se faire, chaque domaine est connecté a au moins deux serveurs DNS, qui vont faire cette association, et seront dupliqués sur d'autres serveurs DNS plus proches du client. Ces serveurs DNS contiennent des zones DNS, dans lesquels on définit des enregistrements DNS (DNS records), c'est a dire des associations nom =&gt; ip ou autres selon le type de champ. Ce mécanisme introduit un "temps de propagation", le temps que les serveurs DNS se mettent a jour.

Rendons nous maintenant sur le [manager OVH v3](https://www.ovh.com/managerv3/) pour associer theocrite.eu avec 178.32.167.243. Pour ce faire, il faut ce rendre dans l'administration de votre domaine, puis dans la gestion des DNS et de l'hébergement, puis en fin dans la zone DNS ou nous éditerons le/les enregistrements concernés.

[![OVH domain management](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/11.png)](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/11.png)

Nous allons particulièrement nous intéresser a la zone DNS, mais nous reviendrons sur les serveurs DNS plus tard, donc garder bien cette section en tete.

[![OVH hosting and dns management](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/12.png)](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/12.png)

Nous allons spécifiquement regarder les enregistrements A et CNAME pour le domaine racine et le le sous domaine www. Un enregistrement A fait le lien entre le nom de domaine et une adresse IPV4. Un enregistrement AAA devra aussi être utilisé si vous désirez rendre votre site accessible en IPV6. Un enregistrement CNAME pour sa part fait le lien entre un domaine et un autre domaine. Ici nous utilisons un A pour le domaine racine, ce qui permet de faire pointer sur l'hébergement, et un CNAME pour s'assurer que www pointera toujours sur le domaine racine.

[![OVH domain dns records](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/13.png)](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/13.png)

En éditant l'enregistrement, et en changeant l'ancienne adresse IP par celle d'Olympe, nous allons donc faire pointer a la fois theocrite.eu et www.theocrite.eu sur Olympe. 

[![OVH edit dns record](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/14.png)](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/14.png)

Rendez-vous maintenant sur votre domaine, sans les www. Vous trouverez une page Apache (c'est le nom du serveur web utilisé par Olympe) avec un dossier www a l'intérieur.

[![Apache on Olympe](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/15.png)](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/15.png)

Allez ensuite sur votre domaine avec les www, et constatez que la meme page s'affiche.

Nous allons maintenant utiliser Filezilla a nouveau, pour charger vos fichiers sur l'hébergement. Dans la section de droite (emplacement distant), entrez dans le dossier www, puis déposez vos fichiers. Votre domaine avec ou sans www va maintenant afficher votre site.

[![Filezilla - Upload on Olympe](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/16.png)](/images/posts/2014-05-10-heberger-un-site-gratuitement-ou-presque/16.png)

Si vous naviguez sur votre adresse en .olympe.in, vous verrez cependant toujours la racine, et non pas les elements contenu dans www. Nous allons donc mettre en place une redirection en utilisant un fichier .htaccess. Je vous laisse chercher sur Google comment créer le fichier sous Windows, il n'y a aucune difficulté sous Linux ou Mac OS. Notre fichier htaccess sera uploadé a la racine de l'hébergement pour fonctionner avec votre adresse .olympe.in, mais aussi dans le dossier www. Il contiendra une redirection dans le cas ou le domaine demandé est different de votre domaine avec les www inclus.

{% highlight ApacheConf %}
RewriteEngine On 

RewriteCond %{HTTP_HOST} !^www.theocrite.eu$ 
RewriteRule (.*)$ http://www.theocrite.eu/$1 [R=301,L]
{% endhighlight %}

Vous pouvez ensuite consulter votre domaine avec ou sans www, ou encore aller sur votre site en .olympe.in, vous serez systématiquement redirigé sur www.

Vous pouvez vous arrêter la si vous le désirez, votre site est hébergé !

## Amelioration : utiliser un CDN ##
Un CDN, content delivery network, est un réseau de serveurs qui va mettre en cache les fichiers statiques de votre site au plus proche de chez vos clients, déchargeant votre hébergeur (qui est gratuit et déja bien gentil), et réduisant les temps de chargements. Par ailleurs, en cas de problème avec le serveur de votre hébergeur (qui je vous rappelle n'a pas d'obligation de service), la version en cache du site sera servie.

Nous allons donc créer un compte chez CloudFlare, qui offre un CDN gratuit en souhaitant que vos projets réussissent et que vous achetiez les fonctions payantes.

Pour des raisons de temps, je finirais cette section plus tard dans la journée / le weekend, mais je vous publie deja ca pour les plus pressés :)

Désolé pour les fautes, je dois remettre les accents plus tard sur mon autre ordinateur (là je suis en qwerty), et finir la relecture !