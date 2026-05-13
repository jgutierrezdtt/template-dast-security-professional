# Paso 16. Gate bloqueante por severidad

## Objetivo de aprendizaje

Este paso introduce un gate bloqueante por severidad en DAST y debe dejar un cambio comprensible en `.github/workflows/dast.yml`.

## Que vas a cambiar y por que

Actualiza `.github/workflows/dast.yml` para explicar un gate bloqueante basado en severidad. A diferencia del paso anterior, aquí el workflow deja de ser solo informativo y pasa a representar una decisión automática: si el escaneo encuentra hallazgos por encima del umbral aceptado, la entrega debe detenerse.

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
- Mantén `name: DAST` y `zap-scan:` como elementos visibles del control que puede bloquear la entrega.
- Usa `pull_request:` y `push:` para dejar claro dónde aplica el gate.
- Explica en el propio paso que el bloqueo depende de severidad y no de cualquier alerta menor.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- Se entiende que el workflow ya actúa como control de liberación y no solo como reporte.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-16.py` comprueba este paso contra el archivo configurado.
- El workflow busca `name: DAST` dentro de `.github/workflows/dast.yml`.
- El workflow busca `pull_request:` dentro de `.github/workflows/dast.yml`.
- El workflow busca `push:` dentro de `.github/workflows/dast.yml`.
- El workflow busca `zap-scan:` dentro de `.github/workflows/dast.yml`.

## Criterio de finalizacion

El paso 16 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 17.
