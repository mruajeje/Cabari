---
layout: page
title: Inicio
---

<style>
    /* Importamos fuentes elegantes */
    @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;1,400&family=Lato:wght@300;400;700&display=swap');

    body { font-family: 'Lato', sans-serif; background-color: #f8f9fa; }
    h1, h2, h3, .card-title { font-family: 'Playfair Display', serif; }

    /* BANNER PRINCIPAL: Ajustado para resaltar CABARI */
    .hero-header {
        background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('{{ site.baseurl }}/objects/coll002.jpg');
        background-size: cover;
        background-position: center;
        background-attachment: fixed; /* Efecto Parallax suave */
        color: white;
        padding: 8rem 1rem;
        margin-bottom: 4rem;
        clip-path: polygon(0 0, 100% 0, 100% 90%, 0 100%); /* Corte diagonal moderno */
    }

    /* SECCIÓN DE PROPÓSITOS (Vuestra Taxonomía) */
    .feature-box {
        background: white;
        padding: 2rem;
        border-radius: 15px;
        border-bottom: 5px solid #333;
        transition: 0.3s;
    }
    .feature-box:hover { transform: translateY(-5px); box-shadow: 0 10px 20px rgba(0,0,0,0.1); }

    /* MEJORA DE TARJETAS: Proporción tipo libro */
    .book-card {
        border: none;
        border-radius: 4px; /* Bordes más rectos para parecer un libro */
        background: #fff;
        box-shadow: 0 4px 6px rgba(0,0,0,0.05);
        transition: all 0.4s cubic-bezier(0.165, 0.84, 0.44, 1);
        height: 100%;
        overflow: hidden;
    }

    .book-card:hover {
        transform: scale(1.03);
        box-shadow: 0 15px 30px rgba(0,0,0,0.2);
    }

    .book-img-container {
        height: 380px; /* Altura mayor para que las portadas no se vean chatas */
        overflow: hidden;
        background-color: #e9ecef;
    }

    .book-img-top {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .btn-aesthetic {
        background: #222;
        color: white;
        border-radius: 0; /* Botón cuadrado elegante */
        padding: 12px 40px;
        font-size: 0.8rem;
        letter-spacing: 2px;
        transition: 0.3s;
        border: 1px solid #222;
    }
    .btn-aesthetic:hover { background: transparent; color: #222; }
</style>

<div class="hero-header text-center mt-n4">
    <div class="container">
        <h1 class="display-2 font-weight-bold">CABARI</h1>
        <p class="lead mb-4" style="font-style: italic; opacity: 0.9;">
            "Biblioteca Virtual de impacto social y desarrollo personal" 
        </p>
        <a href="{{ site.baseurl }}/browse.html" class="btn btn-outline-light btn-lg px-5">Explorar el Catálogo</a>
    </div>
</div>

<div class="container mb-5">
    <div class="row justify-content-center text-center">
        <div class="col-md-10">
            <h2 class="display-4 mb-4">Literatura con Propósito</h2>
            <p class="lead text-muted">Diseñada para ofrecer contenido de alta demanda: desde ficción de evasión hasta no-ficción útil para tu crecimiento.</p>
        </div>
    </div>
    
<div class="row mt-5">
    <div class="col-md-6 mb-4">
        <div class="feature-box text-center">
            <h3 class="h2">Lectura de Utilidad</h3>
            <p>Obras de autoayuda, finanzas y psicología para tu desarrollo personal.</p>
            <a href="{{ site.baseurl }}/browse.html#UTILIDAD" class="btn btn-sm btn-dark mt-2">Ver libros de Utilidad</a>
        </div>
    </div>
    <div class="col-md-6 mb-4">
        <div class="feature-box text-center">
            <h3 class="h2">Lectura de Evasión</h3>
            <p>Sumérgete en mundos de fantasía, misterio y grandes clásicos de la literatura.</p>
            <a href="{{ site.baseurl }}/browse.html#EVASIÓN" class="btn btn-sm btn-dark mt-2">Ver libros de Evasión</a>
        </div>
    </div>
</div>
</div>

<div class="container mt-5">
    <h3 class="text-center mb-5 display-4">Nuestra Colección</h3>
    <div class="row">
        {% assign items = site.data[site.metadata] %}
        {% for item in items limit:8 %}
        <div class="col-lg-3 col-md-6 mb-5">
            <div class="book-card">
                <a href="{{ site.baseurl }}/items/{{ item.objectid }}.html">
                    <div class="book-img-container">
                        <img class="book-img-top" src="{{ site.baseurl }}/objects/{{ item.objectid }}.jpg" alt="{{ item.title }}">
                    </div>
                </a>
                <div class="card-body p-4 text-center">
                    <h5 class="card-title mb-1" style="line-height: 1.2;">
                        <a href="{{ site.baseurl }}/items/{{ item.objectid }}.html" class="text-dark text-decoration-none">{{ item.title }}</a>
                    </h5>
                    <p class="text-muted small mb-0">{{ item.creator }}</p>
                    <hr style="width: 30px; border-top: 2px solid #ddd;">
                    <p class="badge badge-light text-uppercase" style="font-size: 0.6rem; letter-spacing: 1px;">{{ item.proposito }}</p>
                </div>
            </div>
        </div>
        {% endfor %}
    </div>
    
    <div class="text-center mt-4 mb-5">
        <a href="{{ site.baseurl }}/browse.html" class="btn btn-aesthetic">Explorar los 40 volúmenes</a>
    </div>
</div>