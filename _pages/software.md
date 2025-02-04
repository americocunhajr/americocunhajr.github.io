---
layout: single
title: "Computational Tools & Software"
permalink: /software/
collection: software
entries_layout: list
author_profile: true
---

🛠️ Below is a collection of software packages I have developed or contributed to. These tools serve various applications in nonlinear dynamics, energy harvesting, epidemic modeling, uncertainty quantification, machine learning, etc.

---

{% assign softwares = site.software | sort: "title" %}

{% for soft in softwares %}
<table style="width:100%; margin-bottom: 0px; border-collapse:collapse; border: none; border-spacing: 0;">
  <tr>
    <!-- Software Logo -->
    <td style="width: 150px; text-align: center; vertical-align: middle;">
      <img src="{{ soft.logo }}" alt="{{ Logo }} logo" style="width: auto; height: 120px;">
    </td>

    <!-- Software Name & Description -->
    <td style="padding-left: 15px; vertical-align: middle;">
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
- 🔧 All of these tools are **open-source** and available for **academic and research use**.
- 📬 Feel free to **contact me** if you have questions or would like to contribute.

