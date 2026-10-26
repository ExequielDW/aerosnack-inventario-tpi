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

---

## Declaración de Uso de IA

**Transparencia.** El grupo utilizó asistentes de inteligencia artificial generativa en la elaboración de este TPI.
La IA se usó como herramienta de apoyo; las decisiones de diseño, la verificación de la coherencia entre entregas y la responsabilidad
intelectual sobre el contenido son del grupo.

**Herramientas utilizadas**

- **Claude (Anthropic):** análisis de consignas y de coherencia entre entregas, borradores de documentación, generación del diagrama BPMN y plan de ejecución.
- **OpenCode** (agente de código) con el modelo GLM-5.3-Flash Free: ejecución de los comandos Git y GitHub descriptos en el plan.

### Prompts utilizados y control humano

| N.º | Prompt (resumen) | Por qué se formuló así | Resultado de la IA | Verificación y corrección humana |
|---|---|---|---|---|
| 1 | Se pidió leer las consignas de la Entrega 4 y la rúbrica adicional, y revisar las Entregas 1, 2 y 3 antes de resolver nada. | Evitar contradicciones con lo ya entregado y con los datos de AeroSnack S.A. | Un cruce entre entregas que detectó que las tres historias de usuario no estaban definidas en ninguna entrega, e inconsistencias de formato (nombre del tutor, numeración de figuras y tablas, un error de redacción en la Entrega 3). | La IA detectó inconsistencias entre las Entregas 1 a 3: el nombre del docente tutor figuraba con dos formatos distintos, las figuras y tablas repetían numeración entre entregas y había un error de redacción en la conclusión de la Entrega 3. Los PDF de este repositorio son las versiones tal como se presentaron; las correcciones se incorporan en el documento final consolidado. |
| 2 | Se presentaron dos procesos candidatos (reposición de insumos o retiro de producto) para el BPMN. | Elegir un proceso que el módulo automatice y que ya estuviera descripto en el flujo de datos de la Entrega 3. | Una propuesta de proceso con Pools, Lanes y compuertas de excepción. | El grupo decidió, entre dos procesos candidatos, modelar la reposición de insumos. |
| 3 | Se pidió generar el diagrama BPMN con la notación estándar. | Obtener un diagrama con Pools, Lanes y compuertas, alineado con el organigrama y el diccionario de datos. | Un diagrama generado mediante un script. | La IA propuso las Lanes y los estados de la orden a partir del organigrama de la Entrega 3 y del diccionario de datos. |
| 4 | Se informó que las historias de usuario no existían y se pidió una propuesta. | Que cada historia derive de una meta cuantitativa de la Entrega 2. | Tres historias en formato formal con criterios de aceptación. | La IA derivó cada historia de una meta cuantitativa de la Entrega 2 (HU-01 de M1 y M2, HU-02 de M4 y HU-03 de M3), porque las historias no constaban en ninguna entrega previa. |
| 5 | Se delegó la elección del tablero ágil en una recomendación. | Decidir con criterio técnico entre GitHub Projects y Jira. | La recomendación de GitHub Projects por su integración con issues y Pull Requests. | El grupo delegó la elección en una recomendación de la IA, que propuso GitHub Projects por integrarse con los issues y los Pull Requests del mismo repositorio, sin una herramienta externa como Jira. El grupo adoptó esa recomendación. |
| 6 | Se pidió el plan de ejecución de Git y GitHub en formato Markdown, para ejecutarlo con OpenCode. | Automatizar tareas repetitivas con comandos revisables. | Un runbook con comandos paso a paso. | La ejecución de los comandos se hizo con OpenCode (modelo GLM-5.3-Flash Free). El grupo supervisó el proceso: cada comando de publicación (push, issues, tablero y Pull Requests) se mostró y se aprobó antes de ejecutarse. Las revisiones de pares quedan registradas en cada Pull Request y las realiza Ana Laura desde su propia cuenta. |

### Limitaciones detectadas en los resultados de la IA

- La consigna de la Entrega 4 habla de tres historias de usuario "previamente definidas", pero no constaban en ninguna entrega; la IA lo detectó y propuso las historias, que el grupo debió adoptar como propias.
- El primer borrador del diagrama BPMN tenía texto desbordado y flechas de mensaje mal dibujadas, y se corrigió antes de usarlo.
- Un borrador de esta misma declaración, redactado por el agente, daba por hechas verificaciones del grupo que no estaban registradas; el grupo lo detectó y lo reescribió con lo que realmente ocurrió.
- Los comandos de `gh` no se habían probado contra GitHub antes de ejecutarlos y se verificaron durante la ejecución.

### Responsabilidad intelectual

El grupo comprende y puede defender cada decisión, diagrama y herramienta de este trabajo, y asume la responsabilidad por su veracidad y coherencia conceptual.
