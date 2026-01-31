---
layout: default
title: ブログトップ
---

<div style="background-color: #f6f8fa; padding: 20px; border-radius: 8px; margin-bottom: 30px;">
  <h2 style="margin-top: 0;">🇩🇪 Hello from Berlin!</h2>
  <p>
    クラシック音楽が好きです。<br>
    音楽のことや日頃考えたことなどを書き残します。<br>
    気ままな日記を公開しています。
  </p>
  <p>
    <a href="./about">→ 詳しいプロフィールを見る</a>
  </p>
</div>

<h2>最新の記事</h2>

<div class="posts">
  {% for post in site.posts %}
    <div style="display: flex; align-items: flex-start; margin-bottom: 25px; border-bottom: 1px solid #eee; padding-bottom: 20px;">

      {% if post.image %}
        <a href="{{ post.url }}" style="margin-right: 15px; flex-shrink: 0;">
          <img src="{{ post.image | relative_url }}" alt="cover" style="width: 80px; height: 80px; object-fit: cover; border-radius: 50%; border: 1px solid #ddd;">
        </a>
      {% endif %}
      
      <div style="flex-grow: 1;">
        
        <h3 style="margin-top: 0; margin-bottom: 5px;">
          <a href="{{ post.url }}" style="text-decoration: none; color: #333;">
            {{ post.title }}
          </a>
        </h3>
        
        <small style="color: #888; display: block; margin-bottom: 8px;">
           {{ post.date | date: "%Y-%m-%d" }}
           {% if post.tags.size > 0 %}
             | {{ post.tags | join: ", " }}
           {% endif %}
        </small>

        <p style="color: #555; margin: 0; line-height: 1.5; font-size: 0.95em;">
          {{ post.excerpt | strip_html | truncate: 80 }}
        </p>
        
        <a href="{{ post.url }}" style="font-size: 0.9em; display: inline-block; margin-top: 5px;">続きを読む →</a>
      </div>

    </div>
    {% endfor %}
</div>
