## Componentes

-   Las aplicaciones React están hechas de componentes .
-   Un componente es una parte de la IU (interfaz de usuario) que tiene su propia lógica y apariencia.
-   Un componente puede ser tan pequeño como un botón o tan grande como una página entera.
-   Los componentes de React son funciones de JavaScript:


```jsx
const MyButton = () => {
    return <button>i'am a button</button>;
};

const App = () => {
    const title = "Mi primero proyecto con React.js";
    return (
        <div className="container">
            <h1 className="text-primary">{title}</h1>
            <MyButton />
        </div>
    );
};

export default App;
```

componentes siempre en Mayúsculas

Fíjate que `<MyButton />` empieza con mayúscula. **Así es como sabes que es un componente React.** Los nombres de los componentes de React siempre deben comenzar con una letra mayúscula, mientras que las etiquetas HTML deben estar en minúsculas.

## Renderizado condicional[#](https://bluuweb.dev/05-react/#renderizado-condicional)

-   [condicional](https://es.reactjs.org/docs/conditional-rendering.html): En React, puedes crear distintos componentes que encapsulan el comportamiento que necesitas. Entonces, puedes renderizar solamente algunos de ellos, dependiendo del estado de tu aplicación.

```jsx
const MyButton = () => {
    return <button>i'am a button</button>;
};

const UserMessage = () => {
    return <h2>Bienvenido usuario</h2>;
};

const App = () => {
    const title = "Mi primero proyecto con React.js";
    const user = true;
    return (
        <div className="container">
            <h1 className="text-primary">{title}</h1>
            <MyButton />
            {user ? <UserMessage /> : "Offline"}
        </div>
    );
};

export default App;
```

¿Qué pasa si omitimos 'else'?

-   Podemos utilizar el operador lógico AND (&&)
-   Este operador lógico compara dos expresiones.
-   Si la primera se evalúa como "true", la sentencia devolverá el valor de la segunda expresión.
-   Si la primera expresión se evalúa como "false", la sentencia devolverá el valor de la primera expresión, en nuestro caso false.


```jsx
{
    user && <UserMessage />;
}
```

## Listas y keys[#](https://bluuweb.dev/05-react/#listas-y-keys)

-   [listas](https://es.reactjs.org/docs/lists-and-keys.html)

```jsx
const App = () => {
    const fruts = ["🍐", "🍌", "🍎"];
    return (
        <div className="container">
            <ul>
                {fruts.map((frut, index) => {
                    return <li key={index}>{frut}</li>;
                })}
            </ul>
        </div>
    );
};

export default App;
```

TIP

-   React usa el key prop para crear una relación entre el componente y el elemento DOM.
-   La biblioteca utiliza esta relación para determinar si el componente debe volver a renderizarse o no.
-   No se recomienda utilizar el índice de la matriz como key si sabe que la matriz no será estática.
-   Si key es un índice, reordenar un elemento en la matriz lo cambia. Entonces React se confundirá y volverá a renderizar el elemento incorrecto.
-   [fuente](https://sentry.io/answers/unique-key-prop/)

## props[#](https://bluuweb.dev/05-react/#props)

-   Se utiliza para enviar información al componente anidado.
-   La información que transmites de esta manera se llama props.


```jsx
const ItemFrut = (props) => {
    return <li>{props.frut}</li>;
};

const App = () => {
    const fruts = ["🍐", "🍌", "🍎"];
    return (
        <div className="container">
            <ul>
                {fruts.map((frut, index) => {
                    return <ItemFrut key={index} frut={frut} />;
                })}
            </ul>
        </div>
    );
};

export default App;
```

## Práctica props

-   Intenta hacer lo mismo pero con el componente **UserMessage**
-   Puedes utilizar la desestructuración de JS. [más info aquí](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

Opción #01:


```
const UserMessage = ({ user }) => {
    if (user) return <h2>Bienvenido</h2>;

    return <h2>Offline</h2>;
};
```

Opción #02:



```jsx
export default ({ user }) => <h2>{user ? "Bienvenido" : "offline"}</h2>;
```

## Manejando eventos[#](https://bluuweb.dev/05-react/#manejando-eventos)

-   [eventos](https://es.reactjs.org/docs/handling-events.html)
-   Los eventos de React se nombran usando camelCase, en vez de minúsculas.
-   Con JSX pasas una función como el manejador del evento, en vez de un string.


```jsx
const MyButton = () => {
    const handleClick = () => {
        console.log("me diste click");
    };

    return <button onClick={handleClick}>i'am a button</button>;
};
```

Con parámetros:


```jsx
const MyButton = () => {
    const handleClick = (name) => {
        console.log("me diste click: ", name);
    };

    return <button onClick={() => handleClick("🍎")}>i'am a button</button>;
};
```

## Componentes (modularizar)
-   [components](https://es.reactjs.org/docs/components-and-props.html)
-   Los componentes permiten separar la interfaz de usuario en piezas independientes, reutilizables y pensar en cada pieza de forma aislada.

components/MyButton.jsx



```jsx
const MyButton = () => {
    const handleClick = (name) => {
        console.log("me diste click: ", name);
    };

    return <button onClick={() => handleClick("🍎")}>i'am a button</button>;
};

export default MyButton;
```

App.jsx


```jsx
import MyButton from "./components/MyButton";
const App = () => {
    return (
        <div className="container">
            <h1 className="text-primary">{title}</h1>
            <MyButton />
        </div>
    );
};

export default App;
```