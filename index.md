---
layout: index 
title: Inicio
---

{% include index/jumbotron.html title="Biblioteca Digital" subtitle="Explora nuestra colección de libros históricos" objectid="id_de_un_libro_ejemplo" %}

<div class="container mt-4">
  <p class="lead">Bienvenido a nuestro repositorio. Aquí encontrarás una selección curada de libros digitalizados, organizados por fecha, temática y autor. Utiliza el menú para navegar o busca un título específico.</p>
</div>

{% include index/carousel.html title="Libros Destacados" height=500 %}

{% include index/collection-links.html %}
