
## Comentá el HTML

Algo que la mayoría no hace es dejar comentarios en el HTML, esto es importante cuando se trabaja en equipo o cuando hay que mantener el mismo proyecto durante un tiempo para entender que es cada elemento.

Se vuelve más importante cuando tenés muchos <div> que existen solo por razones de diseño.

## Cargá el CSS lo antes posible

Mientras más rápido el navegador descargue y lea el CSS más rápido va a terminar de renderizar la página. Hay que tratar de cargar los archivos CSS lo antes posible, lo ideal es que sea justo después de la etiqueta <title>.

## Insertá en tu HTML el CSS crítico para tu aplicación

La carga de los archivos de CSS es una operación bloqueante, esto quiere decir que el navegador va a dejar de leer el HTML hasta que termine de descargar el archivo CSS.

Esto trae el problema de que si el archivo es muy pesado el navegador va a estar mucho tiempo sin hacer nada mientras espera que descargue. Para evitar este problema se puede detectar cuál es el CSS crítico para tu aplicación y agregar ese CSS en una etiqueta `<style/>` directo en el HTML y el resto de estilos cargarlos de forma diferida usando JS al final del documento.

El CSS crítico básicamente es el CSS que se utiliza “above the fold”, osea que está en la parte visible del viewport al momento de entrar al sitio y sin haber hecho scroll down.

## Cargá el JS al final

La carga de archivos JS es una operación bloqueante por lo que detiene el renderizado de la página, si además de esto el JS se ejecuta inmediatamente al ser descargado puede dar errores si se trata de manipular el DOM antes de que se renderice el HTML.

Para evitar estos problemas es mejor siempre colocar las etiquetas <script> al final del HTML, justo antes de la etiqueta </body>. Esto permite que el usuario pueda interactuar con el resto del sitio mientras el JS se descarga y ejecuta.

## Cargá cualquier JS no indispensable de forma asíncrona

La etiqueta <script> tiene un atributo llamado async que permite realizar la carga de una archivo de forma asíncrona. Para archivos como los de Google Analytics es mejor siempre cargarlos de esta forma para evitar que esta carga se convierta en una operación bloqueante.

Esto solo hay que hacerlo en archivos como Google Analytics que no son indispensables para el uso de nuestra aplicación web. Para los archivos de la aplicación web es mejor no usar async.

## Usá la menor cantidad de etiquetas posibles -- TODO: Agregar semantica de etiquetas

Cada etiqueta HTML que coloquemos ralentiza el renderizado de nuestra aplicación web. Siempre hay que tratar de usar la menor cantidad posible y evitar la “divtitis”, osea poner un <div> dentro de otro, dentro de otro y así. Cosa muy común si se usa Bootstrap o similares.

## Comprime todas tus imágenes

Algo que muchos no hacen es comprimir lo más posible las imágenes de un sitio, esto lleva a que haya imágenes muy grandes y pesadas, sin que sea necesario tanto tamaño y calidad.

Lo mejor es cargar imágenes del tamaño necesario exacto (el doble para retina display) y lo más comprimidas posibles. La compresión puede hacerse de dos formas, sin pérdida y con pérdida, en el caso de con pérdida se le baja la calidad hasta lo mínimo aceptable para que se siga viendo bien.

## Evitá los @import en el CSS

Cuando el navegador esta leyendo un archivo CSS y se encuentra con un @import deja de leer el archivo CSS original y empieza a descargar y leer el archivo importado y recién cuando termina sigue con el original.

Debido a que la carga de CSS es una operación bloqueante el estar haciendo esto ralentiza el renderizado de nuestra aplicación por lo que es mejor evitar el uso de @import en los archivos CSS, en lugar de eso es mejor combinar los archivos o al menos usar dos etiquetas <link>.

## Minificá el CSS

Esto a pesar de ser una gran mejora de rendimiento y velocidad es algo que todavía no se realiza en muchos sitios o aplicaciones web. El minificar el CSS, al igual que con el HTML, reduce el peso del archivo y elimina los comentarios, permitiendo una carga más rápido del archivo y terminar el renderizado antes.

## Agrupá los media query

Aunque durante el desarrollo es mejor dejar los media query al final de cada componente de nuestro CSS, para saber fácilmente que elementos se están modificando, al momento de generar el CSS de producción es mejor agrupar todos los media query al final del archivo.

Esto además reduce la cantidad de media queries ya que es muy común usar los mismos break points en múltiples lugares, lo cual se combinaría en una única media query. 

## Eliminá el CSS innecesario

Al usar Bootstrap o similares es muy común no usar todos los estilos que este trae. También es bastante común que durante el desarrollo queden clases que ya no se utilizan y se dejan “por las dudas” y que el usuario esta descargando al bajar el CSS aunque no los necesite.

Al momento de generar el CSS de producción lo mejor es borrar estos estilos y dejar solo los que sí son necesarios para nuestra aplicación web. 

## Separá tus hojas de estilos en varios archivos.

Hay algo que muchos desarrolladores FrontEnd no saben y es que IE hasta la versión 9 tiene un límite de 4095 en la cantidad de selectores permitidos por cada archivo CSS. Una vez que se alcanza ese límite IE simplemente ignora el resto de estilos dejando parte de tu sitio sin estilos.

## Armá una guía de estilos al escribír código JS - //TODO: Linkear con angular y sus styles

No todos los desarrolladores escribimos código de la misma forma y cuando trabajamos en equipo es importante que todos estemos de acuerdo en como nombrar variables, funciones, donde dejar espacios, como identar, etc. 

Para lograr eso lo mejor es usar una guía de estilos que nos diga como escribir nuestro código. Podemos crear una propia para nuestro proyecto con nuestros gustos o podemos usar algunas ya hechas que hay en internet como la [guía de AirBnB](https://github.com/airbnb/javascript).


## Modularizá el código JS

Separar el código en archivos nos permite hacer que nuestro código sea más fácil de reutilizar y hacer unit-testing para comprobar que funcione correctamente. Además de esto modularizar hace más fácil mantener el código a largo plazo, otra ventaja es que es más fácil escalar una aplicación modular.

Para poder modularizar nuestro código hay varias formas, la mejor es usar los módulos de ECMAScript 2015, sistema oficial de JS, o al menos el de CommonJS. El sistema AMD (Asynchronus Module Definition) no tiene sentido ya que al final hasta que no carguen las dependencias de tu código no vas a ejecutarlo, igual que harías con CommonJS o ES2015.

## Comentá el código

Similar al primer punto, es importante comentar nuestro código para que cualquier desarrollador que trabaje con nosotros sepa que hace. Alcanza con dejar un pequeño comentario antes de crear cada función explicando que hace y que parámetros recibe, aunque para bloques de código complicados es buena idea agregar un comentario explicando que hace.

## Evitá ensuciar el scope global

Cuando no se trabaja con módulos es muy común dejar un montón de variables en el scope global de nuestra aplicación (global en Node.js y window en navegadores) lo que puede causar problemas al intentar usar una librería de terceros o al agregar más código.

Lo mejor es tratar de encapsular el código en NameSpaces, esto lo pueden lograr usando una función auto ejecutable (IIFE) que encapsule el código y lo ejecute. Esto se soluciona si se usan sistemas de módulos.

## Reduce el acceso al DOM

La parte más lenta de cualquier aplicación web es el DOM, cada acceso al DOM nos cuesta mucho tiempo por lo que es mejor evitar todo lo posible acceder al DOM.

Si necesitan editar multiples veces el mismo elemento es mejor acceder una vez y guardar el elemento en una constante que luego puedan usar para manipular el elemento sin volver a acceder al mismo.

## Reduce los Event Listeners

Tener muchos event listeners al mismo tiempo ralentiza nuestras aplicaciones. Si necesitan escuchar multiples elementos (por ejemplo cada elemento de un listado) es mejor escuchar al elemento padre y usar event.target para verificar si el evento es disparado desde el elemento deseado.

## Reduce las peticiones al servidor

Cada petición ralentiza un poco más la carga de la aplicación, es mejor tratar de reducir la cantidad de peticiones al mínimo para que nuestra aplicación cargue más rápido.

## Cargá de forma diferida imágenes, vídeos, etc.

Es mejor solo cargar las imágenes, vídeos, fuentes, audios, etc. que el usuario necesita inmediatamente ya que están dentro del viewport inicial (están above the fold) y cargar de forma diferida (lazy load) el resto de forma que solo se descarguen si el usuario lo necesita o al menos hasta que el contenido sí necesario se termine de cargar.

## Evitá los src vacíos

Algunos navegadores si encuentran una etiqueta <img> o <source> con el src vacío o sin un atributo src van a hacer una petición a la misma página, lo que implica una petición extra e inútil.

Si vas a cargar de forma diferida imágenes y vídeos es mejor dejar una imagen por defecto en el atributo src que se pueda descargar una vez y sirva para todas las imágenes y luego cuando el usuario haga scroll cambiar el src por la imagen correspondiente.

## Precargá el contenido - TODO: linkear esto con lazyload de angular

Trata de adelantarte a lo que el usuario va a hacer y carga el contenido que pueda necesitar antes de que lo necesite. Esto se puede lograr empezando a cargar el contenido cuando el usuario haga hover en algún link o botón permitiéndonos cargar todo el contenido que el usuario vaya a necesitar para luego mostrárselo inmediatamente cuando haga click.

Google hace esto mismo para precargar el contenido del primer resultado de búsqueda, así este carga más rápido al entrar.

## Evitá los 404

Asegurate de evitar cualquier 404 en todas las peticiones. Cada petición toma tiempo y si va a terminar dando un error 404 es mejor evitarla, verifica siempre que tus scripts, hojas de estilos, imágenes, etc. se cargan correctamente.

## No le quites funcionalidad al usuario

Si el usuario tiene una funcionalidad por defecto no deberías quitarle esa funcionalidad. Un ejemplo es que si el usuario puede hacer zoom en móviles no deberíamos quitarle esa posibilidad.

Otro ejemplo muy común es en los formularios, el usuario por defecto puede enviarlos apretando Enter/Return mientras hace foco en un <input> o enviarlo al hacer click en un botón de Submit. Al usar AJAX es común que el envío de los datos por AJAX se agregue al evento _click_ del botón, en lugar de eso es mejor agregárselo al evento _submit_ del formulario lo cual obtendría tanto el click del botón como el Enter/Return de los inputs.

## Recordá las acciones del usuario y el estado de la aplicación

Si el usuario empieza hacer algo, se va a otra página y vuelve para atrás deberías recordar que hizo y en donde se quedo. Un ejemplo muy común es que si el usuario empezó a llenar un formulario de varios pasos y en algún punto quiere volver al paso anterior deberías recordar lo que el usuario ingresó.



[Angular - Angular coding style guide](https://angular.io/guide/styleguide)

[Buenas prácticas en Angular. Esta es una introducción básica a… | by Tatiana Molina | Angular Chile | Medium](https://medium.com/angular-chile/buenas-pr%C3%A1cticas-en-angular-74663897c059)

[airbnb/javascript: JavaScript Style Guide (github.com)](https://github.com/airbnb/javascript)

[Code Guide by @mdo](https://codeguide.co/)



