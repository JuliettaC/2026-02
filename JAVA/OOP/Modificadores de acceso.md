---
tags:
  - java
  - java/oop
status: aprendido
aliases:
  - "Access Specifiers (Modificadores de Acceso)"
  - "private"
  - "protected"
  - "public"
---

# Modificadores de acceso
> [!summary] En una frase
> Controlan desde dónde puede usarse una clase, constructor o miembro.

## Consulta rápida
| Acceso | Alcance |
|---|---|
| private | Dentro del tipo superior que engloba la declaración; incluye sus clases anidadas |
| Sin modificador (package-private) | Mismo package |
| protected | Mismo package; también subclases bajo reglas adicionales |
| public | Accesible donde también lo sea el tipo que lo contiene |

No se escribe `default` para conseguir package-private.

## Ejemplo
```java
class Persona {
    private String nombre = "Ana";

    public String obtenerNombre() {
        return nombre;
    }
}
```

Desde otra clase independiente, persona.nombre no es accesible, pero el método public puede serlo si Persona también es accesible.

## Confusiones comunes
- Una clase superior solo puede ser public o package-private; private/protected sí se permiten en clases miembro.
- Una [[Clases anidadas|clase anidada]] puede acceder a miembros private dentro del mismo tipo superior.
- Para protected desde otro [[Packages|package]], el acceso de una subclase a un miembro de instancia tiene restricciones sobre la referencia usada. Esta es una mención para reconocer el modificador; herencia queda pendiente.
- Las variables locales no llevan modificadores de acceso.

Fuente: [JLS §6.6](https://docs.oracle.com/javase/specs/jls/se25/html/jls-6.html#jls-6.6).
