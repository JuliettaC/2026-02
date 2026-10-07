## Ejercicio 1.4— Requisitos de negocio Prácticas

### Enunciado
> LibBook es una biblioteca digital de éxito que alquila CD y proporciona acceso a Internet para examinar su repositorio de artículos y revistas. Con el crecimiento del negocio, LibBook necesita mejorar su sistema de información para adaptarse a los cambios propuestos en el negocio. LibBook atrae a nuevos miembros con facilidad y el número de miembros crece rápidamente. Sin embargo, el número de miembros no es estable, lo que supone un motivo de preocupación. La idea principal es introducir el concepto de inscripción en LibBook. Los miembros pagarán una cuota de miembro y, en un principio, habrá tres tipos de miembros (corporativo, alumno, particular) aunque se pueden introducir otros más adelante. La inscripción para alumnos es gratuita. Los miembros corporativos y de profesorado deben pagar una cuota pero se les otorgan privilegios. El tipo de miembro solo se puede cambiar si se aporta una justificación válida. 
> **Su tarea consiste en identificar las reglas de negocio y las restricciones asociadas a partir del escenario del caso descrito.**

### Mi intento
REGLAS DE NEGOCIO:
1. hay tres tipos de miembros corporativo, alumno, particular 
2. la inscripción de alumnos es gratuita
3. corporativo y particular pagan una cuota 
4. solo se puede cambiar el tipo de miembro con una justificación valida
### Solución
REGLAS DE NEGOCIO:
1. Inscripción y cobro general: Los miembros deben pagar una cuota de membresía para pertenecer a la biblioteca.
2. Membresía de alumnos: La inscripción para los alumnos es gratuita y no requiere cuota de pago
3. Membresía de corporativos y profesorado: Los miembros corporativos y de profesorado pagan una cuota que les otorga privilegios exclusivos
4. Servicios ofrecidos: LibBook alquila CD y provee acceso a internet para la consulta de revistas y artículos.
RESTRICCIONES: 
- Límite inicial de categorías Inicialmente, los miembros solo pueden pertenecer a una de las tres categorías, con posibilidad de ampliar a otras más adelante.
- Cambio de tipo de membresía: El tipo de miembro no se puede modificar arbitrariamente; solo se permite el cambio si se aporta una justificación válida
### Errores / aprendizaje
**Error:** Me faltaron las restricciones del negocio y confundí una restricción con una regla del negocio
**Aprendí:**  
1. Conocer la diferencia clave entre los conceptos
- **Regla de negocio:** Es una política, norma operativa o directriz general que describe **qué hace o cómo opera el negocio** (por ejemplo: _"los miembros pagan una cuota"_).
- **Restricción:** Es una **limitación o condición estricta** que acota a la regla de negocio, impidiendo que suceda cualquier cosa (por ejemplo: _"el tipo de inscripción no puede cambiarse"_ o _"solo existen 3 categorías"_).
- **Problema:** Es el conflicto o necesidad que la empresa busca solucionar (por ejemplo: _"la base de clientes no es estable"_).
- **Suposición:** Una premisa o conjetura que se toma como verdadera sin haber sido verificada formalmente.    
 2. Método de resolución en 4 pasos
	1. **Lectura y filtrado:** Separa la historia de contexto de los datos operativos. Frases como _"LibBook es una empresa de éxito"_ son decorativas y no generan reglas ni restricciones.
     2. **Subrayar acciones y obligaciones:** Busca verbos de acción y condiciones obligatorias: _"pagarán"_, _"se les otorgan"_, _"ofrece"_, etc. De aquí se obtienen las **reglas de negocio**.
	3. **Detectar los límites y condiciones:**  Localiza palabras clave de limitación como: _"solo"_, _"únicamente"_, _"no se puede"_, _"a menos que"_, o listas cerradas de valores. De aquí se obtienen las **restricciones**.
	4. **Redactar de forma clara y directa:** Escribe cada regla y restricción en una sola frase breve y declarativa, asociando la restricción directamente con la regla que está limitando.
### Enunciado
> El hospital Star Care es un hospital con varias especialidades que atiende las necesidades de diferentes pacientes. A cada médico registrado en este hospital se le asigna un ID único que empieza por las letras "DC". El hospital garantiza que los médicos asociados tienen un mínimo de siete años de experiencia laboral. Cada paciente se debe registrar en el hospital en su primera visita. Cuando llega un paciente, se le asigna un número de paciente único que empieza por las letras "PT". 
> **Su tarea consiste en identificar las reglas de negocio y las restricciones asociadas a partir del escenario del caso descrito.**

### Mi intento
- REGLAS DE NEGOCIO:
	1. Se le asigna un ID único a cada médico que empieza por las letras "DC"
	2. Registro de pacientes
- RESTRICCIONES:
	1. Los médicos tienen un mínimo de 7 años de experiencia laboral 

### Solución
- REGLAS DE NEGOCIO:
	1. Registro e identificación de médicos: A cada médico registrado en el hospital se le debe asignar un identificador
	2. Experiencia del personal médico: Los médicos asociados al hospital deben contar con experiencia laboral comprobable
	3. Registro de pacientes: Cada paciente debe registrarse obligatoriamente en el sistema durante su primera visita al hospital
	4. Identificación de pacientes: A cada paciente que ingresa al hospital debe asignar un número de identificación
- RESTRICCIONES:
	1. Formato ID de médico: Debe empezar con DC
	2. Los médicos tienen un mínimo de 7 años de experiencia laboral 
	3. El ID del paciente debe empezar con PT
### Errores / aprendizaje
**Error:** los mismos del anterior
**Aprendí:**
Una regla describe **qué se hace** y una restricción describe **el límite, condición o formato exacto** de esa acción.
1. **Aplica la prueba de las dos preguntas:**
    - ¿Qué hace el sistema o negocio? $\rightarrow$ Es una **Regla de negocio**.
    - ¿Qué límite, valor fijo o condición le impone el negocio a esa acción? $\rightarrow$ Es una **Restricción**.
2. **Divide la frase en dos mitades:**
    - _Mitad 1 (Acción):_ "A cada médico se le asigna un ID único" (Regla).
    - _Mitad 2 (Límite):_ "El ID debe iniciar obligatoriamente con 'DC'" (Restricción).
3. **Usa siempre la estructura sujeto + verbo:**
    - Evita poner etiquetas sueltas como _"Registro de pacientes"_. Redacta siempre una oración completa: _"Cada paciente nuevo debe registrarse en el hospital"_ o _"El sistema asigna un identificador..."_.
4. **Rastrea palabras de filtro:**
    - Cada vez que leas números, fechas, prefijos o palabras como _"mínimo"_, _"máximo"_, _"únicamente"_ o _"empieza por"_, extráelas de inmediato hacia tu lista de restricciones.
### Conceptos relacionados
[[Sección 1#Reglas de negocio|Reglas de negocio]]

## Ejercicio 1.4:  Base de datos de la tienda Oracle Baseball League

### Enunciado
> Usted es una pequeña empresa de consultoría especializada en el desarrollo de bases de datos. Le acaban de adjudicar un contrato para desarrollar un modelo de datos para un sistema de aplicaciones de bases de datos de una pequeña tienda denominada Oracle Baseball League (OBL). La tienda ofrece servicios de venta de conjuntos de béisbol para toda la comunidad. OBL tiene dos tipos de cliente; hay personas que pueden adquirir artículos como pelotas, zapatillas, guantes, camisas, camisetas serigrafiadas y pantalones. Además, los clientes pueden representar a un equipo cuando adquieren uniformes y equipación conjunta. Los equipos y los clientes individuales son libres de comprar cualquier artículo de la lista de inventario, pero los equipos obtienen un descuento en el precio de lista según el número de jugadores. Cuando un cliente realiza un pedido, registramos los artículos de ese pedido en nuestra base de datos. El equipo de OBL cuenta con tres representantes de ventas que oficialmente solo atienden a equipos, pero se sabe que gestionan las quejas de los clientes individuales.
> **Mediante el texto proporcionado en el escenario anterior, identifique los requisitos de negocio que le permitirán comprender los procesos de negocio implicados en la ejecución de este tipo de organización. 
> Utilice las siguientes categorías como ayuda: 
> • Regla de negocio: se utiliza para comprender los procesos de negocio y la naturaleza, rol y ámbito de los datos. 
> • Suposición: se puede definir como un hecho o afirmación que se da por sentado. 
> • Problema: se puede definir como una situación o escenario que requiere atención y una posible solución para solventar la situación. 
> Elabore una lista de las necesidades de negocio, las reglas y las suposiciones según el escenario, la investigación y los objetivos. (Las respuestas pueden variar).**

### Mi intento
- REGLA DEL NEGOCIO:
	1. Existen dos tipos de clientes los cuales pueden adquirir artículos de la tienda
	2. los clientes pueden representar un equipo al momento de adquirir uniformes y equipación
	3. los equipos obtienen descuentos dependiendo de la cantidad de jugadores que lo conforman
	4. los pedidos se registran en una base de datos
	5. los representantes de ventas solo atienden equipos pero pueden gestionar quejas de los clientes individuales
- SUPOSICIÓN:
	1. 
- PROBLEMA:
	1. 
### Solución
- REGLA DEL NEGOCIO:
	1. **Tipología de clientes:** La base de datos debe admitir clientes individuales y clientes asociados a una entidad "Equipo". Ambos pueden adquirir cualquier artículo del catálogo.
	2. **Cálculo de descuentos por volumen de jugadores:** El descuento sobre el precio de lista solo aplica si la compra corresponde a un equipo, y su porcentaje debe calcularse en función de la cantidad de integrantes registrados para dicho equipo.
	3. **Trazabilidad de pedidos:** Todo pedido debe registrarse con su detalle de líneas de pedido (artículos, cantidades, precio unitario aplicado y subtotales).
	4. **Asignación formal de ventas:** Los representantes de ventas están asignados contractualmente a la gestión de ventas de equipos, no de ventas individuales directas de mostrador.
- SUPOSICIÓN:
	1. **Estructura del descuento:** Existe una tabla o escala tabulada de descuentos (por ejemplo: de 9 a 15 jugadores = 10%, de 16 o más = 15%) y una regla para validar el número de jugadores que componen el equipo.
- PROBLEMA:
	1. **Falta de canal formal para quejas individuales:** Los representantes atienden informalmente las quejas de clientes individuales, lo que desvía su tiempo de la atención a equipos y provoca pérdida de trazabilidad de los reclamos.
- _Solución de datos:_ Incorporar una entidad o módulo de `Reclamo / Queja` vinculada al cliente y a la orden, independientemente del tipo de cliente.
### Errores / aprendizaje

 **Error:**
 Confundir la **descripción literal de la operación diaria** con la formulación formal de reglas de negocio, y dejar vacíos los campos de **suposiciones** y **problemas**.
- **Por qué:**
**Aprendí:**

| **Categoría**        | **Tu pregunta mental**                                 | **Tu plantilla de respuesta**                                     |
| -------------------- | ------------------------------------------------------ | ----------------------------------------------------------------- |
| **Regla de Negocio** | ¿Qué debe obligar o impedir el sistema?                | _«Para que ocurra [X], debe cumplirse obligatoriamente [Y]»_      |
| **Suposición**       | ¿Qué dato falta aquí para que esto funcione?           | _«Se asume que el negocio cuenta con un criterio/tabla para [X]»_ |
| **Problema**         | ¿Qué se está haciendo a ciegas o de forma desordenada? | _«Falta un registro formal de [X], lo que provoca [Y]»_           |
### Conceptos relacionados
[[Sección 1#Reglas de negocio|Reglas de negocio]]
