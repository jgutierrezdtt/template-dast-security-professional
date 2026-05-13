# Paso 12. Baseline de hallazgos

## Objetivo de aprendizaje

Este paso introduce el baseline de hallazgos en DAST y debe dejar un cambio comprensible en `docs/dast-analysis.md`.

## Que vas a cambiar y por que

Actualiza `docs/dast-analysis.md` para que el análisis sirva también como línea base. Un baseline no es solo una lista de findings actuales: es la referencia desde la que después podrás medir si aparecen nuevos problemas, si se mantienen los mismos o si alguna decisión previa dejó de ser válida.

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
- Usa `## Hallazgo` y `## Ruta afectada` para describir de forma estable qué se detectó y dónde.
- Usa `## Riesgo` para registrar la lectura actual del problema y que futuras comparaciones tengan contexto.
- Haz que `## Decision` deje claro si ese hallazgo forma parte de la línea base aceptada, pendiente o priorizada.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- El documento ya puede servir como punto de comparación para regresiones y cambios posteriores.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-12.py` comprueba este paso contra el archivo configurado.
- El workflow busca `## Hallazgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Ruta afectada` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Riesgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Decision` dentro de `docs/dast-analysis.md`.

## Criterio de finalizacion

El paso 12 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 13.
