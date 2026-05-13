# Paso 10. Priorizacion por criticidad

## Objetivo de aprendizaje

Este paso introduce la priorización por criticidad en DAST y debe dejar un cambio comprensible en `docs/dast-analysis.md`.

## Que vas a cambiar y por que

Actualiza `docs/dast-analysis.md` para que la lectura del hallazgo no sea plana. En este paso la clave está en usar `## Riesgo` y `## Decision` para reflejar criticidad: no todos los findings merecen la misma urgencia, y el análisis debe ayudar a distinguir qué requiere atención inmediata.

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
- Usa `## Riesgo` para expresar la severidad o criticidad del hallazgo con un lenguaje accionable.
- Haz que `## Decision` refleje una priorización real: corregir primero, revisar después o aceptar temporalmente.
- Usa `## Ruta afectada` para conectar la criticidad con la parte concreta del sistema expuesta.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- El documento ayuda a decidir qué hallazgo va primero y por qué.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-10.py` comprueba este paso contra el archivo configurado.
- El workflow busca `## Hallazgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Ruta afectada` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Riesgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Decision` dentro de `docs/dast-analysis.md`.

## Criterio de finalizacion

El paso 10 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 11.
