# Descripción de la aplicación PERSONAS-PROYECTOS basada en MICROSERVICIOS

Esta aplicación se hace para explicar cómo vamos a implementar los microservicios en las prácticas de Desarrollo Ágil, para el curso 2022-2023.

## Funcionamiento básico de la aplicación
La funcionalidad es muy simple: hay un conjunto de personas asignadas a un conjunto de proyectos (de software). Y la aplicación permite listar tanto las personas que hay como los proyectos, así como modificar los datos de las personas.

![Pantalla de inicio de la aplicación](./assets/img/front-end-index.png)

Esta aplicación de muestra está formada, a su vez, por 4 aplicaciones (=servidores) independientes:
* Aplicación *front-end*
* Aplicación *api-gateway*
* Aplicación *ms-personas* (un microservicio)
* Aplicación *ms-proyectos* (otro microservicio)

Se respetan siempre las siguientes reglas básicas:
1. El usuario solo interactúa con la aplicación *front-end*
2. La aplicación *front-end* solo interactía con la aplicación *api-gateway*
3. La aplicación *api-gateway* recibe peticiones de *front-end* y las deriva al microservicio correspondiente. El servicio resuelve la petición y envía el resultado a la aplicación *front-end* a través de *api-gateway*
4. Los microservicios interactúan con una BBDD (posiblemente distinta para cada microservicio), con *api-gateway* y también entre ellos.
   
![Esquema de comunicación entre las distintas aplicaciones ](./assets/img/esquema-comunicacion-apps.png)  

## Organización del árbol de directorios de cada app

Las 4 apps que forman el sistema completo tienen su código por separado y no comparten nada de dicho código.

No obstante, todas ellas tienen un conjunto de directorios y de ficheros con nombres idénticos (aunque con contenidos distintos).

Describimos brevemente los ficheros y directorios que se encuentran en todas las apps:
* ```server.js```: fichero en el que se declara el objeto ```app```, el cual hace las veces de servidor web; es decir, recibe llamadas a través del protocolo *http* y devuelve un resultado que puede ser en JSON o como fichero HTML. Las 4 aplicaciones desarrolladas utilizan la biblioteca [Express](https://expressjs.com/) para [Node.js](https://nodejs.org/en/).
* ```routes.js```: fichero en el que se declaran las rutas que se van a atender dentro de la llamada *http* que se está realizando.
* ```callbacks.js```: fichero en el que se encuentran las funciones con las que se va a procesar la llamada a cada una de las rutas definidas en *routes.js*
* ```spec```: directorio en el que se encuentran las pruebas a realizar con el entorno [Jasmine](https://jasmine.github.io/), para realizar TDD con JavaScript.
* ```package.json```: fichero con la configuración de cada app, necesario para que *nodejs* pueda ejecutar el proyecto.
* ```README.md```: fichero con la descripción de cada proyecto, el cual a su vez sirve como documentación del mismo.



 ![Árbol de ficheros y directorios de una aplicación](./assets/img/estructura%20directorios%20y%20ficheros.png) 
 