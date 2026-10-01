aModelo identidad - relación 

El nombre tiene que ser singular y en mayúsculas.

Atributos	
Las entidades poseen cualidades o propiedades conocidas como atributos: una sala de clases tiene, nombre, una ubicacion, un cupo, etc.

Dato especifico, significativo para una entidad, que:
1. La califica; ejemplo: color

Vehiculo
Numero motor --- Identificador unico
Patente
Tipo
Marca --- Atributos obligatorios (opcionalidad)
Modelo
Numero de puertas
Numero de asientos --- Atributos opcionales (opcionalidad)

Cada atributo posee un TIPO,
Ejemplo: 
Rut - Numero
Nombre - String
Fecha - Date

Dominio: Conjunto de reglas de validacion, restricciones de formato, y otras propiedades que se aplican a un grupo de atributos

Conversion de atributos en entidades:
- Esto ocurre cuando: 
	- El atributo puede tener varios valores dada una ocurrencia de una entidad, o 
	- El atributo puede tener a su vez atributos, o
	- Requerimos historia de cambios en los valores del atributo. 

Bomberos:
	- Rut
	- Nombre
	- Edad
	- Lugar de nacimiento
	- Hijos

Para los datos redundantes (que se repiten mucho) se debe normalizar las entidades

Se crea una tabla nueva con lugar de nacimiento

Bomberos:
	- Rut
	- Nombre
	- Edad
	-ID.Nacimiento (si no tiene esta inconsistente)
	- Hijos

Conceptos de Clave foranea y Clave principal

Toda relacion tiene un bombre, que expresa la asociacion entre las entidades,
	- Tiene un grado (o cardinalidad)
	- Tiene opcionalidad
- Formalmente, una relacion R entre con  enter conjuntos de entidades (E1, E2, ..., En), se representa mediante un conjunto de n-tuplas (e1, e2, ..., e(n))
- Una rtelacion tambien puede tener atributos, por ejemplo, en la relacion "arrendar" en atributo de fecha podria indicar la fecha en que se devuelve el libro. 

cardinalidad de la relacion 
m: muchos
 
1 - 1 (1 a 1)
1 - m (1 a muchos)
m - 1 (muchos a 1)
m - m (muchos a muchos)

1 bombero nace en 1 lugar
1 lugar pueden nacer muchos bomberos

- El grado se representa por un extremo simple(uno) o "pata de gallo"(muchos)
- El nombre se escribe en los extremos

24.09

## Ejercicio 2.3.1
ENTIDADES

CLIENTE
ARTICULO
EQUIPO
INVENTARIO
PEDIDO
REPRESENTANTE DE VENTAS
## Ejercicio 2.3.2

Atributos

CLIENTE
~~Tipo de cliente~~
Nombre
Dirección 
Teléfono
correo electrónico
saldo 
equipo

ARTICULO
Nombre del articulo
id inventario

EQUIPO
descuento 
numero judador
nombre

INVENTARIO
-#id inventario
coste unitario 
unidades disponibles

PEDIDO
fecha
articulos comprados
color 
numero de unidades
precio 
precio total

REPRESENTANTE DE VENTAS
nombre 
dirección
teléfono
correo electrónico
comisión 
tipo de comisión

## ejercicio 2.3.3

01.10 
relaciones 
clave foranea es una llave primaria en otra entidad
componentes de una relación 
