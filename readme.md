# Práctica de Python, Django y REST
### José R. Bonilla Alarcón
Se desea crear una plataforma de blogging llamada Wordplease en la cual los usuarios puedan registrarse para crear su blog personal.

## Sitio WEB
* En la página principal, deberán aparecer los últimos posts publicados por los usuarios.
`Se accede a la home, listado fecha publicación más reciente, se listan 5.`
* En la URL /blogs/, se deberá mostrar un listado de los blogs de los usuarios que hay en la
`http://127.0.0.1:8000/blog`
* El blog personal de cada usuario, se cargará en la URL /blogs/<nombre_de_usuario>/ donde aparecerán todos los posts del usuario ordenados de más actual a más antiguo (los últimos posts primero).
`http://127.0.0.1:8000/blog/jrbonilla/. También se puede acceder desde la opción de menú, en listar blog's y dentro del listado, tendremos opción de listar los post de cada blog`
* En la URL /blog/<nombre_de_usuario/<post_id> se deberá poder ver el detalle de un post.
`http://127.0.0.1:8000/detalle/3 Se puede acceder al detalle de un post, desde el listado home, de post recientes, en detalles, como en listado de blogs, opcion listar post y dentro detalle`
* Un post estará compuesto de: título, texto a modo de introducción, cuerpo del post, URL de
`Realizado`
* Tanto en la página principal como en el blog personal de cada usuario, se deberán listar los posts con el mismo diseño/layout. Para cada post deberá aparecer el título, la imagen destacada (si tiene) y el resumen.
`Realizado`
* En la URL /login el usuario podrá hacer login en la plataforma.
`Realizado`
`Realizado`
`Realizado`
* En la URL /new-post deberá mostrarse un formulario para crear un nuevo post. Para acceder a esta URL se deberá estar autenticado. En formulario para crear el post deberá identificar al usuario autenticado para publicar el POST en el blog del usuario.
`Realizado`

## API REST

#### API de blogs
`**Realizado en endpoint "http://127.0.0.1:8000/api/v1/api_blog/"**`

`Desde la dirección http://127.0.0.1:8000/api/v1/, se accederá al api root. se habilita el router   "api_blog": "http://127.0.0.1:8000/api/v1/api_blog/"
}`

#### API de usuarios
`** Realizado en endpoint http://127.0.0.1:8000/api/v1/users/**`

* Endpoint que permita ver el detalle de un usuario. Sólo podrán ver el endpoint de detalle de un usuario el propio usuario o un administrador. 
* Endpoint que permita actualizar los datos de un usuario. Sólo podrán usar el endpoint de un usuario el propio usuario o un administrador.
* Endpoint que permita eliminar un usuario (para darse de baja). Sólo podrán usar el endpoint de un usuario el propio usuario o un administrador. 

#### API de post
`**Realizado en endopoint http://127.0.0.1:8000/api/v1/posts/
**`

* Un endpoint para poder leer los artículos de un blog de manera que, si el usuario no está autenticado, mostrará sólo los artículos publicados. Si el usuario está autenticado y es el propietario del blog o un administrador, podrá ver todos los artículos (publicados o no). En este endpoint se deberá mostrar únicamente el título del post, la imagen, el resumen y la fecha de publicación. Este endpoint debe permitir buscar posts por título o contenido y ordenarlos por título o fecha de publicación. Por defecto los posts deberán venir ordenados por fecha de publicación descendente. ``