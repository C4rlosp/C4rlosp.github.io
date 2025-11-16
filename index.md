---
layout: default
title: "Carlos Pérez | Network Engineering Notes"
lang: es
alt_lang_url: /index-en
description: "Notas sobre ingeniería de redes, automatización, monitoreo y peering."
---

# 👋 Bienvenido a Network Engineering Notes

> El blog técnico de Carlos Pérez sobre ingeniería de redes, automatización, monitoreo y peering.

## 📌 Artículos publicados

{% assign articles = site.data.articles | where: "lang", "es" %}

<div class="articles-grid">
  {% for a in articles %}
    <article class="article-card">
      <a class="article-card-link" href="{{ a.url | relative_url }}">
        
        {% if a.image %}
        <div class="article-thumb">
          <img src="{{ a.image | relative_url }}" alt="{{ a.title }}">
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
            <span class="article-cta">Leer artículo →</span>
          </div>
        </div>

      </a>
    </article>
  {% endfor %}
</div>

---

Gracias por visitar este sitio.
