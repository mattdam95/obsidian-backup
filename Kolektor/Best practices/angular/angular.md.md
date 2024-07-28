# Angular

![](https://d585tldpucybw.cloudfront.net/sfimages/default-source/blogs/templates/angulart2-light-1200x303.png?sfvrsn=4af99b70_4 "AngularT2-light-1200x303")

## Utilizar Lazy Loading

El lazy load  permite cargar partes de la aplicación según demanda, en lugar de cargar todo de una vez. Esto puede mejorar el rendimiento de la aplicación al reducir tanto el tiempo de carga inicial como la cantidad de memoria requerida para ejecutar la aplicación.

Se puede utilizar el Angular Router.

Crea un nuevo módulo para la ruta. Este módulo debe tener sus propios componentes, servicios y rutas.

En el módulo de enrutamiento principal, importa el nuevo módulo y añádelo como una ruta secundaria. Utiliza la propiedad loadChildren para especificar la ruta al archivo del nuevo módulo.

```js
//Angular 15 en adelante
const routes: Routes = [
  { path: 'lazy', loadChildren: './lazy/lazy.module#LazyModule' },
  //other routes
];

//Hasta Angular 14
const routes: Routes = [  
{ path: 'lazy', loadChildren: () => import('./lazy/lazy.module').then(m => m.LazyModule) },  
// ...  
];
```


## Utilizar la Detección de Cambios OnPush

Utilizar la detección de cambios OnPush. De forma predeterminada, Angular utiliza una estrategia de detección de cambios "CheckAlways", que comprueba los cambios en todos los componentes en cada evento del DOM (click, key press, etc). Esto puede llevar a un rendimiento lento.

La detección de cambios OnPush, solo comprueba los cambios en un componente cuando cambia un valor de @Input o se emite un evento desde el template del componente. Esto mejora el rendimiento de la aplicación.  [Documentación de Angular](https://angular.io/api/core/ChangeDetectionStrategy).

## Utilizar un Build de tipo Production-Ready

El build debe estar optimizada para el rendimiento y la seguridad, e incluir características como **minificación**, **tree-shaking** y **compilación por adelantado (AOT)**.

La minificación reduce el tamaño del código al eliminar los espacios en blanco innecesarios y los comentarios. Tree-shaking elimina el código no utilizado de la compilación, reduciendo aún más el tamaño del código. La compilación AOT, precompila los componentes y las plantillas de la aplicación en tiempo de compilación, lo que mejora el rendimiento, la seguridad y la depuración de la aplicación.

Esto en Angular CLI  se logra ejecutando el comando `ng build --prod`.

**Links con mas info:**
[Minification and Tree Shaking in Angular (c-sharpcorner.com)](https://www.c-sharpcorner.com/article/minification-and-tree-shaking-in-angular/)
[Angular - ng build](https://angular.io/cli/build)
[Building Angular apps • Angular](https://angular.dev/tools/cli/build)

## Arquitectura Modular y Standalone Components

La arquitectura modular permite una mejor organización y mantenibilidad de la base de código. Con una arquitectura modular, la funcionalidad se organiza en módulos de características individuales y módulos compartidos.

*Modulos*
![[Pasted image 20240517115817.png]]

VS

*Standalone*
![[Pasted image 20240517115831.png]]


Esta es lo que angular impulsaba hasta la version 15 del mismo, hoy se encuentra en un procesto de cambio hacia los standalone components donde la idea principal es que cada componente se su propio modulo. De esta manera dejamos de depender de la capa de modulos extras que tiene las viejas versiones de angular. 

Desde nuestro lado impulsamos a migrar a hacia standalone components siempre que el proyecto tenga la posibilidad.

**Links con mas info:**
[Angular Standalone Components y su impacto en la modularidad (codigoencasa.com)](https://codigoencasa.com/angular-standalone-components-y-su-impacto-en-la-modularidad/)

## Linting

Linting es el proceso de comprobar automáticamente el código en busca de errores potenciales e inconsistencias en el estilo del código. Hay varias herramientas de linting  disponibles para proyectos con Angular, como **TSLint** y **ESLint**.

A partir de angular 12 utilizamos ESLint y en anteriores usamos TSLint. 

## Mantener el Proyecto y las Dependencias Actualizadas

Esto es de lo mas importante a la hora de hablar buenas practicas y es tan sencillo como mantener las dependencias acualizadas ya que permite aprovechar nuevas características y corregir problemas de seguridad. 

Para facilitar este proceso con angular tenemos la siguiente pagina:
[Angular Update Guide](https://update.angular.io/)





TODO: Agregar cosas de este link:
[Angular: Best Practices for 2023 | Bits and Pieces (bitsrc.io)](https://blog.bitsrc.io/angular-best-practices-to-adapt-in-2023-bf67122b37ab)
