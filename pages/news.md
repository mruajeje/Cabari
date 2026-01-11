---
layout: page
title: Noticias y Reseñas
permalink: /news.html
---

<div class="container mt-4">
    <p class="lead text-center">Críticas literarias y novedades de la colección <strong>CABARI</strong>.</p>
    
    <div class="row mt-5">
        {% assign posts_ordenados = site.posts | sort: 'date' | reverse %}
        {% for post in posts_ordenados %}
        <div class="col-md-4 mb-4">
            <div class="card h-100 shadow-sm border-0">
                {% if post.image %}
                <div style="height: 200px; overflow: hidden;">
                    <img src="{{ post.image | relative_url }}" class="card-img-top" style="height: 100%; object-fit: cover;" alt="{{ post.title }}">
                </div>
                {% endif %}
                <div class="card-body d-flex flex-column">
                    <h2 class="h5 card-title font-weight-bold">{{ post.title }}</h2>
                    <p class="small text-muted mb-3">Por {{ post.author }} | {{ post.date | date: "%d/%m/%Y" }}</p>
                    <p class="card-text small">{{ post.excerpt | strip_html | truncatewords: 15 }}</p>
                    <div class="mt-auto">
                        <a href="{{ post.url | relative_url }}" class="btn btn-dark btn-sm btn-block">Leer reseña</a>
                    </div>
                </div>
            </div>
        </div>
        {% endfor %}
    </div>
</div>