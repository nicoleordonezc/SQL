
# 🐾 Proyecto de Base de Datos: Clínica Veterinaria

## 📋 Descripción General

Este proyecto tiene como objetivo modelar y gestionar la base de datos de una **clínica veterinaria**. A través del diseño lógico, implementación y consultas SQL, se busca representar de manera estructurada la relación entre los dueños, sus mascotas, los servicios ofrecidos, las visitas realizadas y los tratamientos aplicados.

## 🔧 Proceso del Proyecto

### 1. 📐 Diagrama UML E-R

* El diagrama E-R incluye las siguientes entidades:

  * **Dueño**
  * **Mascota**
  * **Servicio**
  * **Visita**
  * **Tratamiento**

* Se especifican:

  * **Llaves primarias** (PK)
  * **Llaves foráneas** (FK)
  * **Relaciones** entre entidades y **cardinalidades** (1\:N, N:1)

  
+-------------------+     +--------------------+     +------------------+
|       Dueño       |     |      Mascota       |     |     Servicio     |
+-------------------+     +--------------------+     +------------------+
| - id: INT         |     | - id: INT          |     | - id: INT        |
| - cedula: INT     |     | - nombre: VARCHAR  |     | - nombre: VARCHAR|
| - nombre_completo:|     | - especie: VARCHAR |     | - descripcion:   |
|   VARCHAR         |     | - raza: VARCHAR    |     |   VARCHAR        |
| - telefono: INT   |     | - fecha_nacimiento:|     | - precio: FLOAT  |
| - direccion: VARCHAR|   |   DATE             |     +------------------+
+-------------------+     | - sexo: VARCHAR    |           ^
        ^                | - vacunado: VARCHAR|           |
        |                | - id_dueno: INT    |           |
        |                +--------------------+           |
        |                         |                        |
        |                         |                        |
        |                         v                        |
        |                +--------------------+           |
        |                |       Visita       |           |
        |                +--------------------+           |
        |                | - id: INT          |           |
        |                | - fecha: DATE      |           |
        |                | - id_mascota: INT  |-----------+
        |                | - id_servicio: INT |
        |                +--------------------+
        |                         ^
        |                         |
        |                         |
        |                         |
        |                +--------------------+
        |                |    Tratamiento     |
        |                +--------------------+
        |                | - id: INT          |
        |                | - nombre: VARCHAR  |
        |                | - observaciones:   |
        |                |   VARCHAR          |
        |                | - id_visita: INT   |
        |                +--------------------+
        |
        |
        |
+-------------------+
|    Mi_Mejor_Amigo |
+-------------------+
| - id: INT         |
| - nombre: VARCHAR |
+-------------------+


#### 🧩 Relación entre Entidades:

* Un **Dueño** tiene varias **Mascotas** (1\:N)
* Una **Mascota** puede tener muchas **Visitas** (1\:N)
* Una **Visita** puede incluir múltiples **Tratamientos** (1\:N)
* Cada **Tratamiento** aplica un **Servicio** (N:1)


### 2. 🗂 Archivo DDL – `estructura.sql`


* Declaración de **tipos de datos** apropiados (`INT`, `VARCHAR`, `DATE`, `DECIMAL`, etc.)
* **Llaves primarias** (`PRIMARY KEY`)
* **Llaves foráneas** (`FOREIGN KEY`)
* **Restricciones** (`NOT NULL`, `UNIQUE`)

### 3. 🧾 Archivo DML – `datos.sql`

* ✅ 5 **Dueños**
* ✅ 10 **Mascotas** relacionadas a dueños
* ✅ 5 **Servicios** ofrecidos por la clínica
* ✅ 10 **Visitas** realizadas por mascotas
* ✅ 5 **Tratamientos** aplicados durante visitas

### 4. 🔍 Archivo DQL – `consultas.sql`

Contiene al menos **15 consultas SQL** que demuestran diferentes capacidades y funciones del lenguaje.

## 📎 Notas Finales

Este proyecto demuestra el ciclo completo de creación de una base de datos relacional:

* Diseño conceptual (UML)
* Implementación física (DDL)
* Población de datos (DML)
* Explotación de información (DQL)

