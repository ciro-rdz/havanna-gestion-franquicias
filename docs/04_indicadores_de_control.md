# Indicadores de control y estándares de desempeño

| ID | Indicador | Fórmula | Estándar | Fuente y frecuencia | Responsable |
|---|---|---|---|---|---|
| K1 | Tiempo de respuesta de consultas de stock | Percentil 95 del tiempo de respuesta, medido con pruebas de carga. | ≤ 2 s (Meta 1) | Pruebas de carga, en cada versión | Jefatura de Calidad (QA) |
| K2 | Capacidad de la plataforma | Cantidad de locales y SKU soportados sin degradación. | ≥ 500 locales y 10.000 SKU (Meta 2) | Pruebas de escalabilidad, antes de la puesta en marcha | Jefatura de Infraestructura y Soporte |
| K3 | Reducción del tiempo de conciliación | (Tiempo manual − tiempo con sistema) / tiempo manual. | ≥ 30 % a los 6 meses (Meta 3) | Comparación de registros, mensual | Gerencia de Sistemas |
| K4 | Cumplimiento del cronograma | (Semanas reales − semanas planificadas) / semanas planificadas. | Desvío ≤ 10 % (Meta 4) | Diagrama de Gantt y tablero, semanal | Oficina de Proyectos (PMO) |
| K5 | Exactitud de inventario | Registros de stock que coinciden con el conteo físico / registros contados. | ≥ 98 % (propuesto) | Conteo físico por muestreo, mensual | Jefatura de Calidad (QA) |
| K6 | Disponibilidad del sistema | Tiempo en servicio / tiempo total del mes. | ≥ 99,5 % (propuesto) | Monitoreo, mensual | Jefatura de Infraestructura y Soporte |
| K7 | Trazabilidad por lote | Movimientos de ingreso con nro_lote / total de movimientos de ingreso. | 100 % | Consulta a MOVIMIENTO_STOCK, mensual | Jefatura de Calidad (QA) |
| K8 | Historias de usuario controladas | Historias con criterios de aceptación y tarjeta en el tablero / total de historias. | 100 % | Tablero GitHub Projects, por iteración | Oficina de Proyectos (PMO) |
| K9 | Cambios integrados con revisión | Pull Requests fusionados con al menos 1 revisión / total de Pull Requests fusionados. | 100 % | Historial del repositorio, por iteración | Jefatura de Desarrollo |

Los estándares K1 a K4 provienen de las metas de la Entrega N.° 2. Los estándares de K5 y K6 son propuestos y deben validarse con la organización.
