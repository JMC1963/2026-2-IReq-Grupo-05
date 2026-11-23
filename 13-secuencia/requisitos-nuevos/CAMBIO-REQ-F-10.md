# CAMBIO-REQ-F-10 · Registrar garantía y calcular plazo

| Campo | Contenido |
|---|---|
| Requisito | REQ-F-10 |
| Fecha · responsable | 21/11/2026 · Equipo SIGCortinas |
| Origen del cambio | DSE-01 y DSE-02: las ramas 3a, 5a y 6a de CU-09 tienen mensajes (OS-02, OS-03, OS-09) sin requisito que las respalde. |

## Antes
Enunciado en la matriz: «Registrar garantía y calcular plazo».

## Después
CUANDO la Gerente confirme el registro de una garantía, SIGCortinas deberá crear la garantía en estado «En fábrica» con pedido, artículo, motivo, fecha de envío y referencia del caso, y calcular los días transcurridos desde la fecha de envío; SI el pedido no está registrado, ENTONCES deberá permitir ingresar los datos mínimos del cliente y del artículo; SI la fecha de envío es posterior a la fecha actual o el artículo ya tiene una garantía abierta, ENTONCES deberá rechazar el registro y mostrar la causa.

## Criterio de ajuste añadido
Con un artículo sin garantía abierta: registrar una garantía con fecha de ayer (se crea, 1 día transcurrido), con fecha de mañana (se rechaza) y repetir el registro del mismo artículo (se rechaza y se muestra la garantía existente). Resultado esperado: 3/3 correctos. Con un pedido no registrado, se permite ingresar los datos mínimos y se crea la garantía.

## Efecto
Se cubre la cobertura parcial C-05 de `operaciones-sistema.md`; OS-02, OS-03 y OS-09 quedan con cobertura completa.
