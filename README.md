# VICTOR-MANUEL

#### 1. Introducción:
   En este documento encontrara los requisitos del sistema para el desarrollo de un software que permita almacenar información sobre diferentes entidades.

2. Objetivo:
   El objetivo del sistema es proporcionar una plataforma para almacenar y gestionar información relacionada con categorías y sus respectivos atributos.

3. Descripción General:
   El sistema deberá permitir la creación, modificación, eliminación y consulta de datos relacionados con las categorías.

4. Requisitos Funcionales:

   1. RF: En las categorias_de_carros se nececita almacenar el id , categoria, tipo_vehiculo y descripción.
   2. RF: En los autos se almacena el id, marca, garantia, cilindraje, id_categorias_de_carros y descripción.
   3. RF: En las persona se almacena el id, nombre, apellido, telefono, dirección y documento.
   4. RF: En Autos_persona requiere almacenar el id, id_autos, id_persona y descripción.
   ref: Se requiere almacenar, modificar, eleminar y consultar información  en autos.
   ref: Se requiere tener informacion actualizada en personas.

5. Requisitos No Funcionales:

   1. El sistema debe ser fácil de usar y comprensible para los usuarios finales.
   2. El sistema debe garantizar la seguridad y privacidad de los datos almacenados.
   3. El sistema debe ser compatible con múltiples plataformas y navegadores web.
   4. El sistema debe tener un tiempo de respuesta rápido para las operaciones de consulta y modificación de  datos.

`categorias_de_carros`:En esta tabla se almanesara Id, Categoria, tipo de vehiculo y descripción.

| id | categoria         | tipo_vehiculo | descripción |
|----|-------------------|---------------|-------------|
| 1  | alto cilindraje   |deportivo      | idal        |
| 2  | alto cilindraje   |trocha         |idal         |
| 3  | alto cilindraje   |deportivo      |idal         |


`autos`: En esta tabla se guardara de manera autoincremental y automantica los autos que se ingresen.

| id | marca         | garantia | cilindraje | id_categorias_de_carros | descripción|
|----|---------------|----------|------------|-------------------------|------------|
| 1  |         bmw   | 1 año    |3000        |  1                      | ideal      |
| 2  | toyota        | 2 años   |2000        |  2                      | ideal      |
| 3  | bugati        | 4 años   |6000        |  3                      | ideal      |

`persona`: En esta tabla se almacenara de maneta autoincremental y automatica los clientes.

| id | nombre        | apellido | telefono | dirección   | documento|
|----|---------------|----------|----------|-------------|----------|
| 1  |    jose       | vargas   |3145789   | cr 11 24 sur| 1547920  |
| 2  |  leonardo     | herrera  |3256879   | cll 1 18    | 1578928  |
| 3  |  julian       | romero   |3147899   | cr 12 78 sur| 1687872  |

`Autos_persona`

| id | id_autos | id_persona | descripción |
|----|----------|------------|-------------|
| 1  |  1       |   1        |idal         |
| 2  |  2       |   2        |idal         |
| 3  |  3       |   3        |idal         |


> Script de la base de datos
```sql
    DROP DATABASE IF EXISTS parcial;

    CREATE DATABASE parcial;

    USE parcial;

    CREATE table categorias_de_carros (
        id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
        categoria VARCHAR1(150) NOT NULL UNIQUE,
        tipo_vehiculo VARCHAR(150) NOT NULL,
        descripción VARCHAR(150) NOT NULL
        
    ); 

    CREATE table autos (
        id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
        marca VARCHAR(150) NOT NULL,
        garantia DATE NOT NULL,
        cilindraje INT NOT NULL,
        FOREIGN KEY (id_categorias_de_carros) REFERENCES categorias_de_carros(id),
        descripciónVARCHAR(150) NOT NULL
    ); 

    CREATE table persona (
        id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
        nombre VARCHAR1(150) NOT NULL UNIQUE,
        apellido VARCHAR(150) NOT NULL,
        telefono INT NOT NULL,
        dirección VARCHAR(150) NOT NULL,
        documento INT NOT NULL
    ); 

    CREATE table Autos_persona  (
        id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
        FOREIGN KEY (id_autos) REFERENCES autos(id),
        FOREIGN KEY (id_persona) REFERENCES persona(id),
        descripción VARCHAR(150) NOT NULL
        
    ); 
```

![vista](jojo/base.png)

[ingresar](https://trello.com/b/epoUPRg2/parcial)