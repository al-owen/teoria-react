El hook `useState` es uno de los hooks básicos en React que permite a los componentes funcionales tener un estado local.

## ¿Cómo Funciona `useState`?

`useState` te permite agregar estado reactivo a un componente funcional. Cuando el estado cambia, el componente se vuelve a renderizar con el nuevo estado, permitiendo que tu aplicación responda a la entrada del usuario y otros eventos en tiempo real.

### Sintaxis Básica

La sintaxis básica de `useState` es la siguiente:

``` jsx
const [state, setState] = useState(initialState);
```

- **initialState:** Es el valor inicial para el estado. Puede ser cualquier tipo de dato: un número, un string, un booleano, un objeto, un array, etc.
- **state:** Es una variable que contiene el valor actual del estado. React se encarga de actualizar esta variable cuando el estado cambia.
- **setState:** Es una función que se usa para actualizar el estado. Cada vez que se llama a `setState`, React programa un nuevo renderizado del componente con el nuevo estado.
### Ejemplo Práctico

Supongamos que queremos crear un componente que muestre un contador con botones para incrementar y decrementar el valor:

``` jsx
import React, { useState } from 'react';  

function Counter() {
	const [count, setCount] = useState(0); // Inicializamos el contador en 0    
	return (
		<div>
			<h1>{count}</h1>
		    <button onClick={() => 
			    setCount(count + 1)}>Incrementar
			</button>
			<button onClick={() =>
				setCount(count - 1)}>Decrementar
			</button>
	     </div>   
	); 
}
```

En este ejemplo, el contador se inicia en `0`. Los botones usan la función `setCount` para actualizar el estado. Cuando se hace clic en "Incrementar", se llama a `setCount` con el nuevo valor de `count + 1`. Similarmente, "Decrementar" reduce el valor del contador.

### Usos Comunes

`useState` es extremadamente versátil y puede ser usado para controlar:

- Formularios, manteniendo el valor de los inputs.
- Interacciones del usuario, como abrir/cerrar modales, toggles entre modos (ej. claro/oscuro).
- Cualquier otra pieza de datos que debe persistir durante el ciclo de vida del componente y puede cambiar en respuesta a alguna acción.