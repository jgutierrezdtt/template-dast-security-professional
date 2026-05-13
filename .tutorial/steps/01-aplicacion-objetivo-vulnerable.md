# Paso 1. Aplicacion objetivo vulnerable

## Objetivo de aprendizaje

Este paso introduce la aplicación objetivo vulnerable y debe dejar un cambio comprensible en `docs/dast-analysis.md`.

## Que vas a cambiar y por que

En este paso vas a estructurar `docs/dast-analysis.md` para que el análisis arranque con una aplicación objetivo clara. En DAST profesional, antes de hablar de herramientas o findings complejos, necesitas saber qué hallazgo se observa, en qué ruta aparece, qué riesgo representa y qué decisión tomas sobre él.

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/dast-analysis.md`.
- Aplícalo en la parte del archivo que corresponde al título del paso.
- Si el archivo aún no existe, créalo con este contenido inicial y luego evoluciona desde ahí en los siguientes pasos.

## Cambio base recomendado

Este bloque no es para pegar a ciegas: úsalo como punto de partida y ajústalo al contexto del repositorio.

```markdown
## Hallazgo
## Ruta afectada
## Riesgo
## Decision
```

## Como adaptarlo correctamente

- Mantén el cambio pequeño y centrado en una sola idea por paso.
- Usa `## Ruta afectada` para dejar claro dónde se manifiesta el problema dentro de la aplicación.
- Haz que `## Decision` cierre el análisis con una acción o criterio y no con una descripción pasiva.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- El documento ya parece una base real para registrar y operar hallazgos DAST.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-01.py` comprueba este paso contra el archivo configurado.
- El workflow busca `## Hallazgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Ruta afectada` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Riesgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Decision` dentro de `docs/dast-analysis.md`.

## Criterio de finalizacion

El paso 1 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 2.
