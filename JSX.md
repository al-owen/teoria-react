JSX es una extensión sintáctica para JavaScript utilizada principalmente con React para describir cómo debería lucir la interfaz de usuario. Combina la potencia de JavaScript con la facilidad de uso del HTML.

1. **Sintaxis Similar a HTML:** JSX se escribe con una sintaxis que se asemeja mucho al HTML. Puedes usar etiquetas que parecen exactamente igual que en HTML, como `<div>`, `<span>`, `<a>`, y otras más. Estas etiquetas pueden anidarse, tener atributos y ser incorporadas dentro del código JavaScript. 

``` jsx
const element = <div className="container">Hola, mundo!</div>;
```
   
2. **Incorporación de Expresiones de JavaScript:** Puedes incorporar cualquier expresión de JavaScript dentro de JSX simplemente encerrándola entre llaves `{}`. Esto te permite insertar valores dinámicos en tu JSX. Por ejemplo, si tienes una variable de JavaScript, puedes insertarla directamente en tu JSX.

``` jsx
const name = 'Juan'; 
const element = <h1>Hola, {name}</h1>;
```

3. **Atributos con JavaScript:** Similar a las expresiones, puedes usar JavaScript para definir los atributos de las etiquetas JSX. Esto es útil para aplicar estilos dinámicamente, asignar clases o cualquier otro atributo HTML basado en condiciones o datos dinámicos.

``` jsx
const user = { 
	firstName: 'Marta',
	lastName: 'García' 
}; 
const greeting = <img src={user.avatarUrl} alt={`Avatar de ${user.firstName}`}/>;
``` 

4.  **[[Componentes]] en JSX:** JSX no solo te permite usar etiquetas HTML, sino también componentes React. Cuando usas un componente en JSX, lo haces escribiéndolo como una etiqueta HTML. Los componentes siempre deben empezar con mayúscula para diferenciarlos de las etiquetas HTML estándar.

``` jsx
function Welcome(props) {   
	return <h1>Hola, {props.name}</h1>; 
}  
const element = <Welcome name="Carlos"/>;
``` 

5.  **JSX debe retornar un Elemento Único:** Un bloque de JSX debe retornar un único elemento padre. Esto significa que si tienes varios elementos a nivel superior, deben estar envueltos en un elemento contenedor, como un `<div>` o cualquier otro componente.

``` jsx
const element = (   
	<>
		<h1>Título</h1>
		<p>Contenido del párrafo</p>
	</>
);
```  

6. **Comentarios en JSX:** Los comentarios en JSX se insertan de manera similar a JavaScript, pero dentro de las llaves y utilizando la sintaxis de comentarios de bloque de JavaScript.

```jsx
const element = (
  <div>
    {/* Esto es un comentario en JSX */}
    <h1>Hola, mundo</h1>
  </div>
);
```