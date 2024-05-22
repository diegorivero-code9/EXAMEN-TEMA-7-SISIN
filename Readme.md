## Control de versiones

## Parte 1: Vagrant y Automatización
## Pregunta: Configuración de Vagrant

1. ¿Qué sistema operativo se debe especificar en el Vagrantfile si queremos un servidor virtual basado en Ubuntu? 

    config.vm.box = "ubuntu/xenial64"

## Pregunta: Automatización con Vagrant

2. ¿Cómo podemos generar desde el entorno real un archivo llamado datos_pacientes.sql en /home/vagrant/ de la virtualización?

    echo "-- Creamos el archivo datos_pacientes">/home/vagrant/datos_pacientes.sql

## Parte 2: Instalación y Configuración de MySQL
## Pregunta: Instalación y Configuración Inicial en Ubuntu

3. ¿Cuál es el comando para elevar privilegios a superusuario?
   
    sudo su

4. ¿Cuál es el primer comando que se debe ejecutar para actualizar los paquetes de una máquina virtual en Ubuntu?

    sudo apt update

5. ¿Qué comando se utiliza para instalar el servidor MySQL en Ubuntu?

    sudo apt install -y mysql-server

## Pregunta: Configuración del Usuario Root en MySQL

6. ¿Qué comandos se utilizan para iniciar, verificar el estado y habilitar el servidor MySQL para que inicie automáticamente al arrancar el sistema?

    sudo systemctl start mysql 
    sudo systemctl status mysql
    sudo systemctl enable mysql

7. ¿Qué comando se utiliza para acceder a MySQL como usuario root después de la instalación?

    mysql -u root -p

8. ¿Cómo se crea una base de datos llamada gestion_clinica_veterinaria?

    CREATE DATABASE gestion_clinica_veterinaria;

9. Escribe el comando SQL para crear la tabla pacientes con las siguientes columnas: idPaciente, nombre, especie, raza, edad, dueño.

    ## Nos conectamos a la base de datos: USE gestion_clinica_veterinaria
    CREATE TABLE pacientes(idPaciente INT PRIMARY KEY, nombre VARCHAR(100), especie VARCHAR(100), raza VARCHAR(100), edad INT, dueño VARCHAR(100));

## Parte 3: Administración de MySQL con Vagrant
## Pregunta: Gestión de la Base de Datos y Tabla

10. ¿Cómo se carga el archivo datos_pacientes.sql en MySQL desde la máquina virtual?

    SOURCE /home/vagrant/datos_pacientes.sql

11. ¿Qué comando se utiliza para detener el servicio MySQL?

    sudo systemctl stop mysql

## Parte 4: Configuración Adicional de MySQL
## Pregunta: Configuración del Juego de Caracteres y la Colación

12. ¿Cómo se modifica la base de datos gestion_clinica_veterinaria para cambiar su juego de caracteres y colación a utf8mb4 y utf8mb4_unicode_ci?

    ALTER DATABASE gestion_clinica_veterinaria CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

