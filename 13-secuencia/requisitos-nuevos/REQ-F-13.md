# REQ-F-13 · Aviso de cambios de cita al Técnico y a la Gerente

| Campo | Contenido |
|---|---|
| Identificador y versión | REQ-F-13 · v1.0 |
| Tipo | Funcional |
| Estado | Propuesto |
| Fecha · responsable | 21/11/2026 · Equipo SIGCortinas |
| Diagramas de origen | DSE-03, DSE-04 |

## 1. Descripción
CUANDO la Empleada confirme, reprograme o cancele una cita, SIGCortinas deberá registrar un aviso dirigido al Técnico asignado (y a la Gerente en reprogramaciones y cancelaciones) con cliente, tipo de visita, fecha, hora y dirección, y mostrarlo en el panel de cada destinatario al iniciar sesión.

## 2. Justificación
El Técnico se comunica de forma presencial con el local; el aviso en el panel evita que se desplace a una visita cambiada o que no sepa de una nueva.

## 3. Origen
`CU-02.docx`, paso 8; `CU-04.docx`, paso 8; acta de constitución §2 (notificación de cambios de agenda al Técnico); WinWin, opción 3; DSE-03 y DSE-04; decisión D-01.

## 4. Criterio de ajuste
Confirmar una cita para un Técnico e iniciar sesión como Técnico: aparece un aviso con cliente, tipo, fecha, hora y dirección. Reprogramar la cita: aparecen avisos nuevos para el Técnico y la Gerente. Cancelarla: ídem. Resultado esperado: 3/3 avisos presentes y con los datos correctos.

## 5. Satisfacción del cliente (1-5)
5: elimina la coordinación manual de cambios.

## 6. Insatisfacción del cliente (1-5)
4: el Técnico puede ir en vano.

## 7. Conflictos
REQ-F-01a y REQ-F-03 generan los cambios que originan el aviso. Falta el caso de uso donde el Técnico lee el aviso (H-06).

## 8. Prioridad
Must — heredada de CU-02 y CU-04.
