**PLANTILLA DE REVISIÓN · UNIDAD 4 · SESIÓN 3 DE 5**

**Ingeniería de Requisitos**

**Checklist ISO/IEC/IEEE 29148: requisito individual y conjunto de requisitos — SIGCortinas**

> Instrumento de verificación aplicado sobre las 6 fichas detalladas en `ficha-req-29148.md` y sobre el conjunto completo de requisitos en `matriz-trazabilidad.md` (13 requisitos y 11 necesidades de los interesados). Los hallazgos del análisis de conjunto se identifican de H-01 a H-08.

| **Proyecto** |
|---|
| SIGCortinas |

| **Moderador(a) y revisores** |
|---|
| Moderador: Edward Steven Rocha Torres (cumple la regla de independencia al no ser autor de ninguna de las 6 fichas). Revisores: Miguel Antonio Gómez Guío, Juan Miguel Chaparro, Rafael Santiago Barriosnuevo Mongui. |

| **Fecha de la revisión** |
|---|
| 15/11/2026 · `matriz-trazabilidad.md` y `ficha-req-29148.md` (FICHAS 1-6). |

## A. Checklist individual: las nueve pruebas

| Característica | Pregunta de prueba | ID: REQ-F-01a | ID: REQ-F-02 | ID: REQ-F-03 | ID: REQ-F-04b | ID: REQ-F-06 | ID: REQ-NF-02 |
|---|---|---|---|---|---|---|---|
| **Necesario** | ¿Qué NI o meta queda sin cubrir si lo quito? | Sí | Sí | Sí | Sí | Sí | Sí |
| **Apropiado** | ¿Es responsabilidad del software y está al nivel del SRS? | Sí | Sí | Sí | Sí | Sí | Sí |
| **No ambiguo** | ¿Dos lectores lo explican igual? | Sí | Sí | Sí | Sí | Sí | **Sí** — incorpora la regla explícita «niega por defecto toda acción o consulta no autorizada» |
| **Completo** | ¿Se construye y prueba sin preguntar quién/qué dato/qué resultado? | Sí | Sí | Sí | Sí | Sí | **Sí** — las reglas de acceso por rol quedaron especificadas a partir de los casos de uso (`CU-01N` a `CU-10`) |
| **Singular** | ¿Puede cumplirse una parte y la otra no? | Sí | Sí | Sí | Sí | Sí | Sí |
| **Factible** | ¿Lo confirmó quien lo va a construir, con lo que hay y en el plazo? | Sí | Sí | Sí | Sí | Sí | **Sí** — confirmado técnicamente por el equipo de desarrollo; ratificación de la Gerente pendiente bajo la prueba «Correcto» |
| **Verificable** | ¿Ya se puede escribir el criterio de aceptación y elegir el método? | Sí | Sí | Sí | Sí | Sí | **Sí** — los casos de prueba e inspección cubren tanto las acciones permitidas como la denegación por defecto |
| **Correcto** | ¿Coincide con su fuente, y el dueño de la fuente lo aprobó? | **? (Vicky Beltrán, sin firma registrada)** | **? (Vicky Beltrán, sin firma registrada)** | **? (Vicky Beltrán, sin firma registrada)** | **? (Vicky Beltrán; regla exacta del 50 % sin confirmar)** | **? (Vicky Beltrán, sin firma registrada)** | **? (Vicky Beltrán, sin firma registrada)** |
| **Conforme** | ¿Sigue identificador, plantilla EARS, «deberá» y glosario del proyecto? | Sí | Sí | Sí | Sí | Sí | Sí |

**Lectura obligatoria de esta tabla:** las seis fichas presentan un «?» en **Correcto**, debido a que ninguna cuenta con firma o aprobación formal registrada de Vicky Beltrán. Conforme a la regla de la plantilla («una ficha con un «?» no puede pasar a Aprobado»), **las 6 fichas se mantienen en estado Propuesto** — ver Conclusión.

## B. Checklist de conjunto: las cinco características

| Característica | Técnica de revisión | Qué se revisó (evidencia) | Resultado y hallazgos |
|---|---|---|---|
| **Completo** | Trazado hacia atrás (requisitos sin NI o sin HU) y hacia adelante (NI e historias Must/Should sin requisito); búsqueda de elementos sin definir. | `matriz-trazabilidad.md` (13 requisitos, 11 NI) y `srs-sigcortinas.md`. | Hacia atrás: todos los requisitos trazan a al menos una NI. Hacia adelante: las **11 NI del StRS tienen cobertura** (H-01 resuelto). Las definiciones operativas del SRS están cerradas por decisión del equipo. |
| **Consistente** | Barrido por pares agrupado por entidad: comparación de requisitos que comparten un dato o término. | Término «cita Programada / agenda compartida» (REQ-F-01a, REQ-F-02, REQ-F-03). | Sin contradicción en la definición de términos. Se registró la dependencia de sincronización entre «notificar» (REQ-F-03) y «reflejar al abrir/recargar» (REQ-F-02), resuelta mediante regla de diseño en el SRS (H-04). |
| **Factible** | Esfuerzo total contra capacidad (`SIGCortinas-backlog-MoSCoW.md`); pares de calidad en tensión; prototipo rápido o medición técnica. | `SIGCortinas-backlog-MoSCoW.md` (§3: Must = 66,04 %) y fichas 1, 3 y 6. | Alerta de esfuerzo Must en 66,04 % registrada para planeación con la Gerente. Tensión de calidad identificada: facilidad de uso para la Empleada (entrevista, hallazgo 9) vs. controles de acceso por rol (REQ-NF-02). Pendiente medición técnica real sobre la función compartida de cruce de horarios (H-05). |
| **Comprensible** | Términos del dominio contra el glosario (1.3 del SRS); sinónimos; lectura por alguien externo al equipo. | Glosario 1.3 de `srs-sigcortinas.md` y los 6 enunciados de las fichas. | Los términos (cita Programada, abono inicial, existencia, duración en finca, etc.) mantienen uniformidad entre glosario y requisitos. Pendiente sesión de lectura con la Gerente y la Empleada para validar comprensión en lenguaje del negocio (H-06). |
| **Validable** | Criterios de aceptación agrupados por NI, presentados a su dueño: «¿esto resuelve su necesidad?». | Sección 2 de `matriz-trazabilidad.md` y criterios de aceptación de las 6 fichas. | Los criterios son observables y medibles, pero aún no se han presentado agrupados por NI a Vicky Beltrán para su validación formal (H-07). |

**Apoyo para el barrido por pares**

| Entidad o término | Requisitos que la mencionan | N.º de pares | Hallazgos (contradicción, duplicado, término) |
|---|---|---|---|
| Cita Programada / agenda compartida | REQ-F-01a, REQ-F-02, REQ-F-03 | 3 | Sin contradicción de definición. Sincronización entre REQ-F-02 y REQ-F-03 resuelta mediante disparador único de evento (H-04) y componente único de verificación de cruce (H-08) en el Apéndice B del SRS. |
| Rol de usuario (Gerente / Empleada / Técnico) | REQ-F-02, REQ-NF-02 | 1 | Sin contradicción de términos; los tres roles se nombran de manera uniforme y sus permisos se derivan de los casos de uso (`CU-01N` a `CU-10`). |
| Abono inicial / 50 % del total | REQ-F-04b | 0 (solo 1 requisito fichado en esta muestra) | Sin pares dentro de las 6 fichas; coherencia con CU-05 documentada en dependencias de la Ficha 4. |

## C. Registro de hallazgos

| # | Requisito(s) | Característica | Hallazgo | Resolución acordada | Aprobó · fecha | Estado |
|---|---|---|---|---|---|---|
| **H-01** | NI-04, NI-05, NI-07, NI-10 | Completo (conjunto) | Necesidades del StRS que requerían cobertura explícita en la especificación. | Incorporación de REQ-F-01b, REQ-F-01c, REQ-F-02a, REQ-F-10 y REQ-F-11 en `srs-sigcortinas.md`. | Decisión del equipo (sin firma de Gerente) · 15/11/2026 | Cerrado en cobertura |
| **H-02** | REQ-F-04a, REQ-NF-01, REQ-F-01b, REQ-F-01c, REQ-F-02a, REQ-F-10, REQ-F-11, REQ-NF-02 | Completo / Clasificado (conjunto) | Asignación formal de prioridad MoSCoW para todos los requisitos de la muestra. | Definida en `SIGCortinas-backlog-MoSCoW.md`: herencia desde CU/HU (incluyendo REQ-F-11 como **Could**) y filas propias para REQ-NF-01 y REQ-NF-02 (**Must**). Genera alerta de 66,04 % Must. | Decisión del equipo (sin firma de Gerente) · 15/11/2026 | Cerrado en clasificación |
| **H-03** | REQ-NF-02 | Necesario / Apropiado (trazabilidad) | Traza directamente a NI-11 (origen legal, Ley 1581 de 2012) sin meta KAOS ni CU propio. | Se acepta el origen legal como justificación suficiente, sin crear metas artificiales (decisión D-03 de la matriz). | Decisión del equipo · 15/11/2026 | Cerrado (aceptado por diseño) |
| **H-04** | REQ-F-02, REQ-F-03 | Consistente | Riesgo de desincronización entre la notificación de cambio (REQ-F-03) y la actualización del panel al abrir/recargar (REQ-F-02). | Regla de diseño incorporada en el Apéndice B de `srs-sigcortinas.md`: ambos procesos se disparan desde el mismo evento de cambio de cita. | Decisión del equipo · 15/11/2026 | Cerrado en especificación |
| **H-05** | REQ-F-01a, REQ-F-03, REQ-NF-02 | Factible | Viabilidad técnica de la función compartida de verificación de cruce y definición de reglas de acceso por rol. | Para REQ-NF-02: reglas cerradas a partir de los casos de uso (`CU-01N` a `CU-10`). Para REQ-F-01a/REQ-F-03: componente único especificado en Apéndice B del SRS; pendiente prueba/medición técnica real en implementación. | Decisión del equipo · 15/11/2026 | Parcialmente abierto (medición técnica pendiente) |
| **H-06** | Las 6 fichas (conjunto) | Comprensible | Ningún lector externo al equipo (Gerente, Empleada) ha revisado los enunciados para validar su lenguaje de negocio. | Agendar lectura conjunta de los 6 enunciados y sus criterios de aceptación con la Gerente. | Pendiente — Gerente (antes del 20/11/2026) | Abierto |
| **H-07** | Las 6 fichas (conjunto) | Validable | Los criterios de aceptación no se han presentado agrupados por NI a Vicky Beltrán. | Presentar los criterios agrupados por NI (`matriz-trazabilidad.md` §2) en sesión de validación con la Gerente. | Pendiente — Gerente (antes del 24/11/2026) | Abierto |
| **H-08** | REQ-F-01a, REQ-F-03 | Factible / Conforme (diseño) | Ambos requisitos comparten la regla de verificación de disponibilidad del Técnico. | Restricción de diseño explícita en el Apéndice B de `srs-sigcortinas.md`: implementación en un único componente reutilizado por ambos requisitos. | Decisión del equipo · 15/11/2026 | Cerrado en especificación |

## Conclusión de la revisión

**Estado de aprobación:** **Propuesto, verificado documentalmente.** Las 6 fichas detalladas cumplen las ocho pruebas técnicas y de redacción (Necesario, Apropiado, No ambiguo, Completo, Singular, Factible, Verificable y Conforme), pero mantienen un «?» en **Correcto** al no contar todavía con la aprobación firmada de Vicky Beltrán.

**Acciones pendientes con los interesados externos:**
- Lectura y aprobación formal de las 6 fichas por Vicky Beltrán — antes del 20/11/2026 (H-06 y cierre de la prueba «Correcto»).
- Validación de los criterios de aceptación agrupados por NI con la Gerente — antes del 24/11/2026 (H-07).
- Confirmación con la Gerente de la regla exacta del abono inicial del 50 % (D-02) y entrevista directa con el Técnico para ratificar NI-04 y NI-05 (D-05).
- Resolución conjunta con la Gerente sobre la alerta de capacidad del backlog (66,04 % en categoría Must) y validación legal/contable del plazo exacto de garantía de REQ-NF-03 (Ley 1480 de 2011).

*Se almacena en `08-requisitos-29148/checklist-conjunto.md`.*
