El hook `useEffect` en React es una herramienta poderosa que permite a los componentes funcionales realizar efectos secundarios en sus renderizados.

### ¿Cómo Funciona `useEffect`?

El hook `useEffect` se utiliza para llevar a cabo tareas que están separadas de la UI principal y que podrían bloquear la actualización del DOM si se realizan de manera síncrona. Algunos ejemplos de estos efectos secundarios incluyen:

- Fetching de datos
- Suscripciones a servicios o APIs
- Modificación manual del DOM
- Temporizadores y intervalos

### Sintaxis Básica

La sintaxis básica de `useEffect` es la siguiente:

``` jsx
useEffect(() => {
	// Aquí estaria el código
	// Función de limpieza opcional
	return () => {
	     // Código de limpieza aquí   
	}; 
}, [dependencias]); // Lista de dependencias
```

### Parámetros de `useEffect`

1. **Función de Efecto:** Es una función que contiene el código del efecto secundario. Puede ser tan simple como imprimir algo en la consola o tan complejo como realizar una solicitud de red.
    
2. **Array de Dependencias:** Es un array que determina cuándo se debe ejecutar el efecto. Cuando los valores en el array cambian entre renderizados, React garantiza que el efecto se ejecutará después de actualizar el DOM. Algunos usos comunes incluyen:
    
    - **Sin dependencias (`[]`):** El efecto se ejecuta solo después del primer renderizado y no se repite.
    - **Con dependencias (`[vars]`):** El efecto se ejecuta inicialmente y luego solo cuando las `vars` cambian.
    - **Sin array de dependencias:** El efecto se ejecuta después de cada renderizado.

### Función de Limpieza

Dentro de `useEffect`, puedes devolver una función de limpieza que se ejecuta antes de que el componente se desmonte o antes de que el efecto se vuelva a ejecutar. Esto es útil para limpiar cualquier suscripción, temporizadores, o cualquier otro recurso que deba liberarse para evitar fugas de memoria.

### Ejemplo Práctico

``` jsx
import { useState, useEffect } from 'react';
function Timer() {
	const [count, setCount] = useState(0);
	useEffect(() => {
	    const interval = setInterval(() => {
			setCount(currentCount => currentCount + 1);
		}, 1000);
		return () => clearInterval(interval);
	}, []);
    return <h1>{count}</h1>;
}
```

En este ejemplo, `useEffect` se utiliza para configurar un temporizador que actualiza un contador cada segundo. La función de limpieza `clearInterval` se llama para limpiar el intervalo cuando el componente se desmonta o antes de re-ejecutar el efecto si `useEffect` tenía dependencias y estas cambian.