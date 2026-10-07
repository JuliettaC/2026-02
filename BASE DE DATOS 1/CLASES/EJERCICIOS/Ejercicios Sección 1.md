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


