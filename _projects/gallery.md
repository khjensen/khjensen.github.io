---
layout: page
title: Photo gallery
description: Photo gallery
img: assets/img/background.jpg
importance: 1
category: work
---

<div class="row row-cols-1 row-cols-md-3 g-4">
  {% for file in site.static_files %}
    {% if file.path contains 'assets/img/dit-projekt-navn' %}
      {% if file.extname == '.jpg' or file.extname == '.jpeg' or file.extname == '.png' or file.extname == '.gif' %}
        <div class="col">
          <div class="card h-100 z-depth-1 rounded">
            <img class="card-img-top img-fluid" src="{{ file.path | relative_url }}" alt="{{ file.basename }}">
            <div class="card-body py-2">
              <p class="card-text text-center text-muted small">{{ file.basename }}</p>
            </div>
          </div>
        </div>
      {% endif %}
    {% endif %}
  {% endfor %}
</div>
