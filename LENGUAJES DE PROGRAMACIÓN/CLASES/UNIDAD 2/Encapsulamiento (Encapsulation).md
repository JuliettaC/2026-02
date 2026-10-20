> [!summary] Qué es
> El encapsulamiento en Java se aplica haciendo los atributos `private` y exponiendo métodos `public` (getters y setters) para leerlos o modificarlos de forma controlada.

- **Getter (`get`):** Método público solo para **leer** el dato privado.
- **Setter (`set`):** Método público para **modificar** el dato privado, donde aprovechas de poner filtros (un `if`) para validar que el dato nuevo sea correcto.
**Trampas comunes al leer código:**
- **Acceso directo a `private` (Error Semántico / Compilación):** Intentar leer o cambiar un atributo `private` desde otra clase usando el punto (ej. `objeto.saldo = 100;`) en lugar de su setter.
- **Shadowing (Ocultamiento) en Setters (Error Lógico):** Si el parámetro del setter se llama igual que el atributo, olvidar la palabra `this` (ej. `saldo = saldo;`) hace que el parámetro se asigne a sí mismo. El atributo de la clase nunca cambia y se queda con su valor por defecto (`0`, `null`, `false`).
SIN EL THIS EL ATRIBUTO DE LA CLASE NUNCA CAMBIA Y SE QUEDA CON SU VALOR POR DEFECTO ES UN ERROR LÓGICO

- **Fuga de referencias mutables (Error Lógico de diseño):** Si un atributo privado es un objeto mutable (como un `Array` o `ArrayList`) y el getter lo devuelve directamente (`return this.lista;`), quien lo llame podrá vaciar o alterar la lista desde fuera sin pasar por el setter, rompiendo la protección del estado interno.