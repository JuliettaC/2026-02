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
> [!summary] Qué es
> Impide reasignar variables, sobrescribir métodos o heredar de una clase.

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

**Importante:** fija la referencia, no el contenido mutable. No toda variable final es una constante de compilación.

## Campos y constructor

```java
class Alumno {
    final String nombre;

    Alumno(String nombre) {
        this.nombre = nombre;
    }
}
```

| Variable final | Dónde se asigna |
|---|---|
| Local | Una vez, antes de leerla |
| Campo de instancia sin inicializar | En cada constructor que deba asignarlo |
| Campo static sin inicializar | En un bloque de inicialización de clase |
| Campo inicializado en su declaración | Allí; no vuelve a asignarse |

Cada objeto puede recibir un valor distinto. Un static final no se inicializa desde cada constructor.

## Métodos y clases: mención estudiada

- **Método final:** no se sobrescribe; no cambia el acceso ni impide editar su fuente.
- **Clase final:** no admite subclases; sí puede instanciarse si sus otras reglas lo permiten.

## Relacionado

[[Clases y objetos#Constructor|constructor]] · [[static#Estado compartido e inicialización]] · [[Herencia, interfaces y composición]] · [[static]] · [[Modificadores de acceso]]

Fuentes: [JLS §4.12.4](https://docs.oracle.com/javase/specs/jls/se25/html/jls-4.html#jls-4.12.4) y [§8](https://docs.oracle.com/javase/specs/jls/se25/html/jls-8.html).
