**Las 4 trampas clásicas al leer código con `abstract`:**
1. **Prohibido hacer `new` (Error Semántico):** Si una clase dice `abstract class Figura`, intentar crear un objeto directo con `new Figura()` no compila.
2. **Métodos `abstract` no llevan llaves `{}` (Error Sintáctico/Semántico):** Un método abstracto es solo una orden vacía (termina en `;`, ej. `abstract void dibujar();`). Si le pones llaves `{}` con código adentro, no compila.
NO USA LLAVES
3. **El hijo está obligado a cumplir (Error Semántico):** Si una clase normal hereda (`extends`) de una clase abstracta, está **obligada** a escribir el código de todos los métodos `abstract` del padre. Si olvida alguno, no compila.
4. **Incompatibilidad con `private` o `final` (Error Semántico):** Un método `abstract` exige que el hijo lo modifique. Por eso, escribir `private abstract` (el hijo no lo ve) o `final abstract` (prohibido modificar) es una contradicción y no compila.