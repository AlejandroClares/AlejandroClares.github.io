---
author: Alejandro
layout: b4-layout
title: CSS3 - Tutorial - Conceptos básicos
nombre: Conceptos básicos
---

# Conceptos básicos

### Menú de navegación
<ul>
    <li><a href="#prefijos-de-navegacion">Prefijos de navegación</a></li>
    <li><a href="#border-radius">border-radius</a></li>
    <li><a href="#box-shadow">box-shadow</a></li>
    <ul>
        <li><a href="#blur-y-spread">Blur y Spread</a></li>
        <li><a href="#valores-negativos">Valores Negativos</a></li>
        <li><a href="#inset">Inset</a></li>
        <li><a href="#box-shadow-multiples-sombras">Múltiples sombras</a></li>
    </ul>
    <li><a href="#text-shadow">text-shadow</a></li>
    <ul>
        <li><a href="#text-shadow-multiples-sombras">Múltiples sombras</a></li>
    </ul>
    <li><a href="#efectos-de-transparencia">Efectos de transparencia</a></li>
    <ul>
        <li><a href="#colores-rgba">Colores RGBA</a></li>
        <li><a href="#colores-hsl-y-hsla">Colores HSL y HSLA</a></li>
    </ul>
    <li><a href="#pseudo-clases">Pseudo-Clases</a></li>
    <li><a href="#pseudo-elementos">Pseudo-Elementos</a></li>
    <li><a href="#word-wrap">word-wrap</a></li>
    <li><a href="#font-face">@font-face</a></li>
</ul>

<a name="prefijos-de-navegacion"></a>

## Prefijos de navegación

Son una forma en la que los fabricantes de navegadores añaden soporte a las nuevas características de css en periodos de prueba o experimentación.

Por ejemplo, el prefijo de Safari y Chrome es -webkit-. 
``` css 
    .cuadrado {
        -webkit-border-radius: 10px;
    }
```
La mayoría de navegadores de hoy en día funcionan sin prefijos, pero es esencial conocerlos para la compatibilidad y entendimiento de códigos antiguos.

Escribir varias veces las propiedades para que funcionen en diferentes navegadores puede ser molesto pero es temporal. Mientras los navegadores mejoran, añadirán soporte a las propiedades y eliminarán los prefijos.

<img style="max-width: 50%;" src="assets/image/prefijosCSS3.jpg" alt="Prefijos de navegador">

<hr>

<a name="border-radius"></a>

##  border-radius
La propiedad **border-radius** nos permite darle esquinas redondeadas a cualquier elemento.
``` css
    .div{
        width: 200px;
        height: 200px;
        background-color: orangered;
        border-radius: 50px;
    }
```

<a href="assets/examples/00border-radius.html" target="_blank">Ejecutar código</a>

Podemos especificar el radio por separado de cada esquina en orden: superior-izquierdo, superior-derecho, inferior-derecho, inferior-izquierdo.

``` css
    .div{
        width: 200px;
        height: 200px;
        background-color: orangered;
        border-radius: 0 0 0 50px;
    }
```
<a href="assets/examples/01border-radius.html" target="_blank">Ejecutar código</a>

Una caja puede ser convertida en un círculo solo usando CSS. El radio debe ser la mitad del ancho y alto de la caja.
``` css
    .div {
        width: 200px;
        height: 200px;
        background-color: orangered;
        border-radius: 100px;
    }
```
<a href="assets/examples/02border-radius.html" target="_blank">Ejecutar código</a>

<hr>

<a name="box-shadow"></a>

## box-shadow

La propiedad CSS3 **box-shadow** permite aplicar sombras a los elementos.    
Los parámetros de esta propiedad son:
- **Desplazamiento horizontal**: Desplaza la sombra hacia la derecha. (Requerido)
- **Desplazamiento vertical**: Desplaza la sombra hacia abajo. (Requerido)
- **Color**: Color de la sombra. El color por defecto es negro. (opcional)

``` css
    .div {
        width: 300px;
        height: 100px;
        background-color: orangered;
        box-shadow: 10px 10px grey;
    }
```
<a href="assets/examples/03box-shadow.html" target="_blank">Ejecutar código</a>
   
<a name="blur-y-spread"></a>

#### Blur & Spread
Adicionalmente, hay dos propiedades opcionales: **Blur** (desenfoque) y **Spread** (propagación).      
Estos valores se añaden antes de asignar el color.

``` css
    .div {
        width: 300px;
        height: 100px;
        background-color: orangered;
        box-shadow: 10px 10px 5px 5px grey;
    }
```
<a href="assets/examples/04box-shadow.html" target="_blank">Ejecutar código</a>

<a name="valores-negativos"></a>

#### Valores negativos
A las propiedades de box-shadow se les permite usar valores negativos.  
- **Desplazamiento horizontal**: La sombra se desplaza hacia la **izquierda**.
- **Desplazamiento vertical**: La sombra se desplaza hacia **arriba**.
- **Desenfoque**: Los valores negativos no estan permitidos.
- **Propagación**: La sombra es encogida.

``` css
    .div {
        width: 300px;
        height: 100px;
        background-color: orangered;
        box-shadow: -10px -10px 5px -5px grey;
    }
```
<a href="assets/examples/05box-shadow.html" target="_blank">Ejecutar código</a>
   
<a name="inset"></a>   

#### Inset
La propiedad **inset** permite crear sombras dentro del elemento.

``` css
    .div {
        width: 300px;
        height: 100px;
        background-color: orangered;
        box-shadow: inset 10px 10px 5px 5px grey;
    }
```

<a href="assets/examples/06box-shadow.html" target="_blank">Ejecutar código</a>
    
<a name="box-shadow-multiples-sombras"></a>

#### Múltiples sombras
Podemos definir múltiples sombras para una misma caja escribiendo éstas en la misma regla **separadas por una coma**. En caso de especificar un valor que pueda contradecir a otro, este se insertará al fondo de la sombra

``` css
    .div {
        width: 300px;
        height: 100px;
        background-color: orangered;
        box-shadow;
        inset 10px 10px 2px grey,
        inset -10px -10px 2px grey;
    }
```

<a href="assets/examples/07box-shadow.html" target="_blank">Ejecutar código</a>

<hr>

<a name="text-shadow"></a>

## text-shadow

La propiedad **text-shadow** permite insertar sombras al texto. La propiedad text-shadow se define:   
**text-shadow: desplazamiento-X, desplazamiento-Y, desenfoque (opcional), color (opcional);**

``` css
    h1 {
        text-shadow: 10px 10px 3px grey;
    }
```
<a href="assets/examples/10text-shadow.html" target="_blank">Ejecutar código</a>

<a name="text-shadow-multiples-sombras"></a>

#### Múltiples sombras

La propiedad text-shadow soporta múltiples sombras, separando con comas sus valores

``` css
    h1 {
        text-shadow: 10px 10px 3px grey,
                    20px 20px 3px orange;
    }
```
<a href="assets/examples/11text-shadow.html" target="_blank">Ejecutar código</a>

<hr>


<a name="efectos-de-transparencia"></a>

## Efectos de transparencia

<a name="colores-rgba"></a>

#### Colores RGBA

Los colores **RGBA** son una extension de RGB, añadiendo un canal *Alpha* que permite cambiar la opacidad del color.   
Los colores RGBA se especifican como: **rgba(red, green, blue, alpha)**. El parámetro alpha es un número entre 0 y 1, donde 0 es transparente y 1 opaco.

``` css
    .div {
        width: 200px;
        height: 200px;
        background-color: rgba(255, 0, 0, 0.7);
    }
```
<a href="assets/examples/08rgba.html" target="_blank">Ejecutar código</a>

<a name="colores-hsl-y-hsla"></a>

#### Colores HSL y HSLA

Los colores **HSL** se especifican como: **hsl(tono, saturación, luminosidad)**.   
- **Tono** es un grado en la rueda de colores que va desde 0 a 360. 0 y 360 es rojo, 120 es verde y 240 el azul.
- **Saturación** es un valor porcentual donde 100% es a todo color.
- **Luminosidad** es un valor porcentual donde 0% es oscuro y 100% es blanco.   

Los colores **HSLA** funcionan igual, añadiendo el canal *alpha*.  

``` css
    .div {
        width: 200px;
        height: 200px;
        background-color: hsl(120, 30%, 50%);
    }
```
<a href="assets/examples/09hsl.html" target="_blank">Ejecutar código</a>

<hr>

<a name="pseudo-clases"></a>

## Pseudo-Clases

Las **pseudo-clases** permiten dar estilo a elementos del arbol DOM sin necesidad de usar javascript. Una pseudo clase se define con dos puntos (selector:pseudo-clase)

Las pseudo-clases más comúnes son **:first-child** y **:last-child**

``` css
    div p:first-child {
        color: orangered;
    }
```
<a href="assets/examples/12pseudo-clases.html" target="_blank">Ejecutar código</a>


La pseudo-clase **:checked** representa cualquier elemento input de tipo radio, option o checkbox que este marcado.
``` css
    input:checked + label {
        color: limegreen;
    }

    input[type="radio"]:checked {
        box-shadow: 0px 0px 0px 3px orangered;
    }

    input[type="checkbox"]:checked {
        box-shadow: 0px 0px 0px 3px hotpink;
    }
```
<a href="assets/examples/13pseudo-clases.html" target="_blank">Ejecutar código</a>

Puedes encontrar una lista de las pseudo-clases en <a href="https://developer.mozilla.org/es/docs/Web/CSS/Pseudo-classes#Indice_de_las_pseudo-clases_est%C3%A1ndar" target="_blank">developer.mozilla.org</a>.

<hr>

<a name="pseudo-elementos"></a>

## Pseudo-Elementos

Los **pseudo-elementos** permiten dar estilo a partes específicas de los elementos seleccionados. Como regla general, los pseudo-elementos se usan con **"::"** aunque tambien pueden usarse **":"**. Es adecuado usar **"::"** para distinguirlo de las **pseudo-clases**.   


El pseudo-elemento **::selection** modifica el aspecto de la parte que es seleccionada.

``` css
    p::selection {
        background-color: black;
        color: orangered;
    }
```
<a href="assets/examples/14pseudo-elementos.html" target="_blank">Ejecutar código</a>

**::first-line** modifica la primera linea del elemento.

``` css
    p::first-line {
        color: orangered;
    }
```
<a href="assets/examples/15pseudo-elementos.html" target="_blank">Ejecutar código</a>


Puedes encontrar la lista de pseudo-elementos en <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements#Index_of_standard_pseudo-elements" target="_blank">developer.mozilla.org</a>.

<hr>

<a name="word-wrap"></a>

## word-wrap

La propiedad **word-wrap** indica como se comportará el texto dentro de su caja. **break-word** hace que el texto no se salga de la caja.

``` css
    #parrafo1 {
        word-wrap: normal;
    }
    #parrafo2 {
        word-wrap: break-word;
    }
```
<a href="assets/examples/16word-wrap.html" target="_blank">Ejecutar código</a>

<hr>

<a name="font-face"></a>

## Regla @font-face

Permite cargar fuentes de texto personalizadas. Los navegadores actuales soportan archivos de tipo **Fuentes True Type** (ttf) y **Fuentes OpenType** (otf).   
Cada forma de la familia de la fuente debe ser declarada usando la regla **@font-face**. Primero se debe asignar un nombre a la fuente y despues asignar el fichero de la fuente.

``` css
    @font-face {
        font-family: miPrimeraFuente;
        src: url('../Courier_Prime/CourierPrime-Regular.ttf');
    }
    @font-face {
        font-family: miPrimeraFuente;
        font-weight: bold;
        src: url('../Courier_Prime/CourierPrime-Bold.ttf');
    }
    @font-face {
        font-family: miPrimeraFuente;
        font-style: italic;
        src: url('../Courier_Prime/CourierPrime-Italic.ttf');
    }
    div {
        font-family: 'miPrimeraFuente';
    }
```
<a href="assets/examples/17font-face.html" target="_blank">Ejecutar código</a>