---
layout: default
title: "Charlas y Presentaciones"
lang: es
permalink: /talks/
alt_lang_url: /en/talks/
---

# 🎤 Charlas y Presentaciones

<div class="page-lang-switch">
  <a href="{{ page.alt_lang_url | relative_url }}" class="lang-switch-btn">
    View this page in English →
  </a>
</div>

Aquí encontrarás mis participaciones en eventos, conferencias, foros técnicos y presentaciones internacionales sobre IXPs, BGP, RPKI y operación de redes.

{% assign talks = site.data.talks | where_exp: "t", "t.lang == 'es' and t.published != false" %}

<div class="talks-grid">
  {% for t in talks %}
  <article class="talk-card">
    <a class="talk-card-link" href="{{ t.url | relative_url }}">
      {% if t.image %}
      <div class="talk-thumb">
        <img src="{{ t.image | relative_url }}" alt="{{ t.title }}">
      </div>
      {% endif %}

      <div class="talk-body">
        <h3 class="talk-title">{{ t.title }}</h3>
        <div class="talk-meta">
          <span>📍 {{ t.location }}</span>
          <span>🗓 {{ t.date }}</span>
        </div>

        <p>{{ t.description }}</p>

        <div class="talk-footer">
          <span class="talk-cta">Ver detalle →</span>
        </div>
      </div>
    </a>

    {% if t.external_url %}
    <a class="talk-external" href="{{ t.external_url }}" target="_blank" rel="noopener">
      Evento oficial ↗
    </a>
    {% endif %}
  </article>
  {% endfor %}
</div>

