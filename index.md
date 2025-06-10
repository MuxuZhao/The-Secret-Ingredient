---
layout: home
title: 赛博厨房？？？ 👨‍💻🍳
---

> "stay foolish, don't stay hungry"

<br>

## 🔥 new recipes


{% for post in site.posts limit:3 %}
<div class="recipe-card">
  <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
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

<br>

## 🍽️ categories



{% assign categories = site.categories | sort %}
{% for category in categories %}
- 🏷️ **{{ category[0] }}** ({{ category[1].size }} 个菜谱)
  {% for post in category[1] limit:3 %}
  - [{{ post.title }}]({{ post.url | relative_url }})
  {% endfor %}
{% endfor %}


<br>

## 😋 the ultimate meaning of the existence of this site


由于我想要通过做出美味的料理来狠狠地享受生活，但是又记不住这些做菜的步骤，我弄了个这样的网站来帮助我做饭~😋  

<br>

---

**调试信息**：
- 总共找到 {{ site.posts.size }} 个菜谱
- 网站根目录：{{ site.baseurl }}

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

/* 增加段落间距 */
h2 {
  margin-top: 2rem;
  margin-bottom: 1rem;
}

br {
  line-height: 1.5;
}
</style>
