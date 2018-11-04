---
layout: page
title: Séries préférées
permalink: /series

list:
  - title: Rick and Morty
    image_url: http://pthumb.lisimg.com/15851577/130full.jpg
    number_of_seasons: 3

  - title: South Park
    image_url: http://pthumb.lisimg.com/863844/130full.jpg
    number_of_seasons: 20

  - title: Game of Thrones
    image_url: http://pthumb.lisimg.com/3396085/130full.jpg
    number_of_seasons: 7

  - title: Breaking Bad
    image_url: http://pthumb.lisimg.com/5502367/130full.jpg
    number_of_seasons: 5

  - title: The Walking Dead
    image_url: http://pthumb.lisimg.com/16173302/130full.jpg
    number_of_seasons: 7

  - title: The IT Crowd
    image_url: http://pthumb.lisimg.com/6446472/130full.jpg
    number_of_seasons: 4

  - title: Scrubs
    image_url: http://pthumb.lisimg.com/15277945/130full.jpg
    number_of_seasons: 8

  - title: Kaamelott
    image_url: http://pthumb.lisimg.com/2651844/130full.jpg
    number_of_seasons: 6

  - title: Black Mirror
    image_url: https://m.media-amazon.com/images/M/MV5BNTEwYzNiMGUtNzRlYS00MTMzLTliNzgtOGUxZGZiNThlNWYwXkEyXkFqcGdeQXVyMjYwNDA2MDE@._V1_SY1000_CR0,0,675,1000_AL_.jpg
    number_of_seasons: 4

  - title: Stranger Things
    image_url: http://pthumb.lisimg.com/16055339/130full.jpg
    number_of_seasons: 2

  - title: Mr. Robot
    image_url: http://pthumb.lisimg.com/11659857/130full.jpg
    number_of_seasons: 2

  - title: Better Call Saul
    image_url: http://pthumb.lisimg.com/14183847/130full.jpg
    number_of_seasons: 4

  - title: Westworld
    image_url: http://pthumb.lisimg.com/15970527/130full.jpg
    number_of_seasons: 1

  - title: The Simpsons
    image_url: http://pthumb.lisimg.com/15692738/130full.jpg
    number_of_seasons: 20

  - title: Ma famille d'abord
    image_url: http://pthumb.lisimg.com/7808586/130full.jpg
    number_of_seasons: 5

  - title: Sense8
    image_url: http://pthumb.lisimg.com/8719046/130full.jpg
    number_of_seasons: 1

  - title: Une nounou d'enfer
    image_url: http://pthumb.lisimg.com/6470208/130full.jpg
    number_of_seasons: 6

  - title: Hero Corp
    image_url: http://pthumb.lisimg.com/5365117/130full.jpg
    number_of_seasons: 2

  - title: Heroes
    image_url: http://pthumb.lisimg.com/7512082/130full.jpg
    number_of_seasons: 4

  - title: Les 4400
    image_url: http://pthumb.lisimg.com/10087947/130full.jpg
    number_of_seasons: 4

  - title: Stargate SG-1
    image_url: http://pthumb.lisimg.com/4034834/130full.jpg
    number_of_seasons: 4

  - title: Dr House
    image_url: http://pthumb.lisimg.com/2531037/130full.jpg
    number_of_seasons: 5

  - title: Charmed
    image_url: http://pthumb.lisimg.com/7334458/130full.jpg
    number_of_seasons: 8

  - title: American Dad!
    image_url: http://pthumb.lisimg.com/10087937/130full.jpg
    number_of_seasons: 8

  - title: Buffy contre les vampires
    image_url: http://pthumb.lisimg.com/6994959/130full.jpg
    number_of_seasons: 5

  - title: Friends
    image_url: https://m.media-amazon.com/images/M/MV5BNDVkYjU0MzctMWRmZi00NTkxLTgwZWEtOWVhYjZlYjllYmU4XkEyXkFqcGdeQXVyNTA4NzY1MzY@._V1_.jpg
    number_of_seasons: 10

  - title: 'NCIS : Enquêtes spéciales'
    image_url: http://pthumb.lisimg.com/6727346/130full.jpg
    number_of_seasons: 8

---

{% for item in page.list %}
1. ![{{ item.title }}]({{ item.image_url }})
### {{ item.title }}
    {%- if item.number_of_seasons %}
    + {{ item.number_of_seasons }} saisons
    {%- endif -%}
{% endfor %}
