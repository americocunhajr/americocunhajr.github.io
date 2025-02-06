---
layout: single
title: "🎨 Nonlinear Art Gallery"
permalink: /NonlinearArt/
author_profile: true
---

---

🔬✨ Nonlinear systems are mesmerizing mathematical structures that give rise to intricate patterns, chaotic beauty, and emergent complexity. This gallery is a carefully curated collection of “mathematical pieces of art” — some derived from my own research, others widely recognized in the scientific literature.

💡✨ While these visualizations are rooted in rigorous mathematics and computational models, their artistic appeal transcends science. Each image captures the elegance of fractals, attractors, wave interactions, and bifurcations, revealing the hidden beauty of complex systems.

🔍✨ Explore, zoom in, and immerse yourself in the wonders of nonlinear mathematics. Whether you're a scientist, an artist, or simply an admirer of beauty, I invite you to see how math becomes art. Discover the elegance of chaos. Witness order emerging from randomness.

🖼️ Enjoy the gallery!

---

<div class="gallery-container">
  {% for art in site.NonlinearArt %}
  <div class="gallery-item">
    <table style="width: 100%; border-collapse: collapse; table-layout: fixed;">
      <tr>
        <!-- Thumbnail (Left) -->
        <td style="width: 120px; height: 100px; text-align: left; vertical-align: middle; padding-right: 15px;">
          <a href="{{ art.images[0] }}" data-lightbox="{{ art.title }}" data-title="{{ art.title }}">
            <img src="{{ art.images }}" alt="{{ Image }}" style="width: 120px; height: auto; max-height: 100px; border-radius: 4px; cursor: pointer;">
          </a>
        </td>
        
        <!-- Description (Right) -->
        <td style="text-align: left; vertical-align: middle;">
          <p><strong>{{ art.title }}</strong> - {{ art.description }}</p>
          <p><small>📖 <a href="{{ art.reference }}" target="_blank">Reference</a></small></p>

          <!-- Hidden additional images for gallery effect -->
          {% for img in art.images offset:1 %}
          <a href="{{ img }}" data-lightbox="{{ art.title }}" data-title="{{ art.title }}" style="display: none;"></a>
          {% endfor %}
        </td>
      </tr>
    </table>
  </div>
  {% endfor %}
</div>


---


