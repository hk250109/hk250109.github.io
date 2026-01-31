---
layout: default
title: 記事一覧
permalink: /archive/
---

<h1>記事一覧</h1>

{% for category in site.categories %}
  <h2 style="margin-top: 40px; border-bottom: 2px solid #eee;">{{ category[0] }}</h2>
  <ul>
    {% for post in category[1] %}
      <li>
        <span style="color: #888; font-size: 0.8em;">{{ post.date | date: "%Y-%m-%d" }}</span>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
