---
layout: page
title: Ejemplo de un post usando Markdown
tags: [Ejemplo de post]
image: /img/mandel.jpg
image-description: descipcción de la images
---

## Creando un nuevo post

Primero, se crea un nuevo archivo en el directorio `_post` llamado `yyyy-mm-dd-tinyTitle.md` donde `yyyy` es el año completo, `mm` el mes y `dd` el día. Jekyll utiliza esto para ordenar chonologicamente los post.  
Si tenemos una idea sobre un nuevo post, pero no lo vamos a terminar de escribir ahora, lo podemos guardar en `_drafts`. Jekyll va a ignorar todos los archivos que estén dentro de este directorio.

## Template

Las primeras lineas del post son:

	---
	layout: post
	title: Lorem Ipsum Dolor Sit Amet test2
	date: 2015-09-10
	tags: [Example, Test, Tag1]
	image: /img/mandel.jpg
	image-description: descipcción de la images
	image-author: Fulano
	author: Nico
	author-img: /img/authors/franco.png
	author-des: Estudiante de física
	author-twitter: fnbellomo
	author-facebook: franco.bellomo.12
	---

Donde `layout: post` nos indica el formato (la estética) del post. Por el momento solo existe un formato, pero se pueden diseñar varios. `title` es el titulo completo de la nota, `date` la fecha del post y `tags` son las etiquetas de la nota que luego se utilizan para hacer el cloud tag. Estos 4 primeros atributos son obligatorios. Si bien, los siguientes atributos son opcionales, el echo de que estén nos va a brindar un post mucho más completo.  
El atributo `image` es el path a la imagen de portada del post. Todas las imagenes se las deben guardar en `/img/`. `image-description` es necesaria para hacer la el sitio accesible y `image-author` es, únicamente, el nombre o un link del autor de esta.
Los últimos 5 atributos son con respecto al autor de la nota, donde el primer atributo (`author`) es su nombre, `author-img` el path a su imagen, `author-des` una breve descripción y los dos restantes son posibles contactos de redes sociales.

## Post

El primer párrafo del post, es el que se muestra en la página principal del blog junto con todos los otros post. Por lo tanto, es importante que este sea un correcto resumen de nuestra nueva entrada. Debemos dejar una linea en blanco antes y despues de este párrafo.

### Títulos

Los títulos son muy simples de utilizar. Solo hay que agregar asteriscos al principio de la linea, donde el mínimo son 2 asteriscos (h2) y el máximo 6 (h6). Solo existe un titulo principal, que es el nombre del post.

    ### Ejemplo titulo de nivel 3

### Nuevo Párrafo

Para indicar el comienzo de un nuevo párrafo hay que dejar  un renglón en blanco entre cada uno.

### Links

Existen dos formas de poner links. La primera es

	...
	mira [este](duckduckgo.com) genial buscador
	...

De donde obtenemos: mira [este](duckduckgo.com) genial buscador

La segunda forma:

	...
	mira [este][link_genial] genial buscador

	# al final del post
	[link_genial]: duckduckgo.com

En ambos casos, el resultado final es el mismo. Ahora, supongamos, que utilizamos un mismo link varias veces en el post. Si en algún momento necesitamos cambiar o actualizar el link, utilizando la segunda forma es muy simple ya que solo hay un link (`[link_genial]: duckduckgo.com`), mientras que utilizando la primer forma necesitamos actualizar link por link.

### Código

Para un bloque de código, simplemente de deja un reglón en blanco por encima y por debajo y se indexa todo el bloque  con 4 espacios (un tab).

Para marcar nombres de paquetes o funciones dentro de un párrafo, se coloca ` al principio y final. Ejemplo:

	usando la librería `numpy`

Nos genera: usando la librería `numpy`

### Citas

Si queremos destacar alguna cita, lo hacemos mediante

	<blockquote>
	  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
	  <footer>Someone famous in <cite title="Source Title">Source Title</cite></footer>
	</blockquote>

Donde obtenemos:

<blockquote>
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
  <footer>Someone famous in <cite title="Source Title">Source Title</cite></footer>
</blockquote>

Además, dentro de las citas es posible poner link como se explico anteriormente.

### Imágenes

Es posible poner imágenes dentro de post

	<img alt="descripción de la img" src="/img/jekyll.jpg" class="mean-img" />

<img alt="descripción de la img" src="/img/jekyll.jpg" class="mean-img" />

Donde `src` nos indica la fuente de la imagen que puede ser un path (recordad que las imágenes siempre se las tiene que guardar en `/img`) o directamente el link de esta. El atributo `class` nos va a indicar el tamaño de la imagen donde las opciones son:

- `full-img`: tamaño completo
- `mean-img`: mitad del tamaño total
- `quarter-img`: un cuarto del tamaño total

### Imagen con texto

	<div class="row">
	  <div class="col-md-4">
	    <img alt="descripción de la img" src="/img/jekyll.jpg" class="full-img" />
	  </div>
	  <div class="col-md-8">
	    <p>Texto al costado de la imagen. Hay que tener cuidado de que el texto no sobre pase el largo de la imagen para que no quede feo.</p>
	  </div>
	</div>

<div class="row">
	<div class="col-md-4">
		<img alt="descripción de la img" src="/img/jekyll.jpg" class="full-img" />
	</div>
	<div class="col-md-8">
		<p>El contenedor del post (lo que tiene fondo blanco) se divide en 12 columnas. Luego, tenemos que especificar cuantas columnas va a tener el texto y cuantas la imagen. En este caso utilizamos `col-md-4` para la imagen y `col-md-8` para el texto.</p>
	</div>
</div>

## Make

Lo mas importante, correr el make:

	$ cd blog
	$ jekyll build

¿Que pasa si nos quedo algo mal? como por ej, el path de una imagen, o algún texto, o lo que sea, entonces podemos correr un servidor local y ver lo que obtuvimos:

	$ jekyll server --watch --baseurl=""

Por ahora, no le daremos importancia a los argumentos que le estamos pasando. Ahora, en nuestro navegador podemos ver lo que obtuvimos en `http://0.0.0.0:4000/`
