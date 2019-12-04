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
        border-radius: 100px;
    }
```
<a href="assets/examples/02border-radius.html" target="_blank">Ejecutar código</a>

<hr>

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
    

#### Múltiples sombras
Podemos definir múltiples sombras para una misma caja escribiendo estas en la misma regla **separadas por una coma**. En caso de especificar un valor que pueda contradecir a otro, este se insertará al fondo de la sombra

``` css
    .div {
        width: 300px;
            height: 100px;
            background-color: orangered;
            box-shadow: 
            inset 10px 10px 2px grey,
            inset -10px -10px 2px grey;
    }
```

<a href="assets/examples/07box-shadow.html" target="_blank">Ejecutar código</a>

<hr>

## Efectos de transparencia

#### Colores RGBA

Los colores **RGBA** son una extension de RGB, añadiendo un canal *Alpha* que permite cambiar la opacidad del color.   
Los colores RGBA se especifican como: **rgba(red, green, blue, alpha)**. El parámetro alpha es un número entre 0 y 1, donde 0 es transparente y 1 opaco.

``` css
    .div {
        width: 200px;
        height: 200px;
        background-color: rgba(255, 0, 0, 0.2);
    }
```
<a href="assets/examples/08rgba.html" target="_blank">Ejecutar código</a>

#### Colores HSL y HSLA

Los colores **HSL** se especifican como: **hsl(tono, saturación, luminosidad)**.   
- **Tono** es un grado en la rueda de colores que va desde 0 a 360. 0 y 360 es rojo, 120 es verde y 240 el azul.
- **Saturación** es un valor porcentual donde 100% Es a todo color.
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