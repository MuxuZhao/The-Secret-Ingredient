---
layout: home
title: 赛博厨房?👨‍💻🍳
---

> "stay foolish, don't stay hungry"

<br>

## 🔥 new recipes

{% for post in site.posts limit:3 %}
<div class="recipe-card">
  {% if post.image %}
  <div class="recipe-image">
    <img src="{{ site.baseurl }}/{{ post.image }}" alt="{{ post.title }}" />
  </div>
  {% endif %}
  
  <div class="recipe-content">
    <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
    <p class="recipe-meta">
      📅 {{ post.date | date: "%Y年%m月%d日" }} 
      {% if post.categories %}
        | 🏷️ {% for category in post.categories %}{{ category }}{% unless forloop.last %}, {% endunless %}{% endfor %}
      {% endif %}
    </p>
    {% if post.excerpt %}
      <p class="recipe-excerpt">{{ post.excerpt | strip_html | truncate: 120 }}</p>
    {% endif %}
    <a href="{{ post.url | relative_url }}" class="read-more">查看完整菜谱 →</a>
  </div>
</div>
{% else %}
<p>❌ 没有找到任何菜谱文件！请检查_posts文件夹中的文件格式。</p>
{% endfor %}

<br>

## 🍽️ categories

{% assign categories = site.categories | sort %}
{% if categories.size > 0 %}
{% for category in categories %}
- 🏷️ **{{ category[0] }}** ({{ category[1].size }} 个菜谱)
  {% for post in category[1] limit:3 %}
  - [{{ post.title }}]({{ post.url | relative_url }})
  {% endfor %}
{% endfor %}
{% else %}
**暂时没有分类内容，请检查菜谱文件的categories设置**
- 🥩 肉类料理
- 🥬 蔬菜料理  
- 🍜 汤品
- 🍰 甜点
- 🎮 来自二次元
- ⚡ 其他
{% endif %}

<br>
<br>
<br>
## 😋 the ultimate meaning of the existence of this site
由于我想要通过做出美味的料理来狠狠地享受生活，但是又记不住这些做菜的步骤，我弄了个这样的网站来帮助我做饭~11

<br>



<style>
.recipe-card {
  border: 1px solid #e1e1e1;
  border-radius: 12px;
  padding: 0;
  margin: 1.5rem 0;
  background: #fafafa;
  overflow: hidden;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  display: flex;
  flex-direction: row;
  align-items: stretch;
}

.recipe-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 16px rgba(0,0,0,0.15);
}

.recipe-image {
  flex: 0 0 200px;
  height: 150px;
  overflow: hidden;
  background: #f0f0f0;
}

.recipe-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 0;
}

.recipe-content {
  flex: 1;
  padding: 1.2rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.recipe-card h3 {
  margin: 0 0 0.5rem 0;
  color: #d63384;
  font-size: 1.3rem;
}

.recipe-card h3 a {
  text-decoration: none;
  color: inherit;
}

.recipe-card h3 a:hover {
  color: #b02a5b;
}

.recipe-meta {
  color: #666;
  font-size: 0.9em;
  margin: 0.5rem 0;
}

.recipe-excerpt {
  color: #444;
  line-height: 1.5;
  margin: 0.5rem 0 1rem 0;
  flex-grow: 1;
}

.read-more {
  color: #d63384;
  text-decoration: none;
  font-weight: 500;
  font-size: 0.9rem;
  align-self: flex-start;
}

.read-more:hover {
  color: #b02a5b;
  text-decoration: underline;
}

/* 隐藏主页 posts 部分的图片 */
.blog .post-thumbnail {
  display: none;
}

/* 移动端适配 */
@media (max-width: 768px) {
  .recipe-card {
    flex-direction: column;
  }
  
  .recipe-image {
    flex: none;
    height: 200px;
  }
  
  .recipe-content {
    padding: 1rem;
  }
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
