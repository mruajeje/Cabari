---
layout: page
title: Inicio
---

<style>
    
    @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Lato:wght@300;400;700&display=swap');

    body { font-family: 'Lato', sans-serif; background-color: #f8f9fa; }
    h1, h2, h3, .card-title { font-family: 'Playfair Display', serif; }

    .hero-header {
        background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('{{ site.baseurl }}/objects/coll002.jpg');
        background-size: cover;
        background-position: center;
        color: white;
        padding: 6rem 1rem;
        margin-bottom: 3rem;
        clip-path: polygon(0 0, 100% 0, 100% 90%, 0 100%);
    }

    /* Ajuste de tarjetas para 4 por fila */
    .book-card {
        border: none;
        border-radius: 4px;
        background: #fff;
        box-shadow: 0 4px 6px rgba(0,0,0,0.05);
        transition: transform 0.3s ease;
        height: 100%;
    }
    .book-card:hover { transform: translateY(-5px); box-shadow: 0 10px 20px rgba(0,0,0,0.1); }

    .book-img-container {
        height: 350px; /* Altura optimizada para 4 columnas */
        overflow: hidden;
    }
    .book-img-top { width: 100%; height: 100%; object-fit: cover; }
</style>

<div class="hero-header text-center mt-n4">
    <div class="container">
        <h1 class="display-3 font-weight-bold">CABARI</h1>
        <p class="lead mb-4">"Biblioteca Virtual: Literatura con Propósito"</p>
        <a href="{{ site.baseurl }}/browse.html" class="btn btn-outline-light btn-lg px-5">Explorar Catálogo</a>
    </div>
</div>

<div class="container mb-5">
    <div class="row">
        <div class="col-md-6 mb-3">
            <div class="p-4 bg-white shadow-sm text-center border-bottom border-dark">
                <h3>Lectura de Utilidad</h3>
                <p class="small text-muted">Autoayuda y formación personal.</p>
                <a href="{{ site.baseurl }}/browse.html#proposito=UTILIDAD" class="btn btn-dark btn-sm">Ver Utilidad</a>
            </div>
        </div>
        <div class="col-md-6 mb-3">
            <div class="p-4 bg-white shadow-sm text-center border-bottom border-dark">
                <h3>Lectura de Evasión</h3>
                <p class="small text-muted">Fantasía, misterio y clásicos.</p>
                <a href="{{ site.baseurl }}/browse.html#proposito=EVASIÓN" class="btn btn-dark btn-sm">Ver Evasión</a>
            </div>
        </div>
    </div>
</div>

<div class="container">
    <div class="row">
        {% assign items = site.data[site.metadata] %}
        {% for item in items limit:8 %}
        <div class="col-lg-3 col-md-6 col-sm-6 mb-5">
            <div class="book-card text-center">
                <a href="{{ site.baseurl }}/items/{{ item.objectid }}.html">
                    <div class="book-img-container">
                        <img class="book-img-top" src="{{ site.baseurl }}/objects/{{ item.objectid }}.jpg" alt="{{ item.title }}">
                    </div>
                </a>
                <div class="card-body p-3">
                    <h5 class="card-title h6 mb-1">{{ item.title }}</h5>
                    <p class="small text-muted mb-0">{{ item.creator }}</p>
                    <span class="badge badge-secondary small" style="font-size: 0.6rem;">{{ item.proposito }}</span>
                </div>
            </div>
        </div>
        {% endfor %}
    </div>
</div>