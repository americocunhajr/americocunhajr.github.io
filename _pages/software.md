---
layout: single
title: "🖥️ Software Tools"
permalink: /software/
collection: software
entries_layout: list
author_profile: true
---

---

{% assign softwares = site.software | sort: "title" %}

{% for soft in softwares %}
<table style="width:100%; margin-bottom: 15px; border-collapse:collapse; border: none; table-layout: fixed; border-spacing: 0;">
  <tr>
    <!-- Software Logo -->
    <td style="width: 150px; text-align: center; vertical-align: middle; border: none;">
      <img src="{{ soft.logo }}" alt="{{ Logo }} logo" style="width: 150px; height: auto;">
    </td>

    <!-- Software Name & Description -->
    <td style="padding-left: 15px; vertical-align: middle; border: none;">
      <h3 style="margin-bottom: 5px;">{{ soft.title }}</h3>
      <p>{{ soft.description }}</p>

      <!-- Links: GitHub, Docs, Download -->
      {% if soft.url %}
      <a href="{{ soft.website }}" target="_blank" class="btn btn-outline-primary btn-sm">🌐 URL</a>
      {% endif %}
      
      {% if soft.github %}
      <a href="{{ soft.github }}" target="_blank" class="btn btn-outline-primary btn-sm">💻 GitHub</a>
      {% endif %}

      {% if soft.docs %}
      <a href="{{ soft.docs }}" target="_blank" class="btn btn-outline-primary btn-sm">📖 Documentation</a>
      {% endif %}

      {% if soft.download %}
      <a href="{{ soft.download }}" target="_blank" class="btn btn-outline-primary btn-sm">⬇️ Download</a>
      {% endif %}
    </td>
  </tr>
</table>
{% endfor %}

---

### 📌 **Notes**
- 🛠️ All of these computational tools are **open-source** and available for **academic and research use**. They serve various applications in nonlinear dynamics, energy harvesting, epidemic modeling, uncertainty quantification, machine learning, etc.
- 📬 Feel free to **contact me** if you have questions or would like to contribute.

