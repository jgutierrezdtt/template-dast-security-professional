# Paso 15. Gate no bloqueante

## Objetivo de aprendizaje

Este paso introduce un gate no bloqueante para DAST y debe dejar un cambio comprensible en `.github/workflows/dast.yml`.

## Que vas a cambiar y por que

Actualiza `.github/workflows/dast.yml` para explicar un gate no bloqueante. La idea es que el workflow ejecute el escaneo y muestre resultados útiles sin impedir todavía el avance del pipeline. Este enfoque sirve cuando el programa aún está afinando cobertura, ruido o criterios de aceptación.

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
- Mantén `name: DAST` y `zap-scan:` como elementos visibles del control automatizado.
- Usa `pull_request:` y `push:` para dejar claro dónde se observa el resultado del gate informativo.
- Explica el carácter no bloqueante en la narrativa del paso, sin necesidad de cambiar los marcadores que valida el repositorio.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- Se entiende que el workflow aporta visibilidad, aunque todavía no detenga la entrega.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-15.py` comprueba este paso contra el archivo configurado.
- El workflow busca `name: DAST` dentro de `.github/workflows/dast.yml`.
- El workflow busca `pull_request:` dentro de `.github/workflows/dast.yml`.
- El workflow busca `push:` dentro de `.github/workflows/dast.yml`.
- El workflow busca `zap-scan:` dentro de `.github/workflows/dast.yml`.

## Criterio de finalizacion

El paso 15 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 16.
