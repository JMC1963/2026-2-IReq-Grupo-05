**PLANTILLA PARA DILIGENCIAR · UNIDAD 6 · SESIÓN 2 DE 5**

**Ingeniería de Requisitos**

**Lista de verificación: inventario de pantallas y navegación — SIGCortinas**

> **Nota de alcance.** La aplica un integrante distinto de quien redactó el inventario y la matriz. Revisada contra los archivos citados en `ficha-inventario-pantalla.md` y `matriz-trazabilidad-pantallas.md`, no de memoria. Tampoco hay ID en `Indice_trazabilidad.md` para la Unidad 6 (se guarda en `17-pantallas-navegacion/trazabilidad/`).

| Proyecto | Versión revisada | Fecha | Revisó | Autor(es) del inventario |
|---|---|---|---|---|
| SIGCortinas | v0.1 de `ficha-inventario-pantalla.md` y `matriz-trazabilidad-pantallas.md` | 22/11/2026 | Otro integrante del equipo (distinto de los autores) | Miguel Antonio Gómez Guío; Juan Miguel Chaparro |

## A. Completitud

| Ítem | Pregunta | C | N | NA | Observación · responsable · fecha |
|---|---|---|---|---|---|
| **A1** | ¿Cada caso de uso con interfaz tiene al menos una pantalla o mensaje asociado en la matriz? | ✔ | | | Los 10 casos de uso (CU-01N a CU-10) tienen pantalla; CU-02 y CU-04 además tienen mensaje (M-01, M-02). |
| **A2** | ¿Cada caso de uso sin pantalla propia dice por qué y dónde deja su rastro (pantalla o mensaje)? | | | ✔ | No se identificó ningún caso de uso de tipo **b** (sistema/Planificador) en el catálogo actual de SIGCortinas: la alerta de plazo excedido (CU-03 ext. 2c) es un estado de P-02, no un caso de uso aparte. No hay nada que verificar aquí todavía. |
| **A3** | ¿Cada pantalla tiene ficha con todos los campos, sin celdas vacías sin explicar? | ✔ | | | Las 11 fichas (P-01 a P-11) tienen los 14 campos llenos; donde falta una decisión se escribió explícitamente en "Preguntas abiertas", no se dejó vacío. |
| **A4** | ¿Cada mensaje (correo, SMS) tiene disparador, destinatario, canal y contenido mínimo? | ✔ | | | M-01 y M-02, en la tabla de mensajes de `ficha-inventario-pantalla.md`. |

## B. Granularidad

| Ítem | Pregunta | C | N | NA | Observación · responsable · fecha |
|---|---|---|---|---|---|
| **B1** | ¿Cada pantalla tiene un solo propósito que se dice sin la palabra «y»? | ✔ | | | Se corrigió en la revisión: el primer borrador describía P-05 como "ver y, si corresponde, registrar el resultado" — se dividió en **P-05 Detalle de la visita** (solo ver) y **P-06 Registrar resultado de la visita** (solo el Técnico, solo registrar), cada una con un propósito sin "y". revisión registrada el 22/11/2026. |
| **B2** | ¿Hay pantallas distintas para un mismo propósito solo porque cambia el rol (en lugar de una pantalla con vistas)? | ✔ | | | No: P-02 (agenda) y P-05 (detalle de visita) son una sola pantalla con vista filtrada por rol, no una copia por cada uno. |
| **B3** | ¿Ninguna pantalla es «Dios» (más de tres propósitos o roles con permisos muy distintos)? | ✔ | | | P-02 y P-05, que comparten varios roles, se revisaron a propósito por este riesgo: cada una mantiene un solo propósito con acciones que varían por rol, no tres propósitos distintos. |
| **B4** | ¿Las ventanas emergentes y secciones están anotadas dentro de la ficha de su pantalla y no como pantallas aparte? | ✔ | | | La acción de reprogramar/cancelar una cita (CU-04) se documentó como una sección/modal dentro de la ficha de P-05, no como pantalla aparte. |

## C. Nombres

| Ítem | Pregunta | C | N | NA | Observación · responsable · fecha |
|---|---|---|---|---|---|
| **C1** | ¿Cada pantalla tiene nombre de inventario estable y una etiqueta de menú en el lenguaje de sus usuarios? | | ⚠ Parcial | | Cada pantalla tiene su ID (P-nn) y su etiqueta propuesta ("Agenda del día", "Nuevo pedido", etc.), tomadas del lenguaje de las entrevistas y los CU; pero ninguna etiqueta se ha comprobado todavía con un usuario real (ver C2). Marcado como **N** por prudencia: una etiqueta sin comprobar no se puede dar por "del lenguaje de sus usuarios" con certeza. |
| **C2** | ¿Las etiquetas se comprobaron con personas del grupo de usuarios (tarjetas o prueba de etiquetas) y el resultado está registrado? | | ✔ N | | **No se ha hecho ninguna prueba todavía.** Además, SIGCortinas tiene solo **tres** usuarios reales del sistema (Gerente, Empleada, Técnico): la actividad pide comprobar con "al menos cinco personas del grupo de usuarios", algo que no se puede cumplir literalmente en un proyecto de esta escala. Se registra como hallazgo H-07 en la lista de huecos, para discutir con el docente cómo adaptar el mínimo de personas a un equipo de tres usuarios reales. |
| **C3** | ¿El mismo término se usa igual en menú, título, ficha, mensajes y requisitos (sin sinónimos)? | | ⚠ Parcial | | Los términos se mantienen iguales en la mayoría de los documentos ("pedido", "garantía", "inventario"), pero "cita" y "visita" se usan de forma intercambiable entre los CU (`CU-02.md`, `CU-03.md`, `CU-04.md`) y el inventario de pantallas todavía no decidió cuál de los dos fijar como término único. |

## D. Rutas y flujos

| Ítem | Pregunta | C | N | NA | Observación · responsable · fecha |
|---|---|---|---|---|---|
| **D1** | ¿Cada flujo F-nn tiene un diagrama de navegación con punto de entrada y condiciones entre corchetes? | | ✔ N | | Los diagramas (.puml) son el entregable de la **Actividad 2** de esta sesión, todavía no construidos. Esta entrega cubre solo las tres plantillas (checklist, matriz, fichas). |
| **D2** | ¿Todo flujo muestra las ramas de error, de vacío y de cancelación (o dice que no aplican)? | | ✔ N | | Las ramas de error, vacío y cancelación están **descritas en texto** dentro del campo "Estados de la pantalla" de cada ficha, pero todavía no están dibujadas en ningún diagrama (depende de D1). |
| **D3** | ¿Se contó la ruta mínima de cada tarea (pantallas y clics) y se comparó con el criterio de usabilidad? | | ✔ N | | No se ha contado todavía para ningún flujo; queda para la Actividad 2, cuando exista el diagrama, comparándola contra REQ-NF-07.1 a REQ-NF-07.3 de `requisitos-usabilidad-accesibilidad.md`. |
| **D4** | ¿Toda pantalla tiene al menos una forma de llegar y una forma de salir (sin callejones)? | ✔ | | | Cada ficha tiene su campo "Viene de / lleva a" lleno con al menos una entrada y una salida. |

## E. Permisos

| Ítem | Pregunta | C | N | NA | Observación · responsable · fecha |
|---|---|---|---|---|---|
| **E1** | ¿Existe la tabla rol por pantalla y el menú de cada rol sale de ella? | ✔ | | | Sección 4 de `matriz-trazabilidad-pantallas.md`. |
| **E2** | ¿Cada rol tiene definida su pantalla de inicio? | ✔ | | | Los tres roles tienen a P-02 (Agenda del día) como inicio, con vista filtrada para el Técnico. |
| **E3** | ¿Las pantallas compartidas por varios roles dicen qué ve y qué puede hacer cada uno? | | ⚠ Parcial | | P-02 y P-05 sí lo precisan; **P-08 (Inventario)** todavía no distingue con el mismo detalle que la Gerente puede decidir compras a partir de la alerta de existencia baja (CU-06 ext. 6a) mientras la Empleada solo consulta — queda como ajuste menor para la ficha de P-08 en la Sesión 3. |
| **E4** | ¿Se aclara que ocultar un ítem del menú no es controlar el acceso (el permiso se exige siempre)? | ✔ | | | Nota explícita en la sección 4 de la matriz, ligada a REQ-NF-02. |

## F. Trazabilidad y huecos

| Ítem | Pregunta | C | N | NA | Observación · responsable · fecha |
|---|---|---|---|---|---|
| **F1** | Dirección A: ¿todo caso de uso con interfaz tiene pantalla? | ✔ | | | Los 10 CU de tipo "a" tienen pantalla (ver Dirección A). |
| **F2** | Dirección B: ¿toda pantalla justifica al menos un caso de uso y un requisito? | ✔ | | | Las 11 pantallas y los 2 mensajes justifican al menos un CU o un requisito (P-01 es transversal, justificado por REQ-NF-02). |
| **F3** | Dirección C: ¿todo requisito funcional con interfaz aparece en alguna pantalla o mensaje, o está justificado? | | ✔ N | | **No todavía.** Cinco requisitos de "alcance futuro" (REQ-F-05, 07, 08, 09, 12) y uno de calidad (REQ-NF-05) quedan como hueco real (H-01 a H-06), porque sus fichas detalladas no existen aún en `srs-SIGcortinas.md`. |
| **F4** | ¿Cada hueco tiene decisión (agregar pantalla, agregar requisito, justificar, posponer) y responsable? | ✔ | | | Los 7 huecos (H-01 a H-07) tienen decisión, responsable y fecha en la sección 5 de la matriz. |
| **F5** | ¿Los requisitos nuevos nacidos del inventario están escritos como propuestos, con criterio verificable? | | | ✔ | Ningún hueco de esta entrega generó un requisito **nuevo**: todos reservan pantalla para requisitos de alcance futuro ya identificados en `srs-SIGcortinas.md`. Si en la Actividad 2 o 3 surge uno genuinamente nuevo, se escribirá como propuesto con criterio verificable. |

## G. Mantenimiento

| Ítem | Pregunta | C | N | NA | Observación · responsable · fecha |
|---|---|---|---|---|---|
| **G1** | ¿La matriz y las fichas tienen versión, fecha y quién revisó (otro integrante)? | ✔ | | | v0.1 · 22/11/2026 · revisó otro integrante del equipo, distinto de los autores. |
| **G2** | ¿Los diagramas se guardaron como fuente editable (.puml) y como imagen? | | ✔ N | | Los diagramas de navegación son el entregable de la Actividad 2, todavía no construidos en esta entrega. |

## Resultado de la revisión

| Cumple | No cumple | No aplica | Decisión (aprobar, aprobar con observaciones, devolver) |
|---|---|---|---|
| 13 | 8 | 2 | **Aprobar con observaciones.** Las tres plantillas de inventario, trazabilidad y checklist están completas y sin celdas vacías sin explicar. Lo marcado "N" corresponde, en su mayoría, a trabajo explícitamente reservado para la **Actividad 2** (diagramas de navegación, ruta mínima, prueba de etiquetas) y la **Actividad 3** (cierre de huecos), no a un defecto de esta entrega. Antes de cerrar la Unidad 6, Sesión 2, deben resolverse: los diagramas .puml (D1, D2, G2), la ruta mínima contada (D3), la prueba de etiquetas adaptada a tres usuarios reales (C2, H-07) y los cinco huecos de requisitos de alcance futuro (F3, H-01 a H-06). |

*Guardada en `17-pantallas-navegacion/trazabilidad/lista-verificacion-pantallas.md`, con la fecha de revisión (22/11/2026), enlazada desde la descripción del Pull Request.*

---
