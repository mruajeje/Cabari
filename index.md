---
layout: default
title: Inicio
---

<style>
    /* Importamos fuentes elegantes de Google */
    @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Lato:wght@300;400;700&display=swap');

    body {
        font-family: 'Lato', sans-serif;
        background-color: #fdfdfd;
    }

    h1, h2, h3, .card-title {
        font-family: 'Playfair Display', serif; /* Letra tipo libro antiguo para títulos */
    }

    /* ESTILO DEL BANNER PRINCIPAL */
    .hero-header {
        /* Aquí elegimos la foto de fondo. He puesto coll002 (El nombre del viento) */
        /* Puedes cambiar 'coll002' por el ID del libro que más te guste para la portada */
        background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), url('{{ site.baseurl }}/objects/coll002.jpg');
        background-size: cover;
        background-position: center;
        color: white;
        padding: 6rem 1rem;
        margin-bottom: 3rem;
        border-radius: 0 0 15px 15px;
        box-shadow: 0 4px 15px rgba(0,0,0,0.2);
    }

    /* ESTILO DE LAS TARJETAS DE LIBROS */
    .book-card {
        border: none;
        border-radius: 8px;
        background: #fff;
        box-shadow: 0 2px 10px rgba(0,0,0,0.05); /* Sombra suave */
        transition: transform 0.3s ease, box-shadow 0.3s ease;
        height: 100%;
        overflow: hidden;
    }

    /* Efecto al pasar el ratón */
    .book-card:hover {
        transform: translateY(-8px); /* Se mueve hacia arriba */
        box-shadow: 0 12px 20px rgba(0,0,0,0.15); /* Sombra más fuerte */
    }

    .book-img-container {
        height: 150px; /* Altura fija para que todas las portadas se vean iguales */
        overflow: hidden;
        background-color: #f0f0f0;
        position: relative;
    }

    .book-img-top {
        width: 100%;
        height: 100%;
        object-fit: cover; /* Recorta la imagen perfectamente */
        transition: transform 0.5s ease;
    }

    .book-card:hover .book-img-top {
        transform: scale(1.05); /* Zoom suave en la foto */
    }

    .btn-aesthetic {
        background-color: #333;
        color: white;
        border-radius: 50px;
        padding: 10px 30px;
        text-transform: uppercase;
        letter-spacing: 1px;
        font-size: 0.9rem;
        transition: background 0.3s;
    }
    .btn-aesthetic:hover {
        background-color: #000;
        text-decoration: none;
        color: white;
    }
</style>

<div class="hero-header text-center">
    <div class="container">
        <h1 class="display-3 font-weight-bold">{{ site.title }}</h1>
        <p class="lead mb-4" style="font-size: 1.4rem; font-weight: 300; opacity: 0.9;">{{ site.tagline }}</p>
        <a href="{{ site.baseurl }}/browse.html" class="btn btn-outline-light btn-lg mt-2" style="border-radius: 50px; padding: 10px 30px;">Explorar Libros</a>
    </div>
</div>

<div class="container mb-5">
    <div class="row justify-content-center">
        <div class="col-md-8 text-center">
            <h2 class="mb-3 text-dark">Bienvenido a la Colección</h2>
            <p class="text-muted">Un espacio digital dedicado a la literatura. Navega a través de clásicos universales, fantasía moderna y obras contemporáneas.</p>
            <hr class="my-4" style="width: 60px; border-top: 3px solid #333; margin: 0 auto;">
        </div>
    </div>
</div>

<div class="container">
    <div class="row">
        {% assign items = site.data[site.metadata] %}
        {% for item in items limit:8 %}
        <div class="col-lg-3 col-md-4 col-sm-6 mb-5">
            <div class="book-card">
                <a href="{{ site.baseurl }}/items/{{ item.objectid }}.html">
                    <div class="book-img-container">
                        <img class="book-img-top" src="{{ site.baseurl }}/objects/{{ item.objectid }}.jpg" alt="{{ item.title }}">
                    </div>
                </a>
                <div class="card-body text-center p-3">
                    <h5 class="card-title mb-1" style="font-size: 1.1rem;">
                        <a href="{{ site.baseurl }}/items/{{ item.objectid }}.html" class="text-dark text-decoration-none">{{ item.title }}</a>
                    </h5>
                    <p class="text-muted small mb-2 text-uppercase" style="letter-spacing: 1px; font-size: 0.75rem;">{{ item.creator }}</p>
                </div>
            </div>
        </div>
        {% endfor %}
    </div>
    
    <div class="text-center mt-2 mb-5">
        <a href="{{ site.baseurl }}/browse.html" class="btn btn-aesthetic shadow">Ver Colección Completa</a>
    </div>
</div>