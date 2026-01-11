---
layout: page
title: Inicio
---

<style>
    @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Lato:wght@300;400;700&display=swap');

    body { font-family: 'Lato', sans-serif; background-color: #fcfcfc; }
    h1, h2, h3, .card-title { font-family: 'Playfair Display', serif; }

    .hero-header {
        background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), url('{{ site.baseurl }}/objects/coll002.jpg');
        background-size: cover;
        background-position: center;
        color: white;
        padding: 7rem 1rem;
        margin-bottom: 3rem;
        border-radius: 0 0 20px 20px;
    }

    /* Píldoras de categorías */
    .pill-cat {
        border-radius: 50px;
        padding: 8px 25px;
        margin: 5px;
        text-transform: uppercase;
        font-size: 0.75rem;
        letter-spacing: 1px;
        font-weight: 700;
        transition: 0.3s;
        border: 1px solid #333;
        color: #333;
    }
    .pill-cat:hover { background: #333; color: white; text-decoration: none; }

    /* Tarjeta estilo libro (4 por fila) */
    .book-card {
        border: none;
        background: transparent;
        transition: transform 0.4s ease;
        height: 100%;
    }
    .book-card:hover { transform: translateY(-10px); }

    .book-img-container {
        height: 380px; 
        box-shadow: 0 10px 20px rgba(0,0,0,0.15);
        border-radius: 4px;
        overflow: hidden;
        margin-bottom: 15px;
    }
    .book-img-top { width: 100%; height: 100%; object-fit: cover; }
</style>

<div class="hero-header text-center mt-n4">
    <div class="container">
        <h1 class="display-3 font-weight-bold">CABARI</h1>
        <p class="lead mb-4" style="letter-spacing: 2px;">BIBLIOTECA VIRTUAL</p>
        <a href="{{ site.baseurl }}/browse.html" class="btn btn-outline-light btn-lg px-5" style="border-radius: 50px;">Entrar al Catálogo</a>
    </div>
</div>

<div class="container mb-5 text-center">
    <h2 class="mb-4 h4 text-uppercase" style="letter-spacing: 3px;">Explorar Categorías</h2>
    <div class="d-flex flex-wrap justify-content-center mb-5">
        <a href="{{ site.baseurl }}/browse.html#Fantasía" class="pill-cat">Fantasía</a>
        <a href="{{ site.baseurl }}/browse.html#Clásico" class="pill-cat">Clásicos</a>
        <a href="{{ site.baseurl }}/browse.html#Romance" class="pill-cat">Romance</a>
        <a href="{{ site.baseurl }}/browse.html#Misterio" class="pill-cat">Misterio</a>
        <a href="{{ site.baseurl }}/browse.html#No Ficción" class="pill-cat">No Ficción</a>
        <a href="{{ site.baseurl }}/browse.html#Juvenil" class="pill-cat">Juvenil</a>
    </div>
    <hr style="width: 50px; border-top: 2px solid #000;">
</div>

<div class="container">
    <div class="row">
        {% assign items = site.data[site.metadata] %}
        {% for item in items limit:12 %}
        <div class="col-lg-3 col-md-6 col-sm-6 mb-5">
            <div class="book-card text-center">
                <a href="{{ site.baseurl }}/items/{{ item.objectid }}.html">
                    <div class="book-img-container">
                        <img class="book-img-top" src="{{ site.baseurl }}/objects/{{ item.objectid }}.jpg" alt="{{ item.title }}">
                    </div>
                </a>
                <h5 class="card-title h6 mb-1">{{ item.title }}</h5>
                <p class="small text-muted mb-0" style="font-style: italic;">{{ item.creator }}</p>
            </div>
        </div>
        {% endfor %}
    </div>
    
    <div class="text-center mt-4 mb-5">
        <a href="{{ site.baseurl }}/browse.html" class="btn btn-dark px-5 py-3" style="border-radius: 50px; font-size: 0.8rem; letter-spacing: 2px;">VER TODO EL CATÁLOGO</a>
    </div>
</div>