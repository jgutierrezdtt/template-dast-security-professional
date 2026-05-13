# Paso 17. Politica organizativa

## Objetivo de aprendizaje

Este paso introduce la política organizativa de DAST y debe dejar un cambio comprensible en `docs/dast-analysis.md`.

## Que vas a cambiar y por que

Actualiza `docs/dast-analysis.md` para que el análisis refleje también criterio organizativo. En este paso la idea es que `## Decision` no dependa solo del analista puntual, sino de una política repetible sobre qué se corrige, qué bloquea y qué puede aceptarse temporalmente.

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
- Usa `## Riesgo` para conectar el hallazgo con el marco de decisión de la organización.
- Haz que `## Decision` suene a política aplicable por el equipo y no a opinión aislada.
- Usa `## Ruta afectada` para que la política se entienda sobre un caso concreto y no quede abstracta.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- El documento ya ayuda a uniformar decisiones DAST entre equipos y revisiones.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-17.py` comprueba este paso contra el archivo configurado.
- El workflow busca `## Hallazgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Ruta afectada` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Riesgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Decision` dentro de `docs/dast-analysis.md`.

## Criterio de finalizacion

El paso 17 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 18.
