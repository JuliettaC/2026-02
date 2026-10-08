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

## 2.3.1 Entidades y atributos
> Escribir aquí qué pide el ejercicio.

### Mi intento

```sql
-- Escribir aquí mi primera solución
```

### Solución

```sql
-- Escribir aquí la solución correcta o final
```

### Errores / aprendizaje

- **Error:**
- **Por qué:**
- **Aprendí:**

### Conceptos relacionados

<!-- Añade solo WikiLinks relevantes para este ejercicio. -->




