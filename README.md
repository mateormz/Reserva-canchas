# Sistema de Microservicios para Gestión de Reservas de Canchas

Este proyecto implementa un sistema de microservicios para la gestión de reservas de canchas de fútbol, incluyendo la administración de usuarios, métodos de pago, reservas y campos. Cada microservicio está alojado en un repositorio independiente y cuenta con su propia configuración de base de datos y funcionalidad específica.

## Arquitectura del Proyecto

El sistema está dividido en los siguientes microservicios:

1. **Reservations Microservice** - [Repositorio](https://github.com/mateormz/reservations-microservice)
   - Maneja las reservas de los usuarios para un time slot específico.
   - Conectado a una base de datos MongoDB para almacenamiento de las reservas y disponibilidad de los horarios.

2. **Fields Microservice** - [Repositorio](https://github.com/mateormz/fields-microservice)
   - Administra la información de los campos deportivos disponibles para reservas.

3. **User Microservice** - [Repositorio](https://github.com/mateormz/user-microservice)
   - Maneja la información de los usuarios y sus reservas.

4. **Orquestador** - [Repositorio](https://github.com/mateormz/orquestador)
   - Actúa como intermediario, gestionando la comunicación entre los microservicios y asegurando la sincronización de datos.

5. **Payments API** - [Repositorio](https://github.com/joelm2405/payments-api)
   - Gestiona los métodos de pago y los pagos realizados por los usuarios.

Cada uno de estos microservicios se implementa y documenta individualmente en sus respectivos repositorios. Además, un archivo `Dockerfile` está incluido en el repositorio para facilitar la creación de contenedores de Docker para los microservicios.

## Despliegue

Para el despliegue, se utiliza Docker para la contenedorización de cada uno de los microservicios. El sistema puede ejecutarse en una red de Docker para permitir la comunicación entre los contenedores.

### Instrucciones Generales de Despliegue

1. **Clonar los Repositorios**: Clonar cada repositorio en una ubicación local.
2. **Construir los Contenedores**: Ejecutar `docker build -t <nombre_del_servicio> .` en cada repositorio para construir los contenedores.
3. **Iniciar los Contenedores**: Utilizar `docker run` o `docker-compose` para iniciar cada contenedor. Asegúrate de que cada servicio esté conectado a la misma red de Docker.
4. **Documentación de APIs**: Cada microservicio cuenta con documentación de API mediante Swagger en las rutas `/api-docs` para las APIs de Java/Spring Boot y `/docs` para FastAPI en Python.

## Tecnologías

- **Node.js** para el microservicio de pagos.
- **Java Spring Boot** para los microservicios de usuarios, orquestador.
- **Python FastAPI** para el microservicio de reservas.
- **MongoDB**, **PostgreSQL** y **MySQL** como bases de datos.
