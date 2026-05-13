# Paso 25. Medalla final dast professional

## Objetivo de aprendizaje

Este paso cierra el recorrido de DAST Professional y debe dejar un cambio comprensible en `docs/dast-analysis.md`.

## Que vas a cambiar y por que

Actualiza `docs/dast-analysis.md` para cerrar el tutorial con una evidencia final coherente. La idea no es añadir un marcador nuevo, sino dejar claro que el análisis ya reúne identificación del hallazgo, ruta afectada, evaluación del riesgo y decisión operativa como una práctica madura y repetible.

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
- Usa `## Hallazgo`, `## Ruta afectada`, `## Riesgo` y `## Decision` como el resumen completo del trabajo realizado en el tutorial.
- Haz que `## Decision` refleje madurez operativa: corregido, priorizado, aceptado temporalmente o listo para auditoría.
- Mantén un lenguaje claro para que el documento funcione como evidencia final del laboratorio.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- El documento ya resume una práctica DAST profesional completa y revisable.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-25.py` comprueba este paso contra el archivo configurado.
- El workflow busca `## Hallazgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Ruta afectada` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Riesgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Decision` dentro de `docs/dast-analysis.md`.

## Criterio de finalizacion

El paso 25 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Este es el ultimo paso del tutorial.
