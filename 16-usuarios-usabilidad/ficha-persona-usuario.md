**PLANTILLA PARA DILIGENCIAR · UNIDAD 6 · SESIÓN 1 DE 5**

**Ingeniería de Requisitos**

**Ficha de persona, escenario y puntos de dolor — SIGCortinas**

> **Nota de alcance y uso de IA.** Tampoco hay ID en `Indice_trazabilidad.md` para la Unidad 6 (el índice solo llega a la Unidad 4). Se diligencia con el nombre de archivo de la guía (`16-usuarios-usabilidad/personas/`). Se construyeron **dos personas**, no tres: solo hay evidencia real suficiente para la Empleada (una entrevista completa) y, de forma mucho más débil, para la Gerente (kickoff y acta, sin entrevista individual). El Técnico no tiene ficha propia porque **no existe ninguna entrevista ni observación con él**; se deja como pendiente explícito (acción AM-01 de `10-mejora-adopcion/autoevaluacion-capacidad.md`) en vez de inventar una persona sin evidencia. Códigos de fuente usados: **E1** = entrevista a Milena Bermúdez, 28/09/2026 (`guia-entrevista-empleada-Milena-Bermudez.md`); **AT1** = acta del kick-off, 18/09/2026 (`Kick - off.md`) y `acta-constitucion.md`, 25/09/2026. No hay observación (O), queja/registro (Q) ni datos de uso (A) para SIGCortinas: el sistema todavía no existe y nadie ha hecho una visita de observación al local — se marca como limitación, no se inventa.

---

# Persona 1 de 2 — PER-01 (persona primaria)

## A. Ficha de persona

Código: **PER-01** Nombre ficticio y edad: **Marcela, 34 años** (nombre ficticio para proteger a Milena Bermúdez, la entrevistada real) Persona primaria: **☒ Sí ☐ No**

| | |
|---|---|
| **Quién es en una frase** | Empleada del local: confecciona, vende y atiende al cliente, lleva la agenda diaria de citas y apoya al Técnico en instalaciones y arreglos (E1). |
| **Metas y tareas (F-nn)** | Registrar el pedido de un cliente sin perder ningún dato (F-01, CU-01N) y agendar una visita de medición o instalación sin que se cruce con otra cita del Técnico (F-02, CU-02). |
| **Contexto de uso** | Atiende de 9 am a 6 pm en el local (E1, hallazgo 1); se transporta en bus veredal/urbano y comentó que un accidente la afectaría (E1, pregunta 4); usa el sistema varias veces al día, entre coser, vender y atender. |
| **Habilidades y barreras** | Sin entrenamiento formal en sistemas de gestión; reparte su jornada entre varias tareas manuales, por lo que cualquier captura de datos compite con la atención al cliente en el mostrador (E1, hallazgo 1 y 9). No hay evidencia de ninguna discapacidad o barrera sensorial/motriz declarada. |
| **Frases literales (con código)** | **No se registró ninguna cita textual de Milena en la entrevista** (`guia-entrevista-empleada-Milena-Bermudez.md` solo reporta sus respuestas en discurso indirecto, p. ej. "Expresó que un sistema le facilitaría el trabajo, pero no en gran medida"). Esto es una limitación real del instrumento usado, no un dato faltante que se pueda rellenar: queda como pendiente para la próxima entrevista (responsable: Juan Miguel Chaparro, según `plan-adopcion-estandares.md` §9) pedir y transcribir al menos dos frases literales. |
| **Qué necesita del sistema** | Captura rápida y sencilla, sin entrenamiento previo, que no le quite tiempo de atención al cliente (E1, hallazgo 9); una sola agenda compartida con la Gerente y el Técnico, sin mantener una paralela (E1, hallazgo 2). |
| **Lo que esta persona NO es** | No representa al Técnico, que trabaja en campo y consulta desde el celular, no desde el mostrador (sin evidencia directa de él). Tampoco representa a la Gerente, que decide compras, inventario y garantías. No representa a un empleado con experiencia previa en sistemas de gestión: no hay evidencia de que Milena la tenga. |
| **Versión y fecha** | v1.0 · 22/11/2026 |

## B. Evidencia de cada dato

| Dato de la ficha | Fuente(s) con código | ¿Hecho, síntesis o supuesto? |
|---|---|---|
| Hace de todo: cose, vende, atiende; horario 9 am-6 pm | E1, hallazgo 1 (respuesta a pregunta de contexto 1) | Hecho |
| Trabaja con la Gerente y el Técnico; a veces ayuda al Técnico a instalar | E1, hallazgo 2 (respuesta a pregunta 2) | Hecho |
| Usa cuaderno, esfero y memoria; el celular no le ayuda para el trabajo | E1, hallazgo 9 (pregunta 4 y 23) | Hecho |
| Alguna vez se le olvida anotar un dato | E1, hallazgo 1 (síntesis de notas y hallazgos) | Síntesis |
| Se transporta en bus; un accidente la afectaría | E1, hallazgo 4 (pregunta 4) | Hecho |
| Un sistema le facilitaría el trabajo, pero no en gran medida | E1, hallazgo 9 (pregunta 3, discurso indirecto) | Hecho (reportado, no cita literal) |
| La Gerente y ella llevan agendas diferentes | E1, hallazgo 2 (pregunta 4) | Hecho |
| Sin barrera visual, motriz o auditiva declarada | — | **Supuesto por ausencia de evidencia**: nunca se le preguntó directamente; no se afirma que no exista, solo que no se elicitó. |

## C. Escenario de hoy

| | |
|---|---|
| **Persona y meta** | Marcela (Milena) quiere registrar el pedido de un cliente y agendarle la visita de instalación sin perder ningún dato ni cruzar el horario del Técnico. |
| **Contexto (lugar, aparato, tiempo, ayuda)** | Está en el mostrador del local, con el cuaderno y el esfero a la mano; un cliente espera mientras ella consulta su propia agenda (E1, hallazgo 1 y 2). |
| **Secuencia de acciones** | El cliente pide una instalación; Marcela anota a mano el nombre, el teléfono y las medidas; calcula de memoria la mitad del total como abono inicial (E1, hallazgo 6); aparta una fecha de su propio cuaderno de agenda para la visita, sin confirmar en ese momento si el Técnico ya tiene otro compromiso ese día, porque la Gerente lleva una agenda distinta a la suya (E1, hallazgo 2). |
| **Qué sale mal** | Alguna vez se le olvida anotar un dato del pedido (E1, hallazgo 1); al no compartir la agenda con la Gerente, puede confirmarle al cliente una fecha que después resulta cruzada con otra cita del Técnico, y eso solo se descubre cuando alguien reclama. |
| **Resultado y cómo lo reconoce** | Éxito: el pedido queda completo en el cuaderno, con todos los datos, y nadie llama después a reclamar un cruce de horario o un dato faltante. |

## D. Puntos de dolor y su salida

| DOL | Fuente | Punto de dolor | Salida | Requisito o criterio | Verificación prevista |
|---|---|---|---|---|---|
| **DOL-01** | E1, hallazgo 1 | "Alguna vez se le olvida anotar" un dato del pedido o de la cita. | **RF** | Ya cubierto: CU-01N (campos solicitados paso a paso) y REQ-F-04a ("SI la Empleada intenta guardar un pedido sin alguno de los campos obligatorios... deberá rechazar el registro e identificar cada campo faltante"). | Ya prevista en `srs-SIGcortinas.md`, Requisito 4: omitir cada campo por separado, 100% de rechazos. |
| **DOL-02** | E1, hallazgo 2 | "La Gerente y ella llevan agendas diferentes." | **RF** | Ya cubierto: HU-02 y CU-02 (agenda única y compartida, paso 8: "la publica en la agenda compartida"). | Ya prevista en `HU-02.md`, Escenario 1: insertar una cita desde la Gerente y otra desde la Empleada, ambas visibles para las dos. |
| **DOL-03** | E1, hallazgo 9 | "El celular no le ayuda para el trabajo"; sus herramientas son "cuaderno, esfero y memoria"; "un sistema le facilitaría el trabajo, pero no en gran medida". | **RNF** (capacidad de interacción) | REQ-NF-04 (ya en `09-calidad/catalogo-rnf.md`) + REQ-NF-07.1, redactado con la fórmula de seis partes en esta sesión (ver `requisitos-usabilidad-accesibilidad.md`, tabla A). | Prueba de usabilidad con cronómetro, Unidad 6, Sesión 5. |
| **DOL-04** | E1, duda pendiente 5 ("¿Usa Excel además del cuaderno? La Gerente dijo que el Excel solo sirve para sumar y no tiene buscador") | No hay forma rápida de "buscar" algo; solo de sumar en el Excel. | **PEN** | Pregunta abierta: ¿qué tan rápido necesita la Empleada encontrar un dato, comparado con hoy, si hoy ni siquiera hay buscador? Se relaciona con REQ-NF-01 y REQ-NF-07.3 (ver tabla A), pero el umbral exacto sigue sin confirmar con la Gerente. | Dueño: Gerente y Empleada. Fecha por confirmar (sin fecha límite escrita todavía — brecha ya señalada en `autoevaluacion-capacidad.md`, indicador G2). |
| **DOL-05** | Inferido de `srs-SIGcortinas.md` §2.1 (el Técnico accede desde el navegador de su celular en campo) y de `CU-02.md`, extensión 4a (visitas en finca) — **no es evidencia directa del Técnico, es un supuesto** | El Técnico podría quedarse sin poder ver su agenda si la pantalla no se adapta a su celular o si la señal falla en una finca. | **RNF** (adaptabilidad) | REQ-NF-09, nuevo de esta sesión (ver tabla B de `requisitos-usabilidad-accesibilidad.md`). | Pruebas en dispositivos reales — pendiente de validar con el Técnico (acción AM-01 de `autoevaluacion-capacidad.md`, todavía sin cerrar). |

---

# Persona 2 de 2 — PER-02 (no primaria)

## A. Ficha de persona

Código: **PER-02** Nombre ficticio y edad: **Doña Esperanza, 48 años** (nombre ficticio; representa el rol de Vicky Beltrán, Gerente real del negocio) Persona primaria: **☐ Sí ☒ No**

| | |
|---|---|
| **Quién es en una frase** | Administra el negocio: decide compras, ventas, citas, instalaciones y garantías; asistió al kickoff y es la patrocinadora del proyecto (AT1). |
| **Metas y tareas (F-nn)** | Ver en un solo panel las actividades programadas del día sin perder ninguna (F-03, CU-03, HU-01); controlar las garantías enviadas a fábrica antes de que venza el plazo de 10-12 días (F-04, CU-09). |
| **Contexto de uso** | Trabaja en el mismo local que la Empleada y recibe al Técnico cuando pasa por el local; hoy usa un Excel que, según reporta Milena, "solo sirve para sumar y no tiene buscador" (E1, duda pendiente 5). |
| **Habilidades y barreras** | **Sin evidencia directa**: la Gerente no ha sido entrevistada individualmente (solo participó del kickoff, AT1). Se supone competencia básica con Excel, sin entrenamiento formal en sistemas de gestión — supuesto, no dato verificado. |
| **Frases literales (con código)** | **Ninguna.** No existe entrevista directa a la Gerente en el repositorio del proyecto; todo lo que se sabe de ella viene de `acta-constitucion.md`, de `plantilla-matriz-poder-interes.md` y de lo que Milena reporta de ella en E1. Esta es la brecha más grande de esta ficha (ver acción AM-01, prioridad Alta, en `autoevaluacion-capacidad.md`). |
| **Qué necesita del sistema** | Visibilidad inmediata de ventas, inventario y garantías (`plantilla-matriz-poder-interes.md`, fila Gerente: "quiere recordatorios y un sistema de apoyo"); encontrar una venta pasada o una existencia en menos de 1 minuto (`acta-constitucion.md`, Criterios de éxito — este sí es un dato con fuente firmada, aunque no sea una cita literal). |
| **Lo que esta persona NO es** | No representa a la Empleada, que opera el sistema todo el día en el mostrador. No representa al Técnico, que lo usaría en campo desde el celular. No es un promedio de "los dueños de negocios pequeños": es específicamente la situación de este negocio, con un solo local y tres roles. |
| **Versión y fecha** | v1.0 · 22/11/2026 |

## B. Evidencia de cada dato

| Dato de la ficha | Fuente(s) con código | ¿Hecho, síntesis o supuesto? |
|---|---|---|
| Administra el negocio y decide compras, ventas, citas e instalaciones | AT1 (`plantilla-matriz-poder-interes.md`, fila Gerente); `acta-constitucion.md` §4 | Hecho |
| Criterio de éxito: encontrar una venta o existencia en menos de 1 minuto | `acta-constitucion.md`, Criterios de éxito | Hecho (firmado en el acta, no entrevista directa) |
| Usa un Excel que solo sirve para sumar, sin buscador | E1, duda pendiente 5 (reportado por Milena, no por la propia Gerente) | Síntesis de segunda mano — **no es un dato directo de la Gerente** |
| Sin barreras o habilidades tecnológicas documentadas | — | Supuesto por ausencia de evidencia |

## C. Escenario de hoy

> **No se construye un escenario completo para PER-02** porque no hay suficiente evidencia de primera mano (no hay entrevista ni observación de la Gerente trabajando). Escribir un escenario paso a paso sobre alguien a quien nunca se ha observado sería inventar, no documentar — la misma regla de evidencia que exige la guía para las personas aplica aquí con más fuerza para los escenarios. Se deja como pendiente: entrevistar a Vicky Beltrán (acción AM-01) antes de construir su escenario y su propio mapa de recorrido.

## D. Puntos de dolor y su salida

| DOL | Fuente | Punto de dolor | Salida | Requisito o criterio | Verificación prevista |
|---|---|---|---|---|---|
| **DOL-06** | `acta-constitucion.md`, Criterios de éxito; E1, duda pendiente 5 | No hay forma de buscar una venta pasada o una existencia rápido; solo un Excel que suma. | **RNF** | Ya cubierto: REQ-NF-01 del catálogo de calidad y REQ-NF-07.3 de esta sesión (ver tabla A). | Prueba de carga + muestreo de tiempos reales durante el piloto. |

---
