

---

# 🔑 Claves y Restricciones en Bases de Datos

## 1. ¿Qué son las Claves?

Las **claves** son **atributos o conjuntos de atributos** que permiten **identificar de forma única** los registros dentro de una tabla.
Su función principal es **mantener la integridad y coherencia** de los datos.

---

### 1.1 ¿Por qué surgió la necesidad de las claves?

Las claves surgieron para **evitar duplicidad y confusión** en los registros de una base de datos.
Permiten identificar con precisión cada fila, asegurando que los datos sean **únicos, precisos y relacionados correctamente** entre tablas.

---

### 1.2 Clave Primaria (**PRIMARY KEY**)

* Identifica de forma **única** cada registro en una tabla.
* No permite **valores nulos** ni **duplicados**.
* Cada tabla debe tener **solo una clave primaria**.
* Ejemplo:

  ```sql
  CREATE TABLE Estudiantes (
      id_estudiante INT PRIMARY KEY,
      nombre VARCHAR(50)
  );
  ```

---

### 1.3 Clave Externa (**FOREIGN KEY**)

* Crea una **relación** entre dos tablas.
* Hace referencia a la **clave primaria** de otra tabla.
* Garantiza la **integridad referencial**.
* Ejemplo:

  ```sql
  CREATE TABLE Matriculas (
      id_matricula INT PRIMARY KEY,
      id_estudiante INT,
      FOREIGN KEY (id_estudiante) REFERENCES Estudiantes(id_estudiante)
  );
  ```

---

## 2. Restricciones

Las **restricciones (constraints)** son **reglas** que se aplican a los datos de las tablas para **garantizar su validez e integridad**.

---

### 2.1 Restricción de Unicidad (**UNIQUE**)

* Garantiza que los valores en una columna sean **únicos**, pero **sí permite valores nulos**.
* Se puede usar en columnas que no sean clave primaria.
* Ejemplo:

  ```sql
  CREATE TABLE Usuarios (
      id INT PRIMARY KEY,
      correo VARCHAR(100) UNIQUE
  );
  ```

---

### 2.2 Restricción de Valor Predeterminado (**DEFAULT**)

* Asigna un **valor por defecto** cuando no se especifica otro.
* Ejemplo:

  ```sql
  CREATE TABLE Productos (
      id INT PRIMARY KEY,
      stock INT DEFAULT 0
  );
  ```

---

### 2.3 Restricción de Verificación (**CHECK**)

* Asegura que los valores cumplan una **condición específica**.
* Ejemplo:

  ```sql
  CREATE TABLE Empleados (
      id INT PRIMARY KEY,
      edad INT CHECK (edad >= 18)
  );
  ```

---

### 2.4 Restricción de No Nulos (**NOT NULL**)

* Evita que una columna tenga valores **nulos**.
* Garantiza que siempre se ingrese un dato válido.
* Ejemplo:

  ```sql
  CREATE TABLE Clientes (
      id INT PRIMARY KEY,
      nombre VARCHAR(50) NOT NULL
  );
  ```

---

### 2.5 Restricción de Valor Único en Clave Primaria

* La **clave primaria** combina las restricciones **NOT NULL** y **UNIQUE**.
* Esto asegura que cada fila tenga un **identificador único y obligatorio**.
* Ejemplo:

  ```sql
  CREATE TABLE Vehiculos (
      placa VARCHAR(10) PRIMARY KEY,
      modelo VARCHAR(50)
  );
  ```

---
