---
layout: default
title: "Technical Projects"
lang: en
permalink: /en/projects/
alt_lang_url: /projects/
---

# 🧠 Technical Projects

Here are some of the open-source tools and monitoring templates developed for IXPs and the broader network engineering community.

{% assign projects = site.data.projects | sort: "order" %}

<div class="projects-grid">
  {% for p in projects %}
    <article class="project-card">
      <header class="project-header">
        <span class="project-pill">
          {{ p.pill_en }}
        </span>
        <h2 class="project-title">
          <a href="{{ p.repo }}" target="_blank" rel="noopener">
            {{ p.icon }} {{ p.title_en }}
          </a>
        </h2>
      </header>

      <p class="project-summary">
        {{ p.summary_en }}
      </p>
      <p class="project-detail">
        {{ p.detail_en }}
      </p>

      <a class="project-link" href="{{ p.repo }}" target="_blank" rel="noopener">
        View on GitHub →
      </a>
    </article>
  {% endfor %}
</div>

<p class="projects-more">
  ✳️ More projects on my GitHub profile:
  <a href="https://github.com/C4rlosp" target="_blank" rel="noopener">github.com/C4rlosp</a>
</p>
