---
layout: home
title: Insight in Science and Medicine
---

A topic-focused journal of notes and commentary, with links to the primary
literature.

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
