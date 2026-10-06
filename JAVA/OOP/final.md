---
tags:
  - java
  - java/oop
status: aprendido
aliases:
  - "Final keywords"
  - "Final Keyword"
---

# final
> [!summary] En una frase
> Impide reasignar una variable; en métodos y clases restringe cambios mediante herencia.

## Variables
```java
final int limite;
limite = 10;
System.out.println(limite);

final int[] numeros = {1, 2};
numeros[0] = 9;
System.out.println(numeros[0]); // 9
// numeros = new int[3]; // No compila: reasignación.
```

Una variable final solo puede asignarse una vez. En referencias se fija la referencia, no el contenido mutable del objeto. final no convierte todo objeto en inmutable ni toda variable en una constante de compilación.

## Campos y constructor
```java
class Alumno {
    final String nombre;

    Alumno(String nombre) {
        this.nombre = nombre;
    }
}
```

Puedes asignar un campo de instancia en su declaración o, si queda sin inicializar, en cada [[Clases y objetos#Constructor|constructor]] que deba hacerlo. Cada objeto puede recibir un valor diferente. Si usas un mismo literal al declarar el campo, todos recibirán ese valor.

Un final local puede asignarse después de declararlo, antes de leerlo. Un campo static final no se inicializa desde cada constructor; los bloques inicializadores ya se mencionaron en clase y quedan pendientes.

## Métodos y clases: mención estudiada
- Un método final no se puede sobrescribir en subclases; su autor sí puede editar su código fuente. final no añade restricciones de acceso.
- Una clase final no admite subclases con extends; sí permite crear instancias normalmente.

Herencia y overriding quedan pendientes de desarrollo. [[static]] distingue un campo compartido; [[Modificadores de acceso]] controla quién puede usarlo.

Fuentes: [JLS §4.12.4](https://docs.oracle.com/javase/specs/jls/se25/html/jls-4.html#jls-4.12.4) y [§8](https://docs.oracle.com/javase/specs/jls/se25/html/jls-8.html).
