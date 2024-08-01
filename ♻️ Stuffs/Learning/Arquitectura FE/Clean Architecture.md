
- Patrón de arquitectura _clean architecture_ o arquitectura limpia: esta arquitectura también se basa en capas
  - **Entidades**: son los objetos de negocio. Por ejemplo, en Platzi las entidades podrían ser los cursos, los profesores, los estudiantes, etc.
  - **Casos de uso**: son las reglas de negocio. Por ejemplo, en Platzi podría ser las creación de un curso, que un estudiante se inscriba a un curso, mostrar las valoraciones de un curso, etc.
- Las capas “entidades” y “casos de uso” son el núcleo que se encarga de la lógica de nuestro negocio. Es la forma en la que codificamos o describimos sómo se usa en el mundo real, y es lo que realmente marca la diferencia con otras aplicaciones y lo que le da el valor diferencial al usuario.
  - **Adaptadores de interfaz**: en esta capa se encuentran los controladores, los presentadores, lo modelos de vista. Acá podriamos tener todo el patrón MVC.
  - **Bibliotecas de terceros**: acá se encuentran los frameworks y drivers. Por ejemplo en Platzi podriamos tener la biblioteca de React, de Redux, la de React Router, etc.\
    .
- Todas estas capas se basan en una regla: nada, nada de una capa interior puede conocer nada de una capa exterior. Es decir, que la capa “entidades” no puede conocer nada de la capa “capas de uso”. A esto se le llama **“regla de la dependencia”**.
- La “regla de la dependencia” es la base en la que se sustenta que una aplicación siga el patrón de _clean architecture_.

---

#### Desventaja del _clean architecture_

- Puede que la curva de aprendizaje sea muy pronunciada. Conseguir que todo el equipo sepa y entienda aplicar esta arquitectura no es una tarea fácil.
- La separación de las capas es un trabajo manual. Requiere experiencia y es fácil confundir responsabilidades.
- En general es un patrón que se aplica mejor a aplicaciones grandes.
- La velocidad de desarrollo al principio sea más lenta

---

#### Ventajas

- Ayuda a estructurar el código y la navegación por el mismo.
- Cambios en una capa no afectan a otras.
- Poder crear tests que solo prueben, por ejemplo, la lógica del negocio

### _Next -->_ [[Screaming Architecture]]
