# Paso 6. Configuracion de scope

## Objetivo de aprendizaje

Este paso introduce la configuración de scope en DAST y debe dejar un cambio comprensible en `zap/config.yaml`.

## Que vas a cambiar y por que

Actualiza `zap/config.yaml` para que el alcance del escaneo quede explícito y revisable. Aquí el punto no es solo tener un contexto nombrado, sino decidir qué entra realmente en el análisis. Un `include:` bien planteado reduce ruido, evita rutas fuera de propósito y hace que los hallazgos sean defendibles.

## Archivo y seccion que debes modificar

- Archivo objetivo: `zap/config.yaml`.
- Aplícalo en la parte del archivo que corresponde al título del paso.
- Si el archivo aún no existe, créalo con este contenido inicial y luego evoluciona desde ahí en los siguientes pasos.

## Cambio base recomendado

Este bloque no es para pegar a ciegas: úsalo como punto de partida y ajústalo al contexto del repositorio.

```yaml
context:
  name: app-context
include:
  - http://localhost:3000/.*
authentication:
  type: form
scan:
  fail_on_risk: high
```

## Como adaptarlo correctamente

- Mantén el cambio pequeño y centrado en una sola idea por paso.
- Haz que `include:` represente de verdad el alcance del ejercicio y no una colección genérica de endpoints.
- Mantén `authentication:` porque el scope útil en DAST profesional suele depender de qué sesión se aplica al rastreo.
- Conserva `fail_on_risk: high` para que el alcance definido siga conectado con una decisión de bloqueo clara.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- Se entiende qué parte de la aplicación entra en el análisis y por qué ese límite importa.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-06.py` comprueba este paso contra el archivo configurado.
- El workflow busca `context:` dentro de `zap/config.yaml`.
- El workflow busca `name: app-context` dentro de `zap/config.yaml`.
- El workflow busca `include:` dentro de `zap/config.yaml`.
- El workflow busca `authentication:` dentro de `zap/config.yaml`.
- El workflow busca `scan:` dentro de `zap/config.yaml`.
- El workflow busca `fail_on_risk: high` dentro de `zap/config.yaml`.

## Criterio de finalizacion

El paso 6 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 7.
