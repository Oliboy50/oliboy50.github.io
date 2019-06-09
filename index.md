---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home

list:
    - title: Recettes préférées
      list:
        - title: La cuisine sans bla bla
          link: /cuisine-sans-blabla

---

{% for item in page.list %}
### {{ item.title }}
    {%- for subitem in item.list %}
#### [{{ subitem.title }}]({{ subitem.link }})
    {%- endfor -%}
{% endfor %}
