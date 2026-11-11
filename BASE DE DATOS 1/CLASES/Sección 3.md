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
