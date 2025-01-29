---
layout: collection
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
