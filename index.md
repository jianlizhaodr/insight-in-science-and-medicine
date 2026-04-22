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

## Recent entries

<ul>
{% assign all_entries = site.biotech | sort: "date" | reverse %}
{% for entry in all_entries limit: 10 %}
  <li>
    <span>{{ entry.date | date: "%Y-%m-%d" }}</span>
    &middot;
    <span>{{ entry.topic | default: "biotech" }}</span>
    &middot;
    <a href="{{ entry.url | relative_url }}">{{ entry.title }}</a>
  </li>
{% endfor %}
</ul>
