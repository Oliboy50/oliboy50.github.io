---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home

list:
    - title: Animes préférés
      permalink: /animes

    - title: Films d'anime préférés
      permalink: /anime-movies

    - title: Séries préférées
      permalink: /series

    - title: Recettes préférées
      list:
        - title: La cuisine sans bla bla
          permalink: /cookbook-la-cuisine-sans-bla-bla

---

{% for item in page.list %}
    {%- if item.list %}
### {{ item.title }}
        {%- for subitem in item.list %}
  + [{{ subitem.title }}]({{ subitem.permalink }})
        {%- endfor -%}
    {%- else %}
### [{{ item.title }}]({{ item.permalink }})
    {%- endif -%}
{% endfor %}
