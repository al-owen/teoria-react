Para añadir event listeners en React, normalmente utilizas la sintaxis de JSX para manejar eventos en tus componentes. React simplifica el proceso de trabajo con eventos del DOM proporcionando su propio sistema de eventos sintéticos, que aseguran que los eventos funcionen de manera idéntica en todos los navegadores. 

1. **Definir el Event Handler:** Primero, necesitas definir una función en tu componente que maneje el evento. Esta función es conocida como un "event handler".
    
``` jsx
function handleClick() {
	console.log('El botón fue presionado.'); 
}
```
    
2. **Asignar el Event Handler a un Elemento:** Después, asignas esta función como un event handler a un elemento JSX usando una prop especial. React utiliza nombres de propiedades que siguen la convención `on<EventName>`, como `onClick`, `onChange`, `onSubmit`, etc. Estos nombres de eventos son camelCase, lo cual es importante porque JSX es case-sensitive.
    
``` jsx
function App() {
	return (
	     <button onClick={handleClick}>
	        Haz click aquí     
		</button>
   ); 
}
```
    
3. **Usar Eventos con Argumentos:** Si necesitas pasar argumentos adicionales al event handler, puedes hacerlo envolviendo el handler en una función anonima (de flecha). Esto es especialmente útil cuando necesitas manejar eventos en listas de elementos generados dinámicamente.
    
``` jsx
function deleteItem(id) {
	console.log(`Eliminando item con id ${id}`); 
}
function TodoItem({ id }) {
	return (     
		<button onClick={() => deleteItem(id)}>
		   Eliminar
		</button>
	);
}
```
    
4. **Eventos en [[Componentes]] de Clase:** Si estás trabajando con componentes de clase, generalmente declararás el event handler como un método de la clase. Para asegurarte de que `this` en tus handlers se refiera a la instancia del componente, es común vincular el método en el constructor de la clase o usar la sintaxis de campos de clase pública para definir tus handlers.
    
``` jsx
class ToggleButton extends React.Component {
	constructor(props) {
		super(props);     
		this.state = { isOn: true };
		this.handleClick = this.handleClick.bind(this);   
	}
	
	handleClick() {
		this.setState(prevState => ({
			isOn: !prevState.isOn     
		}));
	}
	
	render() {
		return (
		    <button onClick={this.handleClick}>
			{this.state.isOn ? 'ON' : 'OFF'}
			</button>
		);  
	} 
}
```
    
5. **Asegurar el Rendimiento:** Cuando asignes handlers en un componente con muchos re-renderizados, como aquellos que tienen listas grandes o que cambian con frecuencia, considera el uso de memorización o mover la definición del handler fuera del componente si no depende de las props o el estado del componente para reducir la creación de funciones innecesarias