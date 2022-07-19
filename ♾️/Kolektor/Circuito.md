# Metodologia de trabajo arquitectura

Arquitectura no se encuentra dentro del circuito de desarrollo, por lo que las tareas se toman en el transcurso de la semana mediante pedidos por mail o teams.

## Metodologia en FE:
_En FE la mayor parte de los pedidos vienen por parte de UX para el desarrollo o ajustes de componentes en la libreria transversal (kolektor-ui-components)_ #kui 

### Una vez recibido el pedido pueden darse dos situaciones: 

 #### Componente ya existente
 - Se debe buscar el componente a modificar dentro de la librería.
 
 #### Componente nuevo:
 -  Siempre debe evaluarse si realmente es candidato a estar en la librería. Lo ideal es que este vaya a ser usado en diferentes proyectos y lugares en la web.

## Primer paso:

- Agregar un card en el trello de Arquitectura con la tarea correspondiente, y detallando un poco su desarrollo. 
- Poner la card en _doing_ una vez empieces a realizar el pedido.

_En arq se maneja con [kanban](https://treze.es/agile/metodologia-kanban-con-trello-organizate-con-eficacia/#:~:text=Metodolog%C3%ADa%20Kanban%20en%20Trello&text=El%20objetivo%20principal%20de%20representar,distribuci%C3%B3n%20y%20seguimiento%20del%20trabajo.) y tenemos un trello para eso._



## _Segundo paso_:

Ya sea para un componente que existe o uno nuevo lo primero a hacer es crear un rama desde `develop` con la siguiente nomenclatura: `NEXT/fix/input-date/placeholder-bug`
###### Esta nomenclatura consta de 4 partes divididas por "/"
1. NEXT -> Indica que es próximo a publicarse en la librería.
   
2. Dependiendo de lo que implica el desarrollo en la rama puede ser:
  - feat: una nueva característica o función.
  - fix: correción de errores.
  - style: cambios que no afectan al significado del código (espacios en blanco, formato, falta de punto y coma, etc.).
  - test: Agregar test faltantes o corregir los existente.
`(build, ci, docs, refactor, perf) `
  _Esto esta basado en la [angular convention](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#-commit-message-guidelines) y sus mensajes de commits, por lo tanto, si hay alguna duda se pueden ver los casos ahi mismo. _
  
  3. En la tercera parte del nombre se coloca el o los componentes a modificar:  _input-date, select, card, etc._ En el caso de que sean mas de dos se debe usar _various_.

  4. Por ultimo se coloca una o dos palabras que represente el cambio a realizar: _placeholder, numeric-field, html-text, setName-function_. (Siempre que se pueda, en caso de que sea complicado de representar en pocas palabras puede ponerse _various_)

## Tercer paso:

Una vez creada la rama se debe realizar los cambios dentro de la misma. Esto incluye:
- Desarrollo o modificacion del componente.
- Test unitarios.
- Desarrollo o modificacion de la documentación(_archivo md con markdown_).
- Creación de las stories para storybook. Ver en [[Kolektor/Crear stories y documentación #kui]].

Todos los componentes modificados y o agregados deben contar con los test unitarios para poder pasar el coverage. (_Esto es necesario ya que antes de cada commit se ejecuta husky que pasa los tests y linter en todo el proyecto_).

### Cuarto paso:

Pushear la rama al repositorio y preparar el Merge request, este debe seguir el siguiente formato: 
1. La rama que se va mergear debe ser la trabajada y tiene que estar actualizada con la ultima versión de _develop_.
2. La rama a mergear con la anterior tiene que ser _develop_. Por lo tanto:
   `NEXT/feat/input_input-date/number-field_text-field ---> develop`
3. El merge request tiene que contar con una descripcion de los cambios y si es posible con imagenes de lo mismo: ![[Pasted image 20220628113905.png]]
 
4. Se debe pasar el MR a algun compañero para que lo revise y le de el okey. 
5. Una vez Mergeado puede publicarse la nueva versión de la librería. [[Publicación]]

## Quinto Paso:

Avisar por el canal de la comunidad la publicación de la nueva de la versión de la kui.

![[Pasted image 20220628120227.png]]
![[Pasted image 20220628120233.png]]


`Nota: Si bien gran parte del desarrollo en este equipo se centra en el la kui, tambien damos soporte a diferentes equipos y buscamos siempre la mejor manera de implementar las soluciones que surgen. Otras tareas que pueden aparecer:`

- Revisar logs de los proyectos para sulucionar bugs.
- Soporte a equipos de desarrollo.
- Revisar plugins en WordPress.
- Agregar tags de Google Tag Manager.
- Investigacion de herramientas que faciliten el trabajo a los desarrolladores.

`

