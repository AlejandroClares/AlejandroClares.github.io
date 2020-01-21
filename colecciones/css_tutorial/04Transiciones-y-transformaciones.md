---
author: Alejandro
layout: default
title: CSS3 - Tutorial - Transiciones y transformaciones
nombre: Transiciones y transformaciones
---

# Transiciones y transformaciones

### Menú de navegación

<ul>
    <li><a href="#transition">transition</a></li>
    <ul>
        <li><a href="#transition-timing-function">transition-timing-function</a></li>
    </ul>
    <li><a href="#transform">transform</a></li>
    <ul>
        <li><a href="#rotate">rotate</a></li>
        <li><a href="#transform-origin">transform-origin</a></li>
        <li><a href="#translate">translate</a></li>
        <li><a href="#skew">skew</a></li>
        <li><a href="#scale">scale</a></li>
        <li><a href="#multiples-transformaciones">Múltiples transformaciones</a></li>
    </ul>
    <li><a href="#animation">animation</a></li>
    <ul>
        <li><a href="#keyframes">@keyframes</a></li>
        <li><a href="#animation-timing-function">animation-timing-function</a></li>
        <li><a href="#animation-iteration-count">animation-iteration-count</a></li>
        <li><a href="#animation-direction">animation-direction</a></li>
        <li><a href="#animation-delay">animation-delay</a></li>
        <li><a href="#animation-fill-mode">animation-fill-mode</a></li>
        <li><a href="#animation-play-state">animation-play-state</a></li>
        <li><a href="#multiples-animaciones">Múltiples animaciones</a></li>
    </ul>
</ul>

<a name="transition"></a>

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

<a name="transition-timing-function"></a>

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

<a name="transform"></a>

## transform

Una transformación es un efecto que permite a un elemento cambiar su forma, tamaño y posición.

<a name="rotate"></a>

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

<a name="transform-origin"></a>

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

<a name="translate"></a>

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

<a name="skew"></a>

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

<a name="scale"></a>

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

<a name="multiples-transformaciones"></a>

#### Múltiples transformaciones

Se pueden aplicar varias transformaciones al mismo tiempo, basta con separarlas con un espacio
``` css
    .transform {
        width: 300px;
        height: 100px;
        position: absolute;
        top: 100px;
        left: 100px;
        background-color: orangered;
        transform: translate(100px) rotate(20deg);
    }
```
<a href="assets/examples/39transform.html" target="_blank">Ejecutar código</a>

<a name="animation"></a>

## animation

Una animación permite a un elemento cambiar gradualmente de un estilo a otro.

<a name="keyframes"></a>

#### @keyframes

Los **@keyframes** registran los estilos que el elemento tendra en ciertos tiempos. Cuando se especifican estilos CSS dentro de la regla @keyframe, la animación cambiara gradualmente desde el estilo actual al nuevo estilo en el tiempo especificado.

``` css
    @keyframes ejemplo {
        0% {background-color: red;}
        50% {background-color: yellow;}
        70% {background-color: blue;}
        100% {background-color: green;}
    }
```

En el ejemplo anterior el elemento comenzará con un fondo rojo, cuando la animación esta 50% completada tendra el color amarillo.

Como una alternativa de uso a los valores porcentuales se pueden usar las palabras clave **from** (0%) y **to** (100%).

Para que una animación funcione debemos asignarle a un elemento el nombre y la duración de la animación
``` css
    div {
        width: 300px;
        height: 100px;
        background-color: black;
        animation-name: ejemplo;
        animation-duration: 4s;
    }
    @keyframes ejemplo {
        0% {background-color: red;}
        50% {background-color: yellow;}
        70% {background-color: blue;}
        100% {background-color: green;}
    }
```
<a href="assets/examples/40animation.html" target="_blank">Ejecutar código</a>

<a name="animation-timing-function"></a>

#### animation-timing-function

Especifica la curva de velocidad de una animación. Dispone de los mismos valores que las transiciones.

- **ease** (predeterminado): La animación comienza con lentitud, luego acelerará rápidamente.
- **ease-in**: Comienza lentamente, luego acelera y se detiene bruscamente.
- **ease-out**: Comienza rápidamente y desacelera hasta detenerse.
- **ease-in-out**: Similar a ease, pero con aceleración y desaceleración más sutil.
- **linear**: Velocidad constante a través de la animación. 
- **cubic-beizer**: Permite definir nuestros propios valores. cubic-beizer(0, 0, 0, 0).

``` css
    div {
        width: 300px;
        height: 100px;
        background-color: black;
        animation-name: ejemplo;
        animation-duration: 4s;
        animation-timing-function: ease-in;
    }
    @keyframes ejemplo {
        0% {background-color: red;}
        50% {background-color: yellow;}
        70% {background-color: blue;}
        100% {background-color: green;}
    }
```
<a href="assets/examples/41animation.html" target="_blank">Ejecutar código</a>

<a name="animation-iteration-count"></a>

#### animation-iteration-count

Determina el número de veces que una animación se repite. Tambien se puede fijar el valor en **infinite** para que se repita indefinidamente.

``` css
    div {
        width: 300px;
        height: 100px;
        background-color: orangered;
        animation-name: ejemplo;
        animation-duration: 3s;
        animation-iteration-count: 3;
    }
    @keyframes ejemplo {
        from {width: 0px;}
        to {width: 300px;}
    }
```
<a href="assets/examples/42animation.html" target="_blank">Ejecutar código</a>

<a name="animation-direction"></a>

#### animation-direction

Establece si una animación debe reproducirse hacia adelante, hacia atrás o alternando de un lado a otro.

- **normal** (predeterminado): Se reproduce desde 0% a 100%.
- **reverse**: Se reproduce desde el 100% hasta el 0%.
- **alternate**: Se reproduce desde el 0% al 100% y en la siguiente iteración volverá del 100% al 0%.
- **alternate-reverse**: Al igual que el valor pero de forma inversa

``` css
    div {
        width: 100px;
        height: 100px;
        left: 0px;
        top: 0px;
        position: absolute;
        background-color: orangered;
        animation-name: ejemplo;
        animation-duration: 4s;
        animation-iteration-count: 2;
        animation-direction: alternate;
    }
    @keyframes ejemplo {
        0%   {left: 0px; top: 0px;}
        25%  {left: 200px; top: 0px;}
        50%  {left: 200px; top: 200px;}
        75%  {left: 0px; top: 200px;}
        100% {left: 0px; top: 0px;}
    }
```
<a href="assets/examples/43animation.html" target="_blank">Ejecutar código</a>

<a name="animation-delay"></a>

#### animation-delay

Especifica el tiempo de retardo que debe transcurrir antes de comenzar la animación. Podemos especificarlo en segundos (usando **s**) o en milisegundos (usando **ms**).

Si especificamos un valor negativo, la animación comenzará inmediatamente, pero no desde el principio de la animación, sino desde el punto que le hemos indicado. Por ejemplo, si ponemos retarde de -1s, la aminación comenzará en el segundo 1 de la secuencia.

``` css
    div {
        width: 50px;
        height: 100px;
        background-color: orangered;
        animation-name: ejemplo;
        animation-duration: 3s;
        animation-delay: -1s;
    }
    @keyframes ejemplo {
        from {width: 50px;}
        to {width: 300px;}
    }
```
<a href="assets/examples/43.1animation.html" target="_blank">Ejecutar código</a>

<a name="animation-fill-mode"></a>

#### animation-fill-mode

Especifica un estilo antes y despues de la animación.

- **none** (Predeterminado): Al elemento no se le aplica ningun estilo.
- **forwards**: El estilo del elemento persiste despues de la animación. Es aplicado antes de la propiedad *animation-delay*.
- **backward**: Antes de comenzar se aplica el primer estilo de la animación.
- **both**: Se aplican tanto *forwards* como *backward*.

En el siguiente ejemplo el div 

``` css
    div {
        width: 100px;
        height: 100px;
        left: 0px;
        top: 0px;
        position: absolute;
        background-color: orangered;
        animation-name: ejemplo;
        animation-delay: 2s;
        animation-duration: 3s;
        animation-fill-mode: both;
    }

    @keyframes ejemplo {
        from   {left: 200px; background-color: blue;}
        to  {background-color: yellow;}
    }
```
<a href="assets/examples/44animation.html" target="_blank">Ejecutar código</a>

En el ejemplo anterior podemos ver que no se especifico una propiedad *left* en el último estado de la animación. Este tratara de volver a sus propiedades definidas.

<a name="animation-play-state"></a>

#### animation-play-state

Determina si una animación esta en ejecución o en pausa. Reanudando una animación en pausa, esta empezará por el lugar donde fue pausada.

``` css
    div {
        width: 200px;
        height: 200px;
        background-color: orangered;
        animation-name: ejemplo;
        animation-duration: 1s;
        animation-direction: alternate-reverse;
        animation-iteration-count: infinite;
    }

    div:hover{
        animation-name: ejemplo;
        animation-play-state: paused;
    }

    @keyframes ejemplo {
        from   {background-color: blue;}
        to  {background-color: red;}
    }
```
<a href="assets/examples/45animation.html" target="_blank">Ejecutar código</a>

<a name="multiples-animaciones"></a>

#### Múltiples animaciones

Todos los valores pueden ser definidos con la propiedad animation. El orden de estos es importante, de lo contrario no funcionará.
``` css
    div {
        animation-name: ejemplo;
        animation-duration: 3s;
        animation-timing-function: ease-in;
        animation-delay: 1s;
        animation-iteration-count: infinite;
        animation-direction: reverse;
    }
```
``` css
    div{
        animation: ejemplo 3s ease-in 1s infinite reverse;    
    }
```
