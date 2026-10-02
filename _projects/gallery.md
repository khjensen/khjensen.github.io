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


<div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 g-4">
  {% assign image_id = 0 %}
  {% for file in site.static_files %}
    {% if file.path contains 'assets/img/my-project-gallery/' %}
      {% if file.extname == '.jpg' or file.extname == '.jpeg' or file.extname == '.png' or file.extname == '.webp' %}
        {% assign image_id = image_id | plus: 1 %}
        <div class="col">
          <div class="card h-100 shadow-sm border-0">
            <!-- Clickable Link triggering the Bootstrap Modal -->
            <a href="#" data-toggle="modal" data-target="#imageModal{{ image_id }}">
              <div class="img-wrapper" style="height: 200px; overflow: hidden;">
                <img src="{{ file.path | relative_url }}" 
                     class="card-img-top w-100 h-100" 
                     style="object-fit: cover;" 
                     alt="{{ file.basename }}" 
                     loading="lazy">
              </div>
            </a>
            <div class="card-body py-2">
              <p class="card-text text-center text-muted small mb-0">
                {{ file.basename | replace: '-', ' ' | replace: '_', ' ' }}
              </p>
            </div>
          </div>
        </div>

        <!-- 2. Dynamic Modal popup for each individual image -->
        <div class="modal fade" id="imageModal{{ image_id }}" tabindex="-1" role="dialog" aria-hidden="true">
          <div class="modal-dialog modal-dialog-centered modal-lg" role="document">
            <div class="modal-content bg-transparent border-0 text-right">
              <button type="button" class="close text-white mb-2" data-dismiss="modal" aria-label="Close" style="font-size: 2rem; outline: none; opacity: 0.8;">
                <span aria-hidden="true">&times;</span>
              </button>
              <img src="{{ file.path | relative_url }}" class="img-fluid rounded mx-auto d-block" alt="{{ file.basename }}">
            </div>
          </div>
        </div>

      {% endif %}
    {% endif %}
  {% endfor %}
</div>
