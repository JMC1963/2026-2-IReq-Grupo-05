# REQ-NF-03 · Sin registros parciales ni duplicados

| Campo | Contenido |
|---|---|
| Identificador y versión | REQ-NF-03 · v1.0 |
| Tipo | No funcional (integridad de datos) |
| Estado | Propuesto |
| Fecha · responsable | 21/11/2026 · Equipo SIGCortinas |
| Diagramas de origen | DSE-01, DSE-02, DSE-03, DSE-04 |

## 1. Descripción
SI una operación de registro (cita, garantía) se cancela o no se confirma, ENTONCES SIGCortinas deberá conservar los datos existentes sin crear ningún registro parcial; y CUANDO reciba una segunda confirmación de la misma operación, deberá mostrar el registro ya creado sin duplicarlo.

## 2. Justificación
La garantía mínima de los casos de uso exige que un fallo o una cancelación no deje citas ni garantías a medias, y una doble confirmación no debe generar cruces falsos ni garantías repetidas.

## 3. Origen
Garantía mínima de `CU-02.docx` y `CU-09.docx`; ext. 7a de CU-02; decisión D-04; DSE-01 a DSE-04.

## 4. Criterio de ajuste
Cancelar el agendamiento antes de confirmar: 0 citas nuevas y 0 clientes nuevos. Cerrar el registro de una garantía sin confirmar: 0 garantías nuevas. Confirmar dos veces la misma cita: 1 cita en la agenda. Confirmar dos veces la misma garantía: 1 garantía. Resultado esperado: 4/4 comprobaciones correctas.

## 5. Satisfacción del cliente (1-5)
4: confía en los datos.

## 6. Insatisfacción del cliente (1-5)
5: datos duplicados o incompletos dañan la agenda y el control de garantías.

## 7. Conflictos
Ninguno identificado con los requisitos vigentes.

## 8. Prioridad
Must — transversal a CU-02 y CU-09.
