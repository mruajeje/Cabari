---
layout: page
title: Inicio
---

<style>
    @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Lato:wght@400;700&display=swap');
    body { font-family: 'Lato', sans-serif; }
    .book-card { border: none; transition: 0.3s; margin-bottom: 20px; }
    .book-img-container { height: 320px; overflow: hidden; box-shadow: 0 4px 10px rgba(0,0,0,0.1); }
    .book-img-top { width: 100%; height: 100%; object-fit: cover; }
    .pill-cat { border-radius: 50px; padding: 5px 15px; margin: 3px; border: 1px solid #333; color: #333; font-size: 0.7rem; font-weight: bold; text-transform: uppercase; }
</style>

<div class="text-center py-5 bg-dark text-white mb-5">
    <h1 class="display-3">CABARI</h1>
    <p class="lead">Biblioteca Virtual</p>
</div>

<div class="container text-center mb-5">
    <h2 class="h5 text-uppercase mb-3">Filtrar por Género</h2>
    <div class="d-flex flex-wrap justify-content-center">
        <a href="{{ site.baseurl }}/browse.html#Fantasía" class="pill-cat">Fantasía</a>
        <a href="{{ site.baseurl }}/browse.html#Clásico" class="pill-cat">Clásicos</a>
        <a href="{{ site.baseurl }}/browse.html#Romance" class="pill-cat">Romance</a>
        <a href="{{ site.baseurl }}/browse.html#Misterio" class="pill-cat">Misterio</a>
    </div>
</div>
<div class="container">
    <div class="row">
        {% assign items = site.data[site.metadata] %}
        {% for item in items limit:8 %}
        <div class="col-lg-3 col-md-4 col-sm-6 mb-4">
            <div class="book-card text-center">
                <a href="{{ '/item.html' | relative_url }}?id={{ item.objectid }}">
                    <div class="book-img-container">
                        <img class="book-img-top shadow-sm" src="{{ '/objects/' | relative_url }}{{ item.objectid }}.jpg" alt="{{ item.title }}">
                    </div>
                </a>
                <h6 class="mt-2 font-weight-bold">{{ item.title }}</h6>
                <p class="small text-muted">{{ item.creator }}</p>
            </div>
        </div>
        {% endfor %}
    </div>
</div>