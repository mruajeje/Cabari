---
layout: default
title: Inicio
---

<div class="jumbotron p-3 p-md-5 text-white rounded bg-dark" style="background-image: url('{{ site.baseurl }}/objects/coll001.jpg'); background-size: cover; background-position: center;">
    <div class="col-md-6 px-0" style="background: rgba(0,0,0,0.6); padding: 20px; border-radius: 5px;">
        <h1 class="display-4 font-italic">{{ site.title }}</h1>
        <p class="lead my-3">{{ site.tagline }}</p>
    </div>
</div>

<div class="container mt-4">
    <div class="row">
        <div class="col-md-12 text-center">
            <h2>Bienvenido al Repositorio</h2>
            <p class="lead">Explora nuestra colección de libros digitalizados.</p>
            <hr>
        </div>
    </div>
</div>

<div class="container">
    <h3 class="text-center mb-4">Libros Destacados</h3>
    <div class="row">
        {% assign items = site.data[site.metadata] %}
        {% for item in items limit:4 %}
        <div class="col-md-3 col-sm-6 mb-4">
            <div class="card h-100">
                <a href="{{ site.baseurl }}/items/{{ item.objectid }}.html">
                    <img class="card-img-top" src="{{ site.baseurl }}/objects/{{ item.objectid }}.jpg" alt="{{ item.title }}" style="object-fit: cover; height: 200px;">
                </a>
                <div class="card-body">
                    <h5 class="card-title">
                        <a href="{{ site.baseurl }}/items/{{ item.objectid }}.html" class="text-dark">{{ item.title }}</a>
                    </h5>
                    <p class="card-text small">{{ item.date }}</p>
                </div>
            </div>
        </div>
        {% endfor %}
    </div>
</div>

<div class="container text-center mt-5 mb-5">
    <a href="{{ site.baseurl }}/browse.html" class="btn btn-primary btn-lg">Ver Colección Completa</a>
</div>
