# Colaboración y mantenimiento del contexto

## Fuente de verdad

Los originales son evidencia primaria y permanecen privados e intactos. `docs/` contiene la interpretación vigente, verificable mediante las referencias F01–F08. Para obligaciones prevalece F01, salvo aclaración posterior documentada de la docente. Una decisión del equipo no elimina un requisito académico. Ante conflicto, registrarlo en [decisiones](decisiones.md), sin resolverlo por suposición.

El [README](../README.md) asigna un único documento responsable a cada tema. Enlazarlo en lugar de copiar sus tablas. Los resúmenes antiguos de la raíz se conservan excluidos como antecedentes, no se mantienen como una segunda fuente vigente.

## Ciclo de trabajo de cada integrante

1. Abrir esta carpeta como proyecto; leer contexto, requisitos, decisiones y estado actual antes de pedir trabajo a una IA.
2. Identificar el pendiente y acordar responsable/revisor. Registrar responsable solo cuando lo acepte; no asignarlo a partir de un nombre encontrado en los originales.
3. Trabajar en una rama de tarea una vez resuelto DEC-08 y validada la raíz Git. No crear ni mover repositorios de forma automática.
4. Editar el documento dueño del tema. Distinguir `Requisito docente`, `Acuerdo confirmado`, `Hipótesis`, `Propuesta de diseño` y `Hallazgo verificado`. Añadir fuente y localizador, o indicar que falta evidencia.
5. Si hay una decisión nueva, conservar su ID DEC y registrar resolución, fecha, responsable y evidencia; actualizar contexto solo cuando corresponda. No modificar los originales para ocultar contradicciones.
6. Actualizar `estadoActual.md` con lo terminado, lo que sigue y sus bloqueos. «Terminado» requiere evidencia y verificación; una propuesta o un archivo vacío no basta.
7. Pedir revisión a otro integrante sobre coherencia, requisitos, trazabilidad y privacidad. Registrar quién revisó y qué falta en el cambio o solicitud de integración.
8. Integrar/publicar únicamente después de las comprobaciones de seguridad y la autorización exigida abajo. Comunicar el enlace al cambio por el canal que el equipo decida; una IA no debe enviar mensajes por iniciativa propia.

## Evidencia y trazabilidad futura

Cuando existan permisos y evidencia revisada, usar H1… para hallazgos, N1… para necesidades, T1… para tareas, D1… para decisiones de diseño e identificadores de pantalla. En cada paso conservar los vínculos con el anterior. Las hipótesis HIP y decisiones de gestión DEC no sustituyen H ni D.

Una cita requiere registro fuente verificable, permiso y revisión de anonimización. P1/P2/P3 son códigos; la tabla que los relaciona con identidades nunca va al repositorio. Revisar también identificadores indirectos en citas y circunstancias personales. No publicar archivos brutos de entrevistas aunque su nombre no contenga datos personales.

Crear nuevos documentos de investigación o diseño solo cuando haya contenido auténtico; enlazarlos desde el índice y actualizar la lista permitida de `.gitignore` tras revisar su contenido. No se crean entregables vacíos para simular avance.

## Privacidad y originales

El tratamiento académico y los permisos están en R17–R21. Los originales internos, consentimientos firmados, audio/video, transcripciones identificables, datos personales, credenciales y archivos temporales quedan fuera de Git mediante exclusión por defecto. Esta regla también excluye formatos nuevos o archivos Markdown no revisados. No usar `git add -f` para sortearla.

No subir originales a herramientas externas ni procesar entrevistas por IA sin comprobar permisos aplicables. Acordar custodia fuera del repositorio; documentar únicamente estado del permiso y referencia privada no identificable cuando proceda. No incluir nombres de participantes, firmas, contactos, contraseñas ni enlaces públicos a evidencia restringida. No borrar originales ahora: la conservación/eliminación autorizada debe coordinarse según F05.

## Seguridad de Git

Antes de **cualquier** `git add`, `git commit` o `git push`:

1. Confirmar raíz con `git rev-parse --show-toplevel`, destino remoto y alcance. Si `git status` falla o la raíz no es la esperada, detener las operaciones de escritura. No interpretar un estado obtenido con una raíz de trabajo artificial como válido.
2. Revisar `.gitignore` y comprobar archivos candidatos con `git check-ignore -v -- ruta`. Un archivo permitido sigue necesitando revisión manual de contenido.
3. Ejecutar `git status --short --untracked-files=all`; revisar `git ls-files` y `git log --all --name-only` para detectar material ya rastreado o histórico. `.gitignore` no lo elimina. No reescribir historial ni quitar seguimiento sin autorización si se descubre un problema.
4. Revisar los cambios con `git diff` y los nuevos archivos completos. Si hay datos sensibles, detener la operación y excluirlos.
5. Cuando corresponda preparar el cambio, usar `git add -- ruta1 ruta2` con rutas específicas de archivos revisados, nunca `git add .`. No preparar otros cursos del repositorio superior.
6. Revisar **ambos** `git diff --cached --name-only` y `git diff --cached`; repetir `git status`. Si aparece información sensible, detenerse y retirarla del conjunto preparado sin borrar originales.
7. No ejecutar `git commit` ni `git push` sin autorización explícita del usuario. Una autorización para redactar o preparar documentos no es autorización para publicar. Revisar el destino y contenido otra vez antes del push.

No se ejecutó `git add`, `git commit` ni `git push` en esta preparación. Los límites de la inspección actual del índice e historial están en [fuentes](fuentes.md); DEC-08 debe resolverse antes de continuar con operaciones Git.

## Registro de asistencia de IA

El 2026-11-15 se utilizó Codex para inventariar los insumos, leer texto de documentos, verificar visualmente páginas PDF, resumir requisitos y preparar esta documentación e instrucciones. No se procesó F06 ni se generaron datos de participantes. La revisión humana del equipo está pendiente. Este registro alimentará la declaración final, pero no certifica ni sustituye declarar otros usos de IA realizados por integrantes.

Al usar IA, registrar herramienta, fecha, propósito, materiales autorizados y revisión humana efectuada. Para iniciar una sesión nueva puede pedirse: «Lee AGENTS.md y sus documentos obligatorios. Indica el estado comprobado y los bloqueos de mi tarea. Trabaja solo con evidencia y actualiza el documento responsable al terminar». No depender de la memoria de una conversación.
