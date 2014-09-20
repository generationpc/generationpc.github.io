---
layout: post
title: Linux - Simplifiez vous l'extraction en console !
date: '2011-06-11 22:09:15 +0100'
date_gmt: '2011-06-11 20:09:15 +0100'
categories: astuces
tags: [Configuration, Console, Terminal, Extraction, Archive, Compression, tar, tar.gz, zip, rar, Linux]
comments: true
share: true
redirect_from: "/2011/06/linux-simplifiez-vous-lextraction-en-console/"
---
Ce soir, je télécharge la dernière version de Zend Framework pour un projet que je dois mettre à jour. Sur le site de Zend, le fichier est proposé en tar.gz, fichier que je télécharge.

Comme à chaque fois que je télécharge un fichier tar.gz, je me pose la question qui tue : **C'est quoi déjà la commande pour dés-archiver un fichier tar.gz ?**

> Mais c'est pourtant simple ! "tar xvzf" suivi du nom de ton fichier...

Ah oui, c'est vrai ! Mais coup de chance, ce soir je suis tombé sur une réponse plus intéressante qu'à l'habitude, ou tout au moins si elle n'est pas forcément plus intéressante, elle va me simplifier la vie à l'avenir.

Ouvrez votre fichier `.bashrc`.

`vim ~/.bashrc`

Ajoutez le code suivant à la fin du fichier. Il s'agit d'une fonction bash qui va déterminer le type de fichier à extraire et lancer la commande associée, ou alors renvoyer un message d'erreur.

{% highlight bash %}
extract () {
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
}
{% endhighlight %}

Vous avez ensuite deux possibilités. Soit vous redémarrez votre console, et vous pourrez alors utiliser la commande extract suivi du nom de votre fichier à dés-archiver, soit vous ne voulez pas redémarrer et il vous suffit alors d'entrer la commande `source ~/.bashrc` et vous pourrez utiliser immédiatement extract.

Astuce trouvée sur CrunchBangLinux : [HOWTO: Extract compressed files in terminals or consoles](http://crunchbanglinux.org/forums/topic/586/howto-extract-compressed-files-in-terminals-or-console).
