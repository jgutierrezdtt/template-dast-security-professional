# Paso 5. Configuracion de contexto

## Objetivo de aprendizaje

Este paso introduce la configuración de contexto en DAST y debe dejar un cambio comprensible en `zap/config.yaml`.

## Que vas a cambiar y por que

Actualiza `zap/config.yaml` para que el contexto del análisis quede explícito y revisable. En DAST, el contexto define qué aplicación estás observando, qué rutas pertenecen a ese objetivo y bajo qué sesión o comportamiento de escaneo se van a interpretar los resultados.

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
- Usa `app-context` como nombre identificable del sistema o flujo que vas a escanear.
- Haz que `include:` delimite el contexto funcional y no una lista arbitraria de URLs.
- Conserva `authentication:` y `scan:` porque forman parte del contexto operativo aunque aquí el foco sea contextualizar el objetivo.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- Queda claro qué aplicación pertenece al contexto y con qué base se ejecutará el análisis.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-05.py` comprueba este paso contra el archivo configurado.
- El workflow busca `context:` dentro de `zap/config.yaml`.
- El workflow busca `name: app-context` dentro de `zap/config.yaml`.
- El workflow busca `include:` dentro de `zap/config.yaml`.
- El workflow busca `authentication:` dentro de `zap/config.yaml`.
- El workflow busca `scan:` dentro de `zap/config.yaml`.
- El workflow busca `fail_on_risk: high` dentro de `zap/config.yaml`.

## Criterio de finalizacion

El paso 5 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 6.
