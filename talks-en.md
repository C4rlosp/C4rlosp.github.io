---
layout: default
title: "Talks & Presentations"
lang: en
permalink: /en/talks/
alt_lang_url: /talks/
---

# 🎤 Talks & Presentations

Here you’ll find my participations in international events, conferences, technical forums and presentations on IXPs, BGP, RPKI and network operations.

{% assign talks = site.data.talks | where: "lang", "en" %}

<div class="talks-grid">
  {% for t in talks %}
  <article class="talk-card">

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

      {% if t.link %}
      <a class="talk-link" href="{{ t.link }}" target="_blank">View event →</a>
      {% endif %}
    </div>

  </article>
  {% endfor %}
</div>
