# Tema 2 - Gestión de espectáculos under

## 1. Consigna

Se pide:

    Implementar un modelo cliente servidor.
    Implementar el paradigma de objetos.
    Implementar al menos en la relación entre dos objetos inyección de dependencias.

Objetivo del primer entregable: se pide documentar el plan de trabajo y las decisiones técnicas tomadas para la resolución del mismo. Se deberán entregar diagramas y justificaciones. NO se requiere la entrega de código en la primera instancia.

Requerimientos:

    Diagrama de clases del sistema.
    Modelo de datos.
    Detalle de las tecnologías a utilizar.
    Tipo de testeo y módulos que se planifican testear.
    Justificación de la elección de tecnología y consideraciones.


Condiciones de entrega:

Deberá entregarse un documento en formato PDF conteniendo todos los requerimientos expuestos, o bien en el repositorio (readme)

En el caso que no se pueda realizar la entrega en la fecha estipulada, deberá entregar todo junto en la fecha de entrega del proyecto integrador. Si en esa instancia no alcanza a cumplir con los objetivos, podrá realizar la reentrega en la instancia de recuperación correspondiente.

En el caso que se realicen observaciones o requerir correcciones en el primer entregable, estos deberán entregarse resueltos en la segunda entrega.

---

Una pequeña sala de teatro independiente requiere que se gestione la venta de entradas para sus espectáculos. Cuentan con dos espacios una sala con capacidad para 70 personas y un anfiteatro a cielo abierto con una capacidad para 120 personas. La primera posee un costo variable en las entradas, las tipo A, tienen un costo del doble de las tipo B. El anfiteatro tiene precio único.

Para lo cual un usuario registrado en el sistema registra la siguiente información:

    Artista
    Fecha de la función
    Hora de la función
    Sala
    Precio de la entrada
    Duración
    Tipo de show (infantil, musical, obra de teatro)

En el proceso de carga se debe validar que no se superpongan los espectaculos en una misma fecha y hora, para permitir la carga de espectaculos un mismo día, debe haber una hora libre en la sala para su limpieza previa al inicio del proximo show

El sistema debe poder mostrar los espectaculos próximos a presentarse en la sala, así como los anteriores, en este ultimo caso por supuesto no debe poder permitir realizar la compra de entradas.


## 2. Modelo de Datos

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

![Diagrama de clases](https://github.com/user-attachments/assets/0dfe3ddd-e078-43d7-90d8-20d8cbe937ba)

---

## 3. Tecnologías a Utilizar

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

## 4. Tipo de Testeo y Módulos a Testear

### Tipos de Testeo
- **Unitario**: Testear funciones aisladas (validaciones, lógica de precios).
- **Integración**: Testear flujos de datos a través de múltiples componentes (por ejemplo, creación y consulta de funciones).

### Módulos a Testear
- Servicio de validación de solapamiento de horarios.
- Controlador de creación y listado de funciones.
- Módulo de autenticación de usuarios.
- Endpoints de gestión de funciones y usuarios.

---

## 5. Justificación de la Elección Tecnológica y Consideraciones

- **Node.js + Express.js** permiten desarrollo ágil y eficiente en JavaScript.
- **PostgreSQL** ofrece seguridad en la integridad de los datos relacionales.
- **Sequelize ORM** facilita la abstracción de consultas SQL y mantiene el código organizado.
- **Docker** permitirá configurar un entorno replicable y portable.
- **Jest** para testing. Es para asegurar que el sistema funcione de forma correcta y confiable.
- **JWT** para autenticación. Es standard en la industria.
