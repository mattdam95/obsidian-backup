```js
let initialCounter = 0

0 // -> falsy
Boolean(0) // -> falsy

//Better this - Solo lo evalua si realmente lo necesita, cuando initalCounter sea Falsy
initialCounter ||= 25
initalCounter ??= 25 

//Than this - Evalua siempre

initialCounter = initialCounter ?? 25
initialCounter = initialCounter || 25
```

##### Ternarios

```js
//Ternarios: 

let firstCheck = false
let secondCheck = false
let access = firstCheck ? "Acceso Denegado" : secondCheck ? "Acceso Denegado" : "Acceso Permitido";

console.log( access ); // muestra "Acceso Permitido"
```


