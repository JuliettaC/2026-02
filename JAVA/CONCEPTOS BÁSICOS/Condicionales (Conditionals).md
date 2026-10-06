---
tags:
  - java
  - java/fundamentos
status: aprendido
aliases:
  - "Condicionales"
  - "Conditionals"
  - "if"
  - "switch"
---

# Condicionales (Conditionals)
> [!summary] En una frase
> Seleccionan instrucciones según una condición boolean o un valor concreto.

## if, else if y else
```java
int edad = 20;
if (edad >= 18) {
    System.out.println("Mayor de edad");
} else if (edad >= 13) {
    System.out.println("Adolescente");
} else {
    System.out.println("Menor de 13");
}
```

Solo se ejecuta la primera rama que corresponda. Un else if se evalúa si las condiciones previas fueron falsas. Java exige boolean; un entero no sirve como condición.

## Ternario
Devuelve un valor: `condicion ? valorSiTrue : valorSiFalse`.

```java
int edad = 18;
String estado = edad >= 18 ? "Mayor de edad" : "Menor de edad";
System.out.println(estado);
```

## switch clásico
Útil para valores específicos en lugar de rangos.

```java
int opcion = 2;
switch (opcion) {
    case 1:
        System.out.println("Crear");
        break;
    case 2:
        System.out.println("Consultar");
        break;
    default:
        System.out.println("Opción desconocida");
}
```

En esta forma con `case ...:`, sin break u otra salida puede continuar por los casos siguientes (fall-through), aunque no coincidan. Puede ser intencional; no falta un break obligatoriamente en todo caso. default sirve cuando no hay coincidencia.

[[Operadores lógicos]] combina condiciones; [[Strings]] explica equals para comparar texto.

Fuente: [JLS §14.9 y §14.11](https://docs.oracle.com/javase/specs/jls/se25/html/jls-14.html).
