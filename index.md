---
layout: default
---

<h1> 最近文章</h1>

<ul class="post-list">
  {% for post in site.posts %}
    <li>
      <span class="post-date">{{ post.date | date: "%Y年%m月%d日" }}</span>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      {% if post.categories %}
        {% for cat in post.categories %}
          <span class="category-tag">{{ cat }}</span>
        {% endfor %}
      {% endif %}
    </li>
  {% endfor %}
</ul>

<hr style="margin: 30px 0; border-color: #ccc;">

<h2> 关于本站</h2>

<p>欢迎来到我的博客！这里会记录我的学习笔记、画和一些碎碎念。</p>
