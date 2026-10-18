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
> [!summary] Qué es
> Eligen una ruta según una condición boolean o un valor.

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

**Importante:** se ejecuta la primera rama aplicable. else if se evalúa si las anteriores fueron falsas; Java no acepta un entero como condición.

## Ternario

**Cómo funciona:** condicion ? valorSiTrue : valorSiFalse devuelve un valor.

```java
int edad = 18;
String estado = edad >= 18 ? "Mayor de edad" : "Menor de edad";
System.out.println(estado);
```

## switch clásico

**Uso:** seleccionar casos por valores concretos.

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

- **break u otra salida:** evita continuar por los casos siguientes.
- Sin salida puede haber **fall-through**, aunque el siguiente caso no coincida; a veces es intencional.
- **default:** se usa cuando ningún caso coincide.

## Relacionado

[[Operadores lógicos]] · [[Strings]]

Fuente: [JLS §14.9 y §14.11](https://docs.oracle.com/javase/specs/jls/se25/html/jls-14.html).
