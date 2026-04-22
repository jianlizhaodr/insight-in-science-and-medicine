---
layout: page
title: Biotech
permalink: /biotech.html
---

Entries on biotechnology, genetics, and drug development.

<ul>
{% assign entries = site.biotech | sort: "date" | reverse %}
{% for entry in entries %}
  <li>
    <span>{{ entry.date | date: "%Y-%m-%d" }}</span>
    &middot;
    <a href="{{ entry.url | relative_url }}">{{ entry.title }}</a>
  </li>
{% endfor %}
</ul>
