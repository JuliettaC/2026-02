# Fuentes y alcance de la revisión

Revisión: 2026-11-15. Las referencias F01–F08 identifican insumos locales; F09 identifica la transcripción aportada por el usuario en la conversación. No son enlaces públicos. No se adjuntan copias ni transcripciones íntegras de materiales internos al repositorio.

| ID | Archivo original | Revisión y autoridad |
|---|---|---|
| F01 | `VF_IHC_Evaluacion_Laboratorio_Parte1_Estudiantes.pdf` | 7 páginas leídas; tablas de rúbrica de pp. 4–7 comprobadas visualmente. Fuente principal de obligaciones académicas. Marcado «Uso Interno» y no distribución externa. |
| F02 | `Resultados Fase 0.pptx` | Texto de las 11 diapositivas y notas disponibles revisado. Material docente con pasos y ejemplos; no contiene resultados de entrevistas del grupo. La diapositiva 11 no tiene texto extraíble. No se hizo revisión visual de las diapositivas ni interpretación de imágenes incrustadas. |
| F03 | `PRESENTACION GRUPO 2.pdf` | 4 páginas leídas; contenido de pp. 2–3 comprobado visualmente. Planteamiento inicial del equipo; no demuestra hallazgos ni aprobación docente. |
| F04 | `PREGUNTAS.md` | Texto completo revisado. Borrador de entrevista. `PREGUNTAS(1).md`, nombre mencionado en la solicitud y F08, no está en esta carpeta; no se afirma que sean versiones idénticas. |
| F05 | `Contenido Consentimiento Informado - IHC.pdf` | 2 páginas leídas; formulario de p. 2 comprobado visualmente, sin completar. Modelo interno, no consentimiento otorgado. |
| F06 | `Grabación wo bu zhi dao.m4a` | Conversación del equipo con la profesora sobre el proyecto, según el usuario; no es una entrevista a participantes. El usuario confirmó autorización de quienes conversan para transcripción o análisis con IA; no se revisaron formularios. El archivo de audio no se escuchó ni decodificó. Se analizó por separado el texto aportado como F09, sin verificar su fidelidad contra el audio. |
| F07 | `contexto_para_codex_claude_antigravity.md` | Texto completo revisado. Síntesis previa, hipótesis e ideas de diseño; autoría, fecha y aprobación no acreditadas. No prevalece sobre F01 ni prueba acuerdos. |
| F08 | `guia_informe_IHC_parte1.md` | Texto completo revisado. Guía derivada y recomendaciones; contrastada con F01. No es pauta docente. |

## Transcripción aportada: F09

F09 es el texto proporcionado por el usuario después de confirmar el consentimiento de la profesora y del equipo. Se revisó su contenido académico. No tiene fecha de reunión, marcas de tiempo ni etiquetas de hablante; contiene errores de transcripción, frases incompletas y cambios de turno ambiguos. Las atribuciones a profesora/equipo se infieren del diálogo y requieren revisión humana. No es una transcripción validada contra F06 ni un acta formal de aprobación.

Para poder rastrear las síntesis sin publicar el texto íntegro, se definen estos localizadores temáticos, en el orden de la conversación:

| Localizador | Tramo identificable | Uso documental |
|---|---|---|
| F09-A | Presentación del problema y pregunta sobre qué significa movilidad reducida. | Planteamiento inicial del equipo; no evidencia empírica de barreras. |
| F09-B | Valoración del tema y solicitud de limitar ciudad, lugar y público; distinción entre condiciones temporales/permanentes y motrices/visuales. | Orientaciones O01/O02 y DEC-01/02. |
| F09-C | Relación con la carrera, ejemplos de lugares y aclaración del equipo sobre elegir el recorrido viable sin modificar físicamente el espacio. | Orientación O03 y contexto tecnológico. |
| F09-D | Dificultad de acceso al público, pasaje sobre asumir una situación y explicación de investigación, persona y prototipos. | Ambigüedad DEC-11; no habilita entrevistas simuladas. |
| F09-E | Posible contacto vecinal, fotografías y levantamiento en terreno; solicitud de definir espacio y público para la clase siguiente. | Posibilidad de reclutamiento no confirmada, O04 y DEC-12. |
| F09-F | Cierre y conversación posterior entre voces no identificadas. | Idea sobre información de Metro sin aprobación atribuible; resto ajeno al proyecto excluido de las síntesis. |

Solo se conservan resúmenes pertinentes, sin nombres de posibles participantes, datos de acceso ni conversación personal. La transcripción completa no se escribió en el repositorio. Los localizadores anteriores son referencias temáticas, no marcas de tiempo inventadas.

## Cómo interpretar las fuentes

F01 prevalece para los requisitos. F02 explica la actividad preparatoria. F03 acredita lo que el equipo presentó inicialmente, no que sus supuestos sean verdaderos. F04 acredita preguntas preparadas, no entrevistas realizadas. F05 define permisos para entrevistas a participantes; no constituye autorización para procesar la conversación académica F06. F07 y F08 aportan propuestas que requieren confirmación. F09 aporta orientación oral contextual, con las limitaciones indicadas; no demuestra una excepción a F01 ni una aprobación formal del guion. La fecha desconocida de la reunión impide afirmar que modifica posteriormente la pauta.

Las referencias del resto de la documentación usan página o diapositiva para poder verificar el original por un canal autorizado. El equipo debe acordar un custodio y acceso restringido; todavía no hay un canal verificado ni permisos de publicación. No incluir enlaces con acceso público, contraseñas o datos de participantes.

## Límites técnicos y de evidencia

El lector de F01 advirtió referencias internas de objetos PDF con offsets incorrectos; pudo extraer las siete páginas y se verificaron visualmente las tablas. No se modificó el PDF. F02 se revisó por su texto y notas, no mediante PowerPoint; cualquier información exclusivamente visual permanece sin verificar. No se investigaron fuentes externas ni versiones posteriores de los documentos.

Los archivos existentes siguen intactos. Las fechas y afirmaciones de F07/F08 no se convierten en hechos por aparecer en esos resúmenes. La revisión no demuestra que el equipo carezca de otros materiales: solo registra lo que se encontró en esta carpeta.

## Comprobación de Git

Se detectó `.git` en la carpeta del semestre, dos niveles por encima. La consulta normal de `git status` falla por acceso a esa raíz en este entorno. Se pudieron leer el índice y los nombres de archivos de los commits alcanzables con `git log --all`, indicando explícitamente la ubicación de Git: no aparecieron rutas bajo `INTERACCIÓN HUMANO COMPUTADOR/PROYECTO/` ni los nombres de los originales revisados. No se examinó contenido histórico de otros cursos, objetos no alcanzables, reflogs ni el servidor remoto; esto no constituye una garantía de ausencia de datos sensibles en todo el repositorio.

Una consulta diagnóstica con otra raíz de trabajo produce falsos borrados de archivos del semestre: no usar ese resultado para preparar cambios. Antes de cualquier operación de escritura en Git se debe obtener un `git status` válido desde la raíz real. No se cambió configuración, índice ni historial y no se creó un repositorio anidado.

## Verificación de la documentación derivada

Se comprobaron los enlaces relativos de los diez archivos Markdown creados y la lectura UTF-8 sin caracteres de sustitución. Las huellas SHA-256 de los siete originales documentales coinciden antes y después de escribir la documentación. El audio no se abrió ni para calcular su huella. `git check-ignore --no-index` confirmó la exclusión de los ocho insumos originales y de ejemplos de datos personales, credenciales, entrevistas, consentimientos y temporales; los once archivos nuevos previstos quedan permitidos. La lista y el resumen del diff preparado estaban vacíos. El `git status` normal sigue bloqueado por acceso a la raíz superior: no se considera habilitada la preparación de cambios.
