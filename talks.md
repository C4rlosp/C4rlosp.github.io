---
layout: default
title: "Charlas y Presentaciones"
lang: es
permalink: /talks/
alt_lang_url: /en/talks/
---

# 🎤 Charlas y Presentaciones

Aquí encontrarás mis participaciones en eventos, conferencias, foros técnicos y presentaciones internacionales sobre IXPs, BGP, RPKI y operación de redes.

{% assign talks = site.data.talks | where: "lang", "es" %}

<div class="talks-grid">
  {% for t in talks %}

  {%- comment -%}
  Si hay external_url, usamos ese.
  Si no, usamos url interna (por si algún día quieres una página propia).
  {%- endcomment -%}
  {% assign talk_link = t.external_url | default: t.url | relative_url %}

  <article class="talk-card">
    <a class="talk-card-link"
       href="{{ talk_link }}"
       {% if t.external_url %}target="_blank" rel="noopener"{% endif %}>

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
          <span class="talk-cta">
            {% if page.lang == "es" %}
              Ver publicación →
            {% else %}
              View publication →
            {% endif %}
          </span>
        </div>
      </div>
    </a>
  </article>

  {% endfor %}
</div>

