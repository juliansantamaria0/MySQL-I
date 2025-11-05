🧠 Guía Rápida de Comandos MySQL
================================

🔹 Conexión y gestión del servicio
----------------------------------

    # Iniciar el servicio MySQL
    sudo systemctl start mysql.service
    
    # Detener el servicio MySQL
    sudo systemctl stop mysql.service
    
    # Reiniciar el servicio MySQL
    sudo systemctl restart mysql.service
    
    # Verificar el estado del servicio MySQL
    sudo systemctl status mysql.service

> 💡 **Nota importante:** Si aparece el mensaje:
>  Warning: The unit file, source configuration file or drop-ins of mysql.service changed on disk.
>  Run 'systemctl daemon-reload' to reload units.
>
> Ejecuta:
>  sudo systemctl daemon-reload

* * *

🔹 Acceso al servidor MySQL
---------------------------

    # Entrar al monitor de MySQL como usuario root
    mysql -u root -p
    
    # Entrar con otro usuario desde una IP específica
    mysql -u andres -h 172.16.101.100 -p

> 💬 Luego se solicitará la contraseña del usuario.

* * *

🔹 Consultar bases de datos existentes
--------------------------------------

    SHOW DATABASES;

**Resultado esperado:**
    +--------------------+
    | Database           |
    +--------------------+
    | information_schema |
    | performance_schema |
    +--------------------+

* * *

🔹 Crear bases de datos
-----------------------

    CREATE DATABASE explicaciondia1;

> ⚠️ **Error común:**
>  ERROR 1064 (42000): You have an error in your SQL syntax;
>
> Revisa que no falte la palabra **DATABASE** después de `CREATE`.

* * *

🔹 Usar una base de datos
-------------------------

    USE explicaciondia1;

* * *

🔹 Ver tablas dentro de una base de datos
-----------------------------------------

    SHOW TABLES;

* * *

🔹 Otorgar privilegios a un usuario
-----------------------------------

### Privilegios sobre una tabla específica

    GRANT INSERT, UPDATE ON explicaciondia1.Persona TO 'andres'@'%';
    GRANT SELECT ON explicaciondia1.Persona TO 'andres'@'%';

### Privilegios de creación sobre todas las bases de datos

    GRANT CREATE ON *.* TO 'andres'@'%';

> 💡 **Tip importante:** Usa comas (`,`) para separar privilegios, **no puntos (`.`)**
>
> ❌ **Incorrecto:** `GRANT INSERT.UPDATE ON ...`
>
> ✅ **Correcto:** `GRANT INSERT, UPDATE ON ...`

* * *

🔹 Revocar privilegios
----------------------

    REVOKE SELECT ON explicaciondia1.Persona FROM 'andres'@'%';

* * *

🔹 Guardar y aplicar cambios
----------------------------

    FLUSH PRIVILEGES;

* * *

🔹 Comentarios en MySQL
-----------------------

    -- Comentario de una línea
    
    /* Comentario
       de varias líneas */

* * *

🔹 Comandos útiles del sistema (fuera de MySQL)
-----------------------------------------------

    # Ver historial de comandos ejecutados
    history
    
    # Editar configuración de MySQL
    sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf

* * *

🧩 Errores comunes y soluciones
-------------------------------

| Error                           | Causa                          | Solución                                                     |
| ------------------------------- | ------------------------------ | ------------------------------------------------------------ |
| `ERROR 1064 (42000)`            | Error de sintaxis SQL          | Revisa la estructura del comando (`CREATE DATABASE`, `GRANT`, etc.) |
| `Can't connect to MySQL server` | El servicio no está iniciado   | Ejecuta `sudo systemctl start mysql.service`                 |
| `Access denied for user`        | Usuario o permisos incorrectos | Revisa el usuario y privilegios con `SHOW GRANTS FOR 'usuario'@'%';` |

* * *

🧾 Ejemplo completo de flujo de trabajo
---------------------------------------

    -- Crear base de datos
    CREATE DATABASE explicaciondia1;
    
    -- Usar base de datos
    USE explicaciondia1;
    
    -- Otorgar permisos a un usuario
    GRANT INSERT, UPDATE, SELECT ON explicaciondia1.Persona TO 'andres'@'%';
    
    -- Aplicar cambios
    FLUSH PRIVILEGES;
    
    -- Revocar un permiso específico
    REVOKE SELECT ON explicaciondia1.Persona FROM 'andres'@'%';
    
    -- Aplicar cambios nuevamente
    FLUSH PRIVILEGES;

* * *

📚 Comandos adicionales útiles
------------------------------

### Ver privilegios de un usuario

    SHOW GRANTS FOR 'andres'@'%';

### Crear un nuevo usuario

    CREATE USER 'nuevouser'@'%' IDENTIFIED BY 'contraseña';

### Eliminar un usuario

    DROP USER 'usuario'@'%';

### Ver usuarios existentes

    SELECT user, host FROM mysql.user;

* * *

🎯 Tips de buenas prácticas
---------------------------

* Siempre usa `FLUSH PRIVILEGES;` después de modificar permisos
* Usa `'%'` en el host para permitir conexiones desde cualquier IP
* Usa `'localhost'` para restringir conexiones solo locales
* Finaliza cada comando SQL con punto y coma (`;`)
* Los nombres de comandos SQL no distinguen mayúsculas/minúsculas, pero por convención se escriben en MAYÚSCULAS

* * *


