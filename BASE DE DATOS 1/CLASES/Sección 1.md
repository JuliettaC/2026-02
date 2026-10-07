---
status: revisar
tags:
  - BaseDeDatos
---
# Sección 1: Introducción

> [!summary] En una frase
> conceptos básicos de base de datos.

## 1.2 Introducción a la base de datos

### Datos vs información
| DATOS                                       | INFORMACIÓN                                                                 |
| ------------------------------------------- | --------------------------------------------------------------------------- |
| Hechos recopilados sobre un tema / elemento | Resultado de la combinación, comparación y realización de cálculos de datos |
>La información es el resultado de los datos recopilados 

### Base de datos
Es una recopilación organizada de datos estructurados que se almacenan de forma electrónica en un sistema informático.
- Proporciona los medios para transformar los datos obtenidos en información útil
#### Base de datos relacionales
Almacena la información en tablas con filas y columnas
- TABLA:  Es una recopilación de registros.
	-> objeto principal de una base de datos 
- FILA: Instancia->SOLO EN ORACLE, registro->en general
- COLUMNA: Campo o atributo-> en general
>Una base de datos relacional consta de tablas que están vinculadas por un atributo común

## 1.3 Tipo de modelo de bases de datos
### Proceso de desarrollo de bases de datos
1. Estrategia y análisis: Modelado de datos conceptuales
2. Diseño: Diseño de base de datos
3. Creación: Creación de base de datos
### Tipo de modelo de bases de datos
#### Modelo de archivo plano
Es una base de datos diseñada en torno a una única tabla 
->Normalmente están en texto sin formato, en el que cada línea contiene solo un registro y se separan con delimitadores (como tabuladores y comas)
![[Pasted image 20261006193456.png|221]]
#### Modelo jerárquico
Los datos se organizan en una estructura de árbol y se almacenan como registros que se conectan entre sí a través de enlaces
![[Pasted image 20261006193731.png|214]]
#### Modelo de red
Organiza los datos como una telaraña donde todo puede conectarse entre si
![[Pasted image 20261006193822.png|196]]
>En el [[Sección 1#modelo jerárquico|modelo jerárquico]] cada dato solo puede tener un padre, mientras que en el [[Sección 1#Modelo de red|de red]] se pueden tener múltiples padres y conectar en cualquier dirección
#### Modelo orientado a objetos
Guarda la información como "objetos" de la vida real, reuniendo en un solo paquete lo que el objeto **es** (sus datos) y lo que el objeto **puede hacer** (sus acciones)
![[Pasted image 20261006195044.png|259]]
#### Modelo relacional
Organiza los datos en [[Sección 1#Base de datos relacionales|tablas]] compuestas por filas y columnas que se conectan entre sí mediante identificadores comunes o claves
![[Pasted image 20261006194833.jpg|231]]
>El [[Sección 1#Modelo de archivo plano|archivo plano]] guarda toda la información en un único texto continuo sin conectar datos automáticamente, mientras que el [[Sección 1#Modelo relacional|relacional]] separa la información en múltiples tablas vinculadas para evitar repeticiones y errores

## 1.4 Requisitos de negocio

### Necesidad de una solución de base de datos
Permite a varios usuarios integrar y gestionar grandes volúmenes de datos interrelacionados, reduciendo la redundancia y asegurando la integridad que un archivo plano no puede ofrecer
### Reglas de negocio 
Son pautas simples que describen los procesos operativos y definen las relaciones y restricciones sobre los datos de una organización
- **Restricción:** Limitación explícita que restringe el alcance o comportamiento de una regla de negocio
- **Suposición:** Declaración o hecho que se da por sentado sin comprobarse
- **Problema:** Situación u obstáculo que genera inconsistencias o requiere solución
### Modelado conceptual
Representa de forma clara los requisitos del negocio para evitar errores y sirve como base sólida para construir la base de datos física

#BaseDeDatos 

