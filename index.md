---
layout: default
---

<div class="posts">
  {% for post in site.posts %}
    <article class="post-preview" style="margin-bottom: 40px;">
      
      <h2 style="margin-bottom: 5px;">
        <a href="{{ post.url | relative_url }}" style="text-decoration: none; color: #333;">
          {{ post.title }}
        </a>
      </h2>
      
      <p style="color: #888; font-size: 0.9em; margin-top: 0;">
        📅 {{ post.date | date: "%Y-%m-%d" }}
        {% if post.category %}
         | 📂 {{ post.category }}
        {% endif %}
      </p>

      <div class="excerpt">
        {{ post.excerpt }}
      </div>
      
      <a href="{{ post.url | relative_url }}" style="font-weight: bold; font-size: 0.9em;">続きを読む →</a>
      
    </article>
    <hr>
  {% endfor %}
</div>
