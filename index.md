---
layout: home
title: 赛博厨房？？？ 👨‍💻🍳
---

# 你好

> "stay foolish, don't stay hungry" 

由于我想要通过做出美味的料理来狠狠地享受生活，但是又记不住这些做菜的步骤，我弄了个这样的网站来帮助我做饭~😋

## 🔥 new recipes

{% for post in site.posts limit:3 %}
<div class="recipe-card">
  <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
  <p class="recipe-meta">
    📅 {{ post.date | date: "%Y年%m月%d日" }} 
    {% if post.categories %}
      | 🏷️ {% for category in post.categories %}{{ category }}{% unless forloop.last %}, {% endunless %}{% endfor %}
    {% endif %}
  </p>
  {% if post.excerpt %}
    <p>{{ post.excerpt | strip_html | truncate: 100 }}</p>
  {% endif %}
</div>
{% endfor %}

## 🍽️ categories

- 🥩 [肉]({{ '/categories/meat' | relative_url }})
- 🥬 [菜]({{ '/categories/vegetable' | relative_url }})  
- 🍜 [汤]({{ '/categories/soup' | relative_url }})
- 🍰 [甜点]({{ '/categories/dessert' | relative_url }})
- 🎮 [来自二次元]({{ '/categories/fromIsekai' | relative_url }})
- ⚡ [其他]({{ '/categories/other' | relative_url }})



<style>
.recipe-card {
  border: 1px solid #e1e1e1;
  border-radius: 8px;
  padding: 1rem;
  margin: 1rem 0;
  background: #fafafa;
}

.recipe-card h3 {
  margin-top: 0;
  color: #d63384;
}

.recipe-meta {
  color: #666;
  font-size: 0.9em;
}
</style>
