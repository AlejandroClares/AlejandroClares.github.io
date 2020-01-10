---
author: Alejandro
layout: default
title: CSS3 - Tutorial - Degradados y fondos
nombre: Degradados y fondos
---

# Degradados y fondos
## linear-gradient

Los degradados en CSS3 te permiten desplegar transiciones suavizadas entre dos o mas colores específicos.   
Para declarar un degradado lineal se debe definir al menos dos parads de colores. Las paradas de colores son los colores entre los cuales se quieren reproducir las transiciones suavizadas.   
También se puede fijar un punto de partida y direccion junto el efecto degradado.

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

#### Dirección del degradado

Podemos definir la dirección en la que se ejecuta el degradado. Los valores soportados son **left**, **right**, **top** y **bottom**. Tambien podemos hacer combinaciones para especificar la dirección, como por ejemplo **bottom right**.

``` css
    div {
        width: 400px;
        height: 100px;
        background: linear-gradient(left, red, yellow);
    }
```
<a href="assets/examples/21linear-gradient.html" target="_blank">Ejecutar código</a>

#### El ángulo del degradado

Como alternativa a las direcciones predefinidas, podemos controlar la dirección del degradado especificando un ángulo. El ángulo de degradado comienza de forma vertical, de abajo hacia arriba, este ángulo es **0deg**. Un degradado horizontal, de izquierda hacia la derecha son **90deg**

``` css
    div {
        width: 300px;
        height: 300px;
        border-radius: 150px;
        background: linear-gradient(90deg, red, yellow);
    }
```
<a href="assets/examples/22linear-gradient.html" target="_blank">Ejecutar código</a>

#### repeating-linear-gradient

La función **repeating-linear-gradient** nos permite repetir un degradado lineal.

``` css
    div {
        width: 300px;
        height: 300px;
        background: repeating-linear-gradient(red, yellow 50px);
    }
```
<a href="assets/examples/23linear-gradient.html" target="_blank">Ejecutar código</a>

## radial-gradient

El degradado **radial** se define por su centro y se deben definir al menos dos paradas.