Descripción
El proyecto es una aplicación CRUD (Create, Read, Update, Delete) que permite a los usuarios gestionar una lista de productos. La aplicación proporciona una interfaz de programación de aplicaciones (API) que permite a los usuarios crear, leer, actualizar y eliminar productos de una base de datos MongoDB.

La aplicación utiliza TypeScript para garantizar la seguridad del tipo y el uso de características modernas de JavaScript, y Express para crear la API. Además, se utiliza Mongoose para la conexión y el manejo de la base de datos MongoDB.

La estructura del proyecto sigue el patrón de diseño MVC (Modelo-Vista-Controlador), donde los modelos representan los datos de la aplicación, las vistas representan la interfaz de usuario y los controladores manejan las solicitudes HTTP y las respuestas.

Estructura del proyecto
El proyecto tiene la siguiente estructura de directorios y archivos:

src/: Contiene el código fuente de la aplicación.
config/: Contiene los archivos de configuración de la aplicación.
config.ts: Contiene la configuración de la aplicación, como el puerto en el que se ejecutará la aplicación y la cadena de conexión a la base de datos MongoDB.
controllers/: Contiene los controladores de la aplicación que manejan las solicitudes HTTP y las respuestas.
productController.ts: Contiene el controlador para la gestión de productos.
models/: Contiene los modelos de la aplicación que representan los datos.
productModel.ts: Contiene el modelo de producto.
routes/: Contiene las rutas de la API de la aplicación.
productRoutes.ts: Contiene las rutas para la gestión de productos.
types/: Contiene los tipos personalizados de la aplicación.
product.ts: Contiene la definición del tipo de producto.
app.ts: Contiene la configuración de la aplicación Express y la definición de las rutas.
server.ts: Contiene el código para iniciar el servidor.
node_modules/: Contiene los módulos de Node.js utilizados por la aplicación.
package.json: Contiene la información de la aplicación, como el nombre, la versión, las dependencias, etc.
tsconfig.json: Contiene la configuración de TypeScript.
Inicio rápido
Para ejecutar la aplicación en su computadora, siga los siguientes pasos:

Clonar el repositorio: git clone https://github.com/lucasduran33/Crud-TS.git.
Ir al directorio del proyecto: cd Crud-TS.
Instalar las dependencias: npm install.
Iniciar la aplicación: npm start.
La aplicación se ejecutará en http://localhost:3000.

Conclusiones

El proyecto "Crud-TS" es una aplicación CRUD simple desarrollada en TypeScript con Node.js y Express, y utilizando MongoDB como base de datos. La estructura del proyecto sigue el patrón de diseño MVC y utiliza Mongoose para conectarse y manejar la base de datos MongoDB.

La aplicación proporciona una interfaz de programación de aplicaciones (API) que permite a los usuarios gestionar una lista de productos. La aplicación se puede ejecutar en su computadora después de seguir los pasos en la sección "Inicio rápido".

Este proyecto puede ser utilizado



DOCKER DOCUMENTS FILES 

Este Dockerfile tiene dos fases, una para desarrollo y otra para producción.

La primera línea especifica la imagen de Docker que se utilizará como base para el contenedor: "node:16-alpine as development". Esto significa que se usará la imagen de Node.js en su versión 16 y la variante alpina, y se etiquetará como "development".

La siguiente línea establece el directorio de trabajo dentro del contenedor como "/usr/src/app".

La siguiente línea copia los archivos "package.json" y "package-lock.json" (o "yarn.lock") del directorio actual (donde se encuentra el archivo Dockerfile) al directorio "/usr/src/app" del contenedor.

La siguiente línea ejecuta el comando "npm install" dentro del contenedor para instalar las dependencias del proyecto. Esto asegura que todas las dependencias están disponibles dentro del contenedor.

La siguiente línea copia todo el contenido del directorio actual al directorio "/usr/src/app" del contenedor.

La siguiente línea ejecuta el comando "npm run build" dentro del contenedor, lo que construye la aplicación en el directorio "/usr/src/app/dist".

La siguiente línea establece la segunda fase de la imagen, etiquetada como "production". También define la variable de entorno "NODE_ENV" con el valor de la variable de argumento "NODE_ENV" que se pasó al comando "docker build" (o "production" si no se proporciona un valor para la variable de argumento).

La siguiente línea establece el directorio de trabajo dentro del contenedor como "/usr/src/app".

La siguiente línea copia los archivos "package.json" y "package-lock.json" (o "yarn.lock") del directorio actual (donde se encuentra el archivo Dockerfile) al directorio "/usr/src/app" del contenedor.

La siguiente línea ejecuta el comando "npm ci --only=production" dentro del contenedor. Esto instala solo las dependencias de producción (omitidas durante el proceso de desarrollo) en el directorio "/usr/src/app/node_modules" del contenedor.

La siguiente línea copia el contenido del directorio "/usr/src/app/dist" de la fase de desarrollo al directorio "/usr/src/app/dist" de la fase de producción.

Finalmente, la última línea establece el comando predeterminado que se ejecutará cuando el contenedor se inicie. En este caso, se ejecutará la aplicación con el comando "node dist/app.js".




Commandos : 
Para Desarrollo:
docker compose -f docker-compose.dev.yml up

Para Produccion
docker compose up --build


