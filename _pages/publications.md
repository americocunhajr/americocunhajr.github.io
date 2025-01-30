---
layout: single
title: "Publications"
permalink: /publications/
collection: publications
entries_layout: list
author_profile: true
---

Several publications presented below are copyrighted by either a publisher or the authors. They are available here for educational or academic use only. All rights of reproduction or distribution in any form are reserved.

{% assign sorted_publications = site.publications | sort: "year" | reverse %}
{% assign current_year = "" %}

{% for pub in sorted_publications %}
  {% if pub.year != current_year %}
    {% assign current_year = pub.year %}
    <h2 class="year-heading">{{ current_year }}</h2>
  {% endif %}

  <div class="pub-container">
    <div class="pub-thumbnail">
      {% if pub.image %}
        <img src="{{ pub.image }}" alt="Thumbnail for {{ pub.title }}">
      {% endif %}
    </div>
    
    <div class="pub-details">
      <div class="article-metadata">
        <strong>Authors:</strong> {{ pub.authors }}
      </div>
      <h3 class="pub-title">{{ pub.title }}</h3>

      <div class="article-metadata">
        <em>{{ pub.journal }}</em>
        {% if pub.volume %}, Vol. {{ pub.volume }}{% endif %}
        {% if pub.number %}, No. {{ pub.number }}{% endif %}
        {% if pub.pages %}, pp. {{ pub.pages }}{% endif %}
        {% if pub.year %}, {{ pub.year }}{% endif %}
      </div>

      <div class="btn-links">
        {% if pub.pdf %}
          <a class="btn btn-outline-primary btn-sm" href="{{ pub.pdf }}" target="_blank" rel="noopener">PDF</a>
        {% endif %}
        {% if pub.arxiv %}
          <a class="btn btn-outline-primary btn-sm" href="{{ pub.arxiv }}" target="_blank" rel="noopener">arXiv</a>
        {% endif %}
        {% if pub.hal %}
          <a class="btn btn-outline-primary btn-sm" href="{{ pub.hal }}" target="_blank" rel="noopener">HAL</a>
        {% endif %}
      </div>
    </div>
  </div>

{% endfor %}
