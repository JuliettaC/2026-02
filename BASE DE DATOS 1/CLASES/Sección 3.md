---
status: Acotación del modelo de datos
ejercicios:
tags:
  - BaseDeDatos
---
# Sección 3

> [!summary] En una frase
> Refinamiento de relaciones, seguimiento de datos históricos, normalización estructural y transformación del modelo lógico al modelo de base de datos física.

## 3.1 Más sobre las relaciones
### Relaciones de Bloqueo
Ocurre cuando el [[Sección 2#2.4 Identificadores únicos|identificador único (UID)]] de una entidad requiere de otra entidad para estar completo
- en el diagrama ERD, se representa mediante una barra cruzando la línea de relación hacia la entidad dependiente.
- Esta relación convierte el UID de la entidad en un [[Sección 2#UID compuesto|UID compuesto]] (formado por un atributo propio más la relación)
![[Pasted image 20261111172228.png]]

### Resolución de relaciones de varios a varios (M:M)
Las [[Sección 2#Relación de varios a varios (M:M)|relaciones M:M]] no pueden implementarse directamente en una base de datos física. Si existen atributos que describen la relación (ej. cantidad, fecha), la relación M:M debe resolverse
- Se resuelve creando una entidad de intersección intermedia.
- La relación M:M original se divide en dos relaciones 1:M de bloqueo

### Características de la entidad de intersección
- Sus relaciones hacia las entidades de origen son siempre obligatorias
- Se identifica a través de sus dos relaciones de origen (son relaciones de identificación)
- Suele contener atributos "consumibles" (cantidades utilizadas, fechas, etc)
- Tienden a ser entidades volátiles y de gran volumen.
-> Ej. Una relación M:M entre ORDER y PRODUCT se resuelve creando la entidad de intersección ORDER ITEM (que contiene el atributo Quantity)

### Relaciones no transferibles
Es una relación que,  una vez establecida, no se puede transferir entre las instancias de las entidades que conecta.
- Se representa gráficamente mediante un diamante sobre la línea de relación
- Solamente pueden ser relaciones obligatorias 
-> ej. El país de nacimiento de una persona (PERSON `born in` COUNTRY). No se puede transferir porque una persona no puede cambiar su país de nacimiento.
![[Pasted image 20261111174950.png]]

### Entidades Supertipo y Subtipo
Cuando varias entidades comparten atributos comunes pero también tienen características únicas, se modelan como una jerarquía principal-secundario.
#### Supertipo:
Entidad de nivel superior que contiene los atributos y relaciones comunes
#### Subtipo:
Sub agrupamiento (entidad de nivel inferior) que hereda del [[Sección 3#Supertipo|supertipo]] y contiene atributos o relaciones especificas.

##### Características del subtipo
- Se dibuja gráficamente dentro de la entidad supertipo
- Hereda todos los atributos y relaciones del supertipo
- Nunca existe en solitario (si hay un subtipo, debe haber al menos otro)
- Comparten exactamente la misma clave primaria que el supertipo.
![[Pasted image 20261111180213.png|144]]

##### Reglas de los subtipos
1. Exhaustivas: cada instancia del supertipo DEBE ser una instancia de algún subtipo. Se debe crear un subtipo "OTHER" para categorizar instancias que no encajen en los demás
2. Mutuamente excluyentes: Cada instancia encaja en un solo subtipo a la vez. No puede pertenecer a dos simultáneamente

### Enfoques de creación 
|**ENFOQUE**|**TIPO**|**DESCRIPCIÓN**|
|---|---|---|
|**Generalización**|Ascendente|Combinar entidades inferiores (ej. CAR, TRUCK) en una superior por atributos comunes (VEHICLE).|
|**Especialización**|Descendente|Desglosar una entidad superior (EMPLOYEE) en inferiores (CURRENT EMPLOYEE, EX-EMPLOYEE).|
### Relaciones jerárquicas 
Los datos jerárquicos se modelan como una serie de relaciones 1:M secuenciales
- Los UID se pueden propagar a través de varias relaciones de bloqueo. 
	--> ej. COMPANY está compuesta por DIVISION, que está compuesta por DEPARTMENT, que está compuesto por TEAM.
### Relaciones recursivas
Ocurren cuando una entidad se relaciona consigo misma (explicado de forma básica en [[Sección 2#Relación recursiva|relación recursiva]]).
- Se modelan gráficamente con un **bucle** (la línea sale y vuelve a entrar a la misma entidad).
- Para resolver una relación recursiva que resulta ser **M:M** (ej. lista de materiales donde un componente es parte de otro y está formado por varios), se debe crear una **entidad de intersección** genérica.