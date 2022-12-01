-   **Framework**  
    Es un conjunto de herramientas y patrones ya definidos, que nos crean restricciones, a cambio de tener un entorno de trabajo estandarizado, con soluciones comunes a problemas frecuentes.

-   Existen muchos _frameworks_ que nos ayudan a aplicar patrones de diseño, y además nos ofrecen los diferentes modos de renderizado.
-   La elección de un _framework_ tiene un impacto en la forma en la que diseñamos nuestra arquitectura.

#### Next.js

Es el _framework_ que usa Platzi. Es un _framework_ de React que nos ofrece:  
- Server-side rendering  
- Static-site generation  
- Incremental static regeneration

-   Nos ayuda a ordenar el código, ya que debemos seguir una estructura de carpetas para poder generar las rutas de nuestra aplicación.  
    **Ventajas de Next.js**
-   Tiene cero configuración
-   Las compilaciones son súper rápidas
-   Solución de internacionalización.
-   Posibilidad de crear _endpoints_ para tu _backend_, simplemente creando archivos en la carpeta “pages/api”
-   Nos ofrece todo lo que necesitamos para crear una aplicación web completa.

#### Remix

-   Lo más destacable es la posibilidad de crear rutas anidadas
-   Simplifica la gestión de los estados en la validación de datos de formularios

#### Nuxt.js

Ofrece renderizado en el servidor, en el cliente y la generación de páginas estáticas de forma incremental.

-   **_Frameworks_ que ofrecen Islas**

1.  **Astro**  
    Es agnóstico a la biblioteca de UI que quieras usar.
2.  **Deno Fresh**  
    No tiene un paso de compilación, ya que la transformación de nuestro código se hace al vuelo. Esto nos permite tener un entorno de desarrollo muy rápido, con despliegues casi instantáneos, y que podemos hacer cambios casi en tiempo real.

#### ¿Cuál _framework_ debería elegir?

Depende de tus necesidades y preferencias.

-   Next.js es la opción más segura. Es el _framwork_ que más está creciendo.

#### _Frameworks_ que no están basados en JavaScript

-   Django (basado en Python)
-   Laravel (basado en PHP)
-   Ruby on Rails (basado en Ruby)