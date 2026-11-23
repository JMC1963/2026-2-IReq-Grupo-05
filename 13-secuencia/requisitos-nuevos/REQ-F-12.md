# REQ-F-12 · Alerta de garantía con plazo excedido

| Campo | Contenido |
|---|---|
| Identificador y versión | REQ-F-12 · v1.0 |
| Tipo | Funcional |
| Estado | Aprobado |
| Fecha · responsable | 21/11/2026 · Equipo SIGCortinas |
| Diagramas de origen | DSE-01, DSE-02 |

## 1. Descripción
MIENTRAS una garantía esté en estado «En fábrica», CUANDO la Gerente abra el panel principal, SI los días transcurridos desde la fecha de envío superan 12 días, ENTONCES SIGCortinas deberá mostrar una alerta con el artículo, el pedido y los días transcurridos de esa garantía.

## 2. Justificación
Sin la alerta, la Gerente debe revisar a mano cada garantía para saber cuál superó el plazo de la fábrica y se repite el descontrol que hoy ocurre con el cuaderno.

## 3. Origen
`03-especificaciones/casos-de-uso/CU-03.docx`, ext. 2c; `CU-09.docx`, paso 8; árbol KAOS, meta G3.2; DSE-01 y DSE-02 (retorno de OS-04 con el plazo de espera); decisión D-02 (se evalúa al abrir el panel).

## 4. Criterio de ajuste
Con una garantía «En fábrica» enviada hace 13 días y otra enviada hace 12, abrir el panel como Gerente: aparece alerta solo para la de 13 días, con su artículo, pedido y «13 días»; la de 12 días no aparece. Resultado esperado: 2/2 casos correctos. Se repite al día siguiente: la alerta del primer caso sigue y no se duplica.

## 5. Satisfacción del cliente (1-5)
4: la Gerente deja de buscar a mano garantías vencidas.

## 6. Insatisfacción del cliente (1-5)
4: se pierde el control del plazo de la fábrica y de la fecha que se le da al cliente.

## 7. Conflictos
REQ-F-02 comparte el panel principal: la alerta no debe ocultar las actividades del día. REQ-F-10 define la fecha de envío que usa el cálculo.

## 8. Prioridad
Must — heredada de CU-09 (Must en `SIGCortinas-backlog-MoSCoW`).
