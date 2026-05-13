# Paso 14. Integracion en github actions

## Objetivo de aprendizaje

Este paso introduce la integración de DAST en GitHub Actions y debe dejar un cambio comprensible en `.github/workflows/dast.yml`.

## Que vas a cambiar y por que

Actualiza `.github/workflows/dast.yml` para que el escaneo DAST quede integrado en la automatización del repositorio. Aquí el foco está en que el workflow tenga identidad clara, se ejecute en los eventos adecuados y contenga un job reconocible para lanzar el análisis.

## Archivo y seccion que debes modificar

- Archivo objetivo: `.github/workflows/dast.yml`.
- Aplícalo en la parte del archivo que corresponde al título del paso.
- Si el archivo aún no existe, créalo con este contenido inicial y luego evoluciona desde ahí en los siguientes pasos.

## Cambio base recomendado

Este bloque no es para pegar a ciegas: úsalo como punto de partida y ajústalo al contexto del repositorio.

```yaml
name: DAST
on:
  pull_request:
  push:
jobs:
  zap-scan:
```

## Como adaptarlo correctamente

- Mantén el cambio pequeño y centrado en una sola idea por paso.
- Usa `name: DAST` para que el workflow sea identificable en la plataforma.
- Mantén `pull_request:` y `push:` como disparadores visibles del control automatizado.
- Usa `zap-scan:` como job claro y específico para el análisis dinámico.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- Se entiende cómo el escaneo DAST entra en la ejecución automática del repositorio.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-14.py` comprueba este paso contra el archivo configurado.
- El workflow busca `name: DAST` dentro de `.github/workflows/dast.yml`.
- El workflow busca `pull_request:` dentro de `.github/workflows/dast.yml`.
- El workflow busca `push:` dentro de `.github/workflows/dast.yml`.
- El workflow busca `zap-scan:` dentro de `.github/workflows/dast.yml`.

## Criterio de finalizacion

El paso 14 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 15.
