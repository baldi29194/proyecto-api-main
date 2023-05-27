
# Proyecto API REST con Node.JS

Este es el proyecto API REST con node.js  
Proyecto deployado en render.com: https://proyecto-api-test.onrender.com  

Lista de APIs en render.com:  
Listar Usuarios: **GET** https://proyecto-api-test.onrender.com/usuarios/  
Listar Usuario: **GET** https://proyecto-api-test.onrender.com/usuarios/5  
Actualizar Usuario (req. json en body): **PUT** https://proyecto-api-test.onrender.com/usuarios/5  
Crear Usuario (req. json en body) **POST** https://proyecto-api-test.onrender.com/usuarios/  
Eliminar Usuario: **DELETE** https://proyecto-api-test.onrender.com/usuarios/10  
Promedio Edades Usuarios: **GET** https://proyecto-api-test.onrender.com/usuarios/promedio-edad/  
Estado Proyecto: **GET** https://proyecto-api-test.onrender.com/estado/  


En PostgreSQL crear el usuario para conectar.

```bash
  postgres=# CREATE USER dbadmin PASSWORD 'dbadmin';
```
Crear la base de datos del proyecto:

```bash
  postgres=# CREATE DATABASE PROYECTO_API;
```

CREACION DE TABLA USUARIOS Y LAS COLUMNAS EN LA BD

```bash
  CREATE TABLE USUARIO (
    id_usuario SERIAL PRIMARY KEY,
    cedula_identidad VARCHAR(20) NOT NULL,
    nombre VARCHAR(50) NOT NULL,
    primer_apellido VARCHAR(50) NOT NULL,
    segundo_apellido VARCHAR(50),
    fecha_nacimiento DATE
  );
```



```bash
  INSERT INTO USUARIO ( cedula_identidad, nombre, primer_apellido, segundo_apellido, fecha_nacimiento) VALUES
('1234567890', 'Daniel', 'Garcia', 'Marques', '1990-01-01'),
('9876543210', 'Lucia', 'Perales', 'Gomez', '1992-05-10'),
('4567890123', 'Cristian', 'Fernandez', 'Rosales', '1985-09-15'),
('3210987654', 'Lorena', 'Jimenez', 'Choque', '1998-07-20'),
('2345678901', 'Marcelo', 'Vargas', 'Fernandez', '1991-03-05'),
('7654321098', 'Luciana', 'Lopez', 'Flores', '1988-12-12'),
('6789012345', 'Pedro', 'Velarde', 'Farfan', '1994-11-08'),
('5432109876', 'Victoria', 'Nieves', 'Gareca', '1997-06-25'),
('8765432109', 'Fernando', 'Perez', 'Garzon', '1993-04-18'),
('9876543219', 'Fernanda', 'Salazar', 'Siles', '1996-02-28');
```

Ejecutar el proyecto Node.JS
```bash
  node index.js
```

## CONSULTAS API 

#### Mostrar Usuarios

```http
  GET /usuarios
```

#### Mostrar usuario especifico

```http
  GET /usuarios/${id_usuario}
```

#### Crear usuario

```http
  POST /usuarios/
```

#### Actualizar usuario

```http
  PUT /usuarios/${id_usuario}
```


#### Eliminar usuario

```http
  DELETE /usuarios/${id_usuario}
```

#### Determinar el promedio de edades

```http
  GET /usuarios/promedio-edad
```

#### Información del Proyecto

```http
  GET /estado
```
