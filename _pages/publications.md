---
layout: single
title: "Publications"
permalink: /publications/
collection: publications
entries_layout: list
author_profile: true
---

Here you can find my **published journal articles, conference papers, and book chapters**.

{% for pub in site.publications reversed %}
  - **{{ pub.title }}**  
    _{{ pub.authors }}_  
    {{ pub.journal }}, {{ pub.year }}  
    [Read more]({{ pub.url }})
{% endfor %}


{% assign sorted_publications = site.publications | sort: "year" | reverse %}

{% assign current_year = "" %}

{% for pub in sorted_publications %}
  {% if pub.year != current_year %}
    {% assign current_year = pub.year %}
    <h2>{{ current_year }}</h2>
  {% endif %}

  <div class="media stream-item">
    <div class="media-body">

      <h3 class="article-title mb-0 mt-0">
        <a href="{{ pub.url }}">{{ pub.title }}</a>
      </h3>

      <div class="article-style">
        {{ pub.authors }}
      </div>

      <div class="stream-meta article-metadata">
        <span>{{ pub.venue }}</span>
      </div>

      <div class="btn-links">
        {% if pub.pdf %}
          <a class="btn btn-outline-primary my-1 mr-1 btn-sm" href="{{ pub.pdf }}" target="_blank" rel="noopener">PDF</a>
        {% endif %}
        {% if pub.arxiv %}
          <a class="btn btn-outline-primary my-1 mr-1 btn-sm" href="{{ pub.arxiv }}" target="_blank" rel="noopener">arXiv</a>
        {% endif %}
        {% if pub.hal %}
          <a class="btn btn-outline-primary my-1 mr-1 btn-sm" href="{{ pub.hal }}" target="_blank" rel="noopener">HAL</a>
        {% endif %}
      </div>

    </div>

    <div class="ml-3">
      {% if pub.image %}
        <a href="{{ pub.url }}">
          <img src="{{ pub.image }}" alt="{{ pub.title }}" style="max-width:150px;">
        </a>
      {% endif %}
    </div>
  </div>
{% endfor %}
