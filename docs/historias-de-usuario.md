# Historias de usuario

Backlog funcional del **Módulo de Gestión de Inventario y Trazabilidad de Stock** de AeroSnack S.A.
Cada historia está vinculada a un issue del tablero de GitHub Projects y a una meta cuantitativa de la Entrega 2.

| ID | Historia | Meta | Entidades (Entrega 3) | Estado al cierre de la Entrega 4 |
|---|---|---|---|---|
| HU-01 | Stock en tiempo real por lote | M1, M2 | `INSUMO`, `MOVIMIENTO_STOCK`, `LOTE_PRODUCCION` | En Progreso |
| HU-02 | Orden de compra sugerida | M4 | `INSUMO`, `ORDEN_COMPRA`, `PROVEEDOR` | En Progreso |
| HU-03 | Trazabilidad de un lote | M3 | `LOTE_PRODUCCION`, `MOVIMIENTO_STOCK`, `PRODUCTO` | Por Hacer |

> Las historias se encuentran **En Progreso** o **Por Hacer** porque a la fecha de esta entrega están completos el análisis, el diseño
> de datos y el modelado del proceso, pero el módulo todavía no está codificado (fases de Codificación y Pruebas del Gantt de la Entrega 2).

---

## HU-01: Stock en tiempo real por lote

**Como** encargado de Almacén e Inventario, **quiero** registrar cada ingreso, consumo y despacho de insumos y producto terminado,
**para** conocer el stock real por lote en tiempo real, sin control manual.

**Criterios de aceptación**

- Dado un ingreso de insumos recibido, cuando el encargado lo registra, entonces se crea un movimiento de ingreso vinculado a su orden de compra y aumenta `stock_actual`.
- Dado un consumo de insumos en producción, cuando se registra, entonces el movimiento queda asociado a `codigo_lote` y `stock_actual` disminuye.
- Dado un despacho de producto terminado, cuando se registra, entonces descuenta `cajas_disponibles` del lote.
- Al menos el 95 % de las consultas de stock se responde en 2 segundos o menos, con 20 usuarios concurrentes (**M1**).
- El sistema soporta 500.000 movimientos y 20.000 lotes sin superar ese tiempo (**M2**).

**Proceso BPMN relacionado:** registro de ingreso y actualización de stock ([ver modelado](bpmn/README.md)).
**Responsable funcional de los datos:** Almacén e Inventario.

---

## HU-02: Orden de compra sugerida

**Como** analista de Compras y Proveedores, **quiero** recibir una orden de compra sugerida cuando un insumo cae por debajo de su stock mínimo,
**para** reponer a tiempo y evitar quedarme sin insumos.

**Criterios de aceptación**

- Dado un insumo cuyo `stock_actual` queda por debajo de `stock_minimo`, cuando el sistema detecta el faltante, entonces emite una alerta y genera una orden con `es_automatica = true` y `estado = sugerida`.
- La alerta y la orden sugerida se generan en un máximo de 60 segundos, en el 100 % de los casos de prueba (**M4**).
- Compras puede aprobar o cancelar la orden sugerida, y el estado de la orden refleja la decisión.

**Proceso BPMN relacionado:** reposición de insumos, completo ([ver modelado](bpmn/README.md)).
**Responsable funcional de los datos:** Compras y Proveedores.

---

## HU-03: Trazabilidad de un lote

**Como** responsable de Calidad y Asuntos Regulatorios, **quiero** reconstruir el recorrido completo de un lote (insumos utilizados,
fecha y parámetros de cocción, y despachos), **para** ejecutar un retiro de producto con rapidez.

**Criterios de aceptación**

- Dado un `codigo_lote`, cuando el responsable consulta su trazabilidad, entonces obtiene los insumos consumidos, `fecha_coccion`, `temp_coccion`, `tiempo_coccion` y los despachos asociados.
- La reconstrucción se obtiene en un máximo de 30 segundos para el 100 % de los lotes registrados (**M3**).
- Ante un retiro de producto, el responsable puede actualizar el estado del lote a «retirado del mercado».

**Proceso BPMN relacionado:** ninguno de esta versión; se apoya en el modelo de datos de la Entrega 3.
**Responsable funcional de los datos:** Calidad y Asuntos Regulatorios (consulta) y Procesamiento y Cocción por Aire (lote).

---

## Definición de terminado (DoD)

Una historia pasa a **Listo** cuando:

1. Cumple todos sus criterios de aceptación.
2. Sus pruebas fueron aprobadas (casos críticos, ver M5).
3. Su Pull Request fue revisado por otro integrante y fusionado a `main`.
4. La documentación asociada está actualizada en el repositorio.
