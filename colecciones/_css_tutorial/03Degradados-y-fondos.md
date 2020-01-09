---
author: Alejandro
layout: default
title: CSS3 - Tutorial - Degradados y fondos
nombre: Conceptos básicos
---

# Degradados y fondos
## Degradados lineales

Los degradados en CSS3 te permiten desplegar transiciones suavizadas entre dos o mas colores específicos. Para declarar un degradado lineal se debe definir al menos dos parads de colores. Las paradas de colores son los colores entre los cuales se quieren reproducir las transiciones suavizadas. También se puede fijar un punto de partida y direccion junto el efecto degradado.

``` css
    div {
        width: 400px;
        height: 100px;
        background: linear-gradient(red, yellow);
    }
```
<a href="assets/examples/18linear-gradient.html" target="_blank">Ejecutar código</a>

Se pueden utilizar nombres de colores, calores hexadecimales, colores RGB o HSL para definir el color del radiante.

#### Paradas de colores
Los colores pueden ser añadidos uno tras otros, separados por comas. El navegador determina la posición de cada color. Las paradas de colores se ejecutan de arriba a abajo.

``` css
    div {
        width: 400px;
        height: 100px;
        background: linear-gradient(red, yellow, blue, green, pink, black, white);
    }
```
<a href="assets/examples/19linear-gradient.html" target="_blank">Ejecutar código</a>

Las posiciones de las paradas de colores pueden ser especificadas en cada color. Si se utiliza la misma posición de parada para uno o más colores se creara una linea delgada entre ellos.

``` css
    div {
        width: 400px;
        height: 100px;
        background: linear-gradient(red 10%, yellow 50%, blue 50%);
    }
```
<a href="assets/examples/20linear-gradient.html" target="_blank">Ejecutar código</a>

Adicionalmente a los **porcentajes**, se puede utilizar **px**, **em** entre otros