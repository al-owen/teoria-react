El operador de propagación (spread operator) en JavaScript es representado por tres puntos (`...`) y permite expandir los elementos de un iterable (como un array o un objeto) en situaciones donde se esperan múltiples argumentos (en llamadas a funciones) o múltiples elementos (en arrays) o pares clave-valor (en objetos).

### En Arrays

El operador de propagación puede ser utilizado para copiar elementos de un array a otro, facilitando la combinación de arrays o la inserción de nuevos elementos. Por ejemplo:

``` javascript
let parte1 = [1, 2, 3];
let parte2 = [4, 5, 6];
let combinado = [...parte1, ...parte2]; // Resulta en [1, 2, 3, 4, 5, 6]
```

También se puede usar para pasar elementos de un array como argumentos independientes a una función:

```javascript
function suma(x, y, z) {
	return x + y + z;
}
let numeros = [1, 2, 3];

console.log(suma(...numeros)); // pasa cada elemento del array como un argumento: 
```

### En Objetos

Cuando se usa con objetos, el operador de propagación puede copiar las propiedades de un objeto en otro, lo cual es útil para crear nuevos objetos a partir de los existentes, modificando o añadiendo propiedades sin modificar el objeto original:

``` javascript
let obj1 = { foo: 'bar', x: 42 };
let obj2 = { foo: 'baz', y: 13 };
let clonedObj = { ...obj1 };
let mergedObj = { ...obj1, ...obj2 }; // { foo: "baz", x: 42, y: 13 }
```

En este ejemplo, `mergedObj` contiene todas las propiedades de `obj1` y `obj2`. Si ambos objetos tienen una propiedad con el mismo nombre, el último objeto (en este caso `obj2`) tiene prioridad, y su valor sobrescribe el del primero.

### Usos Comunes en React

En React, el operador de propagación es comúnmente utilizado para pasar props a componentes de forma más eficiente:

``` jsx
function Componente(props) {
	return <h1>{props.saludo}</h1>;
}

let misProps = { saludo: "¡Hola mundo!" }; 
<Componente {...misProps} />; // Pasa 'misProps' como el prop 'saludo' al Componente
```

Este operador simplifica la transmisión de props y la manipulación de objetos y arrays, haciendo el código más limpio y fácil de entender.