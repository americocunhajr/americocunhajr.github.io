---
layout: single
title: "Publications"
permalink: /publications/
collection: publications
entries_layout: list
author_profile: true
---

📜 Copyright Notice 📜

🏛️👨‍🏫 Several publications presented below are copyrighted by either a publisher or the authors. They are available here for educational and academic use only 📚🎓.

⚠️ All rights of reproduction or distribution in any form are reserved ⚖️❌.

📩 If you have any questions regarding the usage of these publications, feel free to contact me!


{% assign SortedPublications = site.publications | sort: "year" | reverse %}
{% assign CurrentYear = 0 %}
{% for pub in SortedPublications %}
  {% assign PubYear = pub.year | plus: 0 %}
  {% if PubYear != CurrentYear %}
    <h2 class="year-heading">{{ PubYear }}</h2>
    {% assign CurrentYear = PubYear %}
  {% endif %}
  <table style="width:100%; margin-bottom:15px; border-collapse:collapse; border: none; table-layout: fixed; border-spacing: 0;">
      <tr>
        <td style="width: 10%; font-size: 30px; text-align: left; vertical-align: top; padding-right: 30px; border: none;">
        <i class="far fa-file-alt"></i>
      </td>
      <!-- Publication Details (Middle) -->
      <td style="width: 75%; text-align: left; vertical-align: middle; padding-left: 20px; border: none;">
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
      <td style="width: 175px; height: 100px; text-align: right; vertical-align: middle; overflow: hidden; border: none;">
        {% if pub.image %}
          <img src="{{ pub.image }}" alt="Thumbnail" style="height: 100px; width: auto; max-width: 175px; border-radius: 1px;">
        {% endif %}
      </td>
    </tr>
  </table>

{% endfor %}
