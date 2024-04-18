Instalación de los elementos necesarios para crear el proyecto. Para utilizar React, tenemos que utilizar vite. Podemos crear un proyecto con Vite, usando el siguiente comando:
``` bash
npm create vite@latest
```

Esto nos pedirá un nombre de proyecto, nombre de paquete y el tipo de framework que queremos usar, en este caso usaremos react. Finalmente seleccionamos Javascript + SWC.
``` bash
npm create vite@latest
√ Project name: ... nombre_proyecto
√ Package name: ... nombre_proyecto
√ Select a framework: » React
√ Select a variant: » JavaScript + SWC
```

Una vez que se ha instalado entramos en la carpeta instalamos las dependencias e iniciamos el servidor: 
``` bash
cd nombre_proyecto
npm install
npm run dev
```