---
tags:
  - java
  - java/oop
status: documentado
aliases:
  - "Herencia"
  - "Polimorfismo"
  - "Interfaces"
  - "Encapsulamiento"
---

# Herencia, interfaces y composición
> [!summary] En una frase
> Heredar especializa un tipo; implementar una interfaz cumple un contrato; componer reúne objetos que colaboran.

## Herencia y super
Una clase usa `extends` para heredar de una única superclase directa. Una subclase debe representar una especialización que pueda utilizarse donde se espera el tipo base. En los apuntes, LibroImpreso y Revista son tipos de Material; Regular e Intercambio son tipos de Alumno.

Los constructores no se heredan. `super(...)` invoca un constructor de la superclase para inicializar su parte del objeto. Si se omite una invocación explícita, la llamada implícita sin argumentos necesita un constructor accesible compatible. Los campos privados de la superclase no se vuelven accesibles directamente en la subclase: se usan las operaciones que la clase base permite.

## Clases y métodos abstractos
Una clase `abstract` no se instancia directamente, pero puede tener campos, constructor y métodos con implementación. Un método abstracto declara una operación sin cuerpo y termina en punto y coma. Una subclase concreta debe implementar los métodos abstractos heredados que sigan pendientes. Si la clase base proporciona un comportamiento por defecto con cuerpo, ese método no debe declararse abstracto.

## Sobrescritura, sobrecarga y polimorfismo
Sobrescribir (overriding) proporciona en una subclase una implementación compatible de un método de instancia heredado. `@Override` permite al compilador verificar esa intención. No se puede reducir la accesibilidad del método ni ampliar libremente sus excepciones checked. Un método [[final]] no se sobrescribe; los métodos [[static]] se ocultan, no participan del despacho dinámico de instancia.

Con una referencia de tipo Material que apunta a un LibroImpreso, la llamada a un método de instancia sobrescrito ejecuta la implementación del objeto real. Esto es polimorfismo: el mismo contrato admite comportamientos distintos. El tipo declarado sigue limitando qué miembros puede nombrar el código.

Sobrecargar (overloading) significa declarar métodos del mismo nombre con distintas listas de parámetros; cambiar solo el tipo de retorno no basta. La selección de la sobrecarga se hace en compilación según los tipos y argumentos disponibles, y no debe confundirse con el despacho de una sobrescritura.

## Interfaces
Una interfaz define un tipo y un contrato de operaciones. Una clase usa `implements` y puede implementar varias interfaces. Los métodos de instancia declarados sin cuerpo, sin modificadores especiales, son públicos y abstractos; su implementación debe ser pública. Las interfaces modernas también pueden contener métodos `default`, estáticos y privados con cuerpo, con sus respectivas reglas.

Notificador separa la operación de avisar de su implementación en consola. RepositorioMateriales separa guardar o buscar de la decisión de usar memoria o una base de datos. Declarar una variable con el tipo de interfaz permite sustituir la implementación manteniendo el contrato.

## Composición y encapsulamiento
ServicioPrestamo tiene un repositorio y un notificador: recibe referencias por constructor y delega tareas. Esta relación «tiene/usa» es composición en el sentido habitual de diseño con colaboradores; no implica automáticamente propiedad exclusiva ni destrucción conjunta como en una composición estricta de UML. No necesita heredar de esos colaboradores.

Encapsular significa proteger el estado y ofrecer operaciones que mantengan sus reglas. Un campo privado ayuda, pero no basta si un método expone una colección mutable interna sin control. Validar dentro del modelo protege sus invariantes aunque la operación provenga de otra pantalla o servicio. Los getters no son obligatorios para todos los campos y los setters no deben permitir estados inválidos.

Consulta [[Modificadores de acceso]], [[Clases y objetos]] y [[Colecciones y genéricos#Vistas y copias]] para relacionar acceso, construcción y protección de datos.

Fuente: [JLS §8 y §9](https://docs.oracle.com/javase/specs/jls/se25/html/jls-8.html).
