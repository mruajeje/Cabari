---
title: Browse
layout: browse
permalink: /browse.html
# see _data/config-browse.csv for display options
# the Browse visualization will be added below the content in this file
---

<style>
    /* Forzar 4 columnas en el Catálogo CABARI */
    @media (min-width: 992px) {
        #browse-items .item {
            flex: 0 0 25% !important; /* Cada libro ocupa el 25% del ancho */
            max-width: 25% !important;
            padding: 15px !important;
        }
    }

    /* Ajustar las imágenes para que quepan bien 4 por fila */
    #browse-items .card-img-top {
        height: 200px !important; /* Altura reducida para mantener la proporción */
        object-fit: contain !important; /* No recorta la imagen */
        background-color: #f8f9fa;
        padding: 10px;
    }

    /* Igualar el tamaño de las tarjetas */
    #browse-items .card {
        height: 100% !important;
        border: 1px solid rgba(0,0,0,.125);
        transition: transform 0.2s;
    }

    #browse-items .card:hover {
        transform: scale(1.02);
        box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    }
</style>
