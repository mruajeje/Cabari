---
layout: page
title: Noticias y Reseñas
permalink: /news.html
---

<div class="container mt-4">
    <p class="lead">Bienvenidos a la sección de actualidad de <strong>CABARI</strong>. En este espacio, nuestro equipo comparte análisis profundos y reseñas detalladas sobre las obras que forman nuestra colección.</p>
    
    <hr class="my-5">

    <div class="row">
        {% for post in site.posts %}
        <div class="col-md-6 mb-4">
            <div class="card h-100 shadow-sm">
                {% if post.image %}
                <img src="{{ post.image | relative_url }}" class="card-img-top" style="height: 250px; object-fit: cover;" alt="{{ post.title }}">
                {% endif %}
                <div class="card-body">
                    <h2 class="h4 card-title">{{ post.title }}</h2>
                    <p class="card-text text-muted small">Por {{ post.author }} | {{ post.date | date: "%d/%m/%Y" }}</p>
                    <p class="card-text">{{ post.excerpt | strip_html | truncatewords: 25 }}</p>
                    <a href="{{ post.url | relative_url }}" class="btn btn-dark btn-sm">Leer reseña completa</a>
                </div>
            </div>
        </div>
        {% endfor %}
    </div>
</div>