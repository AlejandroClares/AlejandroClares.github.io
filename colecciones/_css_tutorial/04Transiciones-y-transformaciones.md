---
author: Alejandro
layout: default
title: CSS3 - Tutorial - Transiciones y transformaciones
nombre: Transiciones y transformaciones
---

# Transiciones y transformaciones

## transition

La propiedad **transition** permite definir la transición entre dos estados de un elemento. Hay diferentes estados, que pueden ser definidos utilizando <a href="https://developer.mozilla.org/es/docs/Web/CSS/Pseudo-classes#Indice_de_las_pseudo-clases_est%C3%A1ndar" target="_blank">**pseudo-clases**</a>.

- **transition-property**: Especifica la propiedad a ser transicionada.
- **transition-duration**: Duración de la transición.
- **transition-timing-function**: Especifica cómo el ritmo de la transición cambia sobre su duración.
- **transition-delay**: Especifica un retraso para el efecto de la transición.

Estas propiedades tambien pueden ser abreviadas usando la propiedad **transition**, siguiendo el orden anterior.

``` css
    div {
        width: 20%;
        height: 20%;
        background-color: orangered;
        transition-property: width;
        transition-duration: 3s;
    }
    div:hover {
        width: 100%;
    }
```
<a href="assets/examples/32transition.html" target="_blank">Ejecutar código</a>

#### transition-timing-function

Especifica la curva de velocidad del efecto de transición.

- **ease** (predeterminado): La animación comienza con lentitud, luego acelerará rápidamente.
- **ease-in**: Comienza lentamente, luego acelera y se detiene bruscamente.
- **ease-out**: Comienza rápidamente y desacelera hasta detenerse.
- **ease-in-out**: Similar a ease, pero con aceleración y desaceleración más sutil.
- **linear**: Velocidad constante a través de la animación. 
- **cubic-beizer**: Permite definir nuestros propios valores. cubic-beizer(0, 0, 0, 0).

``` css
    div {
        width: 20%;
        height: 20%;
        background-color: orangered;
        transition-property: width;
        transition-duration: 3s;
        transition-timing-function: ease-in;
    }
    div:hover {
        width: 100%;
    }
```
<a href="assets/examples/33transition.html" target="_blank">Ejecutar código</a>

Para entender mejor el funcionamiento de **cubic-beizer** podemos visitar <a href="https://cubic-bezier.com" target="_blank">cubic-beizer.com</a>.


## transform

Una transformación es un efecto que permite a un elemento cambiar su forma, tamaño y posición.

#### rotate

El método **rotate()** rota un elemento en sentido de las agujas del reloj o en sentido contrario si se usan valores negativos.

``` css
    div {
        width: 300px;
        height: 100px;
        position: absolute;
        top: 100px;
        left: 100px;
        background-color: orangered;
        transform: rotate(20deg);
    }
```
<a href="assets/examples/34transform.html" target="_blank">Ejecutar código</a>

#### transform-origin

La propiedad **transform-origin** permite cambiar la posición de los **elementos transformados**. El valor por defecto es 50% (horizontal) 50% (vertical) que corresponde al centro del elemento.
``` css
    .transform-origin {
        width: 300px;
        height: 100px;
        position: absolute;
        top: 100px;
        left: 100px;
        background-color: orangered;
        transform-origin: 0% 50%;
        transform: rotate(5deg);
    }
```
<a href="assets/examples/35transform.html" target="_blank">Ejecutar código</a>

#### translate

El método **translate()** mueve un elemento desde su posición actual. Los valores positivos mueven el elemento hacia la derecha y hacia abajo, mientras que los valores negativos lo mueven hacia la izquierda y hacia arriba.
``` css
    .translate {
        width: 300px;
        height: 100px;
        position: absolute;
        top: 100px;
        left: 100px;
        background-color: orangered;
        transform: translate(100px, 50px);
    }
```
<a href="assets/examples/36transform.html" target="_blank">Ejecutar código</a>

#### skew

Sesga un elemento a lo largo del eje-x y eje-y. El segundo parámetro es opcional y por defecto será 0.
``` css
    .transform {
        width: 300px;
        height: 100px;
        position: absolute;
        top: 100px;
        left: 100px;
        background-color: orangered;
        transform: skew(30deg);
    }
```
<a href="assets/examples/37transform.html" target="_blank">Ejecutar código</a>

#### scale

El método **scale()** aumenta o reduce el tamaño de un elemento de acuerdo a dos parámetros para el ancho y el alto. El valor 1 equivale al tamaño normal, 2 para el doble del tamaño y asi sucesivamente. Si solo se pasa un parámetro, este se aplicará tanto para el ancho como el alto.

``` css
    .transform {
        width: 300px;
        height: 100px;
        position: absolute;
        top: 100px;
        left: 100px;
        background-color: orangered;
        transform: scale(0.7);
    }
``` 

<a href="assets/examples/38transform.html" target="_blank">Ejecutar código</a>

#### Múltiples transformaciones

Se pueden aplicar varias transformaciones al mismo tiempo, basta con separarlas con un espacio

<a href="assets/examples/39transform.html" target="_blank">Ejecutar código</a>