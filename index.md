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

{% assign pinned_title = "ドイツで『第九』を聴いて、人生の解像度が少し上がった話" %}
{% assign pinned_post = site.posts | where:"title", pinned_title | first %}

{% if pinned_post %}
<div style="margin-bottom: 50px;">
  <p style="color: #d32f2f; font-weight: bold; margin-bottom: 10px; font-size: 1.1em;">📌 Pick Up</p>
  
  <div style="border: 2px solid #d32f2f; border-radius: 8px; padding: 20px; background-color: white;">
    <div style="display: flex; align-items: flex-start;">
      {% assign pinned_thumb = pinned_post.image | default: '/images/icon.jpg' %}
      <a href="{{ pinned_post.url }}" style="margin-right: 20px; flex-shrink: 0;">
        <img src="{{ pinned_thumb | relative_url }}" alt="cover" style="width: 100px; height: 100px; object-fit: cover; border-radius: 50%; border: 2px solid #d32f2f;">
      </a>
      <div>
        <h3 style="margin-top: 0; margin-bottom: 10px;">
          <a href="{{ pinned_post.url }}" style="text-decoration: none; color: #333; font-size: 1.2em;">
            {{ pinned_post.title }}
          </a>
        </h3>
        <p style="color: #555; margin: 0; line-height: 1.6;">
          {{ pinned_post.excerpt | strip_html | truncate: 100 }}
        </p>
        <a href="{{ pinned_post.url }}" style="color: #d32f2f; font-weight: bold; display: inline-block; margin-top: 10px;">記事を読む →</a>
      </div>
    </div>
  </div>
</div>
{% endif %}

<h2>最新の記事</h2>

<div class="posts">
  {% for post in site.posts %}
    {% if post.title == pinned_title %}{% continue %}{% endif %}

    <div style="display: flex; align-items: flex-start; margin-bottom: 25px; border-bottom: 1px solid #eee; padding-bottom: 20px;">

      {% assign thumbnail = post.image | default: '/images/icon.jpg' %}
      
      <a href="{{ post.url }}" style="margin-right: 15px; flex-shrink: 0;">
        <img src="{{ thumbnail | relative_url }}" alt="cover" style="width: 80px; height: 80px; object-fit: cover; border-radius: 50%; border: 1px solid #ddd;">
      </a>
      
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
