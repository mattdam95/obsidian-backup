---
date created: 2022-12-17 19:54
---

#### **Renderizado web**

Es la representación gráfica del contenido de una página, es decir, el proceso necesario para mostrar una página web en un navegador.\
**Server-side Rendering**\
El renderizado de las web se ha hecho, de forma histórica, en el servidor. Es decir, que el servidor se encarga de generar el HTML que se va a mostrar al usuario.

- **Ventajas del Server-side Rendering**
  1. El servidor puede generar el HTML de forma dinámica, así que puede mostrar diferentes datos dependiendo de la petición del usuario. Además, si quieres hacer SEO, es vital, ya que tu aplicación web será indexada por Google de manera más fácil. No necesita ejecutar nada de JavaScript para saber qué información muestra tu página. También, si un usuario tiene JavaScript deshabilitado, tu aplicación pordría seguir funcionando.
  2. Rendimiento percibido por el usuario. Como el servidor ya devuelve el HTML, el usuario no tiene que esperar que se cargue el JavaScript para ver la página.
- **Desventajas del Server-side Rendering**
  1. El servidor tiene que generar una archivo HTML, lo que hace que el tiempo de respuesta inicial pueda ser más lento

**Client-side Rendering**\
Se ha popularizado en los últimos años.

- El servidor no genera el archivo HTML o genera uno muy básico. Lo único que se encarga es de enviar el código JavaScript necesario para que el navegador pueda generar el HTML en el cliente
- **Ventajas del Client-side Rendering**
  1. El servidor no tiene que generar nada, por lo que evitamos ese trabajo. Así es más económico.
- **Desventajas del Client-side Rendering**
  1. No es tan fácil de indexar por Google, ya que necesita ejecutar el JavaScript para saber qué información tiene tu página.
  2. Si el usuario tiene JavaScript deshabilitado, tu aplicación no va a funcionar.
  3. El usuario tiene que esperar a que se descargue JavaScript para ver la página, por lo que el rendimiento percibido puede ser peor.

**Static-Site Generation**\
Se ha popularizado últimamente, ya que tiene una mezcla de los dos anteriores.\
En lugar de generar el HTML en el servidor, en cada petición, lo hacemos solo en el momento de la compilación. Así, el servidor no tiene que generar el HTML, solo tiene que servirlo.\
Así sí podemos indexar nuestra página para SEO

- **Desventajas del Static-Site Generation**
  1. Al ser estático no se genera el HTML de forma dinámica\
     **Incremental Static-Regeneration**\
     En lugar de generar un HTML estático, en el momento de la compilación, lo hace en el momento de la petición.\
     El servidor genera el HTML estático, para cada petición, pero solo sino existe. Si el usuario vuelve a visitar la misma página, el servidor devuelve el HTML ya creado.\
     **Islas**\
     Fomenta pequeños trozos de interactividad dentro de las páginas web renderizadas, ya sea por el servidor o de forma estática.

---

#### Ejemplos de uso

- **Página de búsqueda de Platzi**\
  Lo mejor es usar “server-side rendering”, ya que es una página que tiene mucha información dinámica. El servidor genera un HTML de forma dinámica para cada petición
- **Página principal de Platzi**\
  Lo mejor, para esta _landing page_, lo mejor es usar “static-side generation”, ya que es una página que tiene información que no cambia mucho.
- **Página de un curso**\
  Lo mejor sería “incremental static regeneration”, ya que es una página que tiene información dinámica (como las valoraciones) pero tampoco cambia con mucha frecuencia.
- **Página de lista de comentarios**\
  Lo mejor es usar “client-side rendering”, ya que no es información que deseamos indexar en los motores de búsqueda, y si el usuario tiene JavaScript deshabilitado, no pasa nada.
