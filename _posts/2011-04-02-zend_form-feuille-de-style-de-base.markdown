---
layout: post
title: Zend_Form - Feuille de style de base
date: '2011-04-02 14:06:46 +0100'
date_gmt: '2011-04-02 12:06:46 +0100'
categories: articles
tags: [Développement, Web, Zend Framework]
comments: true
share: true
---
Pourquoi vous proposer aujourd'hui une feuille de style de base pour le résultat HTML produit par le composant `Zend_Form` ?

Je suis actuellement sur deux projets de sites web utilisant Zend_Form, et j'ai donc eu besoin d'une feuille de style pour rendre mes pages un peu moins atroce... Surtout que je ne suis pas designer, donc imaginez le résultat si je m'y colle seul !

Voilà donc une proposition de feuille minimale :
{% highlight css %}
.zend_form {
    margin: 5px auto;
    padding: 0;
    overflow: auto;
}
.zend_form dt {
    padding: 0;
    clear: both;
    width: 30%;
    float: left;
    text-align: right;
    margin: 5px 5px 5px 0;
}
.zend_form dd {
    padding: 0;
    float: left;
    width: 68%;
    margin: 5px 2px 5px 0;
}
.zend_form p {
    padding: 0;
    margin: 0;
}
.zend_form input, .zend_form textarea {
    margin: 0 0 2px 0;
    padding: 0;
}
.zend_form ul.errors li {
    display: block;
    border: 1px dashed red;
    padding: 3px;
    margin-bottom: 2px;
    font-weight: bold;
}
.required:after {
    content:' *';
}
label.required {
    color: red;
}
{% endhighlight %}

Voilà une idée du résultat obtenu :
[Résultat du style sur un formulaire basic](/images/posts/2011-04-02-zend_form-feuille-de-style-de-base/01.png)
