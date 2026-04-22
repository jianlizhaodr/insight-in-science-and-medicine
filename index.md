---
layout: home
title: Insight in Science and Medicine
---

<p class="journal-tagline">
A peer-reviewed journal of translational research and clinical science
emphasizing reliability and data reusability.
<em>"This journal is published under CC BY 4.0. ISSN: 3069-8898"</em>
</p>

<!-- =============================================================
     HERO: Cover + Issue info | Action buttons | Journal metrics
     ============================================================= -->
<section class="hero">

  <div class="hero__issue">
    <div class="hero__cover">
      <div class="hero__cover-placeholder">
        <span>Insight in<br>Science and<br>Medicine</span>
      </div>
    </div>
    <div class="hero__issue-info">
      <h3>Current Issue</h3>
      <p class="hero__volume">Volume 1, Issue 1, April 22, 2026</p>
      <a class="btn btn--primary" href="{{ '/biotech.html' | relative_url }}">
        ⬇ Download full issue
      </a>
      <ul class="hero__issue-links">
        <li><a href="{{ '/biotech.html' | relative_url }}">Online now</a></li>
        <li><a href="{{ '/biotech.html' | relative_url }}">Archive</a></li>
      </ul>
    </div>
  </div>

  <div class="hero__actions">
    <a class="btn btn--outline" href="{{ '/about.html' | relative_url }}">Submit article ↗</a>
    <a class="btn btn--outline" href="{{ '/about.html' | relative_url }}">View aims &amp; scope</a>
    <a class="btn btn--outline" href="{{ '/about.html' | relative_url }}">Information for authors</a>
    <a class="btn btn--outline" href="{{ '/about.html' | relative_url }}">Sign up for alerts</a>
  </div>

  <div class="hero__metrics">
    <h4>Journal metrics</h4>
    <div class="metrics-grid">
      <div class="metric">
        <div class="metric__value">—</div>
        <div class="metric__label">Time to first<br>editorial decision</div>
      </div>
      <div class="metric">
        <div class="metric__value">—</div>
        <div class="metric__label">Acceptance to<br>online publication</div>
      </div>
    </div>
  </div>

</section>

<!-- =============================================================
     SUBJECT AREAS
     ============================================================= -->
<section class="subject-areas">
  <h2>Subject areas</h2>
  <ul class="subject-list">
    <li><a href="{{ '/biochemical-sciences.html' | relative_url }}">Biochemical Sciences</a></li>
    <li><a href="{{ '/biotechnology.html' | relative_url }}">Biotechnology</a></li>
    <li><a href="{{ '/molecular-medicine.html' | relative_url }}">Molecular Medicine</a></li>
  </ul>
</section>

<!-- =============================================================
     FEATURED CONTENT
     ============================================================= -->
<section class="content-section content-section--featured">
  <h2>Featured content</h2>
  <div class="article-grid">
    {% assign featured = site.biotech | where: "featured", true | sort: "date" | reverse %}
    {% if featured.size > 0 %}
      {% for entry in featured limit: 4 %}
        {% include article-card.html entry=entry %}
      {% endfor %}
    {% else %}
      {% assign recent = site.biotech | sort: "date" | reverse %}
      {% for entry in recent limit: 4 %}
        {% include article-card.html entry=entry %}
      {% endfor %}
    {% endif %}
  </div>
</section>

<!-- =============================================================
     ONLINE NOW (most recent)
     ============================================================= -->
<section class="content-section">
  <h2>Online now</h2>
  <div class="article-grid">
    {% assign recent = site.biotech | sort: "date" | reverse %}
    {% for entry in recent limit: 4 %}
      {% include article-card.html entry=entry %}
    {% endfor %}
  </div>
</section>

## Publication Information

<ul class="journal-meta">
  <li><strong>Publisher:</strong> Insight in Science and Medicine Publishing Group</li>
  <li><strong>ISSN:</strong> 3069-8898 (U.S. ISSN Center) (Online)</li>
  <li><strong>DOI prefix:</strong> 10.65587</li>
</ul>
