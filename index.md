---
layout: home
title: The Secret Ingredient
---

## new recipes
{% for post in site.posts limit:3 %}
* [{{ post.title }}]({{ post.url }})
{% endfor %}
