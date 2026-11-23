**PLANTILLA PARA DILIGENCIAR · UNIDAD 4 · SESIÓN 5**

**Ingeniería de Requisitos**

**Autoevaluación de capacidad del proceso de requisitos — SIGCortinas**

> **Nota de alcance y uso de IA.** Esta plantilla tampoco tiene ID en `Indice_trazabilidad.md` (la Unidad 4 solo llega hasta la Sesión 1 en el índice actual); se diligencia con el nombre de archivo del Ejemplo resuelto (`10-mejora-adopcion/autoevaluacion-capacidad.md`). Autoevaluación ligera, con la lógica de la serie ISO/IEC 33000; **no es una evaluación formal ni otorga un nivel oficial**. Se usó IA para clasificar la evidencia del repositorio por indicador y para redactar en limpio las brechas y acciones a partir de lo que ya está escrito en los documentos del proyecto; ningún número ni ruta se tomó de memoria. Ver sección 10 para el detalle de dónde se corrigió un borrador de IA.

## 1. Datos de la autoevaluación

| **Proyecto y equipo** |
|---|
| SIGCortinas — Cortinas Ambiente Moderno, Tunja, Boyacá. Miguel Antonio Gómez Guío; Edward Steven Rocha Torres; Juan Miguel Chaparro; Rafael Santiago Barriosnuevo Mongui. |

| **Proceso evaluado y alcance (desde cuándo, hasta cuándo)** |
|---|
| Elicitación y especificación de requisitos, desde el kick-off (`Kick - off.md`, 18/09/2026) hasta el catálogo de requisitos de calidad de la Sesión 4 de la Unidad 4 (`09-calidad/catalogo-rnf.md`, v0.1, 15/11/2026, con la revisión de requisitos todavía pendiente de realizar). |

| **Versión del repositorio evaluada (commit o etiqueta, fecha)** |
|---|
| **No verificable desde este ejercicio.** No se tiene acceso al historial real de commits, PR ni etiquetas de `pqrs-municipal`-equivalente de SIGCortinas en esta conversación; la evaluación se hace sobre el **contenido de los archivos entregados hasta la fecha** (el más reciente es `09-calidad/catalogo-rnf.md`, 15/11/2026). Esto es en sí mismo una limitación de esta autoevaluación: a diferencia del Ejemplo PQRS, aquí no se puede citar un commit exacto (ver indicador P2). |

| **Evaluadores por nivel y quién contrastó cada nivel** |
|---|
| Nivel 1: Juan Miguel Chaparro y Rafael Santiago Barriosnuevo Mongui. Nivel 2: Miguel Antonio Gómez Guío y Edward Steven Rocha Torres. Nivel 3: los cuatro integrantes. Contraste interno: el Nivel 1 lo contrastaron Miguel y Edward (quienes valoraron el Nivel 2); el Nivel 2 lo contrastaron Juan y Rafael. **No hubo contraste de un equipo externo** (a diferencia del Ejemplo PQRS, donde el Equipo B revisó la autoevaluación): esa revisión solo ocurrirá cuando el docente asigne un equipo revisor (Actividad 3 de la guía). |

| **Fecha de la autoevaluación y versión de este documento** |
|---|
| v1.0 · 22/11/2026. |

## 2. Escala y regla de agregación

| Valor | Significado operativo en el curso |
|---|---|
| N · No logrado | No hay evidencia en el repositorio. |
| P · Parcialmente | Hay evidencia aislada o con huecos importantes. |
| L · Ampliamente | La práctica es sistemática; quedan brechas menores y nombradas. |
| F · Totalmente | Completa, sin brechas relevantes, confirmada por otra persona. |

*Regla usada en el curso: un nivel se alcanza si sus atributos están en L o F y los de los niveles inferiores en F. Los umbrales exactos de la escala y la regla vigente se verifican en ISO/IEC 33020.*

## 3. Inventario de evidencia (antes de valorar)

| Carpeta o fuente | Artefactos (con fecha) | Qué demuestran |
|---|---|---|
| **01-kickoff/** | `Kick - off.md` (18/09/2026); `acta-constitucion.md` (25/09/2026); `plantilla-matriz-poder-interes.md` (17/08/2026, fecha anterior al kick-off) | Objetivo preliminar, acta con alcance/supuestos/riesgos, seis interesados puntuados con evidencia |
| **02-elicitacion/** | `guia-entrevista-empleada-Milena-Bermudez.md` (28/09/2026); `plantilla-cuestionario (2).md` (en blanco, sin diligenciar) | Una entrevista real completa (Empleada); un cuestionario diseñado pero nunca aplicado |
| **03-especificacion/** | `Árbol de Metas KAOS.md`; `HU-01.md`, `HU-02.md`; `CU-01N.md` a `CU-10.md` | Metas G0 a G3.2; 2 historias con INVEST; 10 casos de uso "fully dressed" |
| **04-priorizacion/** | `SIGCortinas-backlog-MoSCoW.md`; `Matrices - Valor costo.md` (AHP, CR=0,0115); `SIGCortinas-negociacion-WinWin.md` (todo marcado "propuesta para validar") | Backlog priorizado; comparación pareada de solo 4 de 10 casos de uso; negociación WinWin sin sesión real celebrada |
| **05-validacion/** | `acta-inspeccion__.md` (inspección Fagan de REQ-F-01 y REQ-F-04, explícitamente "simulación documental, no aprobación real"); `ficha-volere-REQ-F-01a__.md`, `ficha-volere-REQ-F-04b__.md` | Inspección formal, pero limitada a 2 de 13+ requisitos; 2 fichas Volere completas |
| **06-estandares-mapa/** | `matriz-aplicabilidad__.md` (15 estándares, decisión y adaptación por fila); `fuentes.md` (F01-F18, con fecha de verificación); `ficha-lectura-29148.md`; `declaracion-aplicacion-v0.1.md` | Estándares con edición verificada y fecha; decisión por estándar; asignación de responsables por parte del plan |
| **07-srs-830/** (en el repo real, `srs-SIGcortinas.md`) | `srs-SIGcortinas.md` (15/11/2026): 14 requisitos detallados (REQ-F-01a, 02, 03, 04a, 04b, 06, F-01b, F-01c, F-02a, F-10, F-11, NF-01, NF-02, NF-03) + 5 de "alcance futuro" sin detallar | Esqueleto adaptado de IEEE 830; requisitos con EARS y Apéndice B de reglas de diseño |
| **08-requisitos-29148/** | `matriz-trazabilidad (2).md` (13 requisitos, NI-01 a NI-11, decisiones D-01 a D-06); `checklist-29148 (2).md` (checklist de 9 pruebas a 6 fichas; hallazgos H-01 a H-08) | Trazabilidad NI → meta → HU → requisito → verificación; revisión de conjunto con hallazgos abiertos (H-06, H-07) |
| **09-calidad/** | `matriz-relevancia-calidad.md` y `catalogo-rnf.md` (esta misma sesión, 15/11/2026): seis RNF, dos tensiones, revisión de requisitos **propuesta pero no realizada**, firma de Vicky Beltrán **pendiente** | Catálogo de calidad construido, pero con la validación real todavía sin ocurrir |
| **GitHub: PR, issues, etiquetas** | **No verificable desde este ejercicio** | No hay visibilidad real de PR, issues ni etiquetas; solo los documentos entregados |

## 4. Nivel 1 · Realización del proceso

| Indicador | Evidencia (ruta exacta, fecha, PR o issue) | Val. N/P/L/F | Brecha observada (como hecho) |
|---|---|---|---|
| **R1. ¿Se identificaron los interesados y sus necesidades?** | `01-kickoff/plantilla-matriz-poder-interes.md` (6 interesados puntuados con evidencia); `Árbol de Metas KAOS.md` (G0 a G3.2); las NI-01 a NI-11 aparecen citadas en `matriz-trazabilidad (2).md`, pero solo como identificador dentro de la matriz. | **P** | No existe un documento propio (tipo StRS) que enuncie cada NI-01 a NI-11 con su texto completo, su interesado dueño y su fuente; solo aparecen como ID dentro de la columna "NI" de la matriz de trazabilidad. |
| **R2. ¿Se elicitó con técnicas documentadas y fuentes registradas?** | `02-elicitacion/guia-entrevista-empleada-Milena-Bermudez.md` (entrevista semiestructurada real, 28/09/2026); `09-calidad/catalogo-rnf.md` §1 (doce preocupaciones, pero 4 de 6 interesados sin cita textual real, marcadas "inferida" o "propuesta"). | **P** | Solo una técnica (entrevista) se aplicó realmente, y a un único interesado (Milena Bermúdez). El cuestionario diseñado (`plantilla-cuestionario (2).md`) sigue en blanco; la Gerente, el Técnico, el Cliente, el Proveedor y la Cámara de comercio nunca han sido entrevistados directamente. |
| **R3. ¿Los requisitos están especificados, identificados y priorizados?** | `srs-SIGcortinas.md` (identificadores REQ-F-xx y REQ-NF-xx estables); `SIGCortinas-backlog-MoSCoW.md` (Must/Should/Could con justificación); `Matrices - Valor costo.md` (AHP con CR=0,0115, consistente). | **L** | El AHP de valor/costo solo compara 4 de los 10 casos de uso (CU-01N, CU-02, CU-06, CU-09); el resto se priorizó únicamente por MoSCoW, sin comparación pareada. |
| **R4. ¿Los requisitos se validaron con los interesados?** | `05-validacion/acta-inspeccion__.md` (marcada explícitamente "cierre técnico... no equivale a aprobación real"); `09-calidad/catalogo-rnf.md` §7 (revisión de requisitos **propuesta, no realizada**; firma "pendiente"); `matriz-aplicabilidad__.md` y `declaracion-aplicacion-v0.1.md` (firmas y aprobación de adaptaciones "sin aprobación registrada"). | **N** | Ninguna validación real con un interesado con autoridad consta en el repositorio: todas las actas de revisión están explícitamente marcadas como simulación académica o pendientes de firma; no hay ninguna firma real de Vicky Beltrán en ningún documento. |
| **Atributo: realización del proceso** | — | **N** | El atributo baja a N porque R4 no tiene evidencia real, pese a que R3 está en L. Sin R4, el equipo no puede afirmar que algún requisito está realmente validado. |

## 5. Nivel 2 · Gestión de la realización

| Indicador | Evidencia (ruta exacta, fecha, PR o issue) | Val. N/P/L/F | Brecha observada (como hecho) |
|---|---|---|---|
| **G1. ¿Hay objetivos y un plan de las actividades de requisitos (qué, quién, cuándo)?** | `acta-constitucion.md` §5 "Cronograma de alto nivel" (hitos por fecha, uno por unidad/sesión); `Kick - off.md` (objetivo general, sin tareas individuales). | **P** | Hay hitos con fecha, pero ningún plan de tareas de requisitos (entrevistas, especificación, validación) con responsable individual; el reparto real entre los 4 integrantes no queda escrito en ningún documento. |
| **G2. ¿La realización se sigue y se ajusta?** | `matriz-trazabilidad (2).md` §3 (decisiones D-01 a D-06, con fecha); `guia-entrevista-empleada-Milena-Bermudez.md` §10 (seis dudas pendientes, sin fecha límite). | **P** | Las seis decisiones D-01 a D-06 casi todas dicen "pendiente revisión de Vicky Beltrán" sin que conste ningún seguimiento posterior a esa fecha; las dudas pendientes de la entrevista no tienen fecha de cierre ni se ha hecho seguimiento desde el 28/09/2026. |
| **G3. ¿Hay responsabilidades y roles asignados?** | `guia-entrevista-empleada-Milena-Bermudez.md` (Entrevistadores y Relator nombrados); `acta-inspeccion__.md` (Moderador, Autor, Lector, Anotador nombrados); `declaracion-aplicacion-v0.1.md` §7 (responsables por tema: SRS, calidad, contexto, gestión). | **L** | Los roles se asignan por evento (entrevista, inspección) y, desde `declaracion-aplicacion-v0.1.md`, también por tema; falta que esa asignación por tema se repita de forma consistente en cada entrega posterior (por ejemplo, en el propio catálogo de calidad de esta sesión no se repitió). |
| **G4. ¿La comunicación con los interesados se gestiona como se planificó?** | `plantilla-matriz-poder-interes.md` (estrategias "gestionar de cerca", "mantener informado", "mantener satisfecho", "monitorear" para los 6 interesados, 17/08/2026). | **N** | Cero registros de que esas estrategias se hayan ejecutado desde que se escribieron: el Técnico y el Proveedor de persianas siguen sin ser contactados (`matriz-relevancia-calidad.md`, columnas "casi en cero"), y no existe ninguna bitácora de comunicación. |
| **Atributo: gestión de la realización** | — | **N** | G4 sin ninguna evidencia arrastra el atributo a N, aunque G3 esté en L. |

## 6. Nivel 2 · Gestión de los productos de trabajo

| Indicador | Evidencia (ruta exacta, fecha, PR o issue) | Val. N/P/L/F | Brecha observada (como hecho) |
|---|---|---|---|
| **P1. ¿Están definidos los requisitos de los productos (plantillas, reglas de calidad)?** | `SKILL.md` (reglas transversales por tipo de artefacto: HU/INVEST, CU Cockburn, EARS/INCOSE, Volere, Fagan, estándares, con checklist de cierre de 5 puntos). | **L** | `SKILL.md` consolida reglas por tipo de documento y se aplicó en cada entrega revisada (ver checklists de cierre al final de cada plantilla diligenciada), pero no hay una "definición de listo" única para un requisito individual, equivalente a la de 29148: cada sesión aplicó su propio checklist por separado. |
| **P2. ¿Los productos están bajo control de versiones y los cambios se registran?** | `matriz-trazabilidad (2).md` §3 (D-01 a D-06, con ID y fecha); ningún documento cita número de PR o commit real; ninguna etiqueta de línea base existe. | **P** | Hay decisiones de cambio registradas con ID y fecha, pero sin evidencia verificable de control de versiones real (PR/commit) ni de ninguna etiqueta de línea base, a diferencia del Ejemplo PQRS (`req-base-1.0`). |
| **P3. ¿Los productos se revisan contra criterios explícitos?** | `checklist-29148 (2).md` (checklist de 9 pruebas aplicado a solo 6 de los 13+ requisitos del SRS); `acta-inspeccion__.md` (checklist INCOSE aplicado a 2 requisitos: REQ-F-01a y REQ-F-04a/b). | **P** | 7 de los 13 requisitos del SRS (REQ-F-02, F-03, F-06, F-10, F-11; y los seis REQ-NF del catálogo nuevo) no han pasado ningún checklist individual completo. |
| **P4. ¿La trazabilidad se mantiene al día?** | `matriz-trazabilidad (2).md` (13 requisitos con NI, meta, HU, prioridad, verificación); `09-calidad/catalogo-rnf.md` (REQ-NF-04 a REQ-NF-06, nuevos de esta sesión). | **P** | Los RNF nuevos de esta misma sesión (REQ-NF-04 a REQ-NF-06) **todavía no están incorporados** en `matriz-trazabilidad (2).md`: hoy mismo hay una desincronización real entre el catálogo de calidad y la matriz, igual al hilo 3 del Ejemplo PQRS. |
| **Atributo: gestión de los productos de trabajo** | — | **P** | Tres de los cuatro indicadores quedan en P; solo P1 llega a L. |

## 7. Nivel 3 · Definición y despliegue del proceso

| Indicador | Evidencia (ruta exacta, fecha, PR o issue) | Val. N/P/L/F | Brecha observada (como hecho) |
|---|---|---|---|
| **D1. ¿Existe una descripción del proceso de requisitos que el equipo sigue?** | `SKILL.md` (reglas de redacción por tipo de artefacto, no una descripción de proceso: entradas, pasos, revisión, salidas). | **P** | `SKILL.md` dice cómo redactar cada plantilla, pero no describe el proceso propio del equipo (quién hace qué, en qué orden); cada sesión se hizo "como decía la guía" del curso, no como un proceso documentado por el equipo. |
| **D2. ¿Las adaptaciones al proyecto están documentadas y justificadas?** | `matriz-aplicabilidad__.md` §5 (tailoring de 29148, 12207, 25010, 29110, 25023, con justificación y riesgo asumido); `declaracion-aplicacion-v0.1.md`. | **L** | Las adaptaciones están bien documentadas y justificadas, pero son adaptaciones del **uso de estándares externos**, no del proceso propio del equipo (misma precisión que marca el Ejemplo PQRS). |
| **Atributo: definición del proceso** | — | **P** | D1 en P arrastra el atributo, pese a D2 en L. |
| **D3. ¿El proceso definido se usa de forma consistente por todos?** | — | **N** | Sin un proceso propio definido (D1), no hay despliegue que valorar: no se puede comprobar que "todos siguen lo mismo" cuando no existe ese "lo mismo" por escrito. |
| **D4. ¿Se recogen datos del uso del proceso para mejorarlo?** | `checklist-29148 (2).md` (hallazgos H-01 a H-08 de la revisión del conjunto); `acta-inspeccion__.md` (tres métricas de la inspección Fagan: tasa de preparación 3,33 pág./h, densidad de defectos 1,50, eficiencia de detección 75%). | **P** | Hay datos de una sola inspección y de una sola revisión de conjunto; nadie los ha comparado entre sesiones ni los ha usado para ajustar cómo trabaja el equipo. |
| **Atributo: despliegue del proceso** | — | **N** | Se valora N porque D3 —el núcleo del atributo— no tiene ninguna evidencia; los datos de D4 se conservan como insumo para cuando exista un proceso que desplegar. |

## 8. Perfil de capacidad y nivel alcanzado

| Nivel · atributo | Valoración | ¿Nivel alcanzado? ¿Por qué? |
|---|---|---|
| **1 · Realización del proceso** | **N** | No. R4 (validación real con interesados) no tiene evidencia, y R1/R2 solo llegan a P. |
| **2 · Gestión de la realización** | **N** | No: ni siquiera el Nivel 1 está en F, y G4 está en N. |
| **2 · Gestión de los productos de trabajo** | **P** | No: tres de cuatro indicadores en P, y el Nivel 1 tampoco está en F. |
| **3 · Definición del proceso** | **P** | No: D1 en P, y los niveles inferiores no están en F. |
| **3 · Despliegue del proceso** | **N** | No: D3 (el núcleo) está en N. |

| **Resultado: nivel alcanzado según esta autoevaluación ligera** |
|---|
| Según esta autoevaluación, el proceso de elicitación y especificación de requisitos de SIGCortinas **no alcanza de forma consistente ni siquiera el Nivel 1 (Realizado)**: aunque la especificación y priorización (R3) está en L, el atributo del nivel baja a N porque la validación real con los interesados (R4) no tiene ninguna evidencia — todas las actas de revisión del repositorio están explícitamente marcadas como simulación académica o pendientes de firma. Esto es más exigente que el resultado del Ejemplo PQRS (que sí alcanzó Nivel 1), y refleja honestamente que SIGCortinas solo ha entrevistado realmente a un interesado de seis. |

| **Nivel objetivo, fecha y qué atributos deben subir para lograrlo** |
|---|
| **Objetivo: Nivel 1 (Realizado) de forma consistente**, al cierre de la Unidad 7 (no se fija el Nivel 2 como meta de esta unidad, a propósito: sería prematuro mientras el Nivel 1 no esté en F). Para lograrlo: (a) **R4** debe pasar de N a al menos L — requiere una validación real y firmada con Vicky Beltrán (AM-01); (b) **R1** debe subir de P a L — requiere el documento StRS propio (AM-02); (c) **R2** debe subir de P a L — requiere entrevistar a la Gerente y al Técnico, y aplicar el cuestionario (AM-01, AM-03). Una segunda autoevaluación al cierre de la Unidad 7, contrastada por el equipo revisor que asigne el docente, comprobará si esto se logró. |

## 9. Acciones de mejora priorizadas

| ID | Brecha | Acción | Prioridad | Responsable | Fecha | Evidencia de cierre |
|---|---|---|---|---|---|---|
| **AM-01** | R4, G4 | Entrevistar a la Gerente (Vicky Beltrán) y al Técnico con la guía de entrevista de la Unidad 3 (Sesión 2), y llevar a firma real el acta de revisión de requisitos de calidad propuesta en `09-calidad/catalogo-rnf.md` §7. | **Alta** | Juan Miguel Chaparro (coordina con Vicky Beltrán) | 28/11/2026 | `02-elicitacion/entrevista-gerente-vicky-beltran.md` y `02-elicitacion/entrevista-tecnico.md` fusionados; firma real (no "pendiente") en `09-calidad/catalogo-rnf.md` §7. |
| **AM-02** | R1 | Redactar un extracto StRS (`08-requisitos-29148/strs-necesidades.md`) que enuncie cada NI-01 a NI-11 con su texto, interesado dueño y fuente, en vez de que solo aparezcan como ID dentro de la matriz. | **Alta** | Miguel Antonio Gómez Guío | 27/11/2026 | Archivo `strs-necesidades.md` fusionado y citado desde `matriz-trazabilidad (2).md`. |
| **AM-03** | R2, G4 | Aplicar `plantilla-cuestionario (2).md` (hoy en blanco) a al menos 5 personas del perfil de clientes, con su registro de piloto. | **Media** | Rafael Santiago Barriosnuevo Mongui | 05/12/2026 | `plantilla-cuestionario (2).md` diligenciado con resultados, piloto y lectura. |
| **AM-04** | P2 | Etiquetar una línea base (`req-base-1.0`) del SRS y la matriz de trazabilidad tras la revisión real de requisitos de calidad; crear la plantilla de issue "Solicitud de cambio de requisito". | **Media** | Edward Steven Rocha Torres | 28/11/2026 | Etiqueta Git `req-base-1.0`; `.github/ISSUE_TEMPLATE/solicitud-cambio-requisito.md` fusionada. |
| **AM-05** | P4 | Actualizar `matriz-trazabilidad (2).md` para incorporar REQ-NF-04 a REQ-NF-06 del nuevo catálogo de calidad, en el mismo PR que fusione `09-calidad/catalogo-rnf.md`. | **Alta** | Miguel Antonio Gómez Guío | 24/11/2026 | `matriz-trazabilidad (2).md` con fila de REQ-NF-04 a 06 y columna de verificación actualizada. |
| **AM-06** | P3 | Aplicar el checklist de 29148 a los 7 requisitos restantes del SRS (REQ-F-02, F-03, F-06, F-10, F-11) y a los seis RNF nuevos. | **Media** | Rafael Santiago Barriosnuevo Mongui | 10/12/2026 | `checklist-29148 (2).md` ampliado con las columnas de los requisitos faltantes. |
| **AM-07** | D1 | Describir en una página el proceso de requisitos propio del equipo (entradas, pasos, plantillas, revisión, salidas), a partir de lo que de verdad funcionó. Preparación, no compromiso de Nivel 3. | **Baja** | Juan Miguel Chaparro | Primera semana de la Unidad 7 | `10-mejora-adopcion/proceso-requisitos-equipo.md` fusionado. |

## 10. Uso de IA y contraste

| **¿Para qué se usó IA? (organizar evidencia, redactar acciones...) ¿Qué se verificó a mano?** |
|---|
| Se usó IA para clasificar el inventario de archivos del proyecto por indicador (paso 3) y para redactar en limpio las brechas y acciones de mejora a partir de las valoraciones que el equipo haría a mano. Un primer borrador de la IA propuso valorar **G1 y P2 en L**, citando "control de versiones por pull request" como evidencia: al revisar, no hay ningún PR, commit o etiqueta verificable desde este ejercicio (no hay acceso real a GitHub en esta conversación), así que ambos indicadores se corrigieron a **P**. Es exactamente el error que advierte la guía: lo que no deja rastro verificable, para esta autoevaluación no existe. También se verificó a mano cada ruta citada contra el contenido real de los documentos del proyecto antes de aceptar cualquier valoración. |

| **Contraste: quién abrió las rutas citadas y qué valoraciones cambiaron** |
|---|
| Cada nivel fue valorado por dos integrantes y contrastado por los otros dos (sección 1). El contraste del Nivel 1, hecho por quienes valoraron el Nivel 2, confirmó R4 en N tras revisar que ninguna acta del repositorio (`acta-inspeccion__.md`, `catalogo-rnf.md` §7, `declaracion-aplicacion-v0.1.md`) tiene una firma real, solo "pendiente de firma" o "sin aprobación registrada". **Pendiente:** a diferencia del Ejemplo PQRS (donde el Equipo B contrastó la autoevaluación completa), esta versión todavía no tiene contraste de un equipo externo; eso ocurrirá en la Actividad 3 de la guía, cuando el docente asigne un equipo revisor, y se registrará en `10-mejora-adopcion/revision-recibida.md`. |

---

## Checklist de cierre (SKILL.md) — verificación de esta entrega

1. **¿Cada afirmación apunta a una fuente del proyecto real?** Sí; cada indicador cita la ruta exacta del documento y, donde no hay evidencia real (control de versiones, validación con interesados), se declaró explícitamente "no verificable" en vez de inventar una ruta.
2. **¿Hay justificación escrita, no solo un «sí»?** Sí, en la columna "Brecha observada" de cada indicador y en cada decisión de la sección 8.
3. **¿Los escenarios/indicadores tienen sujeto explícito y sin condicionales mezclados?** Sí; cada brecha describe un hecho verificable, no una promesa futura.
4. **¿Lo pendiente está marcado como pendiente?** Sí: el contraste de un equipo externo (sección 10), la firma de Vicky Beltrán (R4) y la versión del repositorio (sección 1) quedan explícitamente sin confirmar.
5. **¿Se declaró el uso de IA?** Sí, en la nota de alcance inicial y en la sección 10, incluyendo el error de la IA que se corrigió.

*Este documento se sube en `10-mejora-adopcion/autoevaluacion-capacidad.md` por pull request, con al menos un commit propio de cada integrante y revisión de otro integrante antes de fusionar.*
