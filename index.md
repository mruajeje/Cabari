---
layout: index
title: Inicio
---

{% include index/jumbotron.html title=site.title subtitle=site.tagline objectid="coll001" %}

<div class="container mt-4">
    <div class="row">
        <div class="col-md-12 text-center">
            <h2 class="mt-4">Bienvenido a CABARI</h2>
            <p class="lead">Esta colección contiene 40 volúmenes digitalizados. Aquí podrás consultar documentos históricos, visualizar portadas y filtrar por fechas o temáticas.</p>
        </div>
    </div>
</div>

{% include index/carousel.html title="Muestra de la Colección" height=500 %}

{% include index/collection-links.html %}

{% include index/subjects.html title="Explorar por Temas" %}
