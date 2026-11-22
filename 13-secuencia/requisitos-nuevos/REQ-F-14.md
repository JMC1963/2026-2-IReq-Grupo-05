# REQ-F-14 · Registrar cliente nuevo al agendar una visita

| Campo | Contenido |
|---|---|
| Identificador y versión | REQ-F-14 · v1.0 |
| Tipo | Funcional |
| Estado | Propuesto |
| Fecha · responsable | 21/11/2026 · Equipo SIGCortinas |
| Diagramas de origen | DSE-03, DSE-04 |

## 1. Descripción
CUANDO la Empleada envíe un teléfono que no corresponde a ningún cliente registrado, SIGCortinas deberá solicitar el nombre y la dirección y registrar al cliente antes de continuar con el agendamiento de la visita.

## 2. Justificación
El cliente debe quedar registrado para vincularle la cita, la dirección de la visita y su historial futuro.

## 3. Origen
`CU-02.docx`, extensión 3a; DSE-03 y DSE-04 (OS-10).

## 4. Criterio de ajuste
Agendar con un teléfono inexistente y completar nombre y dirección: la cita queda vinculada al cliente nuevo y, al buscar de nuevo ese teléfono, el cliente aparece con los mismos datos. Resultado esperado: 2/2 comprobaciones correctas. Si la Empleada cancela antes de confirmar, el cliente no queda registrado.

## 5. Satisfacción del cliente (1-5)
4: no hay que registrar al cliente aparte.

## 6. Insatisfacción del cliente (1-5)
3: se agenda con datos incompletos.

## 7. Conflictos
REQ-NF-03: el cliente nuevo se guarda solo si la cita se confirma.

## 8. Prioridad
Must — heredada de CU-02.
