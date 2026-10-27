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
> [!summary] Qué es
> Controlan desde dónde pueden usarse clases, constructores y miembros.

## Consulta rápida

| Acceso | Alcance |
|---|---|
| private | Dentro del tipo superior que engloba la declaración, incluidas anidadas |
| Sin modificador | Mismo package |
| protected | Mismo package; subclases con restricciones adicionales |
| public | Donde también sea accesible el tipo contenedor |

## Ejemplo

```java
class Persona {
    private String nombre = "Ana";

    public String obtenerNombre() {
        return nombre;
    }
}
```

**Cómo funciona:** otra clase independiente no lee persona.nombre directamente; usa el método accesible.

## Confusiones comunes

- **Package-private:** se omite el modificador; no se escribe default.
- Clase superior: public o package-private. Miembro anidado: puede ser private/protected.
- Las anidadas acceden a private dentro del mismo tipo superior.
- **protected fuera del package:** desde una subclase, el receptor de un miembro de instancia debe tener el tipo de esa subclase o una derivada suya.
- Las locales no llevan modificadores de acceso.

## Relacionado

[[Clases anidadas|clase anidada]] · [[Packages|package]] · [[Herencia, interfaces y composición]]

Fuente: [JLS §6.6](https://docs.oracle.com/javase/specs/jls/se25/html/jls-6.html#jls-6.6).
