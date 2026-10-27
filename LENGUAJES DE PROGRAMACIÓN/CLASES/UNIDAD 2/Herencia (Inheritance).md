> [!summary] Qué es


**Las 3 trampas clásicas al leer código con Herencia:**
1. **`private` no se hereda directamente (Error Semántico):** La hija hereda todo lo `public` y `protected` (visibles para hijos), pero los atributos `private` del padre siguen encerrados en su caja fuerte. Si la hija intenta usarlos directo sin un getter, no compila.
2. **El constructor del padre manda (Error Semántico):** Cuando nace un objeto hijo, Java obliga a llamar primero al constructor del padre usando `super(...)`. Si el padre tiene un constructor que pide datos (ej. `String nombre`) y el hijo no se los pasa con `super("Juan")` en su primera línea, no compila.
>**Truco visual para detectar este error en 3 segundos:**
Ves que una clase tiene `extends` (ej. `Celular extends Dispositivo`).
Miras arriba al padre (`Dispositivo`): ¿tiene un constructor que pide datos entre paréntesis? Sí, pide `(String marca)`.
Miras el constructor del hijo (`Celular`): ¿su primera línea dice `super(...)` enviándole ese dato? Si no dice `super(...)`, **no compila (error semántico)**.

3. **Herencia múltiple prohibida (Error Sintáctico/Semántico):** En Java una clase solo puede tener **un** padre directo (`class Hijo extends Padre1, Padre2` es ilegal).