---
layout: single
title: "Publications"
permalink: /publications/
collection: publications
entries_layout: list
author_profile: true
---

Several publications presented below are copyrighted by either a publisher or the authors. They are available here for educational or academic use only. All rights of reproduction or distribution in any form are reserved.

{% for pub in site.publications reversed %}
  - **{{ pub.title }}**  
    {{ pub.authors }}, {{ pub.journal }}, {{ pub.year }}  
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
      
      <h3 class="article-title mb-0 mt-0">{{ pub.title }}</h3>

      <div class="article-style">
        <strong>Authors:</strong> {{ pub.authors }}  
        <strong>Journal:</strong> {{ pub.journal }}  
        {% if pub.volume %}<strong>Volume:</strong> {{ pub.volume }}{% endif %}
        {% if pub.number %} | <strong>Number:</strong> {{ pub.number }}{% endif %}
        {% if pub.pages %} | <strong>Pages:</strong> {{ pub.pages }}{% endif %}
        <strong>Year:</strong> {{ pub.year }}
      </div>

      <div class="btn-links">
        {% if pub.pdf %}
          <a class="btn btn-outline-primary my-1 mr-1 btn-sm" href="{{ pub.pdf }}" target="_blank" rel="noopener">PDF</a>
        {% endif %}
      </div>

    </div>

    <div class="ml-3">
      {% if pub.image %}
        <img src="{{ pub.image }}" alt="Illustration for {{ pub.title }}" style="max-width:150px;">
      {% endif %}
    </div>
  </div>

{% endfor %}
