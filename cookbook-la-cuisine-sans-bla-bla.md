---
layout: page
title: La cuisine sans bla bla
permalink: /cookbook-la-cuisine-sans-bla-bla

list:
  - title: Ratatouille
    number: 152
    is_main_course: true
    total_time: 40
    image_url: https://i.imgur.com/Nr4wcKO.jpg?1

  - title: Sauté de porc au gingembre
    number: 44
    is_main_course: true
    total_time: 30
    image_url: https://i.imgur.com/y2Hk5Eo.jpg

  - title: Cocotte de canard à l'orange et au miel
    number: 66
    is_main_course: true
    total_time: 55
    image_url: https://i.imgur.com/947k1Op.jpg

  - title: Spaghetti bolognaise
    number: 28
    is_main_course: true
    total_time: 30
    image_url: https://i.imgur.com/Fc1HAYG.jpg

  - title: Boeuf à la coriandre et à la citronelle
    number: 24
    is_main_course: true
    total_time: 200
    image_url: https://i.imgur.com/X1WO7xr.jpg

  - title: Bo bun
    number: 97
    is_main_course: true
    total_time: 20
    image_url: https://i.imgur.com/Kps1wKg.jpg

  - title: Marbré
    number: 165
    is_dessert: true
    total_time: 55
    image_url: https://i.imgur.com/5d3ATgh.jpg

  - title: Tian de légumes au thym
    number: 153
    is_main_course: true
    total_time: 65
    image_url: https://i.imgur.com/qbXkGSc.jpg

  - title: Wok de boeuf aux vermicelles et brocoli
    number: 22
    is_main_course: true
    total_time: 35
    image_url: https://i.imgur.com/lk5Oa73.jpg

  - title: Tarte soleil pesto, mozzarella et courgette
    number: 2
    is_starter: true
    total_time: 45
    image_url: https://i.imgur.com/wHWmeVH.jpg

  - title: Mignonnettes de porc et poires (sauce au bleu)
    number: 42
    is_main_course: true
    total_time: 40
    image_url: https://i.imgur.com/05pk3Nvl.jpg

  - title: Curry de légumes à l'indienne
    number: 142
    is_main_course: true
    total_time: 50
    image_url: https://i.imgur.com/3oxhKn3.jpg

  - title: Fritata champignons épinards
    number: 157
    is_main_course: true
    total_time: 45
    image_url: https://i.imgur.com/SGIn2JT.jpg

  - title: Saltimbocca de veau, mozzarella fumée et romarin
    number: 34
    is_main_course: true
    total_time: 30
    image_url: https://i.imgur.com/b6BfKsG.jpg

  - title: Brownie aux noix de pécan
    number: 163
    is_dessert: true
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

    {%- if item.total_time %}
    + en {{ item.total_time }} minutes
    {%- endif -%}
{% endfor %}
