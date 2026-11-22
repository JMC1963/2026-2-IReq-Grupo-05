# Checklist de consistencia: caso de uso vs. secuencia

| Campo | Contenido |
|---|---|
| Revisor | Equipo SIGCortinas |
| Fecha · pasada | 21/11/2026 · primera |
| Caso de uso y versión | CU-09 v1.0 · CU-02 v1.0 |
| Diagramas revisados | DSE-01 v1.0 · DSE-02 v1.0 · DSE-03 v1.0 · DSE-04 v1.0 |

Cada «No» consta en la hoja de hallazgos. Los ítems E se completan en la segunda pasada, después del recorrido.

## A · Alcance y nivel del diagrama

| Ítem | Pregunta | Si falla… | DSE-01 | DSE-02 | DSE-03 | DSE-04 |
|---|---|---|---|---|---|---|
| A1 | Tiene título con su identificador (DSE-nn), el caso de uso, el escenario y el nivel (1 o 2). | No se puede trazar ni referenciar. | Sí | Sí | Sí | Sí |
| A2 | Los participantes son actores y sistemas del catálogo; en el nivel 1 el sistema es un único participante; en el nivel 2 hay seis componentes o menos, definidos en el glosario. | Participantes inventados; diseño interno. | Sí | Sí (2 componentes) | Sí | Sí (3 componentes) |
| A3 | No hay clases, controladores, tablas, colas, tecnologías ni pantallas. | Se mezcló el nivel 3 (diseño). | Sí | Sí | Sí | Sí |
| A4 | Cada participante se llama igual que en el catálogo de actores y en el glosario. | Se rompe la correspondencia con los otros modelos. | Sí | Sí | Sí | Sí |
| A5 | Tiene unos 25 mensajes o menos; si no, se dividió con ref. | Nadie lo lee; no se valida. | Sí (12) | Sí (20) | Sí (14) | Sí (23) |

## B · Notación

| Ítem | Pregunta | Si falla… | DSE-01 | DSE-02 | DSE-03 | DSE-04 |
|---|---|---|---|---|---|---|
| B1 | Cada mensaje síncrono tiene su retorno con nombre, o está marcado como asíncrono con una razón. | Retornos olvidados. | Sí | Sí | Sí (aviso asíncrono con nota) | Sí (aviso asíncrono con nota) |
| B2 | Los tipos de flecha son correctos y apuntan en el sentido correcto. | Se lee al revés quién espera a quién. | Sí | Sí | Sí | Sí |
| B3 | Los nombres son verbo + objeto del negocio, sin métodos, rutas ni gestos de pantalla. | Mensajes que son métodos de diseño. | Sí | Sí | Sí | Sí |
| B4 | Cada fragmento tiene una guarda en lenguaje del negocio, etiquetada con su extensión. | Fragmentos sin guarda. | Sí | Sí | Sí | Sí |
| B5 | Los alt cubren todas las ramas; el anidamiento tiene dos niveles o menos; break, opt y par tienen sentido. | El dibujo afirma lo contrario de lo que se quiso. | Sí | Sí | Sí | Sí |

## C · Consistencia con el caso de uso

| Ítem | Pregunta | Si falla… | DSE-01 | DSE-02 | DSE-03 | DSE-04 |
|---|---|---|---|---|---|---|
| C1 | Cada paso del flujo principal tiene mensaje o una razón escrita de por qué no. | Paso perdido. | Sí (paso 6 en ficha F-01) | Sí | Sí | Sí |
| C2 | El orden de los mensajes coincide con el de los pasos, o la diferencia está explicada. | Dos fuentes de verdad. | Sí | Sí | Sí | Sí |
| C3 | Cada extensión está dibujada o marcada «no dibujada» con su razón. | Excepciones sin tratar. | Sí (3a, 5a, 6a) | Sí (3a, 5a, 6a) | Sí (3a, 6a, 7a; 4a no dibujada) | Sí (3a, 6a, 7a; 4a no dibujada) |
| C4 | Cada fragmento corresponde a una extensión real; lo que el dibujo descubrió se registró como cambio al caso de uso. | Ramas inventadas o CU desactualizado. | Sí (H-01 a H-04) | Sí (H-01 a H-04) | Sí (H-01, H-05, H-06) | Sí (H-01, H-05, H-06) |
| C5 | Quien emite cada mensaje es quien actúa en el paso. | Responsabilidades cruzadas. | Sí | Sí | Sí | Sí |
| C6 | La garantía de éxito se ve en los últimos mensajes y la garantía mínima en las ramas de falla. | El diagrama no respeta la postcondición. | Sí | Sí | Sí | Sí |

## D · Datos, requisitos y trazabilidad

| Ítem | Pregunta | Si falla… | DSE-01 | DSE-02 | DSE-03 | DSE-04 |
|---|---|---|---|---|---|---|
| D1 | Los datos que viajan existen en el caso de uso, el glosario o un requisito. | Datos sin definir. | Sí | Sí | Sí | Sí |
| D2 | Todo mensaje está en la tabla de operaciones con al menos un requisito; los que no, constan como hueco. | Requisitos que faltan. | Sí (C-03) | Sí (C-03) | Sí (C-01, C-02) | Sí (C-01, C-02) |
| D3 | Una rama, un escenario: los criterios de aceptación cubren el camino feliz y cada rama dibujada. | Ramas que nadie comprobará. | Sí | Sí | No — R-01 | No — R-01 |
| D4 | Los requisitos de tiempo visibles están anotados en el diagrama con su punto de medición. | El escenario de tiempo queda invisible. | N/A: ningún requisito de tiempo en este escenario | N/A: ningún requisito de tiempo en este escenario | N/A: ningún requisito de tiempo en este escenario | N/A: ningún requisito de tiempo en este escenario |
| D5 | Cada mensaje a un sistema externo dice qué pasa si no responde, con tiempo, reintentos y riesgo de duplicado. | Falta política de falla. | N/A: no hay externos (D-03) | N/A: no hay externos (D-03) | N/A: no hay externos (D-03) | N/A: no hay externos (D-03) |
| D6 | Cada disparo por tiempo responde qué pasa si se repite o no ocurre. | Alertas duplicadas o perdidas. | N/A: sin disparo por tiempo (D-02) | N/A: sin disparo por tiempo (D-02) | N/A: sin disparo por tiempo (D-02) | N/A: sin disparo por tiempo (D-02) |

## E · Revisión (segunda pasada, después del recorrido)

| Ítem | Pregunta | Si falla… | DSE-01 | DSE-02 | DSE-03 | DSE-04 |
|---|---|---|---|---|---|---|
| E1 | Un interesado lo leyó en voz alta y el acta registra los hallazgos. | Validado solo por quien lo dibujó. | Ver `acta-recorrido-AAAA-MM-DD.md` | Ver `acta-recorrido-AAAA-MM-DD.md` | Ver `acta-recorrido-AAAA-MM-DD.md` | Ver `acta-recorrido-AAAA-MM-DD.md` |
| E2 | Otro integrante lo revisó contra el caso de uso, y el Área de TI revisó los mensajes con externos. | Ningún par lo vio. | Ver hoja de hallazgos; externos: N/A | Ver hoja de hallazgos; externos: N/A | Ver hoja de hallazgos; externos: N/A | Ver hoja de hallazgos; externos: N/A |

## Hoja de hallazgos

| N.º | Ítem | Diagrama | Qué se encontró | Dónde se corrige | Quién | Estado · aprobó |
|---|---|---|---|---|---|---|
| R-01 | D3 | DSE-03, DSE-04 | La extensión 7a de CU-02 (cancelar antes de confirmar) está dibujada pero no tiene escenario de aceptación `.feature`. | Caso de uso CU-02, sección 6: agregar `Cancelacion_agendamiento_visita.feature` | Equipo | Abierto |
