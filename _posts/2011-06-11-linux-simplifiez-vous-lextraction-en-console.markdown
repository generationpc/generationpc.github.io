---
layout: post
status: publish
published: true
title: Linux - Simplifiez vous l'extraction en console !
author:
  display_name: Thomas Dutrion
  login: thomas
  email: thomas@engineor.com
  url: http://www.engineor.com
author_login: thomas
author_email: thomas@engineor.com
author_url: http://www.engineor.com
wordpress_id: 195
wordpress_url: http://blog.generation-pc.net/?p=195
date: '2011-06-11 22:09:15 +0100'
date_gmt: '2011-06-11 20:09:15 +0100'
categories:
- Systèmes d'exploitation
- Linux
tags:
- configuration
- console
- terminal
- extraction
- archive
- compression
- tar
- tar.gz
- zip
- rar
- Linux
- extraire
comments: []
---
<p style="text-align: justify;">Ce soir, je télécharge la dernière version de Zend Framework pour un projet que je dois mettre à jour. Sur le site de Zend, le fichier est proposé en tar.gz, fichier que je télécharge.</p>
<p style="text-align: justify;">Comme à chaque fois que je télécharge un fichier tar.gz, je me pose la question qui tue : "<strong>C'est quoi déjà la commande pour dés-archiver un fichier tar.gz ?</strong>"</p>
<p style="text-align: justify;"><cite lang="fr">Mais c'est pourtant simple ! "tar xvzf" suivi du nom de ton fichier...</cite></p>
<p style="text-align: justify;">Ah oui, c'est vrai ! Mais coup de chance, ce soir je suis tombé sur une réponse plus intéressante qu'à l'habitude, ou tout au moins si elle n'est pas forcément plus intéressante, elle va me simplifier la vie à l'avenir.</p>
<p style="text-align: justify;">Ouvrez votre fichier .bashrc.</p>
<p style="text-align: justify;">vim ~/.bashrc</p>
<p style="text-align: justify;">Ajoutez le code suivant à la fin du fichier. Il s'agit d'une fonction bash qui va déterminer le type de fichier à extraire et lancer la commande associée, ou alors renvoyer un message d'erreur.</p>
<pre><code>extract () {
  if [ -f $1 ] ; then
      case $1 in
          *.tar.bz2)   tar xvjf $1    ;;
          *.tar.gz)    tar xvzf $1    ;;
          *.bz2)       bunzip2 $1     ;;
          *.rar)       rar x $1       ;;
          *.gz)        gunzip $1      ;;
          *.tar)       tar xvf $1     ;;
          *.tbz2)      tar xvjf $1    ;;
          *.tgz)       tar xvzf $1    ;;
          *.zip)       unzip $1       ;;
          *.Z)         uncompress $1  ;;
          *.7z)        7z x $1        ;;
          *)           echo "don't know how to extract '$1'..." ;;
      esac
  else
      echo "'$1' is not a valid file!"
  fi
}</code></pre>
<p style="text-align: justify;">Vous avez ensuite deux possibilités. Soit vous redémarrez votre console, et vous pourrez alors utiliser la commande extract suivi du nom de votre fichier à dés-archiver, soit vous ne voulez pas redémarrer et il vous suffit alors d'entrer la commande "source ~/.bashrc" et vous pourrez utiliser immédiatement extract.</p>
<p style="text-align: justify;">&nbsp;</p>
<p style="text-align: justify;">Astuce trouvée sur CrunchBangLinux : HOWTO: <a href="http://crunchbanglinux.org/forums/topic/586/howto-extract-compressed-files-in-terminals-or-console/">Extract compressed files in terminals or consoles</a>.</p>
