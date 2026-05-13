# Paso 11. Priorizacion por impacto de negocio

## Objetivo de aprendizaje

Este paso introduce la priorización por impacto de negocio en DAST y debe dejar un cambio comprensible en `docs/dast-analysis.md`.

## Que vas a cambiar y por que

Actualiza `docs/dast-analysis.md` para que el análisis no se limite a severidad técnica. En este paso debes usar `## Riesgo` y `## Decision` para conectar el hallazgo con el daño potencial sobre negocio: exposición de cuentas, impacto en pagos, fuga de datos o interrupción de operaciones.

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
- Usa `## Hallazgo` para describir el problema técnico, pero reserva `## Riesgo` para explicar el efecto sobre el negocio.
- Haz que `## Decision` refleje priorización por impacto real, no solo por severidad abstracta.
- Usa `## Ruta afectada` para vincular el riesgo con el flujo funcional comprometido.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- El documento ayuda a justificar por qué un hallazgo debe ir antes que otro en términos de negocio.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-11.py` comprueba este paso contra el archivo configurado.
- El workflow busca `## Hallazgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Ruta afectada` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Riesgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Decision` dentro de `docs/dast-analysis.md`.

## Criterio de finalizacion

El paso 11 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 12.
