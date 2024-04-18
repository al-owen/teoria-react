En React, los **props** (abreviatura de _properties_ o propiedades) son una forma de pasar datos y eventos de un componente padre a un componente hijo en la estructura de una aplicación. Son fundamentales para la programación con React porque permiten que los componentes sean dinámicos y reutilizables.

1. **Inmutabilidad:** Los props son solo de lectura, lo que significa que un componente no puede cambiar sus propios props. Esta característica promueve un flujo de datos predecible y unidireccional, lo que ayuda a mantener la aplicación fácil de entender y debuggear.
    
2. **Reutilización de [[Componentes]]:** Al utilizar props, puedes crear componentes que se comporten de manera diferente según los datos que reciban, lo que hace que los componentes sean reutilizables en diferentes contextos dentro de tu aplicación. Por ejemplo, puedes tener un componente `Button` que muestre diferentes textos y realice diferentes acciones según los props que se le pasen.
    
3. **Pasar Datos:** Los props se utilizan para pasar datos desde un componente padre a un componente hijo. Esto es esencial para el desarrollo de aplicaciones compuestas por muchos componentes pequeños y gestionables que necesitan compartir datos entre ellos.
    
4. **Pasar Funciones:** Además de datos, los props también pueden incluir funciones que los componentes hijos pueden llamar. Esto es útil para manejar eventos como clics o cambios de datos, donde el componente hijo necesita comunicar cambios al padre o a otros componentes.
    
5. **Children Prop:** Un uso especial de los props es el `children` prop, que permite pasar subcomponentes directamente dentro del cuerpo de otro componente. Esto es útil para crear componentes de envoltura o layouts que tienen contenido dinámico.
    
6. **PropTypes y DefaultProps:** React permite especificar `propTypes` que son un conjunto de especificaciones que permiten verificar que los props recibidos por un componente correspondan a lo esperado. Además, puedes definir `defaultProps` que son valores predeterminados para los props, en caso de que estos no sean proporcionados por el componente padre.