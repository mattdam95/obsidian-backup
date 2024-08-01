
#### Multirepositorios

En esta estrategia cada componente o parte de un proyecto con entidad propia se aloja en un repositorio diferente. Por ejemplo, si tenemos un proyecto que tiene un _frontend_ y un _backend_, cada uno de ellos se alojaría en un repositorio diferente. Incluso, dentro del _frontend_ podriamos separar en diferentes repositorios el _design system_ (componentes visuales), el tema, etc.\
**Ventajas**

- Tener un versionado independiente
- Despliegues independientes
- Ayuda a definir el control de acceso
- Las ramas de los repositorios son más pequeñas

**Desventajas**

- Es difícil de orquestar las nuevas versiones y sincronizar entre los repositorios
- Para crear una nueva _feature_ hay que crear diferentes _pull request_ en los diferentes repositorios. Esto cuesta mucho tiempo
- Fragmentación de equipos y ciclos de conocimiento
- El ciclo de _feedback_ es lento
- Mucho trabajo manual

---

#### Monorepositorios

Son repositorios que contienen todo el código de una aplicación. Este repositorio tendría paquetes separados, y cada paquete tiene una entidad propia.\
El monorepositorio debe tener (como todo proyecto) una buena estructura de carpetas.\
**Ventajas**

- Cuando una persona nueva entra al equipo solo tiene que clonar un solo repositorio y ya tiene el proyecto.
- La refactorización de código es más fácil.
- Crear una _feature_ en un solo _pull request_
- Todo los equipos puede estar trabajando en el mismo código

**Desventajas**

- Ciclos pueden ser un poco más lentos
- Se requiere de la descarga de todo el código base para trabajar

---

Lo mejor en un monorepositorio es usar el mismo _stack_ tecnológico, mismo lenguaje de programación, mismo _framework_, las mismas reglas de _linter_.
