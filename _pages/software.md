---
layout: single
title: "Software"
permalink: /software/
collection: software
entries_layout: list
author_profile: true
---

{% for item in site.software %}
- [{{ item.title }}]({{ item.url }}) - {{ item.summary }}
{% endfor %}

## Open-Source Software

- **[STONEHENGE](https://github.com/americocunhajr/STONEHENGE)**: Suite for nonlinear analysis of energy harvesting systems.
- **[SpringpotFit](https://github.com/americocunhajr/SpringpotFit)**: Fitting variable-order fractional elements using Cross-Entropy optimization.
- **[CEopt](https://github.com/americocunhajr/CEopt)**: Cross-Entropy method for nonconvex optimization.

[Visit my GitHub](https://github.com/americocunhajr/)
