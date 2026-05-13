# Paso 3. Interpretacion de resultados

## Objetivo de aprendizaje

Este paso introduce la interpretación de resultados DAST y debe dejar un cambio comprensible en `docs/dast-analysis.md`.

## Que vas a cambiar y por que

En este paso vas a estructurar `docs/dast-analysis.md` para que un hallazgo no quede reducido a una alerta sin contexto. El valor de la interpretación está en conectar el finding con la ruta afectada, el riesgo real y la decisión posterior: corregir, revisar más a fondo o aceptar temporalmente con criterio.

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
- Usa `## Ruta afectada` para localizar el hallazgo en el flujo de la aplicación y no solo en el reporte del escáner.
- Haz que `## Decision` conecte el análisis con la acción siguiente y no con una frase genérica.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- El documento ya sirve para transformar resultados del escáner en decisiones de trabajo.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-03.py` comprueba este paso contra el archivo configurado.
- El workflow busca `## Hallazgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Ruta afectada` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Riesgo` dentro de `docs/dast-analysis.md`.
- El workflow busca `## Decision` dentro de `docs/dast-analysis.md`.

## Criterio de finalizacion

El paso 3 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 4.
