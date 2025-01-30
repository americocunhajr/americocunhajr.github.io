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
  {{ pub.authors }}, {{ pub.journal }}, {{ pub.year }}  
    [Read more]({{ pub.url }})
{% endfor %}
