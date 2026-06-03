---
layout: default
title: 分类
---

#  文章分类

{% for category in site.categories %}
  <div class="window" style="margin-bottom: 20px;">
    <div class="title-bar">
      <div class="title-bar-text"> {{ category[0] }}</div>
    </div>
    <div class="window-body">
      <ul>
        {% for post in category[1] %}
          <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a> - {{ post.date | date: "%Y年%m月%d日" }}</li>
        {% endfor %}
      </ul>
    </div>
  </div>
{% endfor %}
