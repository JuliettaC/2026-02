## Ejercicio 2-1: Bases de datos relacionales Prácticas

### Enunciado
> 1. Identifique las posibles tablas y campos asociados del escenario proporcionado. Book.com es una tienda virtual en línea en Internet donde los clientes pueden examinar el catálogo y seleccionar los productos que deseen. a. Cada libro tiene un título, ISBN, año y precio. La tienda también conserva la información del autor y del editor de cualquier libro. b. Para los autores, la base de datos conserva el nombre, la dirección y la URL de su página inicial. c. Para los editores, la base de datos conserva el nombre, la dirección, el número de teléfono y la URL de su sitio web. d. La tienda tiene varios almacenes, cada uno de los cuales tiene un código, una dirección y un número de teléfono. e. El almacén tiene en stock muchos libros. Un libro puede estar en stock en varios almacenes. f. La base de datos registra el número de copias de un libro almacenadas en stock en varios almacenes. g. La librería conserva el nombre, la dirección, el ID de correo electrónico y el número de teléfono de sus clientes. h. Un cliente es propietario de varios carritos de la compra. El carrito de la compra se identifica mediante un Shopping_Cart_ID y contiene varios libros. i. Algunos carritos de la compra pueden contener más de una copia del mismo libro. La base de datos registra el número de copias de cada libro que hay en cualquier carrito de la compra. j. En ese momento, se necesitará más información para completar la transacción. Normalmente, se le pedirá al cliente que rellene o seleccione una dirección de facturación, una dirección de envío, una opción de envío e información de pago como el número de tarjeta de crédito. Se enviará una notificación por correo electrónico al cliente en cuanto se realice el pedido.

### Mi intento
### Solución

```sql
-- Escribir aquí la solución correcta o final
```

### Errores / aprendizaje

- **Error:**
- **Por qué:**
- **Aprendí:**

### Conceptos relacionados
[[Sección 2#2.1 Base de datos relacionales]]

## Ejercicio 2-2: Modelos de datos conceptuales y físicos Prácticas

### Enunciado
> En esta práctica, ilustrará la diferencia entre una idea y un resultado físico. Tareas 
> 1. Proporcione cinco razones para crear un modelo de datos conceptual. 
> 2. Enumere dos ejemplos de modelos conceptuales y modelos físicos.

### Mi intento
- tarea 1
1. facilita la comunicación con el cliente
2. independencia tecnológica permitiendo concentrarse puramente en las reglas y necesidades de información del negocio
3. detección temprana de errores y omisiones
4. prevención de redundancia y mantenimiento de integridad
5. base y guía para el diseño fisico
- tarea 2
Ejemplos de Modelos Conceptuales (La idea / El plano abstracto):
1. **El plano arquitectónico o croquis de una casa:** Muestra la distribución de espacios, habitaciones y cómo se conectan entre sí, sin entrar en marcas de tuberías o tipos de cableado eléctrico.
2. **Un Diagrama Entidad-Relación (ERD) conceptual:** Modela entidades como `CLIENTE` y `PEDIDO`, indicando que un cliente puede realizar muchos pedidos, sin definir tipos de datos SQL, índices o nombres de tablas de almacenamiento.
Ejemplos de Modelos Físicos (La implementación / El resultado tangible):
3. **La casa construida en el terreno:** La estructura real con ladrillos específicos, tuberías de PVC de cierto diámetro, cableado de cobre y especificaciones exactas de carga y materiales.
4. **El script de tablas (DDL en SQL) en un DBMS específico:** La definición técnica concreta (por ejemplo, en Oracle Database) con sentencias `CREATE TABLE pedidos (id_pedido NUMBER(10) PRIMARY KEY, fecha DATE NOT NULL...)`, asignación de espacios de tabla (_tablespaces_) y creación de índices.

### Conceptos relacionados
[[Sección 2#2.2 Modelos de datos conceptuales y físicos]]

## Ejercicio 2.3 — Base de datos de la tienda Oracle Baseball League

### Enunciado
> Escenario del proyecto: Usted es una pequeña empresa de consultoría especializada en el desarrollo de bases de datos. Le acaban de adjudicar un contrato para desarrollar un modelo de datos para un sistema de aplicaciones de bases de datos de una pequeña tienda denominada Oracle Baseball League (OBL). La tienda ofrece servicios de venta de conjuntos de béisbol para toda la comunidad. OBL tiene dos tipos de cliente; hay personas que pueden adquirir artículos como pelotas, zapatillas, guantes, camisas, camisetas serigrafiadas y pantalones. Además, los clientes pueden representar a un equipo cuando adquieren uniformes y equipación conjunta. Los equipos y los clientes individuales son libres de comprar cualquier artículo de la lista de inventario, pero los equipos obtienen un descuento en el precio de lista según el número de jugadores. Cuando un cliente realiza un pedido, registramos los artículos de ese pedido en nuestra base de datos. El equipo de OBL cuenta con tres representantes de ventas que oficialmente solo atienden a equipos, pero se sabe que gestionan las quejas de los clientes individuales.

> Transcripción de la reunión Entrevistador: En la información proporcionada, ha indicado que existen dos tipos de cliente: individual y equipo. ¿Qué información guarda sobre los clientes y cómo distingue los dos tipos de cliente? Manager: De todos los clientes, realizamos un seguimiento del nombre, la dirección, el número de teléfono, la dirección de correo electrónico y, dado el caso, el equipo al que pertenecen. También se realiza un seguimiento del saldo actual del cliente en nuestro sistema. Entrevistador: Ha dicho que los clientes pueden realizar un pedido de cualquier artículo de la lista de inventario. ¿Qué tipos de artículos pueden comprar? Manager: Los clientes individuales pueden adquirir artículos como pelotas, zapatillas, guantes, camisas, camisetas serigrafiadas y pantalones. Además, los equipos pueden realizar pedidos de toda la equipación, así como de pelotas, camisetas de calentamiento y para jugar, y obtener un descuento sobre la lista de precio según el número de jugadores de dicho equipo. Cuando un equipo compra artículos de la tienda, es necesario que el cliente registrado de ese equipo realice el pedido. Entrevistador: ¿Tiene alguna información específica sobre artículos vendidos que desea registrar en el sistema? Manager: Los clientes nunca compran artículos sin verlos, así que siempre hay una descripción y un precio disponible. El seguimiento de los artículos de inventario forma parte del negocio, así como la descripción y el precio. Realizamos un seguimiento del nombre, color (si procede), tamaño (si procede) y categoría del artículo. Hay tres categorías de artículos que utilizamos: ropa, equipación y otros. Para nuestro inventario, también realizamos un seguimiento del coste unitario del mayorista, así como del número de unidades disponibles; cuando no disponemos de unidades, se registra un cero en el sistema. Entrevistador: ¿Cómo registra los artículos que han pedido los clientes? Manager: Cuando un cliente realiza un pedido, registramos los siguientes detalles de la compra: la fecha, los artículos comprados, el tamaño del artículo, el color, el número de unidades y el precio de cada unidad. También nos gustaría guardar el precio total del pedido para todos los artículos solicitados. Entrevistador: Existen tres representantes de ventas en la empresa, ¿cuál es su función? Manager: Cada cliente de equipo tiene asignado un representante de ventas como vendedor que trabaja a comisión; no se permite que dos vendedores atiendan al mismo cliente. Aunque los representantes de ventas solo atienden a los equipos, es sabido que atienden quejas de los clientes individuales. Entrevistador: ¿Cómo registra los detalles de los representantes de ventas en el sistema? Copyright © 2020, Oracle y/o sus filiales. Todos los derechos reservados. Oracle y Java son marcas comerciales registradas de Oracle y/o sus filiales. Todos los demás nombres pueden ser marcas comerciales de sus respectivos propietarios 3 Manager: Para cada uno de los tres representantes de ventas, realizamos un seguimiento de su nombre, dirección, teléfono, dirección de correo electrónico, comisión total y tipo de comisión.

### 2.3.1 Entidades y atributos
> Mediante el análisis del texto en el escenario especificado, identifique las posibles entidades que tendrán que representarse en un sistema de base de datos relacional. Las entidades suelen ser los sustantivos de la descripción del escenario; sin embargo, no todos los sustantivos se convierten en entidad. Piénselo detenidamente, pero recuerde que está identificando las posibles entidades y no creando una lista definitiva.

#### Mi intento
ENTIDADES:
1. CLIENTE
2. ARTÍCULO
3. EQUIPO
4. PEDIDO
5. REPRESENTANTE_VENTAS

#### Solución
ENTIDADES:
1. CLIENTE
2. EQUIPO
3. REPRESENTANTE DE VENTAS
4. PEDIDO
5. ARTÍCULO
6. INVENTARIO

#### Conceptos relacionados
[[Sección 2#Entidades e instancias]]
[[Sección 2#Entidades]]

### 2.3.2 - atributos
> Analizando el texto del escenario especificado, identifique las posibles entidades que se utilizarán para almacenar información sobre las entidades identificadas previamente. Los atributos suelen encontrarse al identificar los sustantivos que describen otros nombres (nuestras entidades).

#### Mi intento
ENTIDADES:
1. CLIENTE
	- Tipo de cliente
	- Nombre
	- Dirección
	- Número de teléfono
	- Correo electrónico
	- **Equipo**
2. EQUIPO
	- Nombre del equipo
	- Número de jugadores
	- Descuento
3. REPRESENTANTE DE VENTAS
	- Nombre
	- dirección
	- teléfono
	- correo electrónico 
	- comisión
	- tipo de comisión
4. PEDIDO
	- Fecha
	- Artículos
	- Precio total
5. ARTÍCULO
	- Nombre del artículo 
	- Color 
	- Tamaño 
	- Categoría
	- Id artículo
6. INVENTARIO
	- Id artículo
	- coste unitario
	- unidades disponibles
#### Solución

#### Errores / aprendizaje

- **Error:**
- **Por qué:**
- **Aprendí:**

#### Conceptos relacionados
[[Sección 2#Atributos]]





