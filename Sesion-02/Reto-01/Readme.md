`Fullstack con Python` > [`Backend con Python`](../../Readme.md) > [`Sesión 02`](../Readme.md) > Reto-01

## INICIALIZANDO LA BASE DE DATOS EN UN SERVIDOR MARIADB

### OBJETIVO
Inicializar la base de datos en un servidor MariaDB haciendo uso de contenedores para el proyecto BeduTravels.

#### REQUISITOS
1. Contar con Docker instalado
1. Contar con el contenedor __pythonsql__ ya creado en el Ejemplo-01.
1. Contar con los datos de conexión al servidor MariaDB como usuario root:
  - __Host:__ localhost
  - __User:__ root
  - __Pass:__ pythonsql
1. Haber actualizado el repositorio
1. Abrir una terminal y cambiarse a la carpeta de trabajo `Sesion-02/Reto-01`:

   ```console
   $ cd Sesion-02/Reto-01

   Sesion-02/Reto-01 $
   ```

### DESARROLLO
4. Inicializar la base de datos usando el archivo `sql/bedutravels.sql`:

   ```console
   Sesion-02/Reto-01 $ docker exec -i pythonsql mysql -hlocalhost -uroot -ppythonsql < sql/bedutravels.sql
   ```
   ***

7. Para validar que la base de datos se haya inicializado de forma correcta se realiza una conexión a la base de datos BeduTravels usando los datos:

   - __Host:__ localhost
   - __User:__ BeduTravels
   - __Pass:__ BeduTravels
   - __Base de datos:__ BeduTravels

  ```console
  Sesion-02/Reto-01 $ docker exec -it pythonsql mysql -hlocalhost -uBeduTravels -pBeduTravels BeduTravels
  Welcome to the MariaDB monitor.  Commands end with ; or \g.
  Your MariaDB connection id is 11
  Server version: 10.3.15-MariaDB-1:10.3.15+maria~bionic mariadb.org binary distribution

  Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

  Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

  MariaDB [BeduTravels]> EXIT;

  Sesion-02/Reto-01 $
  ```
  ***

Si has llegado hasta este punto __FELICIDADES__, toma __otro__ respiro o ayuda a algún compañero que no lo haya logrado aún o tomate un café te lo mereces.