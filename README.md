# Descripción de la aplicación PERSONAS-PROYECTOS basada en MICROSERVICIOS

Esta aplicación se hace para explicar cómo vamos a implementar los microservicios en las prácticas de Desarrollo Ágil, para el curso 2022-2023.

## Funcionamiento básico de la aplicación
[Pantalla de inicio de la aplicación](./assets/img/front-end-index.png)

Esta aplicación de muestra está formada por 4 aplicaciones (=servidores) distintos:
* Aplicación *front-end*
* Aplicación *api-gateway*
* Aplicación *ms-personas* (un microservicio)
* Aplicación *ms-proyectos* (otro microservicio)

Se respetan siempre las siguientes reglas básicas:
1. El usuario solo interactúa con la aplicación *front-end*
2. La aplicación *front-end* solo interactía con la aplicación *api-gateway*
3. La aplicación *api-gateway* recibe peticiones de *front-end* y las deriva al microservicio correspondiente. El servicio resuelve la petición y envía el resultado a la aplicación *front-end* a través de *api-gateway*
4. Los microservicios interactían con *api-gateway* y también entre ellos.
   
 [Esquema de comunicación entre las distintas aplicaciones ](./assets/img/esquema-comunicacion-apps.png)  