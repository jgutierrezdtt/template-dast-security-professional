# Paso 21. Reporting tecnico

## Objetivo de aprendizaje

Este paso introduce el reporting técnico en DAST y debe dejar un cambio comprensible en `docs/dast-analysis.md`.

## Que vas a cambiar y por que

Actualiza `docs/dast-analysis.md` para que el análisis pueda consumirse como reporte técnico. Aquí `## Hallazgo`, `## Ruta afectada`, `## Riesgo` y `## Decision` deben ayudar a un equipo de ingeniería a entender dónde está el problema, qué gravedad tiene y qué hacer después.

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
- Usa `## Hallazgo` para describir el problema con precisión suficiente para remediación.
- Usa `## Ruta afectada` para ubicar la superficie o flujo exacto que necesita revisión.
- Haz que `## Decision` apunte a la siguiente acción técnica: corregir, verificar, reproducir o revisar excepción.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- El documento ya puede servir como base de trabajo para remediación técnica.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-21.py` comprueba este paso contra el archivo configurado.
- El workflow busca `## Hallazgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Ruta afectada` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Riesgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Decision` dentro de `docs/dast-analysis.md`.

## Criterio de finalizacion

El paso 21 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 22.
