---
layout: page
permalink: /artwork/
title: artwork
description:
horizontal: false
nav: true
---

<div class="artwork">
    {% assign sorted_artwork = site.artwork | sort: "importance" %}
    <!-- Generate cards for each piece -->
    {% if page.horizontal %}
      <div class="container">
        <div class="row row-cols-2">
        {% for artpiece in sorted_artwork %}
          {% include projects_horizontal.html %}
        {% endfor %}
        </div>
      </div>
    {% else %}
      <div class="grid">
        {% for artpiece in sorted_artwork %}
          {% include artpiece.html %}
        {% endfor %}
      </div>
    {% endif %}
</div>
