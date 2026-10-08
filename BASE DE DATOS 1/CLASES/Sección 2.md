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
>Se basa en las necesidades actuales, pero puede reflejar las necesidades futuras

| identifica                                                                      | no especifica                                                                               |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Entidades importantes (objetos que se convierten en tablas en la base de datos) | atributos (objetos que se convierten en columnas o campos en la base de datos)              |
| relaciones entre entidades                                                      | identificadores únicos (un atributo que se convierte en llave primaria en la base de datos) |
### Modelo lógico
Es una representación formal y detallada de las necesidades de información de una organización (entidades, atributos, relaciones y reglas de negocio), completamente independiente de cualquier tecnología, software o base de datos física donde se vaya a implementar.
> se representa en un diagrama de entidad- relación (ERD)

### Modelo físico 
Es la especificación detallada de cómo se implementa el [[Sección 2#Modelo lógico|modelo lógico]] en un motor de base de datos concreto, definiendo tablas, columnas, tipo de datos, claves primarias y foráneas e índices.
#### Paso para crear un modelo de datos físico
1. Modelar entidades como tablas
2. Modelar relaciones como claves foráneas
3. Modelar atributos como columnas
4. Modificar el modelo de datos físico en función de las restricciones y requisitos físicos

> El sueño del cliente (modelo conceptual) se convierte en una realidad física (modelo físico)

## 2.3 Entidades y atributos

### Entidades
Es cualquier cosa, persona, lugar o concepto del mundo real, relevante para el negocio, de la cual se necesita recopilar y registrar información
>El nombre de la entidad se debe escribir en singular y en mayúscula

#### Tipos de entidades
- Principal: Existe de forma independiente
- Característica: Existe gracias a otra entidad principal
- Intersección: Existe gracias a dos o más entidades

### Entidades e instancias
Una instancia es un miembro específico dentro de ese conjunto. Al pasar al modelo físico, cada instancia se convierte en una **fila o registro** de una tabla.
> las entidades contienen instancias

### Atributos
Es una característica, propiedad o dato descriptivo específico que ayuda a identificar, calificar o detallar a una entidad
> Se nombran en minúscula / mayúscula - minúscula y en singular **no debe incluir el nombre de la entidad**
#### Características
Se clasifican en 
- Obligatorios (no se permiten valores nulos) -> se indica con un *
- Opcionales (se permiten valores nulos) -> se indica con un °
#### Volátiles y no volátiles
##### Atributo no volátil
es aquel cuyo valor permanece constante una vez registrado
-> ej. la fecha de nacimiento
##### Atributo volátil
es aquel cuyo valor cambia con frecuencia a lo largo del tiempo
-> ej. edad, saldo disponible

#### Obligatorios y opcionales
##### Atributos obligatorios
deben tener un valor ( * )
##### Atributos opcionales
pueden no tener un valor y esta en blancos ( ° )

#### Únicos y compuestos
> Se diferencian por la posibilidad de dividirse en partes más pequeñas
##### Atributos únicos
no se pueden dividir en subpartes
-> ej. ID, primer nombre, apellido
##### Atributos compuestos 
se pueden dividir en subpartes más pequeñas que representan atributos básicos con diferentes significado propios
-> ej. nombre, se puede subdividir en primer nombre, apellido 

#### Único valor y de varios valores
##### Atributos de único valor
pueden tener un solo valor en un momento concreto 
-> ej. apellido
##### Atributos de varios valores
pueden tener más de un valor al mismo tiempo
-> ej. dirección, una persona o entidad pueden registrar varias direcciones simultáneas

### Estilos de notación para ERD
![[Pasted image 20261007225420.png]]
#### Notación Barker
representa las entidades con rectángulos de esquinas redondeadas; los atributos se listan dentro con símbolos específicos (`#` para UID, `*` para obligatorio y `o` para opcional), y la cardinalidad usa patas de gallo con líneas continuas (obligatorio) o discontinuas (opcional)
![[Pasted image 20261007225154.png]]
#### Notación de Ingeniería de la Información
representa las entidades con rectángulos estándar divididos en secciones (clave primaria arriba y atributos regulares abajo); la cardinalidad y opcionalidad se indican estrictamente en los extremos de las líneas mediante símbolos de círculos (cero / opcional), barras (uno / obligatorio) y patas de gallo (muchos)
![[Pasted image 20261007225216.png]]
#### Notación de Bachman
representa las entidades mediante rectángulos y enfoca las relaciones a través de flechas orientadas; la dirección de la flecha apunta hacia la entidad que representa el lado "muchos" de la relación (punteros o conjuntos en modelos de red)
![[Pasted image 20261007225204.png]]

## 2.4 Identificadores únicos


## 2.5 Relaciones
## 2.6 Modelado de relación de entidades (ERD)



