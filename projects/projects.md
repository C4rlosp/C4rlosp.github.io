---
layout: default
title: "Proyectos Técnicos"
lang: es
permalink: /projects/
alt_lang_url: /en/projects/
---

# 🧠 Proyectos Técnicos

A continuación encontrarás algunos de los proyectos desarrollados para el IXP y la comunidad técnica, centrados en monitoreo, automatización y redes.

{% assign projects = site.data.projects | sort: "order" %}

<div class="projects-grid">
  {% for p in projects %}
    <article class="project-card">
      <header class="project-header">
        <span class="project-pill">
          {{ p.pill_es }}
        </span>
        <h2 class="project-title">
          <a href="{{ p.repo }}" target="_blank" rel="noopener">
            {{ p.icon }} {{ p.title_es }}
          </a>
        </h2>
      </header>

      <p class="project-summary">
        {{ p.summary_es }}
      </p>
      <p class="project-detail">
        {{ p.detail_es }}
      </p>

      <a class="project-link" href="{{ p.repo }}" target="_blank" rel="noopener">
        Ver en GitHub →
      </a>
    </article>
  {% endfor %}
</div>

<p class="projects-more">
  ✳️ Más proyectos en mi perfil de GitHub:
  <a href="https://github.com/C4rlosp" target="_blank" rel="noopener">github.com/C4rlosp</a>
</p>
