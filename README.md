# CMS con Spring y PostgreSQL

Esta es una aplicación Spring Boot diseñada para interactuar con la API JSONPlaceholder. Sigue las mejores prácticas, incluyendo el uso de DTOs, Validación de Beans, Seguridad con Spring Security utilizando JWT y BCrypt, y Swagger para la documentación y prueba de la API. La aplicación también incluye gestión de sesiones para mejorar la seguridad.

## Tabla de Contenidos

- [Características](#características)
- [Requisitos Previos](#requisitos-previos)
- [Instalación](#instalación)
- [Uso](#uso)
- [Endpoints de la API](#endpoints-de-la-api)
- [Seguridad](#seguridad)
- [Documentación con Swagger](#documentación-con-swagger)
- [Pruebas](#pruebas)
- [Contribuciones](#contribuciones)
- [Licencia](#licencia)

## Características

- Consumo de la API JSONPlaceholder
- Uso de Data Transfer Objects (DTOs)
- Validación de Beans
- Seguridad con Spring Security utilizando JWT y BCrypt
- Gestión de sesiones
- Operaciones CRUD para usuarios y posts
- Integración con Swagger para documentación y prueba de la API

## Requisitos Previos

- Java 11 o superior
- Maven 3.6.3 o superior
- Spring Boot 2.5.0 o superior
- PostgreSQL

## Instalación

1. Clona el repositorio:
    ```bash
    git clone https://github.com/tuusuario/cms-spring-postgresql.git
    cd cms-spring-postgresql
    ```

2. Configura la base de datos en `application.properties`:
    ```properties
    spring.datasource.url=jdbc:postgresql://localhost:5432/tu_basedatos
    spring.datasource.username=tu_usuario
    spring.datasource.password=tu_contraseña
    spring.jpa.hibernate.ddl-auto=update
    ```

3. Instala las dependencias:
    ```bash
    mvn clean install
    ```

4. Ejecuta la aplicación:
    ```bash
    mvn spring-boot:run
    ```

## Uso

Una vez que la aplicación esté en ejecución, puedes interactuar con ella a través de los endpoints expuestos.

### Endpoints de la API

#### Endpoints de Usuario

- **GET /api/users**: Obtener todos los usuarios
- **GET /api/users/{id}**: Obtener usuario por ID
- **POST /api/users**: Crear un nuevo usuario
- **PUT /api/users/{id}**: Actualizar usuario por ID
- **DELETE /api/users/{id}**: Eliminar usuario por ID

#### Endpoints de Post

- **GET /api/posts**: Obtener todos los posts
- **GET /api/posts/{id}**: Obtener post por ID
- **GET /api/posts/user/{userId}**: Obtener posts por ID de usuario
- **POST /api/posts**: Crear un nuevo post
- **PUT /api/posts/{id}**: Actualizar post por ID
- **DELETE /api/posts/{id}**: Eliminar post por ID

#### Endpoints de Autenticación

- **POST /authenticate**: Autenticar usuario y obtener token JWT
- **POST /register**: Registrar un nuevo usuario
- **GET /api/logout**: Cerrar sesión del usuario actual

## Seguridad

La aplicación utiliza tokens JWT para la autenticación y BCrypt para el hash de contraseñas. La gestión de sesiones se implementa para proporcionar una seguridad mejorada.

### Gestión de Sesiones

Las sesiones están configuradas para expirar después de 30 minutos de inactividad. El ID de la sesión se regenera al iniciar sesión para prevenir ataques de fijación de sesión.

### Token JWT

Los tokens JWT se utilizan para autenticar las solicitudes a la API. El token debe incluirse en el encabezado `Authorization` con el prefijo `Bearer`.

Ejemplo:
Authorization: Bearer <tu-token-jwt>

shell
Copy code

## Documentación con Swagger

Swagger está integrado para la documentación y prueba de la API. Una vez que la aplicación esté en ejecución, puedes acceder a la interfaz de Swagger en:

http://localhost:8080/swagger-ui.html


## Pruebas

Para ejecutar las pruebas, usa el siguiente comando:

```bash
mvn test
```

Contribuciones
¡Las contribuciones son bienvenidas! Por favor, clona el repositorio y crea un pull request con tus cambios. Asegúrate de que tu código sigue los estándares de codificación del proyecto e incluye las pruebas apropiadas.

Licencia
Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo [LICENSE](#LICENSE) para más detalles.


Este README proporciona una visión clara y completa de tu proyecto, incluyendo todas las secciones esenciales en formato Markdown.

