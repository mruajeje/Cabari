---
layout: page
title: Noticias y Reseñas
permalink: /news.html
---

<div class="container mt-4">
    <p>Bienvenidos a la sección de actualidad de <strong>CABARI</strong>.</p>
    
    <div class="row mt-5">
        {% for post in site.posts %}
        <div class="col-md-6 mb-4">
            <div class="card shadow-sm">
                {% if post.image %}
                <img src="{{ post.image | relative_url }}" class="card-img-top" style="height: 200px; object-fit: cover;">
                {% endif %}
                <div class="card-body">
                    <h2 class="h5">{{ post.title }}</h2>
                    <p class="small text-muted">Por {{ post.author }}</p>
                    <a href="{{ post.url | relative_url }}" class="btn btn-dark btn-sm">Leer más</a>
                </div>
            </div>
        </div>
        {% endfor %}
    </div>
</div>