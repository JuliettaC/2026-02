  # PROYECTO IHC · Wo bu zhi dao

Repositorio de contexto compartido para los cinco integrantes del proyecto de Interacción Humano-Computador de la Universidad Mayor. Estudiamos la información que necesitan las personas con movilidad reducida en extremidades inferiores para planificar sus desplazamientos. El alcance territorial todavía requiere un acuerdo documentado.

La prioridad actual es preparar y mantener el conocimiento del proyecto. No se ha desarrollado una aplicación en esta etapa.

## Por dónde comenzar

Lee [contexto](docs/contexto.md), [requisitos](docs/requisitos.md), [decisiones](docs/decisiones.md) y [estado actual](docs/estadoActual.md), en ese orden. Esta documentación permite comenzar sin acceder a conversaciones previas ni a los originales privados.

| Necesito… | Fuente única que debo consultar o actualizar |
|---|---|
| Comprender el problema, los supuestos y las ideas existentes | [docs/contexto.md](docs/contexto.md) |
| Saber qué exige la Parte 1 y cómo se evalúa | [docs/requisitos.md](docs/requisitos.md) |
| Resolver una contradicción o registrar un acuerdo | [docs/decisiones.md](docs/decisiones.md) |
| Ver avances demostrados, bloqueos y siguientes pasos | [docs/estadoActual.md](docs/estadoActual.md) |
| Comprobar de dónde proviene una afirmación | [docs/fuentes.md](docs/fuentes.md) |
| Actualizar el contexto y trabajar con Git e IA | [docs/colaboracion.md](docs/colaboracion.md) |

## Trabajo de cada integrante

Antes de trabajar, consulta el estado y acuerda qué pendiente atenderás. Al terminar, actualiza el documento responsable del tema, referencia su evidencia y registra el avance en el estado actual. Otro integrante debe revisar los cambios antes de integrarlos. El procedimiento completo está en [colaboración](docs/colaboracion.md).

Codex tiene instrucciones en [AGENTS.md](AGENTS.md); Claude, una entrada en [CLAUDE.md](CLAUDE.md); y Antigravity, una regla en [.agent/rules/contexto.md](.agent/rules/contexto.md). Si una herramienta no carga esas instrucciones, pídele expresamente que lea `AGENTS.md` y los documentos allí indicados. La carga automática no se ha probado en los tres clientes.

## Originales y situación de Git

Los originales permanecen intactos y excluidos del versionado. Sus referencias, alcance y restricciones están en [fuentes](docs/fuentes.md). Los dos resúmenes antiguos de la raíz se conservan como insumos históricos locales; no son documentos vigentes ni se deben usar para reemplazar `docs/`.

Actualmente esta carpeta pertenece a un repositorio de semestre ubicado dos niveles por encima; no es aún un repositorio independiente del equipo. Tras clonar ese repositorio, esta documentación se encontraría en `INTERACCIÓN HUMANO COMPUTADOR/PROYECTO/` **solo después de integrar y publicar estos cambios con autorización**. La elección del repositorio definitivo está pendiente en DEC-08. No se han realizado `git add`, commits ni push durante esta preparación.

No publicar grabaciones, consentimientos firmados, identificadores de participantes ni documentos universitarios de uso interno. `.gitignore` permite únicamente los archivos documentales revisados: no sustituye revisar su contenido, el índice y el historial antes de publicar.
