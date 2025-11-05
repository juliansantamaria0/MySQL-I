# Consultas Básicas con SQL

## 1. ¿Qué es SQL?

El **SQL (Structured Query Language)** es el lenguaje estándar para administrar y manipular bases de datos relacionales. Permite crear, modificar, consultar y gestionar la información almacenada de manera eficiente. Es utilizado por la mayoría de los sistemas de gestión de bases de datos, incluyendo **MySQL**, **PostgreSQL**, **Oracle**, y **SQL Server**.

### 1.1 ¿Qué es SQL? - Introducción al lenguaje de consulta estructurada (SQL)

SQL es un lenguaje **declarativo**, lo que significa que el usuario indica *qué* quiere obtener o modificar en la base de datos, sin especificar *cómo* hacerlo.  
Su principal objetivo es facilitar la comunicación entre el usuario o la aplicación y la base de datos.  
Fue creado en los años 70 por IBM y ha evolucionado para convertirse en un estándar ANSI e ISO.

### 1.2 ¿Qué es SQL? - Definición

**SQL (Structured Query Language)** es un lenguaje diseñado para:

- Crear estructuras de datos (tablas, vistas, índices, etc.).
- Insertar, actualizar y eliminar registros.
- Consultar información mediante criterios definidos.
- Controlar permisos y seguridad dentro del sistema de base de datos.

SQL se basa en la teoría de conjuntos y el álgebra relacional, lo que lo hace muy potente para manejar grandes volúmenes de información.

### 1.3 ¿Qué es SQL? - Datos Curiosos sobre SQL y Bases de Datos Relacionales

- El nombre original fue **SEQUEL (Structured English Query Language)**, desarrollado por IBM.
- SQL es tanto un lenguaje de **definición de datos** como de **manipulación** y **control** de acceso.
- A pesar de ser un estándar, cada sistema de base de datos puede tener *extensiones propias* (por ejemplo, MySQL incluye funciones adicionales como `LIMIT`).
- Las bases de datos relacionales se basan en tablas conectadas mediante **claves primarias** y **foráneas**, permitiendo mantener la integridad de los datos.

### 1.4 ¿Qué es SQL? - Aplicación de SQL en MySQL

En **MySQL**, SQL es el núcleo para todas las operaciones. Algunas de las funciones más comunes incluyen:

- **Definir tablas** con `CREATE TABLE`.
- **Insertar datos** con `INSERT INTO`.
- **Consultar información** con `SELECT`.
- **Actualizar registros** con `UPDATE`.
- **Eliminar datos** con `DELETE`.

MySQL también ofrece funciones SQL avanzadas como **procedimientos almacenados**, **vistas**, **triggers**, y **transacciones** para aplicaciones más complejas.

---

## 2. Componentes principales del SQL

El lenguaje SQL se divide en varios **subconjuntos** de comandos, cada uno con una función específica dentro de la gestión de bases de datos. Los principales son **DDL**, **DML**, y **DQL**.

### 2.1 Componentes principales del SQL - Sentencias de definición de datos (DDL)

El **DDL (Data Definition Language)** se utiliza para definir y modificar la estructura de la base de datos.  
Estas sentencias afectan directamente el esquema (estructura) de las tablas y objetos.

**Principales comandos DDL:**

- `CREATE` → Crea nuevas tablas, bases de datos o vistas.  
- `ALTER` → Modifica la estructura existente de una tabla o base de datos.  
- `DROP` → Elimina completamente una tabla o base de datos.  
- `TRUNCATE` → Borra todos los datos de una tabla, pero mantiene su estructura.

**Ejemplo:**

```sql
CREATE TABLE estudiantes (
    id INT PRIMARY KEY,
    nombre VARCHAR(50),
    edad INT
);

```

