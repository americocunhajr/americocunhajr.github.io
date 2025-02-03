---
layout: single
title: "Software"
permalink: /software/
collection: software
entries_layout: list
author_profile: true
---

## 🛠️ Computational Tools & Software

Below is a collection of **software packages** I have developed or contributed to. These tools serve various applications, including **nonlinear dynamics, epidemic modeling, uncertainty quantification, and machine learning**.

---

{% assign softwares = site.software | sort: "title" %}

{% for soft in softwares %}
<table style="width:100%; border:0; margin-bottom: 20px;">
  <tr>
    <!-- Software Logo -->
    <td style="width: 80px; text-align: center; vertical-align: middle;">
      <img src="/images/software/{{ soft.logo }}" alt="{{ soft.title }} logo" style="width: 60px; height: auto;">
    </td>

    <!-- Software Name & Description -->
    <td style="padding-left: 15px; vertical-align: middle;">
      <h3 style="margin-bottom: 5px;">{{ soft.title }}</h3>
      <p>{{ soft.description }}</p>

      <!-- Links: GitHub, Docs, Download -->
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
- 🔧 Many of these tools are **open-source** and available for **academic and research use**.
- 📬 Feel free to **contact me** if you have questions or would like to contribute.

