# Decisiones, contradicciones y pendientes

Los requisitos docentes viven en [requisitos](requisitos.md); los supuestos e ideas en [contexto](contexto.md). Este registro guarda resoluciones y su evidencia, sin modificar los originales. Estado inicial: 2026-11-15. No hay actas del equipo entre los archivos revisados.

## Instrucciones confirmadas para esta preparación

| ID | Resolución | Autoridad / evidencia |
|---|---|---|
| AC-01 | Preparar documentación compartida antes de desarrollar una aplicación. | Solicitud del usuario, secciones 14–15. Implementada en esta preparación. |
| AC-02 | Conservar originales intactos, usar resúmenes y referencias; excluir materiales internos y datos sensibles de Git. | Solicitud del usuario; restricciones explícitas de F01/F05. |
| AC-03 | No procesar audio con IA sin verificar permiso específico; no inventar entrevistas, citas o avances. | Solicitud del usuario; F01 pp. 3–4 y F05 pp. 1–2. |
| AC-04 | No hacer commit ni push sin autorización explícita; revisar exclusiones, estado, índice e historial antes de preparar cambios. | Solicitud del usuario. No se ha autorizado publicación. |

Son instrucciones vigentes del solicitante, no acuerdos colectivos supuestos. La distribución de roles, la validación del alcance y las decisiones funcionales siguen pendientes.

## Registro de pendientes

| ID / estado | Contradicción o vacío | Decisión necesaria y condición para cerrarla | Quién debe resolver |
|---|---|---|---|
| DEC-01 · Pendiente | F03 pp. 2–3 mezcla Providencia y campus; F07/F08 amplían a Santiago. | Elegir territorio y trayectos, explicar la relación entre comuna, ciudad y campus; actualizar contexto y frase del problema con acta/confirmación fechada. Providencia como piloto es solo una opción existente. | Equipo; validar con docente cuando afecte el reto aprobado. |
| DEC-02 · Pendiente | F03 alterna personas que transitan por la comuna y estudiantes; F07/F08 dicen adultos. No hay muestra verificada. | Definir criterios de inclusión, perfiles de movilidad, acceso real al público y reclutamiento compatible con F05. No asumir homogeneidad ni registrar diagnósticos innecesarios. | Equipo; consultar docente si se pretende incluir menores. |
| DEC-03 · Pendiente | F04 tiene conteo ambiguo y nota editorial; F08 incluye otro guion; falta aprobación previa. | Elegir versión de 6–10 preguntas principales abiertas, separar sondeos, retirar notas y revisar sesgos. Registrar evidencia del hito y de aprobación docente antes de entrevistas nuevas. Confirmar si existió `PREGUNTAS(1).md`. | Equipo y docente. |
| DEC-04 · Pendiente | F01 p. 3 exige grabaciones originales; F05 p. 1 permite no grabar y tomar notas. No se especifica canal de entrega restringido. | Consultar cómo entregar evidencia cuando no hay permiso de grabación, cómo separar anexos identificables y qué canal acepta la docente. No presionar a participantes ni publicar en GitHub. | Docente y equipo. |
| DEC-05 · Bloqueada por permisos no acreditados | F06 existe, pero el modelo F05 está vacío; no se conoce identidad, número de entrevistas ni permisos. | Verificación humana del consentimiento aplicable, alcance y permisos de audio, IA y citas por participante. Documentar solo resultado anonimizado y custodio; conservar formularios fuera de Git. Mientras no se verifique, no procesar audio con IA. | Custodio por designar y equipo. |
| DEC-06 · Pendiente | F01 da 28/10, 11/11 y 18/11 sin año explícito; F08 afirma 2026. No hay aprobación, comprobante de entrega ni prórroga. | Confirmar calendario y situación real con evidencia. Si corresponde a 2026, al 15/11 los dos primeros hitos ya pasaron y la exposición sigue pendiente; eso no demuestra incumplimiento. | Equipo y docente. |
| DEC-07 · Pendiente | F07 permite datos ilustrativos de rutas; F01 sanciona datos/citas/resultados inventados o simulados. | Aclarar alcance permitido de contenido demostrativo del prototipo. Nunca simular investigación; si se admite contenido ficticio de interfaz, rotularlo y separarlo de evidencia. No hay autorización docente documentada para esta excepción. | Docente y equipo. |
| DEC-08 · Pendiente | La carpeta está dentro del repositorio general del semestre, no en uno independiente del equipo; el estado normal de Git está bloqueado por acceso a la raíz. | Elegir mantener subcarpeta o crear repositorio propio, responsables y permisos para los cinco integrantes. Obtener estado válido y revisar el alcance antes de integrar. No crear repositorio anidado, cambiar remotos ni reescribir historial sin resolverlo. | Propietario del repositorio y equipo. |
| DEC-09 · Pendiente | No hay asignación de responsables, canal restringido, permisos de publicación ni política operativa de custodia. | Designar custodio, acceso de equipo/docente y responsable de eliminación de grabaciones al finalizar el curso según F05. Revisar autorización de difusión de resúmenes internos. | Equipo y docente cuando corresponda. |
| DEC-10 · Pendiente | F07/F08 contienen afirmaciones derivadas —duración del audio, año, tareas, pantallas— que no acreditan hechos o acuerdos. | Usar `docs/` como contexto vigente. Registrar evidencia nueva para promover cualquier hipótesis a hallazgo o propuesta a decisión; no reutilizar esos resúmenes como pauta. | Cada autor de cambios y revisor del equipo. |

## Cómo cerrar una decisión

Conservar el ID. Añadir fecha, alternativas consideradas, decisión, motivo, responsable y evidencia verificable no sensible; indicar quién la confirmó. Cambiar el estado solo después de esa confirmación. Actualizar el documento dueño del tema y enlazarlo desde [estado actual](estadoActual.md). No usar códigos D1… de diseño para estas decisiones de gestión: esos códigos se reservan a R14.
