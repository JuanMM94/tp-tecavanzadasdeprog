# Proyecto: Sistema de Gestión de Entradas para Teatro Independiente

## 1. Modelo de Datos

### Usuario
- `id`: UUID
- `nombre`: String
- `email`: String
- `password`: String (hasheado)

### Sala
- `id`: UUID
- `nombre`: "Sala Principal" | "Anfiteatro"

### Funcion
- `id`: UUID
- `artista`: String
- `fecha`: Date
- `hora`: Time
- `salaId`: UUID
- `precio`: Number
- `duracion`: Number
- `tipoShow`: "Infantil" | "Musical" | "Obra de teatro"

---

## 2. Tecnologías a Utilizar

| Tecnología            | Justificación                                                   |
|------------------------|----------------------------------------------------------------|
| Node.js                | Rápido, basado en JS, ideal para APIs ligeras.                 |
| Express.js             | Framework minimalista y robusto para APIs REST.                |
| PostgreSQL             | Base de datos relacional robusta para gestión de funciones.    |
| Sequelize (ORM)        | Mapeo sencillo entre objetos y base de datos relacional.       |
| Jest                   | Framework de testing potente para Node y TypeScript.           |
| Docker                 | Contenerización del entorno para facilidad de despliegue.      |
| JWT (jsonwebtoken)     | Manejo de autenticación mediante tokens seguros.               |

---

## 3. Tipo de Testeo y Módulos a Testear

### Tipos de Testeo
- **Unitario**: Testear funciones aisladas (validaciones, lógica de precios).
- **Integración**: Testear flujos de datos a través de múltiples componentes (por ejemplo, creación y consulta de funciones).

### Módulos a Testear
- Servicio de validación de solapamiento de horarios.
- Controlador de creación y listado de funciones.
- Módulo de autenticación de usuarios.
- Endpoints de gestión de funciones y usuarios.

---

## 4. Justificación de la Elección Tecnológica y Consideraciones

- **Node.js + Express.js** permiten desarrollo ágil y eficiente en JavaScript.
- **PostgreSQL** ofrece seguridad en la integridad de los datos relacionales.
- **Sequelize ORM** facilita la abstracción de consultas SQL y mantiene el código organizado.
- **Docker** permitirá configurar un entorno replicable y portable.
- **Jest** para testing. Es para asegurar que el sistema funcione de forma correcta y confiable.
- **JWT** para autenticación. Es standard en la industria.
