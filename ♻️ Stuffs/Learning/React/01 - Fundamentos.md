## Qué son los Hooks

Los Hooks son una nueva incorporación en React 16.8. Te permiten usar estado y otras características de React sin escribir una clase.

Aviso

¿No entendieron nada? no se preocupen lo veremos con la práctica.

## Crear app con React

[https://es.reactjs.org/docs/create-a-new-react-app.html#create-react-app(opens new window)](https://es.reactjs.org/docs/create-a-new-react-app.html#create-react-app)

Tienes que tener instalado [Node.js (opens new window)](https://nodejs.org/es/)en su últimas versiones.

```
npx create-react-app my-app
cd my-app
npm start
```

## Mi primer componente

Crea una carpeta y archivo `components/Contador.js` el cual se verá así:

```js
import React from 'react';

const Contador = () => {
    return (
        <h3>Contador</h3>
    );
}
 
export default Contador;
```

Lo mandamos a llamar en `App.js`

```js
import React from 'react';
import Contador from './components/Contador'

function App() {
  return (
    <Contador />
  );
}

export default App;
```

Wualá tienes tu primer componente listo 😃

## [#](https://bluuweb.github.io/react-udemy/02-hooks-fundamentos/#hook-de-estado)Hook de estado

Este ejemplo renderiza un contador. Cuando haces click en el botón, incrementa el valor: [https://es.reactjs.org/docs/hooks-overview.html#state-hook(opens new window)](https://es.reactjs.org/docs/hooks-overview.html#state-hook)

```js
import React, { useState } from 'react';

const Contador = () => {
  // Declara una nueva variable de estado, que llamaremos "count".
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```