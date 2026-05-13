# Paso 13. Deteccion de regresiones

## Objetivo de aprendizaje

Este paso introduce la detección de regresiones en DAST y debe dejar un cambio comprensible en `docs/dast-analysis.md`.

## Que vas a cambiar y por que

Actualiza `docs/dast-analysis.md` para que el análisis también sirva para detectar regresiones. La idea no es solo registrar un hallazgo actual, sino dejar suficiente contexto para reconocer cuándo vuelve a aparecer un problema ya conocido o cuándo empeora una ruta que antes estaba controlada.

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
- Usa `## Hallazgo` y `## Ruta afectada` con suficiente precisión para poder comparar futuras ejecuciones.
- Usa `## Riesgo` para dejar constancia del impacto esperado y detectar si una regresión cambia su severidad.
- Haz que `## Decision` indique si el hallazgo es nuevo, recurrente o pendiente de verificación.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- El documento ya puede usarse para comparar resultados futuros y detectar reapariciones.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-13.py` comprueba este paso contra el archivo configurado.
- El workflow busca `## Hallazgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Ruta afectada` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Riesgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Decision` dentro de `docs/dast-analysis.md`.

## Criterio de finalizacion

El paso 13 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 14.
