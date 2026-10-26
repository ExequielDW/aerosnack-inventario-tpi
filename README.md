# AeroSnack S.A. · Módulo de Gestión de Inventario y Trazabilidad de Stock

**Trabajo Práctico Integrador y Progresivo (TPI)** · Organización Empresarial
Tecnicatura Universitaria en Programación a Distancia (TUP AD) · Universidad Tecnológica Nacional (UTN) · 2026

## Enlaces

| Recurso | Enlace |
|---|---|
| Repositorio público | https://github.com/ExequielDW/aerosnack-inventario-tpi |
| Tablero de gestión (GitHub Projects) | https://github.com/users/ExequielDW/projects/1 |

## Descripción del sistema

**AeroSnack S.A.** es una empresa ficticia que elabora y comercializa snacks de papa horneados por aire, con foco en la alimentación saludable
y los empaques sustentables. Hoy el área de almacén controla el stock de insumos y producto terminado de forma manual.

El **Módulo de Gestión de Inventario y Trazabilidad de Stock** digitaliza ese control. Sus funciones son:

- Registrar en tiempo real el stock de insumos y de producto terminado, por lote de producción.
- Generar alertas y órdenes de compra sugeridas cuando un insumo cae por debajo de su umbral mínimo.
- Dar trazabilidad por lote, vinculando cada caja despachada con sus insumos, su fecha de cocción y sus parámetros de proceso.
- Integrarse con los indicadores de rendimiento de materia prima y eficiencia energética del proceso productivo.

El módulo afecta de forma transversal a Compras, Producción, Comercialización, Finanzas y Calidad (enfoque sistémico, Entrega 1).

## Integrantes

| Integrante | Usuario de GitHub |
|---|---|
| Exequiel Martin Gonzalez Jofre | [@ExequielDW](https://github.com/ExequielDW) |
| Ana Laura del Valle | [@annalaradelvalle-web](https://github.com/annalaradelvalle-web) |

**Cátedra:** Prof. Gabriela Martínez (titular) · Docente tutor: Pablo García.

## Contenido del repositorio

| Ruta | Contenido |
|---|---|
| [`docs/entregas/`](docs/entregas) | Entregas 1 a 3 del TPI, en PDF |
| [`docs/bpmn/`](docs/bpmn) | Modelado BPMN del proceso de reposición de insumos |
| [`docs/historias-de-usuario.md`](docs/historias-de-usuario.md) | Las tres historias de usuario con criterios de aceptación |
| [`docs/indicadores-de-control.md`](docs/indicadores-de-control.md) | Indicadores de control y estándares de desempeño |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | Convenciones de ramas, commits y Pull Requests |

### Recorrido del TPI

| Entrega | Tema | Documento |
|---|---|---|
| 1 | La organización y su enfoque sistémico | [PDF](docs/entregas/entrega-1-organizacion-y-enfoque-sistemico.pdf) |
| 2 | Diagnóstico y planeación (FODA, objetivos y metas, Gantt) | [PDF](docs/entregas/entrega-2-diagnostico-y-planeacion.pdf) |
| 3 | Estructura formal y diseño de datos (organigrama, diccionario de datos) | [PDF](docs/entregas/entrega-3-estructura-formal-y-diseno-de-datos.pdf) |
| 4 | Procesos, trabajo colaborativo y control integrador | Este repositorio y el PDF final consolidado |

## Proceso modelado (BPMN)

![Diagrama BPMN de reposición de insumos](docs/bpmn/bpmn_reposicion_insumos.png)

Descripción completa, participantes y excepciones en [`docs/bpmn/README.md`](docs/bpmn/README.md).

## Backlog ágil

| ID | Historia de usuario |
|---|---|
| HU-01 | Como encargado de Almacén e Inventario, quiero registrar cada ingreso, consumo y despacho, para conocer el stock real por lote en tiempo real. |
| HU-02 | Como analista de Compras y Proveedores, quiero recibir una orden de compra sugerida cuando un insumo cae bajo su mínimo, para reponer a tiempo. |
| HU-03 | Como responsable de Calidad y Asuntos Regulatorios, quiero reconstruir el recorrido completo de un lote, para ejecutar un retiro de producto con rapidez. |

Seguimiento en el tablero de GitHub Projects (estados *Por Hacer*, *En Progreso* y *Listo*). Detalle en [`docs/historias-de-usuario.md`](docs/historias-de-usuario.md).

## Mecanismos de control

Los estándares de desempeño del sistema son las metas M1 a M6 de la Entrega 2 (tiempo de respuesta, escalabilidad, trazabilidad, alertas,
calidad y plazo). Se complementan con indicadores del proceso de reposición y con estándares de auditoría del repositorio.
Detalle en [`docs/indicadores-de-control.md`](docs/indicadores-de-control.md).

## Flujo de trabajo con Git

- `main` es la rama estable; los cambios entran por Pull Request desde ramas secundarias (`docs/…`, `feat/…`, `fix/…`).
- Commits en formato Conventional Commits, en español.
- Cada Pull Request requiere la revisión de otro integrante.

Las reglas completas están en [`CONTRIBUTING.md`](CONTRIBUTING.md).

