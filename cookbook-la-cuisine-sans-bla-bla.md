---
layout: page
title: Recettes préférées du livre "La cuisine sans bla bla"
permalink: /cuisine-sans-blabla

list:
  - title:  Mignonnettes de porc et poires (sauce au bleu)
    number: 42
    persons: 4
    total_time: 40
    image_url: https://i.imgur.com/05pk3Nvl.jpg

---

{% for item in page.list %}
1. ![{{ item.title }}]({{ item.image_url }})
### {{ item.title }}
    + Recette n°{{ item.number }}
    + pour {{ item.persons }} personnes
    + en {{ item.total_time }} minutes

{% endfor %}
