---
layout: default
title: "Talks & Presentations"
lang: en
permalink: /en/talks/
alt_lang_url: /talks/
---

# 🎤 Talks & Presentations

<div class="page-lang-switch">
  <a href="{{ page.alt_lang_url | relative_url }}" class="lang-switch-btn">
    Ver esta página en Español →
  </a>
</div>

Here you’ll find my participation in international events, conferences, technical forums and presentations related to IXPs, BGP, RPKI and network operations.

{% assign talks = site.data.talks | where_exp: "t", "t.lang == 'en' and t.published != false and t.published != 'false'" %}

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
          <span class="talk-cta">View details →</span>
        </div>
      </div>
    </a>

    {% if t.external_url %}
    <a class="talk-external" href="{{ t.external_url }}" target="_blank" rel="noopener">
      Official event ↗
    </a>
    {% endif %}
  </article>
  {% endfor %}
</div>
