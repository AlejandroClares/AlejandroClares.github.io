---
author: Alejandro
layout: default
title: CSS3 - Tutorial - Conceptos básicos
nombre: Conceptos básicos
---

# Conceptos básicos
## Prefijos de navegación

Son una forma en la que los fabricantes de navegadores añaden soporte a las nuevas características de css en periodos de prueba o experimentación.

Por ejemplo, el prefijo de Safari y Chrome es -webkit-. 
``` css 
    .cuadrado {
        -webkit-border-radius: 10px;
    }
```
La mayoría de navegadores de hoy en día funcionan sin prefijos, pero es esencial conocerlos para la compatibilidad y entendimiento de códigos antiguos.

Escribir varias veces las propiedades para que funcionen en diferentes navegadores puede ser molesto pero es temporal. Mientras los navegadores mejoran, añadirán soporte a las propiedades y eliminaran los prefijos.

![Prefijos de navegador](assets/image/prefijosCSS3.jpg)

<hr>

##  border-radius
Podemos darle esquinas redondeadas a cualquier elemento.
``` css
    .cuadrado{
        width: 200px;
        height: 200px;
        background-color: orangered;
        border-radius: 50px;
    }
```

<a href="assets/examples/00border.html" target="_blank">Ejecutar código</a>

Podemos especificar el radio de cada esquina en orden: superior-izquierdo, superior-derecho, inferior-derecho, inferior-izquierdo.

``` css
    .cuadrado{
        width: 200px;
        height: 200px;
        background-color: orangered;
        border-radius: 0 0 0 50px;
    }
```
<a href="assets/examples/01border.html" target="_blank">Ejecutar código</a>

Una caja puede ser convertida en un círculo solo usando CSS. El radio debe ser la mitad del ancho y alto de la caja.
``` css
    .circulo {
        width: 200px;
        height: 200px;
        border-radius: 100px;
    }
```
<a href="assets/examples/02border.html" target="_blank">Ejecutar código</a>
