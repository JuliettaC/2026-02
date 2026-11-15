# Fuentes y alcance de la revisión

Revisión: 2026-11-15. Las referencias F01–F08 identifican insumos locales; no son enlaces públicos. No se adjuntan copias ni transcripciones íntegras de materiales internos al repositorio.

| ID | Archivo original | Revisión y autoridad |
|---|---|---|
| F01 | `VF_IHC_Evaluacion_Laboratorio_Parte1_Estudiantes.pdf` | 7 páginas leídas; tablas de rúbrica de pp. 4–7 comprobadas visualmente. Fuente principal de obligaciones académicas. Marcado «Uso Interno» y no distribución externa. |
| F02 | `Resultados Fase 0.pptx` | Texto de las 11 diapositivas y notas disponibles revisado. Material docente con pasos y ejemplos; no contiene resultados de entrevistas del grupo. La diapositiva 11 no tiene texto extraíble. No se hizo revisión visual de las diapositivas ni interpretación de imágenes incrustadas. |
| F03 | `PRESENTACION GRUPO 2.pdf` | 4 páginas leídas; contenido de pp. 2–3 comprobado visualmente. Planteamiento inicial del equipo; no demuestra hallazgos ni aprobación docente. |
| F04 | `PREGUNTAS.md` | Texto completo revisado. Borrador de entrevista. `PREGUNTAS(1).md`, nombre mencionado en la solicitud y F08, no está en esta carpeta; no se afirma que sean versiones idénticas. |
| F05 | `Contenido Consentimiento Informado - IHC.pdf` | 2 páginas leídas; formulario de p. 2 comprobado visualmente, sin completar. Modelo interno, no consentimiento otorgado. |
| F06 | `Grabación wo bu zhi dao.m4a` | Solo existencia identificada. No escuchada, transcrita, decodificada ni analizada mediante IA: falta verificar consentimiento específico. No se verificaron duración, participantes ni contenido. |
| F07 | `contexto_para_codex_claude_antigravity.md` | Texto completo revisado. Síntesis previa, hipótesis e ideas de diseño; autoría, fecha y aprobación no acreditadas. No prevalece sobre F01 ni prueba acuerdos. |
| F08 | `guia_informe_IHC_parte1.md` | Texto completo revisado. Guía derivada y recomendaciones; contrastada con F01. No es pauta docente. |

## Cómo interpretar las fuentes

F01 prevalece para los requisitos. F02 explica la actividad preparatoria. F03 acredita lo que el equipo presentó inicialmente, no que sus supuestos sean verdaderos. F04 acredita preguntas preparadas, no entrevistas realizadas. F05 define permisos separados, no autoriza el tratamiento de F06. F07 y F08 aportan propuestas que requieren confirmación.

Las referencias del resto de la documentación usan página o diapositiva para poder verificar el original por un canal autorizado. El equipo debe acordar un custodio y acceso restringido; todavía no hay un canal verificado ni permisos de publicación. No incluir enlaces con acceso público, contraseñas o datos de participantes.

## Límites técnicos y de evidencia

El lector de F01 advirtió referencias internas de objetos PDF con offsets incorrectos; pudo extraer las siete páginas y se verificaron visualmente las tablas. No se modificó el PDF. F02 se revisó por su texto y notas, no mediante PowerPoint; cualquier información exclusivamente visual permanece sin verificar. No se investigaron fuentes externas ni versiones posteriores de los documentos.

Los archivos existentes siguen intactos. Las fechas y afirmaciones de F07/F08 no se convierten en hechos por aparecer en esos resúmenes. La revisión no demuestra que el equipo carezca de otros materiales: solo registra lo que se encontró en esta carpeta.

## Comprobación de Git

Se detectó `.git` en la carpeta del semestre, dos niveles por encima. La consulta normal de `git status` falla por acceso a esa raíz en este entorno. Se pudieron leer el índice y los nombres de archivos de los commits alcanzables con `git log --all`, indicando explícitamente la ubicación de Git: no aparecieron rutas bajo `INTERACCIÓN HUMANO COMPUTADOR/PROYECTO/` ni los nombres de los originales revisados. No se examinó contenido histórico de otros cursos, objetos no alcanzables, reflogs ni el servidor remoto; esto no constituye una garantía de ausencia de datos sensibles en todo el repositorio.

Una consulta diagnóstica con otra raíz de trabajo produce falsos borrados de archivos del semestre: no usar ese resultado para preparar cambios. Antes de cualquier operación de escritura en Git se debe obtener un `git status` válido desde la raíz real. No se cambió configuración, índice ni historial y no se creó un repositorio anidado.

## Verificación de la documentación derivada

Se comprobaron los enlaces relativos de los diez archivos Markdown creados y la lectura UTF-8 sin caracteres de sustitución. Las huellas SHA-256 de los siete originales documentales coinciden antes y después de escribir la documentación. El audio no se abrió ni para calcular su huella. `git check-ignore --no-index` confirmó la exclusión de los ocho insumos originales y de ejemplos de datos personales, credenciales, entrevistas, consentimientos y temporales; los once archivos nuevos previstos quedan permitidos. La lista y el resumen del diff preparado estaban vacíos. El `git status` normal sigue bloqueado por acceso a la raíz superior: no se considera habilitada la preparación de cambios.
