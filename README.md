# nerdflix_2.0

# Creando el ambiente de desarrollo

##  Crear nuestro repositorio en GITHUB

El control de versión es muy importante para cualquier dev. Comencemos por crear un nuevo repositorio en GITHUB 

[Breve guía](https://desarrolloweb.com/articulos/crear-repositorio-git-codigo.html)

##Crear archivo .gitingore

El .gitignore es un archivo que le dice a GIT que directorios o archivos ignorar. Así los remuevo del control de versión. 

Solemos ignorar directorios que contienen paquetes instalados por gestores como NPM o COMPOSER. 

Otro tipo de directorios que es usual agregar al .gitignore son aquellos que contienen archivos de configuración de nuestro IDE o editor de código.

## Armando un buen README.md

Un archivo README contiene información acerca de otros archivos en un directorio. Es una forma de documentación de software.

Típicamente contienen una o más de estos temas:

- Instrucciones de configuración
- Instrucciones de instalación
- Instrucciones de operación
- Un manifiesto de archivos
- Información sobre la licencia
- Información sobre el desarrollador
- Bugs conocidos
- Solución de problemas 
- Créditos y agradecimientos
- Un registro de cambios
- Una sección de noticias

*Herramientas para crear un readme:*

- [Editor Online de Markdown](https://stackedit.io/)

- [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

## Integrando BOOTSTRAP 4

**CDN DE BOOTSTRAP**

Bootstrap es un conjunto de herramientas y componentes que nos permiten crear rápidamente aplicaciones responsivas y que respeten la consigna mobile-first.

Una de las formas rápidas de integrarlo a nuestro proyecto es utilizando el  BootstrapCDN. Para ello debemos copiar el siguiente código en nuestro index.html justo antes de la etiqueta `</head>`

```
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" integrity="sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z" crossorigin="anonymous">
```

Éste código trae a nuestro proyecto los estilos de BOOTSTRAP. Pero también queremos traer la funcionalidad, por lo que para que BOOTSTRAP pueda crear contenido dinámico, agregamos el siguiente código antes de la etiquta `</body>`

```
<script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.1/dist/umd/popper.min.js" integrity="sha384-9/reFTGAW83EW2RDu2S0VKaIzap3H66lZH81PoYlFhbGU+6BZp6G7niu735Sk7lN" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js" integrity="sha384-B4gt1jrGC7Jh4AgTPSdUtOBvfO8shuf57BaghqFfPlYxofvL8/KUEfYiJOMMV+rV" crossorigin="anonymous"></script>
```

Toda esta información y más se encuentra en la [documentación oficial](https://getbootstrap.com/docs/4.4/getting-started/introduction/)

**INSTALAR BOOTSTRAP CON NPM**

El gestor de paquetes de Node facilita la instalación de muchos paquetes, BOOTSTRAP no es la excepción. Podemos instalar y tener BOOTSTRAP en nuestro proyecto utilizando el comando

    npm i bootstrap

[Link a la documentación](https://www.npmjs.com/package/bootstrap)

**DESCARGAR E INTEGRAR BOOTSTRAP**

También es posible **instalar BOOTSTRAP descargándolo e integrándolo** en nuestro proyecto. [En este link podrás ver un video sobre cómo hacerlo](https://www.youtube.com/watch?v=BkuYU7Rm_qg)

**Ejercicio 1 El Hola Mundo!**

Al aprender algo nuevo es una tradición entre coders crear nuestro primer "Hola Mundo" con la tecnología que estamos aprendiendo.

Vamos a armar nuestro Hola Mundo con Bootstrap. Las consignas son:

1) Crear una plantilla HTML básica 
2) Integrar Bootstrap
3) Copiar el siguiente código dentro del `<body>` (no te preocupes por las clases de las etiquetas. Ya vamos a analizarlas)

```
<div  class="container text-center py-5">
    <h1  class="display-1">Hello, world!</h1>
</div>
```

## La magia de Bootstrap: LAYOUT

**CONTAINER Y CONTAINER-FLUID**

Se trata de dos clases básicas de BOOTSTRAP que funcionan como contenedores de la interfaz de nuestra aplicación. 

El `.container` crea márgenes tanto a la izquierda como a la derecha y el `.container-fluid` ocupa toda la pantalla

En el archivo `container.html` podemos ver la diferencia entre uno y el otro.

[Documentación de Layout: containers](https://getbootstrap.com/docs/4.4/layout/overview/)

**EL GRID SYSTEM**

El GRID SYSTEM de BOOTSTRAP se compone de filas `.row` y columnas `.col`. La columnas pueden dividirse en doce partes y, a su vez esas doce partes, pueden ser combinadas, siempre sumando doce.

| col-1 | col-2 | col-3 | col-4 | col-5 | col-6 | col-7 | col-8 | col-9 | col-10 | col-11 | col-12 |
|-------|-------|-------|-------|-------|-------|-------|-------|-------|--------|--------|--------|

Por ejemplo podemos obtener un layout con solo dos columnas utilizando las clases col-6 y col-6 en dos etiquetas dentro de una fila.container-fluid

| col-6 | col-6 |
|-------|-------|

O 3 columnas de 4 unidades (col-4)

| col-4 | col-4 | col-4 |
|-------|-------|-------|

Esto nos da libertad para crear el layout que necesitemos para nuestra aplicación.

Ejemplo de código

```
<div class="container">
    <div class="row">
        <div class="col-4 bg-primary">
            <p>col-4</p>
        </div>
        <div class="col-4 bg-success">
            <p>col-4</p>
        </div>
        <div class="col-4 bg-warning">
            <p>col-4</p>
        </div>
    </div>
    <div class="row">
        <div class="col-6 bg-danger">
            <p>col-4</p>
        </div>
        <div class="col-6 bg-info">
            <p>col-4</p>
        </div>
    </div>
</div>
```

[Documentación del Grid System](https://getbootstrap.com/docs/4.4/layout/grid/)

**Ejercicio 2 Crear un layout con 4 columnas**

Con lo que aprendimos del GRID SYSTEM debes crear un layout con 3 filas de 4 columnas cada una que contengan texto. Podés basarte en el archivo `grid.html`


**El Grid Responsive. Los puntos de quiebre**

[Ver tabla de Grid Options en documentación](https://getbootstrap.com/docs/4.4/layout/grid/)

Hasta ahora al asignar `.col-12` o cualquier otro valor a la columna le estamos diciendo a BOOTSTRAP que utilice el mismo valor para cualquier dispositivo. Esto hace que en cualquier pantalla se mantengan las mismas columnas. 

Hoy los usuarios usan dispositivos de diferentes tamaños por lo que nuestro diseño debe ser mobile-first, esto es que debemos pensar primero en los dispositivos móviles, que son más pequeños.

Para controlar cómo se ve nuestra aplicación en diferentes dispositivos podemos decirle a BOOTSTRAP cómo debe comportarse según el tamaño de la pantalla. Según esta sea small (sm) -celulares-, medium (md) -tablets-, large (lg) -monitores- o extra large (xl) -smart tvs-.

Veamos el archivo `grid-responsive.html` para ver cómo podemos crear un layout full responsive utilizando estas clases.

**Alineamiento Vertical**

[Documentación de Vertical Alignment](https://getbootstrap.com/docs/4.4/layout/grid/#vertical-alignment)

BOOTSTRAP permite alinear nuestros elementos en la parte superior, media o inferior del elemento contenedor. Por defecto siempre estarán arriba.

Para ahorrarnos calcular el padding superior e inferior en relación al tamaño del elemento contenedor, BOOTSTRAP utiliza flexbox para que podamos hacer esto rápidamente.active

Al `.row` debemos asignarle una clase especial según dónde queramos que se ubique el contenido

```
.align-items-start
.align-items-center
.align-items-end
```

Tambien podemos afectar al elemento html y no a su contenido. Eso lo hacemos con utilizando `.align-self-` en las columnas.

```
.align-self-start
.align-self-center
.align-self-end
```

Ver archivo `alineamientos.html`

**Alineamientos Horizontales**

Independientemente de que nosotros pongamos menos columnas que 12, podemos de todos modos alinearlas como querramos utilizando el alineamiento horizontal.

Ver archivo `alineamientos.html`

## Más sobre BOOTSTRAP

- [Tipografía](https://getbootstrap.com/docs/4.4/content/typography/)
- [Formato de Tipografías](https://getbootstrap.com/docs/4.4/utilities/text/)
- [Componentes](https://getbootstrap.com/docs/4.4/components/alerts/)
- [Ejemplos Oficiales](https://getbootstrap.com/docs/4.4/examples/)


## Creando NERDFLIX 2.0

- Ya tenemos nuestro index.html creado
- Ya somos expertos en BOOTSTRAP
- Ya tenemos nuestro ambiente de desarrollo listo
- Ya tenemos un proyecto bien ordenado y estructurado

¡Comencemos a trabajar en NERDFLIX 2.0!

