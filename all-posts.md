---
layout: default
---

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      - {{ post.date | date: "%Y年%m月%d日" }}
    </li>
  {% endfor %}
</ul>
