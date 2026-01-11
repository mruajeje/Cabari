---
title: Browse
layout: browse
permalink: /browse.html
# see _data/config-browse.csv for display options
# the Browse visualization will be added below the content in this file
---
<style>
    /* SOLUCIÓN NUCLEAR: Forzar 4 columnas (25% de ancho) */
    @media (min-width: 992px) {
        /* Seleccionamos los contenedores de los libros dentro del catálogo */
        #browse-items .col-lg-4, 
        #browse-items .item {
            flex: 0 0 25% !important;
            max-width: 25% !important;
            padding: 10px !important;
        }
    }

    /* Reducir el tamaño de las fotos para que el diseño no se rompa al haber 4 */
    #browse-items .card-img-top {
        height: 180px !important;
        object-fit: contain !important;
        background-color: #ffffff;
    }

    /* Ajustar el texto del título para que quepa bien en columnas más estrechas */
    #browse-items .card-title {
        font-size: 0.85rem !important;
        height: 2.5rem;
        overflow: hidden;
    }
</style>