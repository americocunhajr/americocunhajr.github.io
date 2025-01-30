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
{% assign current_year = 0 %}

{% for pub in sorted_publications %}
  {% assign pub_year = pub.year | plus: 0 %}

  {% if pub_year != current_year %}
    {{ pub_year }}
    ----
    {% assign current_year = pub_year %}
  {% endif %}

  <table style="width:100%; margin-bottom:15px; border-collapse:collapse; border: none; table-layout: fixed; border-spacing: 0;">
    <tr>
      <!-- Icon (Left) -->
      <td style="width: 5%; font-size: 20px; text-align: center; vertical-align: top; padding-right: 10px; border: none;">
        <i class="far fa-file-alt"></i>
      </td>

      <!-- Publication Details (Middle) -->
      <td style="width: 75%; vertical-align: middle; padding-right: 15px; border: none;">
        <strong style="font-size: 18px; font-weight: bold; color: #0073e6;">{{ pub.title }}</strong><br>
        by <span style="font-size: 14px; color: #555;">{{ pub.authors }}</span><br>
        <span style="font-size: 14px; color: #777;">
          <em>{{ pub.journal }}</em>
          {% if pub.volume %}, Vol. {{ pub.volume }}{% endif %}
          {% if pub.number %}, No. {{ pub.number }}{% endif %}
          {% if pub.pages %}, pp. {{ pub.pages }}{% endif %}
          {% if pub.year %}, {{ pub.year }}{% endif %}
        </span><br>
        <span style="font-size: 14px; color: #777;">{{ pub.doi }}</span><br>

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
          {% if pub.news %}
            <a class="btn btn-outline-primary btn-sm" href="{{ pub.news }}" target="_blank" rel="noopener">News</a>
          {% endif %}
        </div>
      </td>

      <!-- Thumbnail (Right) -->
      <td style="width: 210px; height: 120px; text-align: right; vertical-align: middle; overflow: hidden; border: none;">
        {% if pub.image %}
          <img src="{{ pub.image }}" alt="Thumbnail" style="height: 120px; width: auto; max-width: 210px; border-radius: 5px;">
        {% endif %}
      </td>
    </tr>
  </table>

{% endfor %}
