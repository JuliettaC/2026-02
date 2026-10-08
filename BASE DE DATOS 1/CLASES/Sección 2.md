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

### Identificadores únicos
Es un [[Sección 2#Atributos|atributo]] que cumple con las siguientes reglas
1. es único en todas las instancias de la entidad
2. tiene un valor no NULL para cada [[Sección 2#Entidades e instancias|instancia]] de la entidad en el tiempo que dura la instancia 
3. tiene un valor que nunca cambia en el tiempo 
> un UID sirve para distinguir cada registro dentro de una base de datos sin riesgo de confusión. 
#### UID simple
Se compone de un solo atributo se una cuando un único dato basta para garantizar que no existan duplicados.
-> ej. Entidad PERSONA -> Rut

#### UID compuesto
Es una combinación de dos o más atributos se usa cuando ningún campo por sí solo es único pero al juntarlos forman una clave irrepetible
-> ej. ENTIDAD HORARIO DE CLASE -> Número de aula, Hora combinación num de aula + hora crean un identificador único  

#### UID artificial 
Se crea a partir de datos que asigna o genera el sistema y no se producen de forma natural, pero se crean con fines de identificación

#### UIDs candidatos
Ocurre cuando una entidad tiene mas de un posible UID para identificarla
-> ej. Número de identificación, Número de nomina
##### Selección y roles
###### UID Primario
Solo uno de los candidatos se elige como principal
###### UID secundarios
Son todos los demás candidatos que no fueron elegidos como el primario
#### Llave primaria
Columna o juego de columnas que **identifica de forma única cada fila** de una tabla. Puede ser una columna existente o una generada por la base de datos mediante una secuencia.
REGLAS
- Debe contener un **valor único** para cada fila.
- **No puede contener valores nulos** (no admite `NULL`).
> Es la transformación de un **UID** (del modelo lógico) al pasar a la **base de datos física**.

## 2.5 Relaciones

### Relaciones
Es una asociación bidireccional y significativa entre dos entidades o entre una entidad y ella misma. Sirve para representar cómo interactúan o se conectan los datos dentro del modelo
#### Línea de relación
En el [[Sección 2#Estilos de notación para ERD|diagrama de ERD]] se traza una línea entre las dos entidades 
- Línea sólida: representa una relación obligatoria
- Línea discontinua: representa una relación opcional
- Única punta: representa una sola instancia ("uno")
- Pata de gallo: representa una o más instancias ("varios")

### Componentes de una relación
#### Nombre
Etiqueta que describe la conexión en minúsculas y se ubica cerca del punto de inicio de la entidad a la que está asignada
#### Opcionalidad 
Indica si la relación debe existir o no (mínimo de la relación)
- Obligatoria: Al menos un registro coincidente (se lee debe ser o debe)
- Opcional: Cero registros coincidentes (se lee puede ser o puede)
#### Cardinalidad
Mide la cantidad y responde a la pregunta "cuántos?" (máximo de la relación)
- Uno: Un único registro coincidente (termina en línea simple/única punta)
- Varios: Uno o más registros coincidentes (termina en pata de gallo)
#### Sintaxis de regla de negocio 
Cada entidad1 {debe ser o puede ser} nombre de relación {uno o más o único} entidad2

### Tipos de relaciones

### Relación de una a varios o varios a uno 
>1 - 1 (1 a 1)
>1 - m (1 a muchos)
>m - 1 (muchos a 1)
>m - m (muchos a muchos)

#### Relación de uno a varios (1-m) o varios a uno (m-1)
Tiene la cardinalidad de uno o más en una dirección y de solo uno en la dirección contraria

-> ej. Cada CUSTOMER debe recibir la visita de un único SALES REPRESENTATIVE / Cada SALES REPRESENTATIVE puede asignarse a uno o más CUSTOMER
#### Relación de varios a varios (M:M)
Tiene la cardinalidad de uno o más en ambas direcciones.

-> ej. Cada EMPLOYEE puede asignarse a uno o más JOB / Cada JOB puede realizarlo uno o más EMPLOYEE
#### Relación de uno a uno (1:1)
Tiene la cardinalidad de solo uno en ambas direcciones.

-> ej. Cada COMPUTER debe contener una única MOTHERBOARD / Cada MOTHERBOARD debe contenerla un único COMPUTER
#### Relación recursiva
Ocurre cuando una entidad se relaciona consigo misma.

-> ej. Cada EMPLOYEE puede gestionar uno o más EMPLOYEE / Cada EMPLOYEE debe ser gestionado por un único EMPLOYEE

### Matriz de relaciones
Herramienta en cuadrícula para recopilar información inicial entre un juego de entidades:
- Entidades listadas a la izquierda (filas) y arriba (columnas)
- Cuadro con texto: indica la relación y su nombre en esa dirección
- Cuadro vacío: indica que no existe relación directa entre ese par
- Cuadros en la diagonal: representan las relaciones recursivas
- Por encima de la diagonal: es la imagen inversa o duplicada de lo que está por debajo 

### Clave foránea
Es la transformación física de una relación conceptual hacia la base de datos relacional.

Es una columna o combinación de columnas de una tabla que hace referencia a una [[Sección 2#Llave primaria|llave primaria]] en la misma tabla o en otra tabla.\

## 2.6 Modelado de relación de entidades (ERD)


