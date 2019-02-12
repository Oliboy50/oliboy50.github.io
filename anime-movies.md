---
layout: page
title: Films d'anime préférés
permalink: /anime-movies

list:
  - title: Princesse Mononoke
    image_url: http://pthumb.lisimg.com/14085317/130full.jpg

  - title: Your Name
    image_url: http://pthumb.lisimg.com/11637904/130full.jpg
    bluray_bought: true

  - title: La Traversée du temps
    image_url: http://pthumb.lisimg.com/439553/130full.jpg

  - title: Le Voyage de Chihiro
    image_url: http://pthumb.lisimg.com/434341/130full.jpg

  - title: Les Enfants loups, Ame et Yuki
    image_url: http://pthumb.lisimg.com/3826597/130full.jpg

  - title: Le Royaume des chats
    image_url: http://pthumb.lisimg.com/6598577/130full.jpg

  - title: Souvenirs de Marnie
    image_url: http://pthumb.lisimg.com/8758968/130full.jpg
    bluray_bought: true

  - title: Patéma et le monde inversé
    image_url: http://pthumb.lisimg.com/13520597/130full.jpg

  - title: Summer Wars
    image_url: http://pthumb.lisimg.com/11154979/130full.jpg

  - title: Arrietty, le petit monde des chapardeurs
    image_url: http://pthumb.lisimg.com/1678100/130full.jpg
    bluray_bought: true

  - title: Ghost in the Shell
    image_url: http://pthumb.lisimg.com/1691841/130full.jpg

  - title: 'Ghost in the Shell 2: Innocence'
    image_url: http://pthumb.lisimg.com/26320/130full.jpg

  - title: Akira
    image_url: http://pthumb.lisimg.com/290195/130full.jpg

  - title: Voyage vers Agartha
    image_url: http://pthumb.lisimg.com/4743409/130full.jpg

  - title: Time of Eve
    image_url: http://pthumb.lisimg.com/3062903/130full.jpg

  - title: Pompoko
    image_url: http://pthumb.lisimg.com/262174/130full.jpg

  - title: Le Château ambulant
    image_url: http://pthumb.lisimg.com/3107733/130full.jpg

  - title: Si tu tends l'oreille
    image_url: http://pthumb.lisimg.com/4886686/130full.jpg

  - title: Kiki la petite sorcière
    image_url: http://pthumb.lisimg.com/205296/130full.jpg

  - title: Le Tombeau des lucioles
    image_url: http://pthumb.lisimg.com/15092302/130full.jpg
    bluray_bought: true

  - title: Le Garçon et la Bête
    image_url: http://pthumb.lisimg.com/11724604/130full.jpg

  - title: 5 centimètres par seconde
    image_url: http://pthumb.lisimg.com/15092325/130full.jpg

  - title: Piano Forest
    image_url: http://pthumb.lisimg.com/464496/130full.jpg

  - title: Nausicaä de la vallée du vent
    image_url: http://pthumb.lisimg.com/4872085/130full.jpg

  - title: Le Château dans le ciel
    image_url: http://pthumb.lisimg.com/190800/130full.jpg

  - title: Le vent se lève
    image_url: http://pthumb.lisimg.com/5870131/130full.jpg

  - title: Ponyo sur la falaise
    image_url: http://pthumb.lisimg.com/2441765/130full.jpg

  - title: Mon voisin Totoro
    image_url: http://pthumb.lisimg.com/9135550/130full.jpg

  - title: Colorful
    image_url: http://pthumb.lisimg.com/1307510/130full.jpg

  - title: Souvenirs goutte à goutte
    image_url: http://pthumb.lisimg.com/9706387/130full.jpg
    bluray_bought: true

  - title: Le Conte de la princesse Kaguya
    image_url: http://pthumb.lisimg.com/9641715/130full.jpg

  - title: Le Roi des ronces
    image_url: http://pthumb.lisimg.com/9623313/130full.jpg

  - title: La Colline aux coquelicots
    image_url: http://pthumb.lisimg.com/2557818/130full.jpg

  - title: Origine
    image_url: http://pthumb.lisimg.com/441899/130full.jpg

  - title: Porco Rosso
    image_url: http://pthumb.lisimg.com/28049/130full.jpg

  - title: The Garden of Words
    image_url: http://pthumb.lisimg.com/6892716/130full.jpg

  - title: Hotarubi no mori e
    image_url: https://m.media-amazon.com/images/M/MV5BYTI0ZTAzMzctZWVkMS00ZWMyLTkyZDctZjFmMjA3NTNmYzAyXkEyXkFqcGdeQXVyNTI2NTY2MDI@._V1_.jpg

  - title: Je peux entendre l'océan
    image_url: http://pthumb.lisimg.com/15092388/130full.jpg

  - title: Les Contes de Terremer
    image_url: http://pthumb.lisimg.com/68918/130full.jpg
    bluray_bought: true

  - title: Le Château de Cagliostro
    image_url: http://pthumb.lisimg.com/2758930/130full.jpg

  - title: Amer Béton
    image_url: http://pthumb.lisimg.com/109691/130full.jpg

  - title: Mes voisins les Yamada
    image_url: http://pthumb.lisimg.com/7489777/130full.jpg
    bluray_bought: true

---

{% for item in page.list %}
1. ![{{ item.title }}]({{ item.image_url }})
### {{ item.title }}
    {%- if item.bluray_bought %}
    + **$ Blu-ray $**
    {%- endif -%}
{% endfor %}
