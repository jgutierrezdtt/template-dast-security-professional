# Paso 10. Priorizacion por criticidad

## Objetivo de aprendizaje

Explicar resultados, impacto y tratamiento de los hallazgos del escaneo.

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/dast-analysis.md`.
- Seccion donde aplicar el cambio: análisis de hallazgos DAST.
- Resultado esperado: el repositorio incorpora el control de este paso de forma legible y revisable.

## Cambio que debes introducir

Copia este bloque como base y adáptalo al contexto real del repositorio:

```markdown
## Hallazgo
## Ruta afectada
## Riesgo
## Decision
```

## Como adaptarlo correctamente

- Diferencia riesgo explotable de ruido instrumental.
- Describe qué evidencia usarías para reproducir o descartar el hallazgo.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-10.py` comprueba el archivo y los marcadores esperados de este paso.
- Debe encontrar el marcador `## Hallazgo` en `docs/dast-analysis.md`.
- Debe encontrar el marcador `## Ruta afectada` en `docs/dast-analysis.md`.
- Debe encontrar el marcador `## Riesgo` en `docs/dast-analysis.md`.
- Debe encontrar el marcador `## Decision` en `docs/dast-analysis.md`.

## Criterio de finalizacion

El paso 10 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 11.
