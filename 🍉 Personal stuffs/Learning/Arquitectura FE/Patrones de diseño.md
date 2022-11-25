### Frontend

**Patrón MVC (Model–view–controller)**

-   Es uno de los patrones de arquitectura más conocidos y más utilizados.
-   Fue introducido en 1979.
-   Hoy en día ya no es tan usado; sigue siendo un patrón muy util para entender la arquitectura de software.
-   **Se basa en tres capas**:
    -   **Modelo**: se encarga de la lógica de negocio, es decir, de la lógica que procesa los datos de nuestra aplicación.
    -   **Vista**: se encarga de mostrar os datos del modelo, es decir, la interfaz del usuario.
    -   **Controlador**: gestiona las interacciones del usuario con la vista y comunicarlos al modelo.

-   **Ejemplo en la vida real**: sería un restaurante…
    -   **Modelo**: sería la cocina
    -   **Vista**: carta de platos
    -   **Controlador**: camarero o mesonero; se encarga de gestionar las peticiones de los clientes a la cocina.
-   Separa la lógica de negocio (procesamiento de datos) de la lógica de presentación (mostrar los datos).

**MVVM (Model–view–viewmodel)**

-   Es una evolución del MVC
-   **Diferencia**: en lugar de contar con un controlador cuenta con un _view model_, mientras el “controlador” sincroniza la vista con el modelo manualmente, lo que hacemos con el _view-model_ es que se encargue de hacerlo automaticamente.
-   **Problema histórico**: al aplicarse a la web falta la gestión del estado.

**FLUX**  
Patrón que ha revolucionado la arquitectura en el frontend. Fue creado por Facebook (Meta).

-   Se basa en un único flujo de datos. Todos los datos viajan en un único sentido
-   **Vista**: sería la misma que tenemos en el patrón MVC
-   Cuando el usuario interactua con la vista, esta le envia una acción al _dispatcher_
-   **_Dispatcher_**: es el encargado de enviar la acción a todas las _stores_
-   Las _stores_ son las encargadas de procesar la acción y actualizar el estado de la aplicación. Cada vez que eso ocurre, el estado de la aplicación cambia y los _stores_ notifican a la vista para que refleje estos cambios.
-   Una evolución de este patrón (Flux) es el que aportaba Redux donde se añadia un nuevo componente: el _reducer_.
-   **_Reducer_**: es el encargado de procesar la acción y actualizar el estado de la aplicación, y es que, en lugar de que sean las _stores_ que se encarguen de esto, lo que hacemos es que el _reducer_ se encargue de ello.

---

-   En general queremos que nuestra aplicación sea fácil de mantener y fácil de extender, y una de las formas de lograrlo es separando responsabilidades.
-   Hemos evolucionado a un patrón mucho más reactivo, donde la cascada de cambios se produce de forma automática.
-   Aplicar un patrón al 100% es complicado.
-   A veces no se sabe aplicar bien cada patrón.
-   Evita adoptar uno de estos patrones sin antes entender bien qué es lo que te aporta