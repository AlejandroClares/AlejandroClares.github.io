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

La sintaxis css del degradado radial se ve así: radial-gradient(*forma* *tamaño* at *posicion*, *color*, ...)
- **Forma** (Opcional): Se puede definir como un circulo o un ellipse (por defecto)
- **Tamaño** (Opcional): Puede ser *farthest-corner* (por defecto), *closest-side*, *closest-corner*, *farthest-side*. Tambien se pueden usar valores numéricos, como pixeles o em
- **Posición**: Se usan dos valores porcentuales o valores predefinidos como *top* o *right* para definir la posición, por defecto es *center*. El primer valor porcentual define la posición horizontal, siendo 0% izquierda y 100% derecha. El segundo valor define la posición vertical, siendo 0% arriba y 100% abajo.

``` css
    div {
        width: 300px;
        height: 300px;
        background: radial-gradient(circle farthest-side at 20% 50%, gray, blue,
                    brown, orange, yellow);
    }
```
<a href="assets/examples/24radial-gradient.html" target="_blank">Ejecutar código</a>

## background-size

La propiedad **background-size** permite especificar el tamaño de las imagenes de fondo utilizando longitudes o porcentajes.

``` css
    #original {
        float: left;
        width: 425px;
        height: 450px;
        border: 1px solid black;
        background: url('../image/css3.png') no-repeat 50% 50%;
    }
    #bg-size {
        float: left;
        width: 425px;
        height: 450px;
        border: 1px solid black;
        background: url('../image/css3.png') no-repeat 50% 50%;
        background-size: 100px 100px;
    }
```
<a href="assets/examples/25background-size.html" target="_blank">Ejecutar código</a>

Otros dos valores posibles para el tamaño de fondo son las palabras clave **"contain"** y **"cover"**.   

#### El valor contain

El valor **contain** escala la imagen de manera que se ajuste al contenedor, es decir, la imagen crecerá o encogerá proporcionalmente sin exceder las dimensiones del contenedor

``` css
    #original {
        float: left;
        width: 200px;
        height: 200px;
        border: 1px solid black;
        background: url('../image/css3.png') no-repeat 50% 50%;
    }
    #contain {
        float: left;
        width: 200px;
        height: 200px;
        border: 1px solid black;
        background: url('../image/css3.png') no-repeat 50% 50%;
        background-size: contain;
    }
```
<a href="assets/examples/26background-size.html" target="_blank">Ejecutar código</a>

#### El valor cover

Usando el valor **cover** la imagen se escala al mayor tamaño posible sin estirarla. La imagen podrá ser recortada vertical u horizontalmente si el tamaño difiere con el contenedor.
``` css
    #contain {
        float: left;
        width: 200px;
        height: 200px;
        border: 1px solid black;
        background: url('../image/css3.png') no-repeat 50% 50%;
        background-size: contain;
    }
    #cover {
        float: left;
        width: 200px;
        height: 200px;
        border: 1px solid black;
        background: url('../image/css3.png') no-repeat 50% 50%;
        background-size: cover;
    }
```
<a href="assets/examples/27background-size.html" target="_blank">Ejecutar código</a>

## background-clip

La propiedad **background-clip** especifíca el área de dibujo del fondo. Acepta tres valores:

- **border-box** (predeterminado): El fondo es dibujado hasta el exterior del borde.
- **padding-box**: El fondo es dibujado hasta el extremo exterior del relleno.
- **content-box**: El fondo es dibujado dentro de la caja contenedora.

``` css
    p {
        border: 5px navy;
        border-style: dotted double;
        margin: 2em;
        padding: 2em;
        background: orange;
    }
    .border-box { background-clip: border-box; }
    .padding-box { background-clip: padding-box; }
    .content-box { background-clip: content-box; }
```
<a href="assets/examples/28background-clip.html" target="_blank">Ejecutar código</a>

#### Bordes transparentes

Establecer un borde transparente sobre un elemento revelará el propio fondo del elemento bajo el borde. Al fijar la propiedad **background-clip** a **padding-box**, los bordes serán hechos transparentes.

``` css
    .original {
       border: 20px solid rgba(255, 0, 0, 0.3);
       width: 300px;
       position: absolute;
       top: 20px;
       left: 10%;
       background-color: yellow;
    }
    .padding-box {
       border: 20px solid rgba(255, 0, 0, 0.3);
       width: 300px;
       position: absolute;
       top: 20px;
       left: 50%;
       background-color: yellow;
       background-clip: padding-box;
    }
```
<a href="assets/examples/29background-clip.html" target="_blank">Ejecutar código</a>

## Múltiples fondos

Múltiples imágenes de fondo pueden ser especificadas en la propiedad **background-image**. La primera imagen se coloca encima de la segunda.

``` css
    div {
        width: 680px;
        height: 330px;
        background-image: url('../image/css3-logo.png'), url('../image/code.jpg');
        background-position: right bottom, left top;
        background-repeat: no-repeat;
    }
```
Tambien podemos usar la propiedad abreviada **background**.
``` css
    div {
        width: 680px;
        height: 330px;
        background: url('../image/css3-logo.png') no-repeat right bottom,
                    url('../image/code.jpg') no-repeat left top;
    }
```
<a href="assets/examples/30multiples-fondos.html" target="_blank">Ejecutar código</a>

## Opacity

La propiedad **opacity** permite añadir opacidad a cualquier elemento.
``` css
    .img {
        width: 200px;
        height: 200px;
        background: url('../image/css3-logo.png') no-repeat;
        opacity: 0.3;
        float: left;
    }
    .text {
        width: 400px;        
        opacity: 0.3;
        float: left;
    }
```
<a href="assets/examples/31opacity.html" target="_blank">Ejecutar código</a>