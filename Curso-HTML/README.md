# Curso de HTML básico

## 📚 Curso

📌 **HTML** - [Acceder al curso](https://github.com/alejanCodeGF/Curso-Desarrollo-Web/tree/main/Curso-HTML)\
🎨 **CSS** - [Acceder al curso](https://github.com/alejanCodeGF/Curso-Desarrollo-Web/tree/main/Curso-CSS)\
💻 **JavaScript** - [Acceder al curso](https://github.com/alejanCodeGF/Curso-Desarrollo-Web/tree/main/Curso-JS)

---

## 👤 Sobre el Autor

**AlejanCodeGF**

📎 [LinkedIn](https://www.linkedin.com/in/alejan-gomez-fernandez/)\
🌐 [Portfolio Web](https://alejancodegf.github.io/Portfolio)

✉️ **Contacto**: [alejan.gomez.fernandez@gmail.com](mailto\:alejan.gomez.fernandez@gmail.com)

---

## Conceptos básicos

```
Nombrar al archivo de arranque como "index.html". Será el primero que se mostrará

Tipos de comportamiento:
display block -> Ocupan toda la línea de la web, da igual que el contenido sea menor (<h1>, <p>...)
display inline -> Ocupan únicamente el contenido que contenga (<span>, <a>...)
    > Esto se podrá modificar con el estilo en CSS

Atributo booleano (BOOL):
Aquel que no necesita un valor, su sola presencia significa que está "activado"
<input type="checkbox" checked> (checked es un atributo, pero no hace falta hacer checked=3)

Enlaces:
Referencia a otro recurso (página, imagen, archivo, etc.)
Puede ser local (dentro del proyecto) o externo (hacia otra web) y hay de varios tipos:
    1. Relativas -> Dentro del mismo sitio (/carpeta/archivo.html)
    2. Absolutas -> Incluyen el dominio completo (https://ejemplo.com)
    3. Anclas -> Navegan dentro de la misma página (#seccion)
    4. Especiales -> Para llamadas telefónicas (tel:123456789) o emails (mailto:correo@ejemplo.com)"""
```

## Comentar en código

```
<!--COMENTARIO-->
```

## Estructura básica de etiqueta

```
<etiqueta atributo="valor">Contenido</etiqueta>
    > En la mayoría de casos se necesitará una etiqueta de apertura y otra de cierre, pero habrá casos en los que no (<br>, <img>, <input>...)
    > A lo largo del cheat sheet verás las que no necesitan cierre con <etiqueta />, aunque se suelen escribir sin la barra
```

## Estructura básica de documento HTML

```
<!DOCTYPE HTML> <!--Versión del HTML-->

<html>
    <head>
        ...
    </head>
    <body>
        ...
    </body>
</html>
```

## `<head>`

```
Dentro de esta etiqueta irán los elementos que no se ven directamente en la web

<title> -> Añadir título en la pestaña
<meta> -> Añadir metadatos
<link> -> Linkear algo (archivo css, icono, etc.)
```

### _Metadatos_

```
Metadatos -> Información oculta que describe y optimiza la página para navegadores, buscadores y redes sociales

<meta>
    charset -> Cambiar la codificación (poder poner tildes y caracteres especiales (ç,ñ...))
        = "utf-8" -> El más usado para los idiomas europeos
    name -> Crear una "carpeta" de datos (y con el atributo "content" la rellenas)
        ="keywords" -> Etiquetas para el SEO, separadas por comas
        ="description" -> Descripción de la página web (entre 70-140 char)
        ="autor" -> Nombre del autor de la web
        ="copyright" -> Poner el nombre de la empresa dueña de los derechos
        ="robots" -> Dar instrucciones a los motores de búsqueda
            > Si la web debería ser indexada o no (que aparezca en el buscador)
                > content = "index" / "noindex"
            > Si los links DENTRO de la web deberían afectar al SEO o no
                > content = "follow" / "nofollow"
    content -> Especificar los datos del atributo "name"
        > (P.e: name="keywords" content="HTML, metadato, ejemplo")
```

### _Link_

```
Enlazar recursos externos (hojas de estilo, iconos...)

<link>
    rel -> Que queremos linkear
        ="icon" -> Icono de la pestaña
        ="stylesheet" -> Archivo de estilo (css)
    type -> Formato del archivo
        ="image/png"
        ="text/css"
    href -> Ubicación del archivo (enlace)

Ejemplos:
    <link rel="icon" type="image/png" href="Logo_web.png">
    <link rel="stylesheet" type="text/css" href="style.css">
```

### _Enlazar JavaScript_

```
<script> -> Enlazar código JavaScript
    src = "archivo.js" (URL)
    defer (BOOL) -> Ejecuta el script después de cargar el HTML
        > Es similar a poner el <script> al final del <body>, pero mejor de esta forma
    async (BOOL) -> Descarga y ejecuta el script en paralelo sin esperar al HTML

También es posible escribir directamente código, sin enlazar a un archivo externo con "src"

Ejemplo:
"""
<script>
    console.log("Hola, mundo!");
</script>
"""
```

## `<body>`

```
Dentro de esta etiqueta irán los elementos que se muestran
```

### _Textos_

```
<hi> -> Añadir títulos (y solo títulos)
    > i = 1,2,...,6 (1 título, 2 subtítulo, 3 subsubtítulo...)
<p> -> Párrafo de texto
<hr /> -> Línea de separación
<br /> -> Salto de línea
<span> -> Aplicar estilos a un grupo de letras (CSS)
<strong> -> Resaltar un texto con énfasis (negrita)
<em> -> Resaltar un texto con énfasis (cursiva)
<blockquote> -> Para destacar citas largas o textos tomados de otra fuente
    cite -> Para poner el enlace en la cual se cita el texto
<code> -> Para mostrar fragmentos de código
<pre> -> Permite mostrar el texto tal cual como lo escribes, respetando espacios y saltos de línea
```

### _Navegación_

```
<a> -> Crear enlaces a otras páginas o recursos
    href = "URL" -> Especifica el destino del enlace
        > Puede ser una ruta local, externa, ancla o especial
    target = "_blank" -> Abre el enlace en una nueva pestaña
        > Si usamos "_blank", agregar rel="noopener noreferrer" por seguridad
```

### _Multimedia_

```
<img /> -> Añadir una imagen (png, jpg, gif...)
    src = "URL" ("imagen.png" en local o enlace externo)
    width = ... | height = ...
        > Si defines solo uno, el otro se ajusta automáticamente para mantener la proporción
    alt -> Texto alternativo si no carga la imagen / contenido
        > VITAL para el SEO y la accesibilidad
    title -> Texto que aparece al pasar el cursor sobre la imagen

<video /> -> Insertar un vídeo
    src = "URL" (ruta local o externa)
    controls (BOOL) -> Activa los controles del vídeo (reproducir, pausar, volumen, etc.)
        > Su apariencia depende del navegador
        > Si no se especifica, el vídeo se reproduce sin controles

<audio /> -> Insertar un audio
    src = "URL" (ruta local o externa)
    controls (BOOL) -> Activa los controles de reproducción
        > Funciona igual que `<video>`, pero reproduce sonido
```

### _Contenedores y organizar la web_

```
En HTML se usan contenedores para organizar el contenido de una página en secciones estructuradas
Cada contenedor forma grupos relacionados, lo que facilita la navegación y el diseño

<div> -> Contenedor genérico sin significado específico
<header> -> Encabezado de la web (logo, menú, título, etc.)
    > Normalmente se mantiene igual en todas las páginas del sitio
<nav> -> Barra de navegación (menú, buscador, enlaces, etc.)
    > Suele estar dentro del <header>
<main> -> Contenido principal de la web
    > Ejemplo: En un periódico, aquí irían las noticias
<article> -> Bloques de contenido independiente dentro del <main>
    > Ejemplo: Una noticia, un post de blog, un producto en una tienda
    > Para SEO: Debe incluir títulos (<h1>-<h6>) y texto (<p>)
<section> -> Agrupa contenido dentro de <article> o <main>
    > Ejemplo: En una noticia, puede haber una sección para cada parte del artículo
<figure> -> Para imágenes, gráficos o contenido multimedia con su descripción
    > No es lo mismo que <section>, se usa para elementos visuales
<aside> -> Contenido relacionado pero no esencial
    > Ejemplo: Una barra lateral con enlaces o publicidad
<footer> -> Pie de página (copyright, contacto, redes sociales, etc.)
```

### _Formularios_

```
<form> -> Contiene el formulario para enviar la información
    action = "/formulario.php" (Donde se enviará el formulario)
    method -> Método de envío de datos
        = "GET" -> Parámetros en la URL (obtener información)
            > Tiene un limite, se usa para búsquedas y navegadores
        = "POST" -> No tiene límite de datos (cambiar información), usado para formularios
        > Nota: Ningún método es seguro por sí solo
<label /> -> Asocia un texto con un campo de formulario y mejora la accesibilidad
    for -> Vincula el label con el id de un input
<input /> -> Permite introducir información (texto, checkbox, etc.)
    id -> Identificador único del elemento
    name -> Clave en el JSON enviado ({"Nombre":"Alejandro", "Edad":"..."})
    value -> Valor por defecto del campo, se mantiene escrito, no como el placeholder
    placeholder -> Texto de ayuda, desaparece al escribir
    type -> Define el tipo de input
        = "text" (Por defecto) -> Campo de texto
        = "email" -> Requiere formato "aaa@bbb.ccc" (validación mejor en backend)
        = "number" -> Solo números (con flechas para ajustar valores)
        = "password" -> Oculta el texto ingresado, y muestra "***"
        = "radio" -> Permite seleccionar solo una única opción (poner el mismo "name" agrupa las opciones)
            checked (BOOL) -> La opción seleccionada por defecto
        = "checkbox" -> Permite seleccionar múltiples opciones (poner el mismo "name" agrupa las opciones)
            > Si no se especifica value, su valor es "true"/"false"
            checked (BOOL) -> La opción/es seleccionadas por defecto
        = "range" -> Permite seleccionar un valor dentro de un rango, entre un "min" y un "max"
        = "date" -> Seleccionar fecha
        = "time" -> Seleccionar hora
        = "color" -> Seleccionar un color
    required (BOOL) -> Hace obligatorio introducir un campo
<select> -> Desplegable para seleccionar una opción de una lista, sobre todo en listas grandes
    name -> Similar al <input>
<option> -> Irá dentro del <select></select>, para poner la lista de opciones
    value -> Valor de la selección. El que se envia al servidor (perro, gato, etc.)
    selected (BOOL) -> Opción seleccionada por defecto
<optgroup> -> Si quieres separar el <select> con las opciones en varios grupos
    > (P.e: Select: 1.Ropa -> Calcetines, pantalones... 2.Tallaje -> XL, L...)
    label -> Etiqueta del grupo (Con el ejemplo de arriba, "Ropa" y "Tallaje")
<textarea> -> Muy parecido al input text, pero con algunas diferencias
    id... (...muy parecido a input...)
    ...
    cols = "Número de columnas" (caracteres)
    row = "Número de filas"
    readonly (BOOL) -> No permite editar el texto
    > Nota: No usa value, se escribe entre las etiquetas.
<button> -> Botón con texto o imagen
    type
        = "button" -> Para usarlo con JavaScript
        = "reset" -> Restablece valores del formulario
        = "submit" -> Envía los datos del formulario
<fieldset> -> Para organizar, agrupando elementos del formulario en partes
<legend> -> Dar a cada <fieldset> un encabezado, o una descripción del grupo
```

### _Listas_

```
<ul> -> Lista no ordenada
<ol> -> Lista ordenada (1,2,3...)
    start -> Número de inicio (default = 1)
    type -> Tipo de numeración
        = "A" (A,B,C,D...)
        = "a" (a,b,c,d...)
        = "I" (I,II,III,IV...)
        = "i" (i,ii,iii,iv...)
    reversed (BOOL) -> Enumera en orden inverso
<li> -> Cada elemento de la lista irá rodeado de esta etiqueta

<dl> -> Lista de descripción (elemento1-descripción1, elemento2-descripción2...)
<dt> -> Cada elemento de la lista irá rodeado de esta etiqueta
<dd> -> Cada descripción del elemento de la lista irá rodeado de esta etiqueta

> Nota: Se pueden anidar listas dentro de listas
```

### _Tablas_

```
Las tablas se organizan por filas y elementos

Estructura básica:
"""
<table>
  <tr>
    <th>Encabezado 1</th>
    <th>Encabezado 2</th>
  </tr>
  <tr>
    <td>Dato 1</td>
    <td>Dato 2</td>
  </tr>
</table>
"""

Elementos principales:
<table> -> Rodeando la tabla
<tr> -> "Table row", fila de la tabla
<td> -> Celdas o elementos
    colspan = "n" (Juntar "n" columnas como un unico elemento)
    rowspan = "n" (Juntar "n" filas como un unico elemento)
<th> -> Parecido a td, para el encabezado de la tabla (los apartados)
<caption> -> Descripción de la tabla y su contenido

Agrupación de columnas:
<colgroup> -> Seleccionar columnas de la tabla (Ponerlo dentro de <table>)
    <col /> -> Cada "col" es una columna (Si quieres poner un estilo en la 2a columna, poner 1 <col /> vacia, y la siguiente con el estilo)
        span = "n" (Juntar "n" columnas para darle el mismo estilo a todas)

Organización de la tabla (Secciones):
<thead> -> Sección de encabezado (nombre, edad... (ponerlo con <th>))
<tbody> -> Elementos de la tabla (datos)
<tfoot> -> Información resumen (mediana, valor máximo...)

Reglas de mejora para la accesibilidad:
    - Utilizar los elementos <th> para los nombres de encabezados
    - En estos <th> decir a que hacen referencia (col/row) con el atributo "scope"
```
