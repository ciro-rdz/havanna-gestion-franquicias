# Proceso de negocio: reposición de stock en locales y franquicias

![BPMN](bpmn_reposicion_de_stock.png)

## Participantes
| Pool | Carril | Tipo |
|---|---|---|
| Franquicia | Encargado de local | Actor humano |
| Havanna S.A. – Casa Central | Sistema de Gestión de Stock | Automatizado |
| Havanna S.A. – Casa Central | Logística y Distribución | Actor humano |
| Havanna S.A. – Casa Central | Facturación | Automatizado / actor humano |

## Flujo estándar
1. El encargado del local registra una venta o el ingreso de mercadería con su lote.
2. El sistema recibe el movimiento y actualiza el stock.
3. Si el stock queda bajo el mínimo, el sistema genera una alerta de reposición.
4. Logística evalúa la alerta y prepara el pedido.
5. Si hay stock en planta, despacha el pedido y emite el remito.
6. El local recibe la mercadería y registra el ingreso con su lote.
7. El sistema emite la factura al local.

## Excepciones (compuertas)
- **¿Stock bajo el mínimo?** Si no lo está, el proceso termina sin alerta.
- **¿Hay stock en planta?** Si no hay, Logística notifica la demora y reprograma, y el local recibe el aviso.
