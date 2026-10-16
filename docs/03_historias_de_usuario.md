# Historias de usuario

Tablero: https://github.com/users/ciro-rdz/projects/1

Estados posibles: **Por Hacer**, **En Progreso**, **Listo**.

## HU-01 – Registrar movimientos de stock en el local

**Historia:** Como encargado de un local franquiciado, quiero registrar las ventas y los ingresos de mercadería indicando su lote, para que el stock de mi local se actualice en tiempo real.

**Prioridad:** Alta · **Estado:** Listo

**Criterios de aceptación:**
- Al registrar una venta o un ingreso, se actualiza cantidad_disponible en STOCK y se guarda un registro en MOVIMIENTO_STOCK con nro_lote y fecha_hora.
- El sistema no permite que cantidad_disponible quede en un valor negativo.
- La consulta del stock actualizado responde en 2 segundos o menos (percentil 95).

## HU-02 – Alerta de reposición por stock bajo

**Historia:** Como analista de Logística y Distribución de la casa central, quiero recibir una alerta cuando el stock de un producto en un local baje del mínimo, para planificar la reposición antes de que se produzca un quiebre de stock.

**Prioridad:** Alta · **Estado:** En Progreso

**Criterios de aceptación:**
- Se genera una alerta cuando cantidad_disponible es menor que stock_minimo.
- La alerta informa local, producto, cantidad disponible y stock mínimo.
- No se generan alertas duplicadas mientras la reposición del mismo producto y local siga pendiente.

## HU-03 – Reporte consolidado de stock

**Historia:** Como miembro de la Dirección General, quiero ver un reporte consolidado del stock por local, ciudad y país, para decidir la producción y la distribución con datos actualizados.

**Prioridad:** Media · **Estado:** Por Hacer

**Criterios de aceptación:**
- El reporte permite filtrar por pais, ciudad y tipo_local (PROPIO o FRANQUICIA).
- El reporte destaca los productos cuyo lote está próximo a la fecha_vencimiento.
- El reporte puede exportarse en formato CSV.

**Definición de Listo en esta etapa:** especificación, criterios de aceptación y modelo de datos documentados y revisados mediante Pull Request.
