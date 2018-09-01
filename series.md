---
layout: page
title: Séries préférées
permalink: /series

list:
  - title: Rick et Morty
    image_url: http://pthumb.lisimg.com/15851577/130full.jpg

---

{% for item in page.list %}
1. ![{{ item.title }}]({{ item.image_url }})
### {{ item.title }}
    {%- if item.bluray_bought %}
    + **$ Blu-ray $**
    {%- endif -%}
{% endfor %}
