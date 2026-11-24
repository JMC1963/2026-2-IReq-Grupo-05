---
title: Guía de estilo mínima — SIGCortinas
project: SIGCortinas
version: 0.1
date: 2026-11-24
---

# Guía de estilo mínima — SIGCortinas

**Ingeniería de Requisitos · Unidad 6 · Sesión 3**

| Proyecto | Equipo | Versión | Fecha de elaboración | Revisión por par |
|---|---|---:|---|---|
| SIGCortinas | Miguel Antonio Gómez Guío, Edward Steven Rocha Torres, Juan Miguel Chaparro, Rafael Santiago Barriosnuevo Mongui | v0.1 | 24/11/2026 | Pendiente de revisión por otro integrante del equipo |

## Alcance y criterio de uso

Esta guía fija decisiones mínimas reutilizables para las pantallas internas de SIGCortinas: inicio de sesión, agenda, pedidos, visitas, inventario, historial y garantías. **No es un manual de marca ni un sistema de diseño completo.** Se mantiene la paleta CANON, la tipografía, las medidas y las razones de contraste descritas en la guía académica adjunta.

SIGCortinas no tiene portal público: lo usan Gerente, Empleada y Técnico. La Gerente y la Empleada trabajan principalmente desde navegador de escritorio en el local; el Técnico consulta la agenda desde el navegador de su celular. Por eso, la adaptación móvil se aplica especialmente a P-02 y a las funciones del Técnico. El ancho de 360 px es una referencia propuesta en REQ-NF-09, todavía pendiente de validación con el Técnico.

> **Estado de la guía:** borrador v0.1. Las decisiones de estilo están diligenciadas, pero no se afirma que hayan sido probadas en un prototipo o aprobadas por usuarios. La verificación con teclado, ampliación y dispositivos reales queda pendiente.

## 1. Tokens de color y contraste calculado

### 1.1 Tokens

| Token | Valor | Uso permitido | Par de contraste recomendado | Razón | ¿Cumple? · decisión |
|---|---|---|---|---:|---|
| `--color-primario` | `#1f5c8b` | Botón primario, enlaces y foco de selección cuando corresponda | `#ffffff` / `#1f5c8b` | 7,09:1 | Sí. Apto para texto normal, texto grande y componentes. |
| `--color-acento` | `#b8860b` | Solo decoración: barras, bordes y pequeños detalles gráficos | `#1a1a1a` / `#b8860b` | 5,35:1 | Sí con texto oscuro. No usar el acento como texto sobre blanco ni texto blanco sobre el acento para texto normal: ambos dan 3,25:1. |
| `--color-ok` | `#1b7a3c` | Texto e icono de éxito | `#ffffff` / `#1b7a3c` | 5,39:1 | Sí. Mantener también etiqueta textual e icono. |
| `--color-error` | `#b3261e` | Texto e icono de error | `#ffffff` / `#b3261e` | 6,54:1 | Sí. No usar el color como único indicador. |
| `--color-texto` | `#1a1a1a` | Texto principal, títulos, etiquetas y texto sobre el acento | `#1a1a1a` / `#ffffff` | 17,40:1 | Sí. Par principal recomendado. |
| `--color-fondo` | `#ffffff` | Fondo principal de las pantallas | `#1a1a1a` / `#ffffff` | 17,40:1 | Sí, con texto principal oscuro. |
| `--color-fondo-suave` | `#f3f5f7` | Agrupaciones, paneles secundarios y filas alternas | `#1a1a1a` / `#f3f5f7` | 15,92:1 | Sí. |
| `--color-borde` | `#8a8f94` | Bordes de campos, separadores y límites de componentes | `#8a8f94` / `#ffffff` | 3,26:1 | Sí para componente gráfico (3:1); no usar como texto normal. |
| `--color-error-fondo` | `#fdecea` | Fondo suave de alertas de error | `#b3261e` / `#fdecea` | 5,72:1 | Sí. |
| `--color-ok-fondo` | `#e8f5ec` | Fondo suave de confirmaciones de éxito | `#1b7a3c` / `#e8f5ec` | 4,80:1 | Sí. |

### 1.2 Pares de contraste

Los valores corresponden a los pares de la paleta CANON reproducida en la guía adjunta. Se verifican contra el criterio indicado allí: 4,5:1 para texto normal y 3:1 para texto grande o componentes gráficos.

| Par (texto / fondo o componente / fondo) | Razón | Texto normal ≥ 4,5:1 | Texto grande o componente ≥ 3:1 | Decisión de uso |
|---|---:|---|---|---|
| `#1a1a1a` / `#ffffff` | 17,40:1 | Sí | Sí | Texto principal. |
| `#1a1a1a` / `#f3f5f7` | 15,92:1 | Sí | Sí | Texto en paneles suaves. |
| `#ffffff` / `#1f5c8b` | 7,09:1 | Sí | Sí | Texto de botones primarios. |
| `#b3261e` / `#ffffff` | 6,54:1 | Sí | Sí | Mensajes de error. |
| `#b3261e` / `#fdecea` | 5,72:1 | Sí | Sí | Mensajes de error sobre fondo de error. |
| `#1b7a3c` / `#ffffff` | 5,39:1 | Sí | Sí | Mensajes de éxito. |
| `#1b7a3c` / `#e8f5ec` | 4,80:1 | Sí | Sí | Mensajes de éxito sobre fondo suave. |
| `#b8860b` / `#ffffff` | 3,25:1 | No | Sí | No usar como texto normal; solo adorno o elemento grande. |
| `#ffffff` / `#b8860b` | 3,25:1 | No | Sí | No usar texto blanco normal sobre el acento. |
| `#1a1a1a` / `#b8860b` | 5,35:1 | Sí | Sí | Cuando sea indispensable texto sobre el acento, usar texto oscuro. |
| `#8a8f94` / `#ffffff` | 3,26:1 | No | Sí | Borde de componente; no usar para texto. |

**Nota de verificación:** la guía adjunta incluye los resultados de la paleta CANON. El archivo `herramientas/contraste.js` no está incluido en el ZIP del proyecto, por lo que no se afirma que ese script se haya ejecutado. Los valores de la tabla se contrastaron con la fórmula de luminancia relativa descrita en la guía; para la entrega técnica final debe ejecutarse también el script oficial de la sesión cuando esté disponible.

## 2. Tipografía, espaciado y tamaños

| Elemento | Regla | Razón / aplicación |
|---|---|---|
| Familia | `system-ui, -apple-system, "Segoe UI", Roboto, sans-serif` | Fuente de sistema, sin depender de una fuente externa. |
| Tamaño base | 16 px | Texto principal de formularios, agendas y detalles. |
| Títulos | H1: 28 px; H2: 22 px | Jerarquía clara entre nombre de pantalla y secciones. |
| Ayudas y pies | Mínimo 14 px | No reducir más el texto auxiliar; debe seguir siendo legible. |
| Interlínea | 1,5 para texto corrido; 1,25 para títulos | Regla de composición propuesta para facilitar lectura; validar en prototipo. |
| Escala de espaciado | 4, 8, 12, 16, 24 y 32 px | Múltiplos de 4 px; usar la escala y evitar valores arbitrarios. |
| Radio de borde | 6 px | Campos, botones y paneles sencillos. |
| Alto de control | 44 px como mínimo para botones y controles de acción | Se adopta como regla consistente también para la vista móvil del Técnico. El valor de 44 px aparece en la guía para el portal público; SIGCortinas no tiene portal público, por lo que su aplicación a las pantallas internas es una decisión de diseño que debe confirmar el equipo. |
| Foco visible | Anillo de 3 px, sólido, color `#1a1a1a` | Debe distinguirse sobre los fondos y no eliminarse por razones estéticas. |
| Ampliación | Mantener contenido y funciones al ampliar texto hasta 200 % | Pendiente de formalizar como criterio y verificar en el prototipo; identificado como brecha en `requisitos-usabilidad-accesibilidad.md`, punto 3. |

## 3. Componentes

| Componente | Cómo se construye | Estados que tiene | Cuándo se usa |
|---|---|---|---|
| **Botón primario** | Fondo `#1f5c8b`, texto blanco, etiqueta con verbo + objeto, alto mínimo definido en esta guía. | Normal, foco visible, presionado, deshabilitado y cargando. | Una acción primaria por pantalla: «Confirmar pedido», «Agendar visita», «Buscar». |
| **Botón secundario / enlace** | Menor peso visual que el primario; texto oscuro o azul primario, sin competir con la acción principal. | Normal, foco, visitado (si es enlace) y deshabilitado. | Navegación secundaria, volver al listado o abrir detalle. No usar «Sí/No» para confirmar acciones. |
| **Campo de texto / numérico** | Etiqueta visible encima; ayuda bajo el campo si aplica; unidad o formato explícito cuando se conozca. La marca de obligatorio se explica. | Normal, foco, error con icono y texto, deshabilitado. | Nombre, teléfono, medidas, valor total, abono, observaciones y criterios de búsqueda. No fijar máscaras o longitudes que el SRS no haya definido. |
| **Lista desplegable** | Etiqueta visible, opciones con nombres comprensibles; selección de una sola opción. | Cerrada, abierta, foco, seleccionada, error y deshabilitada. | Tipo de visita y selección del Técnico cuando corresponda. |
| **Tabla / bandeja de agenda** | Filas ordenadas por hora; columnas de cliente, tipo de visita, dirección, Técnico y estado; cada fila abre el detalle. | Cargando, con resultados, vacía, con alertas, error de servicio. | P-02 Agenda del día. La vista del Técnico se filtra a sus visitas. |
| **Insignia de estado** | Texto + símbolo + color; el color nunca es el único indicador. Ejemplos: «Por confirmar», «Plazo excedido», «Agotado». | Neutra, advertencia, error/plazo excedido y éxito, según estado. | Agenda, inventario y garantías. |
| **Banda de mensaje** | Icono, tipo, frase breve y acción correctiva cuando corresponda; errores de campo junto al campo. | Error, éxito, advertencia e información. | Validaciones, servicio no disponible, confirmación de operaciones y alertas. |
| **Resumen de pedido / visita** | Panel de solo lectura que agrupa los datos digitados antes de confirmar. | Normal, con datos incompletos resaltados y confirmado. | Revisión previa en P-03 y resumen de visita en P-04. |

## 4. Patrones de interfaz

### 4.1 Formulario «Nuevo pedido» (P-03)

1. Agrupar los datos en: cliente; producto o servicio y medidas; valor total y abono inicial.
2. Mantener una etiqueta visible por campo. Los campos obligatorios se determinan según el Apéndice B del SRS: nombre, teléfono, tipo de producto/servicio, valor total positivo, abono inicial y medidas/especificaciones.
3. Mostrar la ayuda del abono: «El abono inicial corresponde al 50 % del valor total, redondeado al peso superior». La regla del 50 % está pendiente de ratificación comercial (decisión D-02).
4. Antes de confirmar, mostrar el resumen del pedido.
5. Si faltan campos o el abono no coincide, señalar cada problema en texto y conservar lo digitado. La conservación durante una caída del servicio debe formalizarse como criterio de interfaz antes de desarrollo.
6. Una sola acción primaria: «Confirmar pedido».

### 4.2 Formulario «Agendar visita» (P-04)

1. Mostrar cliente y dirección, tipo de visita, fecha y hora, Técnico asignado y observaciones del trabajo.
2. Mostrar la duración estimada calculada según el tipo de visita. Para visitas a finca, el SRS establece 4 u 8 horas según la distancia; el límite exacto de 30 minutos necesita aclaración.
3. Comprobar la disponibilidad del Técnico antes de confirmar. Si hay cruce, mostrar franjas libres de igual duración dentro de los próximos siete días o informar que no existen.
4. La acción primaria es «Confirmar agendamiento».
5. Al confirmar, la cita se actualiza en la agenda compartida y se genera M-01. La política de reintento del correo queda pendiente; el correo no es la única fuente de verdad.

### 4.3 Agenda del día (P-02)

1. Mostrar fecha actual y actividades ordenadas por hora.
2. Presentar cliente, tipo de visita, dirección, Técnico y estado.
3. Marcar citas «Por confirmar» y garantías «Plazo excedido» con texto y símbolo, no solo color.
4. Para la Gerente y la Empleada, presentar la vista completa; para el Técnico, filtrar sus propias visitas.
5. Si no hay actividades, indicar que la agenda está vacía y mostrar la fecha de la próxima cita, según CU-03, extensión 2a.
6. Si el servicio no puede actualizar la agenda, mostrar una alerta explícita y no presentar datos antiguos como si fueran actuales.

### 4.4 Detalle de visita (P-05)

Al abrir una actividad, mostrar los datos de la cita y las acciones permitidas por rol. Reprogramar o cancelar actualiza la agenda, registra el motivo y genera M-02. Se rechaza una nueva fecha anterior al momento actual o que se cruce con otra cita del mismo Técnico.

## 5. Contenido y patrones de mensaje

- Idioma: español.
- Tono: respetuoso, directo y neutral; usar «usted» cuando el texto se dirija a la persona.
- Frases cortas y voz activa. Evitar jerga técnica, códigos de error y frases que culpen a quien usa el sistema.
- Etiquetas: sustantivos («Teléfono», «Fecha de visita», «Valor total»).
- Botones: verbo + objeto («Confirmar pedido», «Agendar visita», «Abrir detalle»).
- Error: qué pasó + cómo corregirlo + ejemplo si ayuda. El mensaje aparece junto al campo o en un resumen que enlaza al campo.
- Éxito: qué se hizo y qué sigue, sin afirmar que se envió un correo hasta tener confirmación del envío.
- Advertencia: explica la consecuencia o el estado pendiente («Por confirmar», «Plazo excedido»).
- Los términos del dominio se mantienen: «pedido», «visita»/«cita» (queda pendiente elegir uno como término preferido), «abono», «Técnico», «agenda compartida» y «garantía».
- Fechas y horas: formato visible propuesto `dd/mm/aaaa` y 24 horas (`09:30`); se debe validar con el equipo antes de congelar el formato.

## 6. Lista de verificación de diseño y accesibilidad

| Verificación | Decisión de diseño | Estado real |
|---|---|---|
| La acción primaria es una sola por pantalla y se llama con verbo + objeto. | Una primaria para P-02, P-03 y P-04; por ejemplo, «Confirmar pedido». | Definido en esta guía; pendiente verificar en HTML/prototipo. |
| Cada campo tiene etiqueta visible encima y se indica si es obligatorio u opcional. | Etiqueta visible; en P-03 se consideran obligatorios los campos enumerados en Apéndice B. Para P-04 falta confirmar obligatoriedad campo por campo. | Parcial; P-04 pendiente. |
| Los textos cumplen 4,5:1 y ningún estado depende solo del color. | Pares aprobados en la sección 1; usar texto + símbolo en estados. | Contraste de tokens calculado; falta inspección de todos los componentes del prototipo. |
| Los objetivos de acción tienen al menos 44 px de alto. | Adoptado como regla de diseño interna; revisar alcance para desktop y móvil. | Definido como propuesta; pendiente prueba de tamaño. |
| Se recorre solo con teclado en orden lógico y el foco se ve. | Orden DOM igual al visual; Tab / Shift+Tab / Enter / Espacio; foco de 3 px. | Definido; prueba de teclado pendiente. |
| Cada mensaje del catálogo corresponde a una regla o requisito. | Los mensajes sin requisito explícito se marcan `PROP-UI` y no se presentan como requisitos aprobados. | Parcial; falta formalizar `PROP-UI-01` y validar mensajes con los responsables. |
| La interfaz del Técnico funciona desde 360 px sin desplazamiento horizontal. | REQ-NF-09 propone 360 px para P-02 en móvil. | Pendiente validar con el Técnico y probar en dos celulares reales. No hay portal público. |
| Están descritos los estados inicial, vacío, cargando, error, error de servicio, éxito, sin permiso y sin conexión. | Se describen en las fichas P-02, P-03 y P-04. | Documentados; falta dibujar y probar cada estado. |
| Lo digitado se conserva cuando algo falla. | Se propone mantener el formulario en pantalla y evitar reenvíos ciegos. | Pendiente formalizar como criterio verificable, especialmente ante pérdida de conexión. |

**Marco de accesibilidad:** REQ-NF-08 fija WCAG 2.2 nivel AA como buena práctica voluntaria para las pantallas internas. El propio proyecto indica que el alcance legal exacto debe confirmarse con asesoría jurídica; esta guía no presenta WCAG ni la Resolución 1519/2020 como obligación legal de SIGCortinas.

## 7. Registro de cambios

| Versión | Fecha | Qué cambió y por qué | Quién |
|---|---|---|---|
| v0.1 | 24/11/2026 | Diligenciamiento inicial a partir de la guía de estilo de la Unidad 6 y los requisitos, inventario y matriz de pantallas de SIGCortinas. Se conserva la paleta CANON de la guía; se marcan como pendientes las decisiones no respaldadas por el SRS o no probadas con usuarios. | Equipo SIGCortinas |

## Fuentes del proyecto usadas

- `17-pantallas/ficha-inventario-pantalla.md` — alcance, roles, pantallas, mensajes M-01/M-02 y estados.
- `17-pantallas/matriz-trazabilidad-pantallas.md` — relación CU, pantallas, requisitos, prioridad y huecos.
- `7-srs/srs-sigcortinas.md` — requisitos REQ-F-01a/b/c, REQ-F-02/02a, REQ-F-03, REQ-F-04a/b, REQ-NF-01/02/03 y Apéndice B.
- `16-usuarios-usabilidad/contexto-uso-tareas.md` — contexto, tareas, frecuencia, criticidad y medidas.
- `16-usuarios-usabilidad/requisitos-usabilidad-accesibilidad.md` — REQ-NF-07.1/07.2/07.3, REQ-NF-08 y REQ-NF-09.
- `SIGCortinas-backlog-MoSCoW.md` — prioridades Must/Should/Could.
- Guía adjunta, sección 7 y secciones 5–6 — tokens, componentes, patrones, microcopy, contraste y accesibilidad.
