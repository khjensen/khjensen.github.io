---
layout: page
title: Photo gallery
description: Photo gallery
img: assets/img/background.jpg
importance: 1
category: DTU
---
<div class="row row-cols-1 row-cols-md-3 g-4">
  {% for file in site.static_files %}
    {% if file.path contains 'assets/img/artwork/' %}
      {% if file.extname == '.jpg' or file.extname == '.jpeg' or file.extname == '.png' or file.extname == '.webp' %}
        <div class="col">
          <div class="card h-100 jekyll-thumbnail">
            <img src="{{ file.path | relative_url }}" class="card-img-top" alt="{{ file.basename }}" loading="lazy">
            <div class="card-body">
              <p class="card-text text-center text-muted">{{ file.basename | replace: '-', ' ' | replace: '_', ' ' }}</p>
            </div>
          </div>
        </div>
      {% endif %}
    {% endif %}
  {% endfor %}
</div>


