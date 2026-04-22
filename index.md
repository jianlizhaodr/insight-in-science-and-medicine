---
layout: home
title: Insight in Science and Medicine
---

<p class="journal-tagline">
A peer-reviewed journal of translational research and clinical science
emphasizing reliability and data reusability.
<em>"This journal is published under CC BY 4.0. ISSN: 3069-8898"</em>
</p>

## Publication Information

<ul class="journal-meta">
  <li><strong>Publisher:</strong> Insight in Science and Medicine Publishing Group</li>
  <li><strong>ISSN:</strong> 3069-8898 (U.S. ISSN Center) (Online)</li>
  <li><strong>DOI prefix:</strong> 10.65587</li>
</ul>

## Topics

- [Biotech](/biotech.html)

## Most recent

<div class="recent-grid">

  <div class="card card--issue">
    <div class="card__cover">
      <div class="card__cover-placeholder">
        <span class="cover-title">Current Issue</span>
        <span class="cover-subtitle">Insight in Science and Medicine</span>
      </div>
    </div>
    <ul class="card__links">
      <li><a href="{{ '/' | relative_url }}">Journal Home</a></li>
      <li><a href="{{ '/biotech.html' | relative_url }}">Table of Contents</a></li>
      <li><a href="{{ '/biotech.html' | relative_url }}">Online Now</a></li>
      <li><a href="{{ '/about.html' | relative_url }}">About</a></li>
    </ul>
  </div>

  {% assign all_entries = site.biotech | sort: "date" | reverse %}
  {% for entry in all_entries limit: 6 %}
    <a class="card card--entry" href="{{ entry.url | relative_url }}">
      <div class="card__body">
        <h3 class="card__title">{{ entry.title }}</h3>
        <p class="card__category"><em>{{ entry.category | default: "Insight in Science and Medicine" }}</em></p>
      </div>
      {% if entry.image %}
        <div class="card__thumb">
          <img src="{{ entry.image | relative_url }}" alt="{{ entry.title }}">
        </div>
      {% endif %}
    </a>
  {% endfor %}

</div>
