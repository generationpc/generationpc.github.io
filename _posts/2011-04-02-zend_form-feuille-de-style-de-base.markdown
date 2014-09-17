---
layout: post
status: publish
published: true
title: Zend_Form - Feuille de style de base
author:
  display_name: Thomas Dutrion
  login: thomas
  email: thomas@engineor.com
  url: http://www.engineor.com
author_login: thomas
author_email: thomas@engineor.com
author_url: http://www.engineor.com
wordpress_id: 23
wordpress_url: http://dev.generation-pc.net/?p=23
date: '2011-04-02 14:06:46 +0100'
date_gmt: '2011-04-02 12:06:46 +0100'
categories:
- Développement
- Web
- Zend Framework
tags: []
comments: []
---
<p>Pourquoi vous proposer aujourd'hui une feuille de style de base pour le résultat HTML produit par le composant Zend_Form ?</p>
<p>Je suis actuellement sur deux projets de sites web utilisant Zend_Form, et j'ai donc eu besoin d'une feuille de style pour rendre mes pages un peu moins atroce... Surtout que je ne suis pas designer, donc imaginez le résultat si je m'y colle seul !</p>
<p>Voilà donc une proposition de feuille minimale :</p>
<p>[sourcecode]<br />
.zend_form {<br />
    margin:5px auto;<br />
    padding:0;<br />
    overflow:auto;<br />
}<br />
.zend_form dt {<br />
    padding:0;<br />
    clear:both;<br />
    width:30%;<br />
    float:left;<br />
    text-align:right;<br />
    margin:5px 5px 5px 0;<br />
}<br />
.zend_form dd {<br />
    padding:0;<br />
    float:left;<br />
    width:68%;<br />
    margin:5px 2px 5px 0;<br />
}<br />
.zend_form p {<br />
    padding:0;<br />
    margin:0;<br />
}<br />
.zend_form input, .zend_form textarea {<br />
    margin:0 0 2px 0;<br />
    padding:0;<br />
}<br />
.zend_form ul.errors li {<br />
    display: block;<br />
    border: 1px dashed red;<br />
    padding:3px;<br />
    margin-bottom:2px;<br />
    font-weight: bold;<br />
}<br />
.required:after {<br />
    content:' *';<br />
}<br />
label.required {<br />
    color:red;<br />
}<br />
[/sourcecode]</p>
<p>Voilà une idée du résultat obtenu :<br />
[caption id="attachment_35" align="aligncenter" width="640" caption="Résultat du style sur un formulaire basic"]<a href="http://dev.generation-pc.net/wp-content/uploads/2011/04/temp.png"><img src="http://dev.generation-pc.net/wp-content/uploads/2011/04/temp.png" alt="Résultat du style sur un formulaire basic" title="Résultat du style sur un formulaire basic" width="640" height="179" class="size-full wp-image-35" /></a>[/caption]</p>
