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
    <h2 style="font-size: 24px; font-weight: bold; margin-top: 30px; color: #3f51b5; border-bottom: 2px solid #3f51b5; padding-bottom: 5px;">{{ current_year }}</h2>
  {% endif %}

  <table style="width:100%; margin-bottom:15px; border-collapse:collapse; border: none; table-layout: fixed;">
    <tr>
      <!-- Icon (Left) -->
      <td style="width: 5%; font-size: 20px; text-align: center; vertical-align: middle; padding-right: 10px;">
        <i class="far fa-file-alt"></i>
      </td>

      <!-- Publication Details (Middle) -->
      <td style="width: 75%; vertical-align: middle; padding-right: 15px;">
        <strong style="font-size: 18px; font-weight: bold; color: #0073e6;">{{ pub.title }}</strong><br>
        by <span style="font-size: 14px; color: #555;">{{ pub.authors }}</span><br>
        <span style="font-size: 14px; color: #777;">
          <em>{{ pub.journal }}</em>
          {% if pub.volume %}, Vol. {{ pub.volume }}{% endif %}
          {% if pub.number %}, No. {{ pub.number }}{% endif %}
          {% if pub.pages %}, pp. {{ pub.pages }}{% endif %}
          {% if pub.year %}, {{ pub.year }}{% endif %}
        </span><br>

        <div>
          {% if pub.pdf %}
            <a style="display:inline-block; padding:5px 10px; margin-right:5px; border:1px solid #0073e6; color:#0073e6; text-decoration:none; border-radius:5px;" href="{{ pub.pdf }}" target="_blank" rel="noopener">PDF</a>
          {% endif %}
          {% if pub.arxiv %}
            <a style="display:inline-block; padding:5px 10px; margin-right:5px; border:1px solid #0073e6; color:#0073e6; text-decoration:none; border-radius:5px;" href="{{ pub.arxiv }}" target="_blank" rel="noopener">arXiv</a>
          {% endif %}
          {% if pub.hal %}
            <a style="display:inline-block; padding:5px 10px; border:1px solid #0073e6; color:#0073e6; text-decoration:none; border-radius:5px;" href="{{ pub.hal }}" target="_blank" rel="noopener">HAL</a>
          {% endif %}
        </div>
      </td>

      <!-- Thumbnail (Right) -->
      <td style="width: 210px; height: 120px; text-align: right; vertical-align: middle; overflow: hidden;">
        {% if pub.image %}
          <img src="{{ pub.image }}" alt="Thumbnail for {{ pub.title }}" style="height: 120px; width: auto; max-width: 210px; border-radius: 5px;">
        {% endif %}
      </td>
    </tr>
  </table>

{% endfor %}
