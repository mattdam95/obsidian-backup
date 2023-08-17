#Microfrontend 
## Configuración inicial
- En la la terminal correr el siguiente comando:
#### Para angular menor a 14
  `ng add single-spa-angular`
#### Para angular mayor a 14
  `ng add single-spa-angular --project my-cool-app`

>Revisar que versión de single-spa necesitan segun la versión de angular en el siguiente link: [single-spa-angular](https://single-spa.js.org/docs/ecosystem-angular/)

Seguir los pasos del schematics.

- Instalar de vuelta todos los paquetes con `npm install`
- Una vez hecho esto es necesario revisar algunos archivos que generó el schematics tales como: main.single-spa.ts ( Dentro del mismo hay que asegurarse que esté cargando el modulo principal de la aplicación correctamente) y tambien el tsconfig.app.json para verificar que esté incluido el archivo anterior en el mismo.

Luego, si el proyecto tiene rutas hay que agregar la siguiente linea al app.routing.module.ts: ` providers: [{ provide: APP_BASE_HREF, useValue: '/' },]`. En el use value tiene que ir el path base del proyecto.

