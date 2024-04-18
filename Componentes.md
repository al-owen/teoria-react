1. **Definición de Componentes:** Los componentes en React pueden definirse como funciones o clases. Los componentes de función se han vuelto más comunes con la introducción de los hooks, que permiten el uso de estado y otros rasgos de React sin necesidad de escribir una clase.
    - **Componentes Funcionales:** Son funciones de JavaScript que aceptan props como argumentos y retornan elementos de React que describen lo que debería aparecer en la pantalla.
    - **Componentes de Clase:** Son clases de JavaScript que extienden `React.Component`. Deben incluir un método `render()` que retorne lo que se debe mostrar en la pantalla.
2. **[[Props]]:** Los props (abreviatura de properties) son cómo los componentes reciben datos de sus componentes padres. Los props son inmutables dentro del componente, lo que significa que un componente no puede cambiar sus propios props, pero puede pasar partes de ellos junto con su propio estado a componentes hijos.
    
3. **[[Estados]]:** El estado es una característica que permite a los componentes reaccionar a cambios de datos internos o externos. Solo está disponible en componentes de clase, o en componentes funcionales a través del hook `useState`. Cuando el estado de un componente cambia, React re-renderiza automáticamente el componente para reflejar ese cambio.
    
4. **Ciclo de Vida:** Los componentes de clase en React tienen lo que se conoce como "ciclo de vida," que incluye varias "etapas" por las que pasa el componente, como montaje (cuando el componente se crea y se inserta en el DOM), actualización (cuando los props o el estado del componente cambian), y desmontaje (cuando el componente se elimina del DOM). React proporciona "métodos del ciclo de vida" como `componentDidMount`, `componentDidUpdate`, y `componentWillUnmount` que se pueden usar para ejecutar código en diferentes puntos del ciclo de vida.
    
5. **Renderizado:** Cada componente debe tener un método `render` (en componentes de clase) o simplemente retornar elementos [[JSX]] (en componentes funcionales). Lo que retorna este método o función es lo que React pinta en el DOM. React se encarga de mantener eficiente este proceso a través del Virtual DOM, un concepto que permite a React hacer actualizaciones de manera muy eficiente.
    
6. **Composición de Componentes:** Los componentes pueden incluir otros componentes en su salida. Esto permite a los desarrolladores construir aplicaciones complejas a partir de componentes pequeños, simples y reutilizables. Esta composición es un elemento clave de la arquitectura de cualquier aplicación en React.