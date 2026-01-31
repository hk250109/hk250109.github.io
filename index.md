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

<h2> 最新の記事</h2>

<div class="posts">
  {% for post in site.posts %}
    <div style="margin-bottom: 25px; border-bottom: 1px solid #eee; padding-bottom: 20px;">

      {% if post.image %}
        <div style="margin-bottom: 15px;">
          <a href="{{ post.url }}">
            <img src="{{ post.image | relative_url }}" alt="cover" style="width: 100%; height: 200px; object-fit: cover; border-radius: 8px;">
          </a>
        </div>
      {% endif %}
      
      <h3 style="margin-bottom: 5px;">
        <a href="{{ post.url }}" style="text-decoration: none; color: #333;">
          {{ post.title }}
        </a>
      </h3>
      
      <small style="color: #888;">
         {{ post.date | date: "%Y-%m-%d" }} | 
         {{ post.tags | join: ", " }}
      </small>

      <p style="color: #555; margin-top: 10px;">
        {{ post.excerpt | strip_html | truncate: 80 }}
      </p>
      
      <a href="{{ post.url }}">続きを読む →</a>
    </div>
  {% endfor %}
</div>
