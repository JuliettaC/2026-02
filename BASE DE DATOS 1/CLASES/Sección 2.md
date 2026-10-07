---
status: revisar
ejercicios: "[[ejercicios Sección 2]]"
---
# Sección 2

> [!summary] En una frase
> Modelado de datos

## 2.1 Base de datos relacionales
### Tabla única
una [[Sección 1#Modelo de archivo plano|base de datos de archivo plano]] almacena datos en una única tabla están normalmente en texto sin formato, en el que cada línea contiene solo un registro

| ventajas                                       | desventajas                                 |
| ---------------------------------------------- | ------------------------------------------- |
| Fáciles de -> comprender                       | menos seguridad                             |
| -> implementar                                 | inconsistencias de datos                    |
| -> extraer información                         | redundancia de datos                        |
| todos los registros se almacenan un solo lugar | uso de compartido de información laborioso  |
| ordenamiento y filtrado de informes simples    | lentitud para bases de datos de gran tamaño |
| menos requisitos de software y hardware        |                                             |
![[Sección 1#Modelo relacional]]
### Tablas relacionales
es una estructura simple donde se organizan y se almacenan datos
### Reglas para tablas de bases de datos relacionales 
- cada tabla tiene un nombre distinto
- puede contener varias filas
- cada tabla tiene un valor para identificar de forma única las filas
- las entradas en las columnas son valores únicos y son del mismo tipo
- el orden de las filas y columnas no es importante
### Términos clave
- TABLA: estructura de almacenamiento básica
- COLUMNA: atributo que describe la información de la tabla
- LLAVE PRIMARIA: identificador único para cada fila
- CLAVE FORANEA: columna que hace referencia a una columna de llave primaria en otra tabla
- FILA: datos de una instancia de tabla
- CAMPO: el único valor que se encuentra en la intersección de una fila y una columna

## 2.2 Modelos de datos conceptuales y físicos
### Modelo conceptual
Aborda las necesidades de un negocio (lo ideal desde el punto de vista conceptual), pero no su implantación (lo físicamente posible)

## 2.3 Entidades y atributos
## 2.4 Identificadores únicos
## 2.5 Relaciones
## 2.6 Modelado de relación de entidades (ERD)



