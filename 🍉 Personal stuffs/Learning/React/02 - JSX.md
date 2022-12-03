## JSX: JavaScript + XML

-   Como ha visto, hemos estado usando lo que parece HTML en nuestro código React, pero no es HTML del todo. Esto es JSX , que significa JavaScript XML.
-   El uso de JSX no es obligatorio para escribir React.
-   Debajo del capó, se está ejecutando `createElement`, lo que toma la etiqueta, las propiedades y los elementos secundarios del componente y muestra la misma información.
-   JSX está más cerca de JavaScript, no de HTML, por lo que hay algunas diferencias clave a tener en cuenta al escribirlo.
    -   `className` se usa en lugar de `class` para agregar clases CSS, ya que `class` es una palabra clave reservada en JavaScript.
    -   Las propiedades y métodos en JSX son camelCase.
    -   Las etiquetas de cierre automático deben terminar en una barra inclinada,  
        Ej. `<img />`
    -   Su componente tampoco puede devolver varias etiquetas JSX. Tienes que envolverlos en un padre compartido, como un envoltorio `<div>...</div>` vacío o: `<>...</>`

Las expresiones de JavaScript también se pueden incrustar dentro de JSX usando llaves, incluidas variables, funciones y propiedades.

jsx

```js
const App = () => {
    const title = "Mi primero proyecto con React.js";
    return (
        <div className="container">
            <h1 className="text-primary">{title}</h1>
        </div>
    );
};

export default App;
```

jsx

```js
const App = () => {
    const title = "Mi primero proyecto con React.js";
    const classColors = {
        primary: "text-primary",
        info: "text-info",
    };
    return (
        <div className="container">
            <h1 className={classColors.primary}>{title}</h1>
            <p className={classColors.info}>Lorem ipsum dolor sit.</p>
        </div>
    );
};

export default App;
```