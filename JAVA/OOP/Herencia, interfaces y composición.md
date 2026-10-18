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
> [!summary] Qué es
> Heredar especializa tipos; las interfaces definen contratos; la composición conecta objetos.

## Herencia y super

- **extends:** una clase hereda de una sola superclase directa.
- Relación **«es un»**: LibroImpreso es un Material.
- **super(...):** llama al constructor de la superclase; los constructores no se heredan.
- Sin llamada explícita, el constructor implícito sin argumentos debe ser accesible.
- Los miembros private de la clase base no pasan a ser accesibles directamente.

## Clases y métodos abstractos

| Elemento | Qué recordar |
|---|---|
| Clase abstract | No se instancia; puede tener constructor, campos y métodos con cuerpo |
| Método abstract | No tiene cuerpo; termina en punto y coma |
| Subclase concreta | Implementa los métodos abstractos pendientes |

**Importante:** un método con implementación no se declara abstract.

## Sobrescritura, sobrecarga y polimorfismo

| Concepto | Significado | Selección |
|---|---|---|
| Sobrescritura | Subclase redefine un método de instancia compatible | Implementación según el objeto real |
| Sobrecarga | Mismo nombre, distintas listas de parámetros | Compilación |
| Polimorfismo | Un tipo común permite comportamientos distintos | Despacho de métodos de instancia |

- **@Override:** comprueba que realmente sobrescribes.
- No reduzcas el acceso ni amplíes libremente las excepciones checked.
- **final:** impide sobrescribir. **static:** se oculta, no tiene despacho dinámico.
- Cambiar solo el retorno **no** crea una sobrecarga.
- El tipo declarado limita qué miembros puedes nombrar; el objeto real decide qué implementación sobrescrita se ejecuta.

## Interfaces

- **Qué es:** contrato que una clase cumple mediante implements.
- Una clase puede implementar **varias interfaces**.
- Métodos de instancia sin cuerpo ni modificadores especiales: **public abstract**; la implementación debe ser public.
- También pueden existir métodos default, static y private con cuerpo.
- **Uso:** Notificador permite cambiar consola por otra implementación; RepositorioMateriales separa el servicio del almacenamiento.

## Composición y encapsulamiento

| Concepto | Para qué sirve |
|---|---|
| Composición («tiene/usa») | Recibir colaboradores y delegar, sin heredar de ellos |
| Encapsulamiento | Proteger el estado y mantener sus reglas mediante operaciones |

- ServicioPrestamo recibe repositorio y notificador por constructor.
- «Composición» aquí no implica propiedad exclusiva ni destrucción conjunta de UML.
- **private no basta:** exponer una lista mutable puede romper la protección.
- Valida en el **modelo**, aunque la pantalla también valide.
- No necesitas getters para todo ni setters que permitan estados inválidos.

## Relacionado

[[final]] · [[static]] · [[Modificadores de acceso]] · [[Clases y objetos]] · [[Colecciones y genéricos#Vistas y copias]]

Fuente: [JLS §8 y §9](https://docs.oracle.com/javase/specs/jls/se25/html/jls-8.html).
