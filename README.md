
# 🧠 Informacion de todos los dias 

## 📘 Información

**JULIAN ANDRÉS SANTAMARÍA BUSTAMANTE**

**P3**

**PEDRO FELIPE GÓMEZ BONILLA**

* * *

**CAMPUSLANDS – APOLO – RUTA JAVA – FLORIDABLANCA – 2025** 


## 📅 Día 1 – Comandos Básicos de MySQL

### 🔹 Servicio MySQL

```bash
sudo systemctl start mysql.service     # Iniciar
sudo systemctl stop mysql.service      # Detener
sudo systemctl restart mysql.service   # Reiniciar
sudo systemctl status mysql.service    # Ver estado
```

💡 Si aparece un aviso de configuración, ejecuta:

```bash
sudo systemctl daemon-reload
```

### 🔹 Acceso y bases de datos

```bash
mysql -u root -p                      # Entrar como root
mysql -u andres -h 172.16.101.100 -p  # Desde otra IP
SHOW DATABASES;                       # Ver bases de datos
CREATE DATABASE explicaciondia1;       # Crear base
USE explicaciondia1;                   # Seleccionar base
SHOW TABLES;                           # Ver tablas
```

### 🔹 Permisos y usuarios

```sql
GRANT INSERT, UPDATE, SELECT ON explicaciondia1.Persona TO 'andres'@'%';
REVOKE SELECT ON explicaciondia1.Persona FROM 'andres'@'%';
FLUSH PRIVILEGES;
CREATE USER 'nuevo'@'%' IDENTIFIED BY 'clave';
DROP USER 'usuario'@'%';
SHOW GRANTS FOR 'andres'@'%';
```

### ⚠️ Errores comunes

| Error         | Causa               | Solución                             |
| ------------- | ------------------- | ------------------------------------ |
| ERROR 1064    | Sintaxis incorrecta | Revisa el comando                    |
| Can't connect | Servicio detenido   | `sudo systemctl start mysql.service` |
| Access denied | Falta de permisos   | Verifica con `SHOW GRANTS`           |

---

## 📅 Día 2 – Conceptos de SQL

**SQL (Structured Query Language)** es el lenguaje estándar para manejar bases de datos relacionales.
Permite **crear, modificar, consultar y controlar acceso** a la información.

Principales comandos:

* **DDL:** `CREATE`, `ALTER`, `DROP`
* **DML:** `INSERT`, `UPDATE`, `DELETE`
* **DQL:** `SELECT`

Ejemplo:

```sql
CREATE TABLE estudiantes (
  id INT PRIMARY KEY,
  nombre VARCHAR(50),
  edad INT
);
```

---

## 📅 Días 3 y 4 – Tarea

📄 Archivo: [Muertes accidentales en Colombia](https://drive.google.com/file/d/1f9kFjnoszlrCmxJLbcPjWZtBpnHvuJRM/view?usp=drivesdk)
Usa esta base de datos para practicar consultas y permisos.

---


¿Quieres que lo prepare en formato Markdown listo para copiar y pegar en GitHub (con emojis y formato visual) o en texto plano para un documento PDF o Word?
