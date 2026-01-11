---
title: Browse
layout: browse
permalink: /browse.html
# see _data/config-browse.csv for display options
# the Browse visualization will be added below the content in this file
---

<style>
    /* Forzar 4 columnas en pantallas grandes */
    @media (min-width: 992px) {
        #browse-items .item {
            flex: 0 0 25% !important;
            max-width: 25% !important;
            padding: 10px !important;
        }
    }
    /* Hacer las imágenes más pequeñas para que quepan bien las 4 */
    #browse-items .card-img-top {
        height: 220px !important;
        object-fit: contain !important;
    }
    /* Estilo para que todas las tarjetas midan lo mismo */
    #browse-items .card {
        height: 100% !important;
    }
</style>
