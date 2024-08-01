
#### Backend for Frontend

Es una arquitectura que consiste en crear una API que se adapta a las necesidades del _frontend_, así puedes optimizar al máximo la peticiones que se hacen, la información que devuelve, y al final, la experiancie del usuario (es lo que más nos interesa).

- Este paradigma permite crear una abstracción sobre nuestras APIs

- Reduce la lógica a escribir en nuestras vistas

- Puede ser implementado con cualquier tecnología

**GraphQL**\
Es un lenguaje de consulta y patrón que permite definir una API que se adapte a las necesidades del cliente que las consulta. La ventaja es que se hace desde un solo _endpoint_. Así, no se debe crear una API para cada necesidad.

- Si necesitas muy pocos _endpoints_, o los datos que vas a tratar son muy simples, quizá GraphQL no sea la mejor opción.

**TRPC**\
Permite construir y consumir APIs totalmente tipadas gracias a TypeScript, sin necesidad de definir esquemas o generar código adicional
