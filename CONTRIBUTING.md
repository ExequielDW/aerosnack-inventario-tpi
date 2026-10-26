# Guía de colaboración

Este repositorio aloja la documentación técnica del TPI de **Organización Empresarial** (TUP AD – UTN).
Para mantener un historial trazable y auditable, el equipo acuerda las siguientes reglas.

## 1. Ramas

- `main`: rama estable. **No se hacen commits directos** después de la configuración inicial; todo cambio entra por Pull Request.
- Ramas secundarias, una por tarea del tablero, con el formato `tipo/descripcion-corta` en minúsculas y con guiones:

| Prefijo | Uso | Ejemplo |
|---|---|---|
| `docs/` | Documentación | `docs/bpmn-reposicion-insumos` |
| `feat/` | Funcionalidad del módulo (etapa de codificación) | `feat/alertas-stock-minimo` |
| `fix/` | Corrección de errores | `fix/typo-entrega-3` |
| `chore/` | Tareas de mantenimiento | `chore/plantillas-github` |

## 2. Mensajes de commit

Se usa [Conventional Commits](https://www.conventionalcommits.org/es/v1.0.0/) en español, en modo imperativo:

```
tipo(ámbito): descripción breve en minúscula, sin punto final

Cuerpo opcional: qué cambia y por qué.
```

Tipos usados: `docs`, `feat`, `fix`, `chore`, `refactor`, `test`.

Ejemplos:

- `docs(bpmn): agrega diagrama BPMN de reposición de insumos`
- `docs(indicadores): define estándares de desempeño a partir de las metas M1 a M6`
- `fix(entregas): corrige typo en la conclusión de la Entrega 3`

## 3. Pull Requests

1. Cada PR parte de una rama secundaria y se vincula a un issue del tablero (`Closes #n`).
2. Debe tener **al menos una revisión de otro integrante** antes de fusionarse. Nadie aprueba su propio PR.
3. Los comentarios de la revisión se resuelven con commits en la misma rama o con una respuesta fundamentada.
4. Se fusiona con *merge commit* (no *squash*) para conservar el historial, y se elimina la rama.

## 4. Tablero

Las tareas e historias de usuario se gestionan en el tablero de GitHub Projects con tres estados:
**Por Hacer**, **En Progreso** y **Listo**. El estado debe reflejar el avance real.
