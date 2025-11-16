---
layout: default
title: "Carlos Pérez | Network Engineering Notes"
lang: en
alt_lang_url: /
permalink: /index-en/
description: "Field notes on network engineering, automation, monitoring, and peering."
---

# 👋 Welcome to Network Engineering Notes

> The technical blog of Carlos Pérez on network engineering, automation, monitoring, and peering.

## 📌 Published articles

{% assign articles = site.data.articles | where: "lang", "en" %}

<div class="articles-grid">
  {% for a in articles %}
    <article class="article-card">
      <a class="article-card-link" href="{{ a.url | relative_url }}">
        
        {% if a.image %}
  <div class="article-thumb">
    <img src="{{ a.image | relative_url }}" alt="{{ a.title }}">
  </div>
{% else %}
  <div class="article-thumb placeholder">
    <div class="placeholder-content">
      <span class="emoji">{{ a.emoji }}</span>
    </div>
  </div>
{% endif %}


        <div class="article-body">
          <div class="article-meta">
            <span class="article-category">{{ a.category }}</span>
            <span class="article-date">{{ a.date }}</span>
          </div>

          <h2 class="article-title">
            {{ a.emoji }} {{ a.title }}
          </h2>

          <p class="article-excerpt">
            {{ a.excerpt }}
          </p>

          <div class="article-footer">
            <span class="article-readtime">⏱ {{ a.read_time }}</span>
            <span class="article-cta">Read article →</span>
          </div>
        </div>

      </a>
    </article>
  {% endfor %}
</div>

---

Thanks for visiting this site.
