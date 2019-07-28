---
layout: page
title: La cuisine sans bla bla
permalink: /cookbook-la-cuisine-sans-bla-bla

list:
  - title: Sauté de porc au gingembre
    number: 44
    is_main_course: true
    persons: 4
    total_time: 30
    image_url: https://i.imgur.com/y2Hk5Eo.jpg

  - title: Mignonnettes de porc et poires (sauce au bleu)
    number: 42
    is_main_course: true
    persons: 4
    total_time: 40
    image_url: https://i.imgur.com/05pk3Nvl.jpg

  - title: Saltimbocca de veau, mozzarella fumée et romarin
    number: 34
    is_main_course: true
    persons: 8
    total_time: 30
    image_url: https://i.imgur.com/b6BfKsG.jpg

  - title: Brownie aux noix de pécan
    number: 163
    is_dessert: true
    persons: 8
    total_time: 31
    image_url: https://i.imgur.com/tydSJ93.jpg

---

{% for item in page.list %}
1. ![{{ item.title }}]({{ item.image_url }})
### {{ item.title }}
    {%- if item.number %}
    + Recette n°{{ item.number }}
    {%- endif -%}

    {%- if item.is_starter %}
    + Entrée
    {%- endif -%}

    {%- if item.is_main_course %}
    + Plat principal
    {%- endif -%}

    {%- if item.is_dessert %}
    + Dessert
    {%- endif -%}

    {%- if item.persons %}
    + pour {{ item.persons }} personnes
    {%- endif -%}

    {%- if item.total_time %}
    + en {{ item.total_time }} minutes
    {%- endif -%}
{% endfor %}
