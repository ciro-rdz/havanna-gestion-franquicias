# Diccionario de datos inicial

Entidades críticas del módulo de Gestión de Franquicias y Trazabilidad de Stock. Los tipos de dato son genéricos y deben ajustarse al motor de base de datos elegido.

## PUNTO_VENTA
Local propio o franquiciado que integra la red de Havanna.

| Campo | Tipo de dato | Descripción funcional |
|---|---|---|
| id_punto_venta (PK) | Integer | Identificador único e interno del local. |
| nombre | String (100) | Denominación comercial del local o franquicia. |
| tipo_local | String (10) | Clasifica el local: PROPIO o FRANQUICIA. |
| pais | String (50) | País de operación; permite consolidar reportes por país. |
| ciudad | String (80) | Localidad donde funciona el punto de venta. |
| fecha_alta | Date | Fecha de incorporación del local a la red. |
| activo | Boolean | Indica si el local opera actualmente. |

## PRODUCTO
Artículo comercializable, identificado por su SKU.

| Campo | Tipo de dato | Descripción funcional |
|---|---|---|
| id_producto (PK) | Integer | Identificador único e interno del producto. |
| sku | String (20) | Código comercial único. |
| nombre_producto | String (100) | Nombre del producto. |
| categoria | String (50) | Rubro: alfajores, chocolates, galletitas, dulce de leche, cafetería. |
| precio_lista | Decimal (10,2) | Precio de lista vigente, usado para la facturación a locales. |
| vida_util_dias | Integer | Días de vida útil desde la elaboración. |
| activo | Boolean | Indica si el producto está vigente en el catálogo. |

## STOCK
Inventario vigente de un producto en un punto de venta. Existe un único registro por cada combinación (id_punto_venta, id_producto).

**Restricción de unicidad:** `UNIQUE (id_punto_venta, id_producto)`, para evitar registros de stock duplicados.

| Campo | Tipo de dato | Descripción funcional |
|---|---|---|
| id_stock (PK) | Integer | Identificador único del registro de inventario. |
| id_punto_venta (FK) | Integer | Referencia a PUNTO_VENTA. |
| id_producto (FK) | Integer | Referencia a PRODUCTO. |
| cantidad_disponible | Integer | Unidades disponibles; no puede ser negativa. |
| stock_minimo | Integer | Umbral que dispara una alerta de reposición. |
| fecha_actualizacion | DateTime | Momento de la última modificación. |

## MOVIMIENTO_STOCK
Registro histórico de cada ingreso, venta, ajuste o merma; da soporte a la trazabilidad por lote.

| Campo | Tipo de dato | Descripción funcional |
|---|---|---|
| id_movimiento (PK) | Integer | Identificador único del movimiento. |
| id_punto_venta (FK) | Integer | Referencia a PUNTO_VENTA. |
| id_producto (FK) | Integer | Referencia a PRODUCTO. |
| tipo_movimiento | String (15) | INGRESO, VENTA, AJUSTE o MERMA. |
| cantidad | Integer | Unidades involucradas en el movimiento. |
| nro_lote | String (30) | Lote de producción de origen. |
| fecha_vencimiento | Date | Vencimiento del lote. |
| fecha_hora | DateTime | Instante en que se registró el movimiento. |

## Relaciones
- PUNTO_VENTA 1:N STOCK y PRODUCTO 1:N STOCK.
- PUNTO_VENTA 1:N MOVIMIENTO_STOCK y PRODUCTO 1:N MOVIMIENTO_STOCK.
