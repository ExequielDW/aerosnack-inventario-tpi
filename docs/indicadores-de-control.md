# Indicadores de control y estándares de desempeño

La etapa de **Control** del proceso administrativo consiste en establecer estándares, medir, comparar y aplicar acciones correctivas.
Este documento reúne los estándares de desempeño del sistema, tomados de las metas de la Entrega 2, y los estándares de auditoría
del proceso de trabajo y del repositorio.

## 1. Estándares de desempeño del sistema (metas de la Entrega 2)

Basados en las características de eficiencia de desempeño de la norma ISO/IEC 25010 (comportamiento temporal y capacidad).

| Meta | Aspecto | Estándar (valor objetivo) | Cómo se mide | Verificación en el Gantt | Responsable |
|---|---|---|---|---|---|
| M1 | Tiempo de respuesta | ≥ 95 % de las consultas de stock y trazabilidad en ≤ 2 s, con 20 usuarios concurrentes | Pruebas de carga con datos simulados | P3 (S15) | R2 |
| M2 | Escalabilidad de registros | ≥ 500.000 movimientos y 20.000 lotes sin superar el tiempo de M1 | Carga masiva de datos simulados y repetición de M1 | P3 (S15) | R2 |
| M3 | Trazabilidad | Reconstrucción de un lote (insumos, cocción, despacho) en ≤ 30 s para el 100 % de los lotes | Consulta de trazabilidad sobre todos los lotes de prueba | P4 (S15-S16) | R1 |
| M4 | Alertas de reposición | Alerta y orden sugerida en ≤ 60 s desde que el stock cae bajo el mínimo, en el 100 % de los casos de prueba | Casos de prueba que provocan stock bajo el mínimo y miden el tiempo | P2 (S13-S14) | R3 y R2 |
| M5 | Calidad del software | ≥ 90 % de casos críticos aprobados y 0 defectos críticos abiertos antes de la puesta en marcha | Registro de casos de prueba y defectos | P2 y P4 (S13-S16) | R3 |
| M6 | Plazo | Módulo en producción al final de S17, con desvío máximo de 1 semana sobre la línea base | Comparación del avance real contra el Gantt | I3 (S17) e I4 (S18) | R1 |

Los valores son parámetros de diseño del grupo y se recalibran con los usuarios en la validación de requerimientos (tareas A1 y A2) antes de
aprobarse en el hito H1.

## 2. Indicadores del proceso de reposición (propuestos)

Derivados del [modelo BPMN](bpmn/README.md). Los valores objetivo son **propuestos** y deben validarse en el hito H1, igual que las metas.

| ID | Indicador | Fórmula | Valor objetivo propuesto | Fuente de datos |
|---|---|---|---|---|
| IP-1 | Cobertura de stock | Insumos con `stock_actual` ≥ `stock_minimo` ÷ insumos activos | ≥ 98 % | `INSUMO` |
| IP-2 | Entregas conformes | Entregas aceptadas en la inspección ÷ entregas recibidas | ≥ 95 % | `MOVIMIENTO_STOCK`, `ORDEN_COMPRA` |
| IP-3 | Órdenes sugeridas aprobadas | Órdenes aprobadas sin cancelar ÷ órdenes sugeridas | A calibrar con la primera medición | `ORDEN_COMPRA` |

## 3. Comparación y acciones correctivas

En cada hito de control (H1 a H5), R1 compara lo real con lo planificado. Si un indicador no alcanza su estándar, se aplica la acción correctiva:

| Desvío | Acción correctiva |
|---|---|
| M1 o M2 fuera del estándar | Optimizar consultas e índices de la base de datos y repetir la prueba de carga (P3) |
| M3 fuera del estándar | Revisar las relaciones `LOTE_PRODUCCION` – `MOVIMIENTO_STOCK` y los índices por `codigo_lote` |
| M4 fuera del estándar | Revisar la detección del umbral y la generación automática de la orden |
| M5 fuera del estándar | Posponer la puesta en marcha y reasignar esfuerzo a pruebas en las tareas con holgura |
| M6 con desvío mayor a 1 semana | Replanificar con las tareas con holgura (D3, D4, P1, P3, I2) y acotar el alcance |
| IP-1, IP-2 o IP-3 bajo el estándar | Revisar umbrales de `stock_minimo` y la gestión con proveedores |

## 4. Estándares de auditoría del repositorio y el trabajo colaborativo

| ID | Estándar | Cómo se verifica |
|---|---|---|
| AU-1 | Todo cambio llega a `main` mediante Pull Request, sin commits directos tras la configuración inicial | Historial de `main` |
| AU-2 | Cada Pull Request tiene al menos una revisión de otro integrante | Pestaña *Pull requests* |
| AU-3 | El 100 % de los commits sigue Conventional Commits | `git log --oneline` |
| AU-4 | Cada rama secundaria corresponde a una tarea del tablero | Ramas e issues vinculados |
| AU-5 | Las tres historias de usuario están vinculadas a issues con estado actualizado | Tablero de GitHub Projects |
| AU-6 | El README incluye la Declaración de Uso de IA actualizada | [README](../README.md) |
